---
Colaboradores:
  - "[[Danae T]]"
  - "[[Flavio A]]"
  - "[[Bastián R]]"
tags:
  - ActiveProject
  - SOM
  - Global
Related:
  - "[[9.0.- Archive]]"
  - "[[8.0.- Knowledge]]"
---
---
Título: `= this.file.name`
Colaboradores: `= this.colaboradores`
Tags: `= this.file.tags`
Última edición: `= dateformat(this.file.mtime, "dd-MM-yyyy HH:mm")`
Documentos relacionados: `= this.related`
___

| Actualizaciones recientes                                                                                                                                     | Proyectos Activos                                                                      | Estadísticas                      |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | --------------------------------- |
| `$=dv.list(dv.pages('').sort(f => f.file.mtime.ts, "desc").limit(5).map(f => f.file.link + " - : " + (f.Colaboradores ? f.Colaboradores : "-")))`<br><br><br> | `$=dv.list(dv.pages('#ActiveProject').sort(f=>f.file.name,"desc").limit(5).file.link)` | File Count: `$=dv.pages().length` |






---
```dataviewjs
// ========================================
// TAREAS COMPLETADAS POR MES
// ========================================

// ----------------------------------------
// 1. NOMBRES DE LOS MESES
// ----------------------------------------

const meses = [
    "Ene", "Feb", "Mar", "Abr", "May", "Jun",
    "Jul", "Ago", "Sep", "Oct", "Nov", "Dic"
];


// ----------------------------------------
// 2. CONTADOR DE TAREAS POR MES
// ----------------------------------------

const tareasPorMes = Array(12).fill(0);


// ----------------------------------------
// 3. RECORRER TODA LA BÓVEDA
// ----------------------------------------

let tareasCompletadas = 0;
let tareasContadas = 0;
let tareasSinFecha = 0;

for (const pagina of dv.pages()) {

    for (const tarea of pagina.file.tasks) {

        // Ignorar tareas que todavía no están completadas
        if (!tarea.completed) {
            continue;
        }

        tareasCompletadas++;

        // ----------------------------------------
        // BUSCAR LA FECHA DE COMPLETADO
        // ----------------------------------------
        // Formato: YYYY-MM-DD

        const coincidencia = tarea.text.match(
            /(\d{4})-(\d{2})-(\d{2})$/
        );

        if (!coincidencia) {
            tareasSinFecha++;
            continue;
        }

        const año = Number(coincidencia[1]);
        const mes = Number(coincidencia[2]) - 1;
        const dia = Number(coincidencia[3]);

        const fecha = new Date(año, mes, dia);

        // Verificar que la fecha sea válida
        if (
            fecha.getFullYear() !== año ||
            fecha.getMonth() !== mes ||
            fecha.getDate() !== dia
        ) {
            tareasSinFecha++;
            continue;
        }

        // Sumar una tarea al mes correspondiente
        tareasPorMes[mes]++;
        tareasContadas++;
    }
}


// ========================================
// 4. CONFIGURACIÓN DEL GRÁFICO
// ========================================

const configuracionGrafico = {

    // ------------------------------------
    // TIPO DE GRÁFICO
    // ------------------------------------
    // "bar" = barras
    // "line" = líneas
    // ------------------------------------

    type: "bar",

    data: {

        // --------------------------------
        // NOMBRES DEL EJE X
        // --------------------------------

        labels: meses,

        datasets: [{

            label: "Tareas completadas",

            // --------------------------------
            // DATOS
            // --------------------------------
            // Aquí están las cantidades de
            // tareas de cada mes.
            // --------------------------------

            data: tareasPorMes,


            // ==================================
            // APARIENCIA DE LAS BARRAS
            // ==================================

            backgroundColor: "rgba(75, 192, 192, 0.7)",


            // COLOR DEL BORDE DE LAS BARRAS

            borderColor: "rgba(75, 192, 192, 1)",


            // GROSOR DEL BORDE

            borderWidth: 1,


            // --------------------------------
            // ANCHO DE LAS BARRAS
            // 0.5 -> 1.0
            barPercentage: 0.7,

            categoryPercentage: 0.8,


            // --------------------------------
            // BORDES REDONDEADOS
            // 0 -> 10


            borderRadius: 5

        }]
    },


    // ========================================
    // 5. CONFIGURACIÓN GENERAL
    // ========================================

    options: {

        // Permite que el gráfico se adapte
        // al ancho disponible.

        responsive: true,


        // ====================================
        // EJES
        // ====================================

        scales: {

            // --------------------------------
            // EJE Y
            // --------------------------------

            y: {

                // El eje comienza en 0

                beginAtZero: true,


                // --------------------------------
                // NÚMEROS DEL EJE Y
                // --------------------------------
                //
                // stepSize: 1 significa que
                // veremos:
                //
                // 0
                // 1
                // 2
                // 3
                // 4
                //
                // en lugar de decimales.
                // --------------------------------

                ticks: {

                    stepSize: 1,
                    precision: 0
                },


                // TÍTULO DEL EJE Y

                title: {

                    display: true,
                    text: "Número de tareas"
                }
            },


            // --------------------------------
            // EJE X
            // --------------------------------

            x: {

                title: {

                    display: true,
                    text: "Meses del año"
                }
            }
        }
    }
};


// ========================================
// 6. MOSTRAR EL GRÁFICO
// ========================================

if (window.renderChart) {

    window.renderChart(
        configuracionGrafico,
        this.container
    );

} else {

    dv.paragraph(
        "⚠️ Activa el plugin Obsidian Charts."
    );
}


// ========================================
// 7. INFORMACIÓN DE CONTROL
// ========================================

dv.paragraph(
    `📊 Tareas completadas encontradas en toda la bóveda: ${tareasCompletadas}`
);

dv.paragraph(
    `✅ Tareas contabilizadas en el gráfico: ${tareasContadas}`
);

if (tareasSinFecha > 0) {

    dv.paragraph(
        `⚠️ Tareas completadas sin fecha detectada: ${tareasSinFecha}`
    );
}
```










# Relevant Links:

[[00.- Templates & Resources HOME]]


# To-Do List:
```tasks
not done
```

# To-Done List:

```tasks
done
```
---

> [!Templates & Resources]
> Aquí podrás encontrar todos los templates con los que trabajamos.
> **[[00.- Templates & Resources HOME]]**
---
# Index
[[1.0.- Library]]
[[2.0.- Global Systems]]
[[3.0.- Global props & assets]]
[[4.0.- Projects]]
[[5.0.- Outputs]]
[[8.0.- Knowledge]]
[[9.0.- Archive]]





---
```dataviewjs
// ========================================
// TAREAS COMPLETADAS POR MES
// ========================================

// ----------------------------------------
// 1. NOMBRES DE LOS MESES
// ----------------------------------------

const meses = [
    "Ene", "Feb", "Mar", "Abr", "May", "Jun",
    "Jul", "Ago", "Sep", "Oct", "Nov", "Dic"
];


// ----------------------------------------
// 2. CONTADOR DE TAREAS POR MES
// ----------------------------------------

const tareasPorMes = Array(12).fill(0);


// ----------------------------------------
// 3. RECORRER TODA LA BÓVEDA
// ----------------------------------------

let tareasCompletadas = 0;
let tareasContadas = 0;
let tareasSinFecha = 0;

for (const pagina of dv.pages()) {

    for (const tarea of pagina.file.tasks) {

        // Ignorar tareas que todavía no están completadas
        if (!tarea.completed) {
            continue;
        }

        tareasCompletadas++;

        // ----------------------------------------
        // BUSCAR LA FECHA DE COMPLETADO
        // ----------------------------------------
        // Formato: YYYY-MM-DD

        const coincidencia = tarea.text.match(
            /(\d{4})-(\d{2})-(\d{2})$/
        );

        if (!coincidencia) {
            tareasSinFecha++;
            continue;
        }

        const año = Number(coincidencia[1]);
        const mes = Number(coincidencia[2]) - 1;
        const dia = Number(coincidencia[3]);

        const fecha = new Date(año, mes, dia);

        // Verificar que la fecha sea válida
        if (
            fecha.getFullYear() !== año ||
            fecha.getMonth() !== mes ||
            fecha.getDate() !== dia
        ) {
            tareasSinFecha++;
            continue;
        }

        // Sumar una tarea al mes correspondiente
        tareasPorMes[mes]++;
        tareasContadas++;
    }
}


// ========================================
// 4. CONFIGURACIÓN DEL GRÁFICO
// ========================================

const configuracionGrafico = {

    // ------------------------------------
    // TIPO DE GRÁFICO
    // ------------------------------------
    // "bar" = barras
    // "line" = líneas
    // ------------------------------------

    type: "bar",

    data: {

        // --------------------------------
        // NOMBRES DEL EJE X
        // --------------------------------

        labels: meses,

        datasets: [{

            label: "Tareas completadas",

            // --------------------------------
            // DATOS
            // --------------------------------
            // Aquí están las cantidades de
            // tareas de cada mes.
            // --------------------------------

            data: tareasPorMes,


            // ==================================
            // APARIENCIA DE LAS BARRAS
            // ==================================

            backgroundColor: "rgba(75, 192, 192, 0.7)",


            // COLOR DEL BORDE DE LAS BARRAS

            borderColor: "rgba(75, 192, 192, 1)",


            // GROSOR DEL BORDE

            borderWidth: 1,


            // --------------------------------
            // ANCHO DE LAS BARRAS
            // 0.5 -> 1.0
            barPercentage: 0.7,

            categoryPercentage: 0.8,


            // --------------------------------
            // BORDES REDONDEADOS
            // 0 -> 10


            borderRadius: 5

        }]
    },


    // ========================================
    // 5. CONFIGURACIÓN GENERAL
    // ========================================

    options: {

        // Permite que el gráfico se adapte
        // al ancho disponible.

        responsive: true,


        // ====================================
        // EJES
        // ====================================

        scales: {

            // --------------------------------
            // EJE Y
            // --------------------------------

            y: {

                // El eje comienza en 0

                beginAtZero: true,


                // --------------------------------
                // NÚMEROS DEL EJE Y
                // --------------------------------
                //
                // stepSize: 1 significa que
                // veremos:
                //
                // 0
                // 1
                // 2
                // 3
                // 4
                //
                // en lugar de decimales.
                // --------------------------------

                ticks: {

                    stepSize: 1,
                    precision: 0
                },


                // TÍTULO DEL EJE Y

                title: {

                    display: true,
                    text: "Número de tareas"
                }
            },


            // --------------------------------
            // EJE X
            // --------------------------------

            x: {

                title: {

                    display: true,
                    text: "Meses del año"
                }
            }
        }
    }
};


// ========================================
// 6. MOSTRAR EL GRÁFICO
// ========================================

if (window.renderChart) {

    window.renderChart(
        configuracionGrafico,
        this.container
    );

} else {

    dv.paragraph(
        "⚠️ Activa el plugin Obsidian Charts."
    );
}


// ========================================
// 7. INFORMACIÓN DE CONTROL
// ========================================

dv.paragraph(
    `📊 Tareas completadas encontradas en toda la bóveda: ${tareasCompletadas}`
);

dv.paragraph(
    `✅ Tareas contabilizadas en el gráfico: ${tareasContadas}`
);

if (tareasSinFecha > 0) {

    dv.paragraph(
        `⚠️ Tareas completadas sin fecha detectada: ${tareasSinFecha}`
    );
}
```














