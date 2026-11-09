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
Título: `= this.file.name`
Colaboradores: `= this.colaboradores`
Tags: `= this.file.tags`
Última edición: `= dateformat(this.file.mtime, "dd-MM-yyyy HH:mm")`
---

```
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
Título: `= this.file.name`
Colaboradores: `= this.colaboradores`
Tags: `= this.file.tags`
Última edición: `= dateformat(this.file.mtime, "dd-MM-yyyy HH:mm")`
---

```






`$=dv.list(dv.pages('').sort(f => f.file.mtime.ts, "desc").limit(5).map(f => f.file.link + " - : " + (f.Colaboradores || "-")))`











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

- Quote all note:
- Quote a Full paragraph
- Quote a paragraph section
- Link WikiLink:
- CALOUTS:
- SIMBOLOS!
```

COPIAR INSTA TOC


> [!abstract] Resumen
Este es un resumen de lo que podrán encontrar en este documento

> [!note] Objetivos
-Este es EL o LOS objetivos de el documento
-Deben redactarse como bullets
-Y nunca deberán ser más de 3


# Quote all note:
```
![[Lorem Ipsum]]
```
![[Lorem Ipsum]]

---
# Quote a Full paragraph
```
![[Lorem Ipsum#3°Párrafo]]
```
![[Lorem Ipsum#3°Párrafo]]

---

# Quote a paragraph section
![[Lorem Ipsum#^54d03a]]

```
![[Lorem Ipsum#^54d03a]]
```

# Link WikiLink:
[[Lorem Ipsum#4°Párrafo]]
```
[[Lorem Ipsum#4°Párrafo]]
```

For paragraph
```
^
```

For headers
```
#
```





# CALOUTS:

> [!danger]
> Lorem ipsum dolor sit amet


> [!note]
> Lorem ipsum dolor sit amet


> [!abstract]
> Lorem ipsum dolor sit amet

> [!info]
> Lorem ipsum dolor sit amet

> [!todo]
> Lorem ipsum dolor sit amet

> [!tip]
> Lorem ipsum dolor sit amet

> [!success]
> Lorem ipsum dolor sit amet

> [!question]
> Lorem ipsum dolor sit amet

> [!warning]
> Lorem ipsum dolor sit amet

> [!failure]
> Lorem ipsum dolor sit amet

> [!danger]
> Lorem ipsum dolor sit amet

> [!bug]
> Lorem ipsum dolor sit amet

> [!example]
> Lorem ipsum dolor sit amet

> [!quote]
> Lorem ipsum dolor sit amet



# **SIMBOLOS**!

↑↓→←↔↕↨▲▼►◄ —







Recent file updates
`$=dv.list(dv.pages('').sort(f=>f.file.mtime.ts,"desc").limit(5).file.link)`
- Active projects:  `$=dv.list(dv.pages('#ActiveProject').sort(f=>f.file.name,"desc").limit(5).file.link)`
- Stats
	-  File Count: `$=dv.pages().length`
	-  Personal recipes: `$=dv.pages('"Family/Recipes"').length`



- **Dashboard:** Resumen general del estado del desarrollo
- **Accesos rápidos:** Links importantes a los cuales acceder
- **Proyectos activos:** Proyectos en los que se está trabajando ==OK==
- **Últimas modificaciones:** Changelog ==OK==
- **Calendario:** Visualización de fechas importantes, como entregas o feria ==OK==
- **Templates:** -En eso-



0.0 Home
Centro de navegación de la Vault.
No almacena información de proyectos.






```tasks
not done

```
