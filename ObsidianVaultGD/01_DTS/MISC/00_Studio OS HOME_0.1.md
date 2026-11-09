---
Colaboradores:
  - "[[Danae T]]"
  - "[[Flavio A]]"
  - "[[Bastián R]]"
tags:
  - ActiveProject
  - SOM
  - Global
---
---
Título: `= this.file.name`
Colaboradores: `= this.colaboradores`
Tags: `= this.file.tags`
Última edición: `= dateformat(this.file.mtime, "dd-MM-yyyy HH:mm")`
___

| Actualizaciones recientes | Proyectos Activos | Estadísticas|
| --- | --- | --- |
|  `$=dv.list(dv.pages('').sort(f=>f.file.mtime.ts,"desc").limit(5).file.link)`   | `$=dv.list(dv.pages('#ActiveProject').sort(f=>f.file.name,"desc").limit(5).file.link)`    |   File Count: `$=dv.pages().length`

``` md-calendar
{
  "version": 1,
  "calId": "cujtge3q",
  "settings": {
    "view": "month",
    "showCompleted": true
  },
  "events": [
    {
      "id": "ernzqjlm",
      "title": "Test_01",
      "date": "2026-08-13",
      "created": "2026-08-11",
      "order": 0
    },
    {
      "id": "evpmcdj7",
      "title": "Test_02",
      "date": "2026-09-18",
      "created": "2026-08-11",
      "order": 1
    }
  ]
}
```

---

> [!Templates]
> Aquí podrás encontrar todos los templates con los que trabajamos.
> **[[00.- Templates & Resources HOME]]**
---


```insta-toc
---
title:
  name:
  level:
  center:
exclude:
style:
  listType:
omit:
levels:
  min:
  max:
---

# Table of Contents

- 1.0.- Library
    - ![[1.1.- Game Design1.1.- Game Design]]
    - ![[1.2.- Learning Design1.2.- Learning Design]]
    - ![[1.3.- Global UX UI1.3.- Global UX/UI]]
    - ![[1.4.- Global XR1.4.- Global XR]]
    - ![[1.5.- Technical1.5.- Technical]]
    - ![[1.6.- Production1.6.- Production]]
    - ![[1.7.- Global Assets1.7.- Global Assets]]
    - ![[1.8.- References1.8.- References]]
- 2.0.- Global systems
    - 2.1.- [[Progression system]]
- 3.0.- Global props & assets
- 4.0.- Projects
    - 4.1.- [[STT]]
        - ![[Vision]]
        - ![[Production]]
        - ![[Features]]
        - ![[Levels]]
        - ![[Scenarios]]
        - ![[Learning]]
        - ![[Assets]]
        - ![[Credits]]
        - ![[Releases]]
        - ![[QA]]
    - 4.2.- [[PilotLab]]
    - 4.3.- MRStudio
    - 4.4.- ETC
- 5.0.- Outputs
- 8.0.- Knowledge
- 9.0.- Archive
- Notas de la entrega de este documento:
```



---



```insta-toc
---
title:
  name:
  level:
  center:
exclude:
style:
  listType:
omit:
levels:
  min:
  max:
---

# Table of Contents

- Notas de la entrega de este documento:
```


# 1.0.- Library
Es la **biblioteca de conocimiento reutilizable del estudio**.
Todo lo que pueda utilizarse en dos o más proyectos pertenece aquí.
Nunca depende de un proyecto.
## ![[1.1.- Game Design#1.1.- Game Design]]
## ![[1.2.- Learning Design#1.2.- Learning Design]]
## ![[1.3.- Global UX UI#1.3.- Global UX/UI]]
## ![[1.4.- Global XR#1.4.- Global XR]]
## ![[1.5.- Technical#1.5.- Technical]]
## ![[1.6.- Production#1.6.- Production]]
## ![[1.7.- Global Assets#1.7.- Global Assets]]
![[1.8.- References#1.8.- References]]
---
# 2.0.- Global systems
Aquí viven los sistemas  transversales que se pueden utilizar en todos los proyectos.
Las implementaciones viven en cada proyecto.

## 2.1.- [[Progression system]]

# 3.0.- Global props & assets
Aquí viven los props y assets que se pueden usar en todos los proyectos.
Las implementaciones y variantes viven en cada proyecto.
Analizar si alguno de esos elementos deben considerarse como globales.

# 4.0.- Projects
Aquí viven únicamente las implementaciones.
Nunca el conocimiento base.

Dentro de un proyecto:
## 4.1.- [[STT]]


---**PRE-PRO**---

### ![[Vision]]

---**PRODUCTION**---

### ![[Production]]
### ![[Features]]
### ![[Levels]]
### ![[Scenarios]]
### ![[Learning]]
### ![[Assets]]
### ![[Credits]]
### ![[Releases]]
### ![[QA]]
---**POST-PRO**---

---**LIVE-OPS**---
## 4.2.- [[PilotLab]]
## 4.3.- MRStudio
## 4.4.- ETC

---
# 5.0.- Outputs
Documentación generada automáticamente.
Nunca se edita.

/Outputs
- GDD
- TDD
- Learning Guide
- Art Bible
- UX Bible
- PDF
- Presentation
---
# 8.0.- Knowledge
Acá van todas las capacitaciones de Simón además de posibles documentos de registro de las capacitaciones que realice el equipo.
# 9.0.- Archive
Proyectos terminados.
Versiones antiguas.
Backups.
Todos los formatos.

# Notas de la entrega de este documento:
Se propone en primera instancia utilizar directamente la el espacio de almacenamiento NASX para eventualmente migrar a Gitea, que debería ser la solución final para los problemas de versionamiento y acceso.

Se propone el uso de Gitea para el manejo de versiones de los documentos y de la Bóveda en general, ya que debido a la escala del proyecto no es necesario buscar alguna solución con mayores características. Si el proyecto eventualmente lo requiere, se considerará migrar a otro sistema.

