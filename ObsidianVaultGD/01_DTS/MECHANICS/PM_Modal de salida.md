# **Descripción**
**Nombre:** Modal de salida
**Resumen:** Modal de salida
# **Contexto**
**Proyecto:** PILOTLAB
**Nivel:** Maniobras
**Escenario:** El usuario está en el menu de maniobras y el modal es el elemento que permite salir de ese nivel
**Problemática:** La interacción actual es invasiva y provoca demasiados mis triggers
**Condiciones:** La interacción debe ser de carácter físico y debe ser gatillada desde un elemento en el nivel
**Ruta de almacenamiento:**
\nasx\ENTRENAMIENTO\09_SOM\99_Modelos\
StaticMeshes\Seleccionadordemaniobras
**Objetivo:** Permitir dejar salir al usuario del nivel de manera clara, sin provocar interacciones accidentales
# **Lógica MODEL**
**Reglas y restricciones:** El elemento que gatilla el modal debe estar presente en el mundo en toda ocasión, pero no siempre activo.

Se propone que el elemento para gatillar el modal se encuentre en la piernera del piloto, para aprovechar elementos que ya están en la escena y el usuario debe revisar constantemente

El modal en si mismo debe tener una confirmación que requiera mantener presionado el botón antes que pase al estado de 'pressed'

**Parámetros configurables:**
-La cantidad de tiempo que requiere el modal para cambiar de estado
-Los colores que posee el modal
**Casos borde o excepcionales:** La mecánica debe estar bloqueada de acuerdo al progreso del usuario
**Casos Negativos:** Los malos usos dependerán principalmente del estado de progresión del usuario. 

En el nivel de maniobras debe activarse después del tutorial correspondiente a ese nivel.
**Criterios de éxito y métricas:** -
# **Interacción CONTROLLER**
**Flujo de interacción:** ![[Pasted image 20260702142153.png]]
**Maquina de estados:** No disponible → Disponible → Hover → Pressing → Pressed

El estado Pressing es el que hace que la barra de avance se complete, cuando se completa el modal puede pasar 'Pressed'
**Inputs y Outputs:** La interacción debería iniciarse mediante una combinación del laser que se rescata para crear el highlight de cada instrumento más un botón del control. 
Una vez desplegado el modal la interacción es física, presionando el botón mismo.
Como respuesta el usuario ve como aparece el modal, y mientras interactúa con él ve como se llena la barra de confirmación se llena
# **Experiencia VIEW**
**Feedback**
**Visual:** El usuario ve claramente la ubicación del trigger, y sus diferentes estados. debe configurarse como un Widget físico, que aparece una vez es llamado por su correspondiente trigger. Visualmente debe poseer al menos un elemento circular que es el que contiene la palabra asociada a la confirmación o cancelación del evento, este elemento redondo debe poseer un circulo de completación que se va llenando en la medida que el usuario mantiene presionado el botón, y cuando es mantenido suficiente tiempo, pasa al estado de 'Pressed'
**Sonoro:** Debe tener un sonido el trigger y el botón mismo, el sonido asociado al circulo de completación debe ir aumentando de volumen o de pitch en la medida que pasa a el estado de 'pressed'
**Háptica:** La respuesta háptica propuesta es consistente con el volumen de la respuesta sonora, pero se propone que sea un pulso que aumente su frecuencia en la medida que avanza el proceso
**Percepción del usuario:** Se espera que el usuario experimente una experiencia fluida, pero sobre todo clara de lo que está ejecutando, sin generar interacciones accidentales
**Referencias**
**Alternativas consideradas:**


![[Checklist.png]]

![[botón modal conf.gif]]
