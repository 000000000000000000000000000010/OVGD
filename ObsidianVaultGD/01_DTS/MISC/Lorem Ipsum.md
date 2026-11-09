# Intro
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla aliquet ante ligula, nec

## Subintro

^074011

Nam et ullamcorper felis. Quisque ullamcorper, lorem nec varius commodo, arcu libero  ^09aed6

# 2°Párrafo
Suspendisse mollis rutrum aliquam. Nullam ante orci, posuere eu tincidunt eu, laoreet

# 3°Párrafo
Vestibulum tincidunt nisi eu nisl finibus molestie. Ut nisl orci, convallis vitae est vitae, mollis ^54d03a

# 4°Párrafo
Ut egestas dolor id eleifend varius. In in nibh eros. Quisque bibendum, augue quis suscipit

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















---


- [x] caca ✅ 2026-08-27
- [x] puchi ✅ 2026-08-27
- [x] meao ✅ 2026-08-27


- [x] aaahhhhh ✅ 2026-08-27
- [x] eeeeeeeeeeehhh ✅ 2026-08-27
- [x] aaaaaauuhh ✅ 2026-08-27


- [ ] eeyyy
- [ ] oooo
- [x] hh ✅ 2026-08-27
- [x] Lets ✅ 2026-08-27
- [x] Go ✅ 2026-08-27







asdasdsad
