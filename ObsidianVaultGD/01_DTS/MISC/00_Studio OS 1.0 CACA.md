---
Status: Draft
Colaboradores:
  - "[[Danae T]]"
  - "[[Flavio A]]"
  - "[[Bastián R]]"
date: 2026-07-23T21:42:00
---
**Título:** `= this.file.name`
**Colaboradores:** `= this.Colaboradores`
**Status:** `= this.Status`
**Fecha de Creación:** `= this.file.cday`

---

# **0.0 Home**
# **1.0 Documentation**
# **2.0 Global systems**
# **3.0 Global props & assets**
# **4.0 Projects**
# **5.0 Outputs**
# **8.0 Knowledge**
# **9.0 Archive**

---



# **0.0 Home**
Centro de navegación de la Vault.
No almacena información de proyectos.

- **Dashboard:** Resumen general del estado del desarrollo
- **Accesos rápidos:** Links importantes a los cuales acceder
- **Proyectos activos:** Proyectos en los que se está trabajando
- **Últimas modificaciones:** Changelog
- **Calendario:** Visualización de fechas importantes, como entregas o ferias
- **Templates:**

.md .canvas .excalidraw

---

# **1.0.- Documentation**
Es la **biblioteca de conocimiento reutilizable del estudio**.
Todo lo que pueda utilizarse en dos o más proyectos pertenece aquí.
Nunca depende de un proyecto.

## **1.0 Library**

## **1.1.- Game Design**
Cada mecánica existe **una sola vez**.
- Mechanics (Interact)
- Systems
- Core Loops
- Interaction Patterns
- Progression
- Balancing
- Game Feel
- Design Principles

.md.canvas.excalidraw.mmd.png.svg

## **1.2.- Learning Design**
- Competencies
- Learning Objectives
- Assessments
- Rubrics
- Feedback
- Learning Loops
- Evaluation
- Models

.md.canvas.csv

## **1.3.- UX/UI**
- Interaction Patterns
- Personas
- Journey Maps
- Heuristics
- Accessibility
- Mental Models

.md.canvas.excalidraw

## **1.4.- XR**
- Comfort
- Locomotion
- Hand Tracking
- Passthrough
- Spatial UI
- Voice
- Eye Tracking

.md.canvas.png

## **1.5.- Technical**
- Architecture
- Blueprint Patterns
- OpenXR
- Networking
- Performance
- Save System
- Localization
- Coding Standards

.md.json.yaml.mmd

## **1.6.- Production**
- Pipelines
- Workflows
- Checklists
- Definition of Done
- Standards

.md

==(acá va todo lo del Notion de Simón)==

## **1.7.- Assets**
Recursos reutilizables.
No específicos de un proyecto.

- Icons
- Logos
- Templates
- Fonts
- UI Kit
- Shaders
- Materials

.svg.png.psd.ttf.otf

## **1.8.- References**
- Research
- Papers
- Books
- Benchmark
- Norms

.pdf.md.bib.url

---





# **4.0 Projects**
Aquí viven únicamente las implementaciones.
Nunca el conocimiento base.

Dentro de un proyecto:
## **4.1.- STT**

---**PRE-PRO**---

## **4.1.1.-  Vision**
- Objetivos
- Alcance
- KPIs
- Público objetivo
- Restricciones

---**PRODUCTION**---

## **4.1.2.- Production**
Estado actual del proyecto.
- Roadmap
- Sprint
- Meeting Notes
- Decisions
- Risks
- Backlog

## **4.1.3.- Features**
Implementaciones.
No define mecánicas. Las utiliza.
Usualmente una combinación de mecánicas, más un contexto y contenido.
```
Ejemplo.
# Electrical Cabinet InspectionUses[[Grab]][[Inspect]][[Hazard Detection]][[Hand Tracking]][[Assessment]]
```

(Implementación de interact)
## **4.1.4.- Levels**
Diferentes niveles donde el jugador interactúa.
- Diseño del espacio.
- Eventos.
- Triggers.
- Secuencia espacial.

## **4.1.5.- Scenarios**
Implementaciones de los niveles más contenido.
```
Ejemplo.
Electrical Cabinet
Hydraulic Pump
Control Room
```

## **4.1.6.- Learning**
Cómo este proyecto implementa:
- Competencias
- Objetivos
- Evaluaciones

Referenciando la Library.



## **4.1.7.- Assets**
Recursos exclusivos del proyecto.

```
Ejemplo:
Project Logo
Specific UI
Specific Audio
Client
Documents
```

## **4.1.8.- Credits**
- People
- Roles
- Localization
- Licenses

## **4.1.0.- Releases**
- Release Notes
- Build History
- Version Log
- Versions (FIDAE)

## **4.1.10.- QA**
- Bugs
- Test Cases
- Playtests
- Resultados

---**POST-PRO**---

## **4.1.11 LiveOps**



## **4.2.- PilotLab**
## **4.3.-MRStudio**
## **4.4.- ETC**


---**LIVE-OPS**---


---
# **5.0 Outputs**
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


# 8.0 Knowledge
Acá van todas las capacitaciones de Simón además de posibles documentos de registro de las capacitaciones que realice el equipo.



# 9.0 Archive

Proyectos terminados.
Versiones antiguas.
Backups.




Todos los formatos.


---
# Notas de la entrega de este documento:

Se propone en primera instancia utilizar directamente la el espacio de almacenamiento NASX para eventualmente migrar a Gitea, que debería ser la solución final para los problemas de versionamiento y acceso.

Se propone el uso de Gitea para el manejo de versiones de los documentos y de la Bóveda en general, ya que debido a la escala del proyecto no es necesario buscar alguna solución con mayores características. Si el proyecto eventualmente lo requiere, se considerará migrar a otro sistema.

