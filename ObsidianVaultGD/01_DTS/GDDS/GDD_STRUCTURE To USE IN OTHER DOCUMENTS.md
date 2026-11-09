




___________________________________________________________________________
ORIGINAL
______________________________________
01_GDD
│
├── 00_Context
│   ├── Context.md
│   ├── Training Objectives.md
│   ├── Target User.md
│   └── Learning Pillars.md
│
├── 01_Core Design
│   ├── Core Pillars.md
│   ├── Gameplay Loop.md
│   ├── Training Loop.md
│   └── Learning Loop.md
│
├── 02_Learning
│   ├── Competencies.md
│   ├── Skill Matrix.md
│   └── Certification Path.md

├── 03_Architecture
│   ├── System Architecture.md
│   ├── Data Flow.md
│   └── Dependencies.md
│
├── 04_Systems
│   ├── System Overview.md
│   ├── Progression.md
│   ├── Feedback.md
│
├── 05_Mechanics
│   ├── Movement.md
│   ├── Interaction.md
│   ├── Manipulation.md
│   └── Abilities.md
│
├── 06_Content
│   ├── Content Overview.md
│   ├── Levels.md
│   ├── Scenarios.md
│   └── Procedures -Procedure Flows
│
├── 07_UX_UI
│   ├── UX Overview.md
│   ├── User Journey.md
│   └── HUD/UI
│
├── 08_Aestetics
│   ├── Tone
│   ├── Visuals
│   ├── Sounds
│   └── Haptics
│
└── 09_Narrative
    ├── Story.md
    ├── Scenario Context.md
    └── Dialogue.md

___________________________________________________________________________
ORIGINAL
______________________________________

01_GDD
│
├── 00_Context
│   │
│   ├── Context.md
│   │   ⚪ TEXTO
│   │
│   ├── Training Objectives.md
│   │   🟢 TEXTO + TABLA
│   │
│   ├── Target User.md
│   │   🟢 TEXTO + TABLA
│   │
│   └── Learning Pillars.md
│       🟢 TEXTO + DIAGRAMA
│       └── Concept Map / Hierarchy
![[CoreDesignPillars_Escotillon.png]]



│
├── 01_Core Design
│   │
│   ├── Core Pillars.md
│   │   🟢 TEXTO + DIAGRAMA
│   │   └── Concept Map
│   │
![[CoreDesignPillars_Escotillon.png]]


│   ├── Gameplay Loop.md
│   │   🔵 DIAGRAMA
│   │   └── Loop Diagram
│   │
![[GamePlayLoop_ESCOTILLÓN.png]]
│   ├── Training Loop.md
│   │   🔵 DIAGRAMA
│   │   └── Loop Diagram
│   │
![[TrainingLoop_ESCOTILLÓN.png]]
│   └── Learning Loop.md
│       🔵 DIAGRAMA
│       └── Learning Cycle
│
![[TrainingLoop_ESCOTILLÓN-1.png]]

├── 02_Learning
│   │
│   ├── Competencies.md
│   │   🟢 TEXTO + DIAGRAMA
│   │   └── Competency T
│   │
![[Arbol de competencias.png]]



│   ├── Skill Matrix.md
│   │   🟡 TABLA + TEXTO
│   │




| Rol        | Project <br>management | Leadership | Comunication |
| ---------- | ---------------------- | ---------- | ------------ |
| Supervisor |                        |            |              |
| Técnico    |                        |            |              |
| Analista   |                        |            |              |
| Ingeniero  |                        |            |              |


Basico: B
Avanzado: A
Insuficiente: I





│   └── Certification Path.md
│       🟢 TEXTO + DIAGRAMA
│       └── Process Flow
│
│Aquí necesitamos un **process flow**.

| 1           | 2        | 3           | 4            |
| ----------- | -------- | ----------- | ------------ |
| Fundaciones | Asociado | Profesional | Especialista |
| Desc        | Desc     | Desc        | Desc         |

![[C ertificationpath.png]]



├── 03_Architecture
│   │
│   ├── System Architecture.md
│   │   🔵 DIAGRAMA
│   │   └── Architecture Diagram
│   │
![[DataFlow.png]]




│   ├── Data Flow.md
│   │   🔵 DIAGRAMA
│   │   └── Data Flow Diagram
│   │???????
│   └── Dependencies.md
│       🟢 TEXTO + DIAGRAMA
│       └── Dependency Graph
│?????????



├── 04_Systems
│   │
│   ├── System Overview.md
│   │   🟢 TEXTO + DIAGRAMA
│   │   └── System Flow
│   │
Tipo: System Flowchart
│   ├── State Machine.md
│   │   🔵 DIAGRAMA
│   │   └── State Machine
│   │
│   │       Tipo: State Machine Diagram
│   │?????????????????????
IDLE
  ↓
TRAINING
  ↓
EVALUATION
 ↙       ↘
PASS     FAIL
 ↓        ↓
END      RETRY


Estaba De la garganta


│   ├── Progression.md
│   │   🟢 TEXTO + DIAGRAMA
│   │   └── Progression Flow
│   │
Un flowchart estándar utiliza cajas para procesos y diamantes para decisiones; el ejemplo de loop de control muestra muy claramente esta convención.



│   └── Feedback.md
│       🟢 TEXTO + DIAGRAMA
│       └── Feedback Flow
│
│           Tipo: Flowchart
│
Linear Flow chart con detalles hacia abajo de cada etapa
![[Feedbackexample.png]]




├── 05_Mechanics
│   │
│   ├── Movement.md
│   │   🟢 TEXTO + DIAGRAMA
│   │   └── Movement / Interaction Flow
│   │
│   ├── Interaction.md
│   │   🔵 DIAGRAMA
│   │   └── Interaction Flow
│   │
![[InteractionFlow.png]]



│   ├── Manipulation.md
│   │   🟢 TEXTO + DIAGRAMA
│   │   └── Manipulation Flow
│   │
![[ManipulationFLow.png]]
![[ManipulationFLow_2.png]]

│   └── Abilities.md
│       🟢 TEXTO + DIAGRAMA
│       └── Ability Flow
│noooo??


├── 06_Content
│   │
│   ├── Content Overview.md
│   │   🟢 TEXTO + DIAGRAMA
│   │   └── Content Hierarchy
│   │
Gran Flowchart


│   ├── Levels.md
│   │   🟢 TEXTO + DIAGRAMA
│   │   └── Level Flow
│   │
![[LevelFlowChart.png]]


│   ├── Scenarios.md
│   │   🟢 TEXTO + DIAGRAMA
│   │   └── Scenario Flow
│   │


BRIEFING
   ↓
SCENARIO INTRO
   ↓
TASK
   ↓
EVENT
   ↓
DECISION
   ↓
OUTCOME
   ↓
DEBRIEF




│   ├── Events.md
│   │   🟢 TEXTO + DIAGRAMA
│   │   └── Event Flow
│   │

TRIGGER
   ↓
EVENT
   ↓
SYSTEM RESPONSE
   ↓
USER RESPONSE
   ↓
NEXT EVENT




│   └── Procedures
│       │
│       ├── Procedures.md
│       │   🟢 TEXTO + DIAGRAMA
│       │   └── Procedure Overview
│       │
│       ├── Procedure Flows.md
│       │   🔵 DIAGRAMA
│       │   └── Procedure Flowchart
│       │
│       ├── Decision Trees.md
│       │   🔵 DIAGRAMA
│       │   └── Decision Tree
│       │
│       ├── Exception Flows.md
│       │   🔵 DIAGRAMA
│       │   └── Exception / Recovery Flow
│       │
│       └── Critical Paths.md
│           🔵 DIAGRAMA
│           └── Critical Path
│
├── 07_UX_UI
│   │
│   ├── UX Overview.md
│   │   🟢 TEXTO + DIAGRAMA
│   │   └── UX Map
│   │
│   ├── User Journey.md
│   │   🔵 DIAGRAMA
│   │   └── Journey Map
│   │



│   └── HUD_UI.md
│       🟢 TEXTO + DIAGRAMA
│       └── UI Flow
│
├── 08_Aesthetics
│   │
│   ├── Tone.md
│   │   ⚪ TEXTO
│   │
│   ├── Visuals.md
│   │   🟢 TEXTO + REFERENCIAS VISUALES
│   │
│   ├── Sounds.md
│   │   🟢 TEXTO + TABLA
│   │
│   └── Haptics.md
│       🟢 TEXTO + TABLA
│
└── 09_Narrative
    │
    ├── Story.md
    │   🟢 TEXTO + DIAGRAMA
    │   └── Narrative Flow
    │
    ├── Scenario Context.md
    │   🟢 TEXTO
    │
    └── Dialogue.md
        🟢 TEXTO + DIAGRAMA
        └── Dialogue Tree





































V2 REFERENCES
____________________________


01_GDD
│
├── 00_Context
│   │
│   ├── Context.md
│   ├── Training Objectives.md
│   ├── Target User.md
│   └── Learning Pillars.md
│       └── [DIAGRAMA] Learning Pillars
│           Tipo: Concept Map / Hierarchy
│
├── 01_Core Design
│   │
│   ├── Core Pillars.md
│   │   └── [DIAGRAMA] Core Design Map
│   │       Tipo: Concept Map
![[CoreDesignPillars_Escotillon.png]]






│   ├── Gameplay Loop.md
│   │   └── [DIAGRAMA] Gameplay / Simulation Loop
│   │       Tipo: Loop Flowchart
│   │
│   ├── Training Loop.md
│   │   └── [DIAGRAMA] Training Loop
│   │       Tipo: Loop Flowchart
│   │
│   └── Learning Loop.md
│       └── [DIAGRAMA] Learning Loop
│           Tipo: Loop Flowchart
│
├── 02_Learning
│   │
│   ├── Competencies.md
│   │   └── [DIAGRAMA] Competency Tree
│   │       Tipo: Hierarchy / Tree
│   │
![[GDD_STRUCTURE.png|409]]
![[GDD_STRUCTURE_02.png|388]]
                 BEGINNER     INTERMEDIATE      ADVANCED
Procedure A                       X                    X
Procedure B                                              X                         X
Procedure C                                                                         X


│   ├── Skill Matrix.md
│   │   └── [DIAGRAMA] Skill Matrix
│   │       Tipo: Matrix
│   │


![[SkillMatrix_01.png]]


│   └── Certification Path.md
│       └── [DIAGRAMA] Certification Path
│           Tipo: Process Flowchart
│Aquí necesitamos un **process flow**.

![[Certification_Flow.png]]


├── 03_Architecture
│   │
│   ├── System Architecture.md
│   │   └── [DIAGRAMA] System Architecture
│   │       Tipo: Architecture Diagram
│   │
![[SystemArquitecture.png]]
VR INPUT
    ↓
INTERACTION
    ↓
SIMULATION
    ↓
PROCEDURE VALIDATION
    ↓
ASSESSMENT
    ↓
REPORTING


│   ├── Data Flow.md
│   │   └── [DIAGRAMA] Data Flow
│   │       Tipo: Data Flow Diagram
│   │
![[DataFlow.png]]


│   └── Dependencies.md
│       └── [DIAGRAMA] Dependency Graph
│           Tipo: Graph / Network Diagram
│????????????????????
├── 04_Systems
│   │
│   ├── System Overview.md
│   │   └── [DIAGRAMA] System Flow
│   │       Tipo: System Flowchart
│   │??????????????????????
│   ├── State Machine.md
│   │   └── [DIAGRAMA] State Machine
│   │       Tipo: State Machine Diagram
│   │?????????????????????
IDLE
  ↓
TRAINING
  ↓
EVALUATION
 ↙       ↘
PASS     FAIL
 ↓        ↓
END      RETRY



│   ├── Progression.md
│   │   └── [DIAGRAMA] Progression Flow
│   │       Tipo: Process Flowchart
│   │
Un flowchart estándar utiliza cajas para procesos y diamantes para decisiones; el ejemplo de loop de control muestra muy claramente esta convención.



│   └── Feedback.md
│       └── [DIAGRAMA] Feedback Flow
│           Tipo: Flowchart
│
Linear Flow chart con detalles hacia abajo de cada etapa
![[Feedbackexample.png]]



├── 05_Mechanics
│   │
│   ├── Movement.md
│   │   └── [DIAGRAMA] Movement Flow
│   │       Tipo: Flowchart / Interaction Flow
NO
│   │
│   ├── Interaction.md
│   │   └── [DIAGRAMA] Interaction Flow
│   │       Tipo: Interaction Flowchart
│   │
NO
│   ├── Manipulation.md
│   │   └── [DIAGRAMA] Manipulation Flow
│   │       Tipo: Interaction Flowchart
│   │
NO
│   └── Abilities.md
│       └── [DIAGRAMA] Ability Flow
│           Tipo: Flowchart
│
NO
├── 06_Content
│   │
│   ├── Content Overview.md
│   │   └── [DIAGRAMA] Content Structure
│   │       Tipo: Hierarchy / Content Map
│   │
│   ├── Levels.md
│   │   └── [DIAGRAMA] Level Flow
│   │       Tipo: Flowchart
│   │
│   ├── Scenarios.md
│   │   └── [DIAGRAMA] Scenario Flow
│   │       Tipo: Scenario Flowchart
│   │
│   └── Procedures
│       │
│       ├── Procedures.md
│       │   └── [DIAGRAMA] Procedure Overview
│       │       Tipo: Hierarchy / Process Map
│       │
│       ├── Procedure Flows.md
│       │   └── [DIAGRAMA] Procedure Flow
│       │       Tipo: Process Flowchart
│       │
│       ├── Decision Trees.md
│       │   └── [DIAGRAMA] Decision Tree
│       │       Tipo: Decision Tree
│       │
│       ├── Exception Flows.md
│       │   └── [DIAGRAMA] Exception Flow
│       │       Tipo: Exception / Recovery Flowchart
│       │
│       └── Critical Paths.md
│           └── [DIAGRAMA] Critical Path
│               Tipo: Process Flow / Critical Path
│
├── 07_UX_UI
│   │
│   ├── UX Overview.md
│   │   └── [DIAGRAMA] UX Structure
│   │       Tipo: UX Map
│   │
│   ├── User Journey.md
│   │   └── [DIAGRAMA] User Journey
│   │       Tipo: Journey Map
│   │
│   └── HUD_UI.md
│       └── [DIAGRAMA] UI Flow
│           Tipo: UI Flowchart
│
├── 08_Aesthetics
│   │
│   ├── Tone.md
│   │
│   ├── Visuals.md
│   │   └── [DIAGRAMA] Visual Direction
│   │       Tipo: Visual Reference Map
│   │
│   ├── Sounds.md
│   │   └── [DIAGRAMA] Audio Flow
│   │       Tipo: Audio Flowchart
│   │
│   └── Haptics.md
│       └── [DIAGRAMA] Haptic Feedback Flow
│           Tipo: Interaction / Feedback Flowchart
│
└── 09_Narrative
    │
    ├── Story.md
    │   └── [DIAGRAMA] Narrative Flow
    │       Tipo: Narrative Flowchart
    │
    ├── Scenario Context.md
    │   └── [DIAGRAMA] Scenario Context Map
    │       Tipo: Context Map
    │
    └── Dialogue.md
        └── [DIAGRAMA] Dialogue Flow
            Tipo: Dialogue Flowchart




____________________________
V2:

