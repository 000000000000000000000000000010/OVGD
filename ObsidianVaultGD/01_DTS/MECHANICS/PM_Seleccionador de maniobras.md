# **Descripción**
**Nombre**: Seleccionador de Maniobras
**Resumen**: Permite al usuario poder seleccionar entre multiples categorías de maniobras y  maniobras
# **Contexto**
**Proyecto:** PILOTLAB
**Nivel:** Briefing
**Escenario:** El Nivel de Briefing debe permitir 3 grandes secciones: seleccionador de maniobras, previsualización de maniobras y confirmación. Cada una de esas secciones es una cara del mesón donde se encuentra sentado el usuario. Cada vez que el usuario mira a una de esas caras debe poder interactuar solo con esa cara y no con las demás, estableciéndose un flujo lineal de izquierda a derecha
**Problemática:** Los usuario deben poder elegir la maniobra que quieren estudiar, de acuerdo a su particular progresión
**Condiciones:** Como en todos los productos del Proyecto NEWEN, se establece que toda interacción del usuario debe ser física, y no con una UI plana o tradicional. Interacción en XR con controles
**Ruta de almacenamiento:**
\nasx\ENTRENAMIENTO\09_SOM\99_Modelos\StaticMeshes\Seleccionadordemaniobras
**Objetivo**: -Permite seleccionar maniobras
-Interacción física
-Separación entre categorías y maniobras
-Debe alimentarse de la progresión del usuario
# **Lógica MODEL**
**Reglas y restricciones**: El seleccionador siempre tiene que tener al menos una maniobra seleccionada.
La interacción vertical siempre va a cambiar las categorías que el usuario ve y la interacción horizontal cambiará cada maniobra por si sola
La grilla de maniobras debe configurarse como una esfera, de modo que al llegar al final de una sección, pueda continuar con la primera y la interacción sea continua
Para saber que sección del mesón esta activa, se establece la necesidad de incorporar un indicador de avance que se active una vez se realicen algunas interacciones. La selección de maniobras debería ser libre y siempre debe encontrarse activa al menos una maniobra, la liberación de diferentes maniobras debe estar vinculada al sistema de progresión del usuario, por lo que una  vez el usuario se encuentre en la maniobra esperada se iluminará el mesón como 'listo' y 'encenderá' la sección siguiente. De ese modo evitando que se interactúe con secciones del mesón que aun no le corresponden de manera lineal.
**Parámetros configurables**:  cambio de categorías debería tener un poco más de resistencia que el cambio de maniobra
Deben ser las mimas categorías base que aparecen en el manual de procedimientos
**Casos borde o excepcionales**: Debe permitir solo una rotación a la vez. Solo horizontal o solo vertical
Toda este nivel debe permitir interacción con solo una cara del mesón a la vez, por lo tanto no es posible interactuar con el seleccionador de maniobra y la cara de confirmación ni ninguna interacción simultáneamente
**Casos Negativos**: El usuario podría girar entre las diferentes caras del meson, pero el mesón debe obligar el uso lineal y secuencial
Si el usuario se equivoca seleccionando maniobras debe poder volver a la cara anterior del mesón
**Criterios de éxito y métricas**: -El usuario logra navegar a la maniobra que quiere o le corresponde visualizar.
El usuario entiende en qué parte del proceso se encuentra
# **Interacción CONTROLLER**
**Flujo de interacción**:
![[Pasted image 20260626125915.png|525]]

**Maquina de estados**: Activa → explorada
**Inputs y Outputs**: El seleccionador debe contar con 2 inputs, ambos son de interacción mediante grab y mover
La selección de categorías debe funcionar mediante una interacción similar a la de las tragamonedas y la selección de maniobras mediante un timón que rota en paralelo al suelo: la sección de categorías se Rota verticalmente y la sección de maniobras se Rota horizontalmente
Como outputs el usuario ve y escucha el movimiento de la grilla de maniobras
# **Experiencia VIEW**
**Feedback**
**Visual:** el control debe verse como una rueda y una palanca, que rote cuando el usuario tome alguna y rote la grilla de maniobras. Debe tener maniobras y categorías bloqueadas, pero siempre al menos una maniobra desbloqueada
**Sonoro:** debe emitir pequeños sonidos al pasar por cada sección/maniobra. Para las maniobras debería ser 1/3 menos intenso que para las secciones.
**Háptica:** debe emitir hápticas simultáneas con los sonidos, en la misma intensidad
**Percepción del usuario**
**Referencias**
**Alternativas consideradas**:
**Widgets:** Se estima que el uso de widgets en este caso es lo más genérico y la solución de la cual estamos alejándonos
**Otra orientación:** se considera que la orientación seleccionada es la ideal, por la disposición de los ojos en el cuerpo humano; porque permite ver más opciones con una sola mirada, sin necesariamente girar la cabeza y nos permite rescatar gestos de interacción universales
**Grilla expuesta:** entrega demasiada información en una sola mirada y puede resultar abrumador


![[botón modal conf 1.gif]]