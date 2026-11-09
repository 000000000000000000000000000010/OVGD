---
Colaboradores:
  - "[[Flavio A]]"
tags:
  - ActiveProject
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

# 00_Context

- [ ] Traducir
- [ ] Referenciar externamente
## Context
Como parte del entrenamiento de toda persona que entra en un nuevo navío, es necesario que cada persona se familiarice con las instalaciones del navío en cuestión. Es desde ese escenario que nace este proyecto, que busca invertir el proceso de entrenamiento a una instancia previa a subir al navío, de modo que al momento de subir, ya estén familiarizados con todos las secciones y salas que conforman el navío.

El navío en cuestión se llama Escotillón y se encuentra en construcción en estos momentos, con fecha de botadura para el 01/01/2027. Así mismo se están creando 3 otros navíos gemelos, por lo que el total de navíos idénticos serán 4.

## Training Objectives
-Familiarización con cada sección y sala del Navío.
-Comprensión de diferentes rutas posibles para llegar desde dos diferentes puntos del navío.
## Target User
Los Usuarios objetivos serán los cadetes que usen cualquiera de los 4 navíos gemelos que se encuentran en construcción.

## Learning Pillars (Concept Map / Hierarchy DIAGRAM)
https://www-unesco-org.translate.goog/en/dtc-financing-toolkit/six-pillars?_x_tr_sl=en&_x_tr_tl=es&_x_tr_hl=es&_x_tr_pto=tc
**Data and evidence**
The data and evidence pillar focuses on using data to inform and improve educational experiences. It emphasizes the importance of generating practical recommendations through data analysis, ensuring interconnected and interoperable data systems, applying standardised methods for accurate and comprehensive data collection, establishing strong data protection measures, and ethically leveraging AI to enhance education processes.

Central to this pillar is the bidirectional relationship between data and all other aspects of digital transformation. Data shapes decisions across areas like capacity development, content, and infrastructure—while digital transformation, in turn, produces richer, more useful data that feeds back into planning and improvement.

Without robust data and evidence systems, digital transformation efforts risk lacking direction, impact, and the ability to drive continuous improvement in education.


**Connectivity and infrastructure**
Connectivity and infrastructure focuses on the availability, reliability, and accessibility of the technical systems needed to support digital education. It includes five key components: electricity; internet access; hardware and devices; system software and services; and learning spaces.

This pillar emphasises the importance of reliable electricity and affordable internet for all educational institutions, adequate access to digital devices and technical systems, strong IT support and security measures, and adaptable physical spaces that enable effective digital learning.

It also considers online–offline alternatives to support learning in areas with limited connectivity, including mobile and low-tech solutions. In addition, it recognises the need for renewable energy infrastructure to improve sustainability, and the importance of secure digital environments, supported by system software and services that protect sensitive educational data.

**Content and solutions**
Content and solutions examines the quality, accessibility, and relevance of digital learning materials, tools, and platforms. It focuses on ensuring that educational content is high-quality, open, inclusive, and aligned with curricular standards, and that platforms are secure, user-friendly, and regularly updated.

It includes five key components: learning platforms that effectively deliver and manage content; application software that is high-quality and open to promote equitable access; alignment with curricula to ensure relevance; digital and blended pedagogical models that enhance teaching and learning; and assessment and certification systems that recognise and validate learning.

This pillar emphasises the importance of developing user-friendly platforms that support personalised learning, deploying high-quality digital content aligned with national curricula, adopting innovative pedagogical approaches, and implementing assessment systems that guide learners through structured educational pathways.

# 01_Core Design ----
- [ ] Revisar contenido
- [ ] Diagramas con alpha
- [ ] Textos de diagramas

## Core Pillars  (Concept Map DIAGRAM)
- [x] Integrar definición corta de cada pilar ✅ 2026-10-15
Se distinguen, en orden de importancia, los siguientes Core Pillars para la experiencia:
#### -Exploración:
Es la mecánica base desde la cual se construye el resto de la experiencia
#### -Reconocimiento:
Los elementos que construyen el mundo, tanto como objetos o espacios, deben configurarse como instancias reconocibles, ya sea por si sola mediante indicadores diegéticos o sobrepuestos.

#### -Progresión:
El usuario debe poder estar al tanto de su progresión, de modo de comprender el estado actual de su progresión, respecto del estado final o subsecciones que se definan en la experiencia general de la aplicación.
#### -Simulación de escenarios:
Es fundamental someter al usuario a simulación de escenarios en los que deba realizar recorridos específicos, recreando uso real dentro del buque.





![[CorePillars_Escotillon.png]]



## Gameplay Loop (Loop Flowchart DIAGRAM)
- [x] Integrar definición corta de cada nodo ✅ 2026-10-16

Este es el principal flujo que ejecutará el usuario y cada elemento debe quedar explicito o implícito.
#### Login
Es el proceso de identificación del usuario. Permite llevar registro de la progresión del usuario.

#### Brief / Progression check
Es el proceso de entrega de estado actual de la progresión y los siguientes pasos correspondientes a la sesión actual.

#### Exploración
Es la principal mecánica que el usuario realizará. Consiste en explorar el buque, usando las funciones de locomoción.

#### Reconocimiento
Es el proceso implícito que debe realizar el usuario. Para ello el diseño de cada sala o sección deberá tener elementos reconocibles, tanto visuales como funcionales.

#### Logout
Proceso de cierre de la sesión, liberando el equipo que está utilizando el usuario.
![[GamePlayLoop_ESCOTILLÓN.png]]
## Training Loop (Loop Flowchart DIAGRAM)
- [ ] Integrar definición corta de cada nodo
- [ ] ???????

#### Intro
asd
#### Ejecución
asd
#### Aumento de complejidad
asd

#### Conclusión

![[TrainingLoopEscotillon.png]]






## Learning Loop (Loop Flowchart DIAGRAM)
- [ ] Integrar definición corta de cada nodo
Un Learning Loop o ciclo de aprendizaje es un proceso cíclico continuo, en el que el estudiante realiza diferentes etapas, repetidas veces, analizando su desempeño del ciclo anterior, para poder cambiar su comportamiento para el siguiente loop, en el que integrará más contenido o contenido dependiente del ciclo anterior.


#### Aprender
Como primera etapa en este loop, es la etapa en la que se entrega el contenido a los estudiantes, y donde deben investigar, examinar y aprender los nuevos conceptos entregados.
#### Aplicar
Los estudiantes deben aplicar la comprensión del contenido entregado, mediante entrenamiento situacional.
#### Analizar
Retroalimentación respecto del proceso de aprendizaje, mediante evaluación y feedback. Para que esta parte del proceso sea efectiva, es necesario entregar feedback de su desempeño de manera continua, para que puedan reajustar su comportamiento antes del termino del proceso educativo.
#### Revisar
Esta es la etapa de evaluación global del proceso enseñanza-aprendizaje, y planificación mejoras para el siguiente ciclo. Por un lado el ente docente puede adaptar de manera optima el diseño del programa deacuerdo al desempeño del estudiante,  y el estudiante puede mejorar aspectos del ciclo anterior.




![[LearningLoopEscotillon.png]]



# 02_Learning
- [x] Traducir ✅ 2026-10-19
- [ ] Referenciar externamente
- [ ] Revisar con Oscar
Se integran conceptos y procesos de la educación experiencial. Para esto se utilizan diferentes recursos para organizar el proceso educativo.

## Skill Matrix (Matrix DIAGRAM)
- [x] Integrar definición ✅ 2026-10-19
La matriz de habilidades es una herramienta para poder categorizar a los usuarios, además de poder evaluar a cada uno, de modo de poder registrar su evolución al inicio, durante y al finalizar la experiencia. De ese modo es posible adaptar la experiencia entre sesiones de uso, de acuerdo a la evolución de cada estudiante.

| Rol        | Project <br>management | Leadership | Comunication |
| ---------- | ---------------------- | ---------- | ------------ |
| Supervisor |                        |            |              |
| Técnico    |                        |            |              |
| Analista   |                        |            |              |
| Ingeniero  |                        |            |              |
En la columna de Rol va cada nombre o rol de los participantes, y en las demás columnas van los aspectos a ser evaluados (revisar con Oscar)


Se establecen 3 niveles de evaluación dentro de esta matriz.
Insuficiente: I
Básico: B
Avanzado: A
 

## Competencies (Competency Tree Hierarchy / Tree DIAGRAM)
- [x] Integrar definición del arbol y su intención ✅ 2026-10-19


El arbol de competencias define las habilidades y competencias que se buscan desarrollar en los estudiantes y su dependencia constructiva, vale decir, las competencias que se construyen en base a otras. Partiendo desde competencias clave básicas para formar parte del proceso de aprendizaje-enseñanza como filtro inicial.

Se distinguen 4 etapas del desarrollo de competencias:

#### 1.- Exploratoria / Explorar
En esta etapa el estudiante debe demostrar conocimiento de indicadores comunes, e inicia la aplicación de nuevos conceptos, tomando riesgos, aprendiendo tanto de éxitos como fracasos e integrando el feedback del ente educador.

#### 2.- Expansiva / Expandir
En esta etapa, el estudiante intencionalmente practica las competencias que está desarrollando en variadas situaciones y contextos.

#### 3.- Integradora / Integrar
Esta es la etapa en la que el estudiante aplica, adapta y experimenta de manera consistente con las competencias que está desarrollando. Siendo en esta etapa, la nueva capacidad reconocible como un recurso por otros.

#### 4.- Avanzadora / Avanzar
El estudiante en esta etapa es capaz de usar de manera estratégica e innovadora las nuevas capacidades desarrolladas, en complejas situaciones y escenarios. También será capaz de apoyar el crecimiento de otros estudiantes, a nivel personal, comunitario y organizacional.

![[Arbol de competencias Escotillon.png]]


## Certification Path (Approval Path?) Quizás no va* (Process Flowchart DIAGRAM)
- [ ] Integrar definición corta de cada pilar
- [ ] Revisar con Oscar

Se establece un proceso de certificación, basado en elasdsadsad





![[C ertificationpath.png]]


# 03_Architecture

- [ ] Investigar
- [ ] Revisar con Rafael / Mati (quizás todos?)

## System Architecture (Architecture Diagram)



## Data Flow (Data Flow Diagram)



## Dependencies (Dependency Graph Graph / Network Diagram)
==What?==
==Dependencias entre los diferentes sistemas?==




# 04_Systems

- [ ] Investigar
- [ ] Revisar con equipo de progra


## System Overview (System Flowchart)
==Resumen general de los sistemas involucrados y sus interdepencias==

## State Machine (State Machine Diagram)


## Progression System (Process Flowchart)
==Presentación del progression System que está desarrollado Bastián==
## Feedback System (Flowchart DIAGRAM)
Se utilizará el sistema de feedback para el usuario que se encargará de entregarle  información correspondiente a su progreso y performance.

Este sistema consta tres grandes grupos de elementos:
### Visuales
Progreso
Guardián
Menús

### Sonoros
-Emisión de sonidos 2D o 3D según corresponda
para esto se usarán sonidos de librerías libres de derechos

-Emisión de Metasound Sources en el uso de UI
para eso se ha creado una librería de Metasounds que responda adecuadamente a las diferentes interacciones con la UI

### Hápticas
Todas las respuestas hápticas están supeditadas directamente a la potencia y cambios que producen las respuestas sonoras


## Navigation system (Flowchart DIAGRAM)
Registro de cada M2 recorrido / cada sala / cada sector
### Metro Cuadrado
Registrar cada metro cuadrado que recorre el usuario en un espacio determinado, viéndose representado en un mini mapa que va representando de manera acumulativa el area recorrida por el usuario.


### Registro de recorrido (líneas)
Registrar el recorrido lineal del usuario en cualquier lugar, con tal de recoger los diferentes recorridos y puntos de interés con los que el usuario se encuentra durante la experiencia.

### Pistas  e indicadores
Incorporación de pistas, que den señales de donde se podrían encontrar puntos de interés relevantes para el usuario que debe encontarar por si mismo. Estas pistas pueden tomar forma de punto o de area, con tal de no transformarse en un indicador.

Incorporación de Indicadores, que muestren lugares exactos donde se encuentren puntos de interés relevantes para el usuario.




# 05_Mechanics (mechanics= Systems + Content)

- [ ] Investigar
- [ ] Definir
- [ ] Diseñar
- [ ] Proponer
## Movement (Flowchart / Interaction Flow)
**

## Interaction (Interaction Flowchart)
**


## Manipulation (Interaction Flowchart)
**

## Abilities (Flowchart)
**


## Navigation (Flowchart)
**





# 06_Content
- [ ] Establecer junto con cliente
- [ ] Testear viabilidad de implementación respecto de la extensión



## Content Overview (Hierarchy / Content Map DIAGRAM)
==Presentación introductoria del contenido con el que se poblará la experiencia==




## Levels (Flowchart DIAGRAM)
==Presentación de todos los niveles que tendrá la experiencia==





## Scenarios (Scenario Flowchart DIAGRAM)
Presentation de la lista de scenarios (historias de usuario)




## Procedures


### Procedure Overview (Hierarchy / Process Map)


### Procedure Flow (Tipo: Process Flowchart)


### Decision Tree (Tipo: Decision Tree)


### Exception Flow (Exception / Recovery Flowchart)


### Critical Path (Process Flow / Critical Path)


## Procedures + Procedure Flows
==Todos los procedimientos que se enseñarán en la experiencia, estos dependen de los niveles y de los requerimientos establecidos con cliente==

==Flowcharts con cada uno de los procedimientos que se quieren enseñar==

(procedures= Levels+Scenarios)

# 07_UX_UI
- [ ] Investigar
- [ ] Revisar con equipo de progra


## UX Overview (UX Structure Tipo: UX Map)
==Presentación de los conceptos centrales de UX UI que gobernarán la toma de decisiones del UX/UI==
Se plantean los siguientes flujos de usuario





## User Journey (Journey Map)
==Flowchart con el viaje mental que se espera el usuario experimente==




## HUD/UI (UI Flowchart)
==Presentación con todos los elementos de User Interface que conforman la experiencia==

# 08_Aestetics
- [ ] Referenciar Propuesta de arte DTS_A
- [ ] Incorporar contenido faltante en la propuesta (Sonido, háptica)


## Tone
==Tono que se utiliza en la presentación del producto==
## Visuals (Visual Direction Visual Reference Map)
==Propuesta gráfica ya existente para los proyectos de DTS==

## Sounds (Audio Flowchart)
==Propuesta sonora para los proyectos de DTS==


## Haptics (Haptic Feedback Flow Interaction / Feedback Flowchart)






# 09_Narrative ?*

- [ ] Definir si va o no


## Story (Narrative Flow Narrative Flowchart)
## Scenario Context  (Narrative FlowScenario Context Map Tipo: Context Mapchart)
## Dialogue (Dialogue Flowchart)






Contrato:


## Hardware a usar

### HMD
Head Mounted Display

**Meta Quest 3:** Hardware conocido y usado por el equipo. No requiere conexión a internet, pero si una red inalámbrica exclusiva, para potenciar la transmisión del contenido entre el PC y el HMD.

https://knasta.cl/detail/falabella/156345470/lentes-de-realidad-virtual-quest-3-512gb?q=meta+quest+3%2C

**Steam Frame:** Nuevo HMD Hardware de Valve. aún no se encuentra disponible para la venta en Latinoamérica. Posee especiaciones superiores en algunos aspectos al Meta Quest 3, en particular lo que respecta a la transmisión de datos entre el PC y el HMD

https://www.ebay.com/itm/206631814714?_trkparms=itmf%3D0%26aid%3D1110006%26rkt%3D10%26algo%3DHOMESPLICE.SIM%26asc%3D346198%26pid%3D101506%26mech%3D1%26algv%3DSimOrganicCassiniWithToraRecalls%26pmt%3D0%26amclksrc%3DITM%26sd%3D128085102642%26sid%3DAQALAAAAEDNmoy%2F1fLtaacOpDqFmR4w%3D%26itm%3D206631814714%26noa%3D1%26ao%3D1%26rk%3D5%26mehot%3Dnone%26lsid%3D0%26meid%3D13c62cce90b3471fbe4810f654f44c3d%26pg%3D4481478&_trksid=p4481478.c101506.m1851

### PC
Personal Computer

**Custom PC:** Un computador donde se puede elegir cada componente ya sea para alcanzar cierta performance o cierto presupuesto económico. cuenta con las posibles complicaciones de solicitar un producto de estas características, como compatibilidad entre los componentes y viabilidad al momento de comprar.

https://invasiongamer.com/pc-gamer-radiant-amd-ryzen-7-5700x-nvidia-rtxe284a2-rx-9060-xt-16g-nvidia-rtxe284a2-5060-ti-16g

**Steam Machine:** Un computador pre-configurado desarrollado por Valve. Forma parte del ecosistema de Steam, por lo que es perfecto para ser usado con Steam Frame. En particular cuenta con una antena que permite una conexión directa, que se ve mejorada por el uso de una red inalámbrica.

https://www.ebay.com/itm/206385150766?_skw=steam+machine&itmmeta=01M5G2DYBV3N8GV2BAAFPWTVPP&hash=item300d837b2e:g:dNwAAeSwwz5qRH8o&itmprp=enc%3AAQALAAAA8CHNgUiiE%2FjQhlDTaMiAde9MMi0Vb1bBQ5EfWgOg7PDXjfee8DimJ2Hk00Be4Wgh%2FHcFj2yK%2FDp%2FBFeAS%2B122yh%2BRVxoKyaNR5zA1AAx3VxXU8CciCleSxK12xjUirc39eIgJZBq4Nhr%2FQTbbOnaVM7rJwNwI%2FaIcnrgiuWsHsvivd6btdhlqCEt5k6bXD0q5pk1xcnU--L5%2Bpl17S0Okply2lX%2BlCMe4RyGL2BY7%2F%2BpqBhQ0Jszrwv%2FX9jJZIrmwytPcU4IWcII1yKPSNkHj3dvTE6oNGMaXHSL2o%2BYUtAYGnMHR%2Bjcl4KjGMxt6WHjaA%3D%3D%7Ctkp%3ABk9SR7Dmt4KsaA



Si se opta por una combinación de productos, Steam Machine es un equipo suficientemente competente para cumplir con todos los requerimientos que se necesitan para el proyecto.


Arquitectura:


# Requerimientos para cliente:
## Entorno VR

**Definiciones:** si es recorrido guiado, libre o ambos
Si es guiado incluir tanto puntos de inicio, fin e interpolación
(si quieren que siga alguna ruta en específico o lo decidimos nosotros, buscando el recorrido más corto)
(entiendo que es solo libre, o consultar con cliente o revisar contrato)

**Assets:**
Modelos 3D de todo el navío y todos los elementos que contiene
(navío, muebles, maquinaria, etc.)

**Contenido:** Toda la información de cada sala o elemento interno del buque, que sea visible a la vista, que cliente desee entregar a los usuarios mediante Tooltip

## LMS

**Definiciones:** Definir si el curso ya existe en un LMS. De no existir, necesitamos el diseño instruccional del curso completo, para poder articularlo nosotros.

**Assets:**
Manual de normas gráficas
Todas las imágenes finales que irán en el curso
Todos los audios asociados al curso
Todos los elementos multimedia que quieran incluir (videos, fotos, etc.)

**Contenido:** Todo el contenido definido del curso (diseño instruccional)
Todas evaluaciones y actividades

## Demostrador AR

**Definiciones:**
Lista de objetos a demostrar

**Assets:** Modelos 3D de los objetos a demostrar

**Contenido:** El contenido a mostrar en formato de texto, acorde a todos los objetos que desean demostrar





