

# PILOTLAB

Plataforma inmersiva de entrenamiento aéreo.

## Contexto

La instrucción de maniobras aéreas exige normalmente combinar clases teóricas, horas de cabina real y simuladores de alto costo. Este proyecto nace para cerrar la brecha entre la teoría y los simuladores full-motion, ofreciendo una experiencia inmersiva en realidad virtual que:

-Reproduce con fidelidad el entorno de cabina de un solo modelo de aeronave.

-Guía al alumno a través de briefing, reproducción y evaluación de cada maniobra.

-Permite al instructor supervisar el progreso mediante métricas objetivas sin incrementar horas de vuelo reales.

Con ello se busca reducir costes operativos y riesgos, al tiempo que se estandariza el aprendizaje básico antes de pasar a dispositivos de entrenamiento más avanzados. 

==**(contextualizar las necesidades y escenario de uso de la App)**==

### Género

Simulación, educación, Juegos serios.

### Audiencia objetiva

Dirigida a pilotos en activo, alumnos en formación y a sus instructores, quienes necesitan supervisar el avance y la correcta ejecución de las maniobras en un entorno VR realista. 

**==(Quién usará la app)==**

### Resumen ejecutivo

Esta es una herramienta de realidad virtual que combina la reproducción detallada de maniobras de vuelo; el control de la reproducción misma; con la entrega de los valores exactos tanto de indicadores como de controles, con la finalidad que el usuario memorice el procedimiento de ejecución de cada maniobra. Reemplazando de esa manera la práctica del Vuelo Seco, técnica con la que en la actualidad se enseñan dichas maniobras de vuelo. 

**==(qué es, de qué sirve, a quién va dirigida)==**

### Declaración conceptual

Ya está aquí la siguiente etapa en el aprendizaje práctico en maniobras de vuelo.  Podrás ver con tus propios ojos lo mismo que vería un piloto al momento de realizar cualquier maniobra. Además te ayudará a aprender qué factores son determinantes en cada etapa del desarrollo de una maniobra de vuelo. 

**==(Párrafo de speech de venta directa steam)==**

## Core Pillars







## Gameplay Loop

**==(Reemplazar por FLowChart)==**




## Mecánicas de juego

______________________________________
#### Dash  Example (should be a table)
  
##### Purpose  
Permitir evasión rápida y reposicionamiento.  
  
##### Input  
Shift  
  
##### Rules  
- Distancia: 5m  
- Duración: 0.3s  
- Cooldown: 3s  
- Invulnerabilidad: 0.2s  
  
##### Conditions  
- No usable airborne  
  
##### Output  
- Movimiento rápido  
- Evade attacks  
  
##### Feedback  
- Motion blur  
- Dash SFX  
- Trail VFX  
  
##### Dependencies  
- Movement system  
- Stamina  
- Animation state machine

__________________________________________________________

**De Interacción:**
Mediante apuntar y presión de botones, se podrá interactuar con diferentes interfaces:

Menús VR: Para distintas elecciones del usuario, como selección de maniobra, modos, configuraciones, etc.

Línea temporal interactiva: Barra situada en UI espacial que muestra las fases de la maniobra. Se puede avanzar, retroceder y reproducir/pausar.

Señalamiento y descripción: Señaladores flotantes que se activan solo cuando la fase lo requiere; muestran texto breve sobre palancas, instrumentos o referencias externas.

**De Movimiento:**
Solo se establece el movimiento de cámara guiado por el Headset.

**De Comunicación:**
Mediante Tooltips, locución  y efectos de sonido. 

==(principales mecánicas que constituyen la experiencia)==



## Systems

### Sistemas y arquitectura de juego


|                                   |                                        |                                                                                      |                                                |
| --------------------------------- | -------------------------------------- | ------------------------------------------------------------------------------------ | ---------------------------------------------- |
| **Sistema**                       | **Responsabilidad principal**          | **Componentes clave**                                                                | **Datos que intercambia**                      |
| **Módulo Briefing**               | Presentar vista externa guiada.        | Reproductor de vídeo con vista externa de la maniobra. Notas generales a considerar. | Metadatos de la maniobra, marcadores de fases. |
| **Módulo Reproducción en cabina** | Mostrar la maniobra en POV 1ª persona. | Escenario cabina, sistema de cámaras, indicadores 3D contextuales.                   | Estados de elementos destacados.               |
| **Panel de instructores**         | Supervisar progreso y asignar tareas.  | Dashboard, filtros por alumno y maniobra, descarga de reportes.                      | Datos consolidados del registro de desempeño.  |
| **Subsistema de audio**           | Ambiente de cabina + feedback sonoro.  | Bucle de ambiente, efectos de interacción, alertas de checkpoint.                    | Triggers de evento desde los tres modos.       |
| **Interactivos VR / Input**       | Controles o hand-tracking.             | Mapeo de dispositivos (PCVR), colisionadores de UI espacial.                         | Eventos de entrada (selección, señalamiento).  |

==**(Principales sistemas de la App)**==

### Progression

**Objetivos**
Facilitar la formación de pilotos mediante una experiencia inmersiva que reduzca costos operativos, comunique con claridad los puntos clave de cada maniobra y permita medir el progreso con evaluaciones integradas. 

**==(objetivo general del producto, con su valor de venta particular)==**

### Objetivos particulares

**-Comprensión global de la maniobra** - Proporcionar al alumno una vista externa guiada que identifique trayectoria y fases antes de entrar a cabina.

**-Interiorización procedimental en cabina** - Permitir la reproducción en primera persona con indicadores 3D que señalen controles y parámetros clave hasta que el alumno pueda anticipar cada paso sin ayuda visual.

**-Verificación del conocimiento crítico** - Detener la secuencia en momentos predefinidos y exigir al usuario señalar o describir los elementos que deben controlarse, registrando aciertos y omisiones.

**==(objetivos funcionales de características de la aplicación)==**  

### Experiencia del jugador y POV

Tras iniciar sesión, el usuario elige la maniobra que desea estudiar y selecciona uno de tres modos de uso:

**Briefing:**
En una sala virtual, se reproduce la maniobra mediante un vídeo externo de la aeronave mientras un narrador explica objetivos y contexto.

**Reproductor en cabina:**
El usuario observa la maniobra desde un punto de vista en primera persona. Los indicadores 3D resaltan los elementos críticos de cada etapa y muestran información contextual.

**Evaluación:**
El sistema detiene la secuencia en momentos clave y pide al usuario identificar, señalar o describir los elementos importantes. Al final presenta retroalimentación sobre aciertos y omisiones.

Esta progresión permite al alumno comprender, observar y finalmente demostrar su conocimiento de cada maniobra dentro de un entorno inmersivo coherente con la cabina real. **(que experimentará el usuario, niveles y mecánicas principales)**

### Estilo visual y de sonido

El arte adoptará un estilo realista, reproduciendo con la mayor fidelidad posible el interior de la cabina. Los elementos de interfaz se integrarán en el espacio 3D como UI espacial, con un diseño moderno y minimalista que no oculte los controles reales. El audio apoyará las acciones del usuario con efectos de retroalimentación claros e incluirá un fondo sonoro ambiental que recree el ruido auténtico de cabina. 

==**(párrafo explicativo  del estilo visual y sonoro, acompañado con 4 imágenes)**==

**Referencias:**

|                                |
|:------------------------------ |
| **Microsoft Flight Simulator** |
| ![[image5.png\|679]]           |
| Vista POV de cabina            |
|                                |
| **Half Life: Alyx**            |
| ![[image4.png\|679]]           |
| Menús espaciales               |
|                                |
| **Aliens: Fireteam**           |
| ![[image6.png]]                |
| Tooltip interactivos           |

## Product Design

### Monetización / Distribución 

El proyecto se comercializará bajo un modelo B2B a medida: se licenciará directamente a organizaciones de entrenamiento aeronáutico que soliciten una versión personalizada. No habrá precio de venta al público ni distribución en tiendas minoristas. 

==**(cómo se vende la App, y cómo se monetiza)**==

### Plataformas, Tecnologías y Alcance

**Plataforma objetivo:** realidad virtual en escritorio (PC + visores VR).

**Motor de desarrollo:** Unreal Engine 5.

**Cronograma y equipo:** 18 meses de producción con un equipo núcleo de 4 personas.

**Duración de la experiencia por maniobra:** Al rededor de 10 minutos.

==**(en qué plataforma se desarrolla, plataforma objetivo, cronograma tentativo de desarrollo, duración aproximada de la experiencia)**==

  

## Detailed & Game Systems Design


### Misiones / Niveles

Cada maniobra es un nivel en sí misma. Además de que cada una tiene 2 subniveles: Briefing y Reproducción. 

==**(Todas los niveles que se experimentan en la App)**==

### Interactividad

Controles VR, Visores VR. 

==**(Que elementos se usan para interactuar con la App)**==

### **Button Mapping**





Las interacciones se harán mediante punteros los cuales harán interacción con los elementos del entorno.

Estos serán indistintamente con la izquierda o derecha, aunque sólo apuntará la que esté activa. Se mantendrá activa el último control que haya sido utilizado.

Para seleccionar y/o arrastrar un elemento, se tendrá que apretar el gatillo (botones 5 y 12) del control correspondiente y mantener presionado durante la interacción.

El botón 4 abrirá el menú.





INCORPORAR OSCURECIMIENTO DE LOS CONTROLES/INDICADORES QUE NO SE ESTAN USANDO ESTO LO ESCRIBO CON MAYUSUCLSAPORQUE ES IMPORTANTE


DCL: DIAGRAMA CUERPO LIBRE: debiera esto estar en el mesón? yo creo que si



Incorporar un nivel(?) de 'conoce la cabina'
Incorpora un nivel (?) de compensación del avión  