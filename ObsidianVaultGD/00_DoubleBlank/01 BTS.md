LITE:



![[Pasted image 20260724173747.png]]



![[Pasted image 20260724174053.png]]
# **CCC**
Gana más dinero, atendiendo a tus clientes y haciendo que tu jefe se enoje, al mismo tiempo que haces que él también gane más dinero
# **PILARES**

**Economía divertida:** la elección de los ingredientes para preparar los coktels determina la cantidad de propina que recibes y hace enojar al dueño.

**Psicología etílica:** Leer los diálogos que tienen los clientes, reconocerlos y preparar los coktels como a ellos les gustan o como les podría gustar, resulta en ingredientes mas caros, pero muchos mas pedidos y propinas.

**TBD:** mejorar tu personaje? tu casa? interés romántico? ser dueño de u bar?

____

# GAMEPLAY LOOP
Solo puedes hacer cierta cantidad de movimientos por día, por lo que el jugador tiene que elegir muy bien que cosas hacer y qué no, para maximizar su ganancia económica.


## Loop por día:
-Cinemática de intro/narrativa
-Cinemática del nivel mismo
-Tutorial de lo que hay que hacer
-Día de trabajo
-Pantalla de resumen de performance
-Cinemática de final del día

## Día de trabajo
### ESTADO: CUSTOMER_ARRIVAL
Cliente entra
↓
Dialogo
↓
Pedido

### ESTADO: PREPARATION
UI de preparación
↓
Servir X vasos

### ESTADO: EVALUATION
Calcular calidad
↓
Mostrar resultados

### ESTADO: CUSTOMER_EXIT
Dialogo final
↓
Pagar
↓
Actualizar recursos
### Repetir




# ARQUITECTURA
Game
│
├── World
│   ├── Bar
│   ├── CustomerSpawn
│   └── Customer
├── UI
│   ├── DialogueUI
│   ├── PreparationUI
│   ├── ResultsUI
│   └── HUD
└── Managers
	├── GameManager
	├── ResourceManager
	├── OrderManager
	├── CustomerManager
	└── ScoreManager



## SISTEMAS

Sistema                           Responsabilidad

 GameManager → Controla el flujo completo del juego
 CustomerManager → Genera clientes y controla diálogos
 OrderManager → Controla pedidos activos
 ResourceManager → Dinero e ingredientes
 ScoreManager → Calidad y puntajes
 DialogueUI → Conversaciones
 PreparationUI → Minijuego de preparación
 ResultsUI → Resultados de la ronda


## STATE MACHINE
CUSTOMER_ARRIVAL
↓
PREPARATION
↓
EVALUATION
↓
CUSTOMER_EXIT
↓
CUSTOMER_ARRIVAL

## Escenas Principales
Game.tscn
Customer.tscn
BeerGlass.tscn
DialogueUI.tscn
PreparationUI.tscn
ResultsUI.tscn

---

Proyecto: juego Godot 4.7.1 de atención de pedidos de cerveza.

Reglas de colaboración:
- Por cada modificación, entregar el script completo, listo para reemplazar y comentado.
- Agrupar cambios relacionados para minimizar mensajes.
- Usar snake_case en nombres nuevos de archivos, nodos, variables y funciones.
- No definir posición, tamaño, anclas, fuentes ni estilo visual de UI desde código; el usuario lo ajusta en el editor.
- Antes de modificar código existente, pedir el script completo actual si no se tiene certeza de su versión.
- No asumir que cambios sugeridos están aplicados: los scripts que el usuario comparta son la fuente de verdad.

Arquitectura objetivo:

Game
├── World
│   ├── Bar
│   ├── CustomerSpawn
│   ├── Customer
│   └── BeerGlass
├── UI
│   ├── DialogueUI
│   ├── PreparationUI
│   ├── ResultsUI
│   ├── DaySummaryUI
│   └── HUD
├── TimerBar
├── LiquidBar
└── Managers
    ├── GameManager
    ├── OrderManager
    ├── PreparationManager
    ├── customer_manager
    ├── score_manager
    └── resource_manager

Nota de nombres:
- Los nodos existentes originales siguen usando `OrderManager`, `PreparationManager` y `GameManager`.
- Los nuevos nodos se crearon como `customer_manager`, `score_manager` y `resource_manager`.
- No renombrar nodos existentes sin actualizar rutas y verificar el árbol.

Loop por día:

1. INTRO_NARRATIVE
2. LEVEL_CINEMATIC
3. TUTORIAL
4. WORKDAY
5. DAY_SUMMARY
6. DAY_OUTRO
7. GAME_COMPLETE tras el día 5.

Actualmente estas cinemáticas y tutorial se presentan temporalmente con DialogueUI. Después podrán sustituirse por cinemáticas reales sin cambiar la lógica del loop.

Estados durante WORKDAY:

CUSTOMER_ARRIVAL
→ PREPARATION
→ EVALUATION
→ CUSTOMER_EXIT
→ siguiente cliente o resumen del día.

Reglas de juego:
- El juego tiene 5 días por ahora.
- `customers_per_day` es configurable desde GameManager; normalmente 3.
- TimerBar representa la duración total del día, actualmente configurable con valor por defecto de 180 segundos.
- Cuando termina el TimerBar, NO se interrumpe al cliente activo.
- Se permite terminar su pedido, evaluación, despedida y pago.
- Después de ese cliente no entra otro; se muestra DAY_SUMMARY.
- LiquidBar representa la cerveza disponible para todo el día, no el contenido del vaso.
- La cerveza diaria se reinicia al iniciar cada día; el dinero persiste.
- El objetivo ideal es 90% cerveza y 10% espuma.
- Una coincidencia perfecta obtiene puntaje 100 y la propina máxima.
- La propina se calcula linealmente a partir del puntaje final.
- El pago y la propina se procesan tras el diálogo final de CUSTOMER_EXIT.
- El consumo de cerveza se descuenta al cerrar el pedido, no continuamente mientras se sirve.

Sistemas y responsabilidades:
- GameManager: loop de día, estados de clientes, timer, cierre tras 5 días.
- customer_manager: perfiles, llegada, diálogos y salida.
- OrderManager: pedido actual y elección de recursos OrderData.
- PreparationManager: conteo, resultados de vasos y señales de progreso.
- score_manager: evaluación, puntajes y propina.
- resource_manager: dinero, cerveza diaria, pago y consumo.
- BeerGlass: interacción del vaso; no controla puntajes ni estados globales.
- DialogueUI: diálogos.
- PreparationUI: pedido y progreso.
- ResultsUI: evaluación individual de vasos.
- DaySummaryUI: resumen diario.
- HUD: dinero y cerveza.

Grupos usados para evitar rutas rígidas:
- BeerGlass se añade a `beer_glass`.
- PreparationManager se añade a `preparation_manager`.
- resource_manager se añade a `resource_manager`.
- TimerBar se añade a `timer_bar`.
- Customer puede añadirse a `customer`.
- Los scripts suelen usar grupos o búsqueda diferida (`call_deferred`) para conexiones.

Estructura necesaria de UI:

UI/PreparationUI/PreparationPanel/
  DrinkLabel
  QuantityLabel
  ProgressLabel
  FinishButton

UI/ResultsUI/ResultsPanel/
  TitleLabel
  FinalScoreLabel
  ResultTextLabel
  DetailsLabel
  ContinueButton

UI/DaySummaryUI/SummaryPanel/
  DayLabel
  CustomersLabel
  AverageScoreLabel
  EarningsLabel
  ContinueButton

UI/HUD/
  MoneyLabel
  BeerStockLabel

TimerBar/
  ProgressBar
  Timer (opcional; timer_bar.gd lo crea automáticamente si no existe)

LiquidBar/
  ProgressBar

Estado de scripts y comportamiento implementado:

1. OrderData.gd
- Tiene: drink_name, drink_type, quantity, target_liquid, target_foam, payment_per_glass, max_tip_per_glass y beer_cost_per_glass.
- Valores ideales actuales: target_liquid = 0.9, target_foam = 0.1.
- Los recursos .tres antiguos deben actualizarse manualmente a 0.9 / 0.1 y configurar max_tip_per_glass.

2. OrderManager.gd
- Tiene `current_order`.
- Usa `available_orders: Array[OrderData]`.
- Recorre pedidos configurados en orden.
- Si no hay recursos configurados, crea un pedido de respaldo.

3. customer_data.gd
- Extiende Resource.
- Tiene customer_name, arrival_dialogue y exit_dialogue.
- Se crean recursos .tres para perfiles de clientes.
- customer_manager usa `customer_profiles: Array[Resource]` y los recorre en orden.
- Si no hay perfiles, mantiene el cliente configurado en la escena.

4. Customer.gd
- Tiene customer_name, arrival_dialogue, exit_dialogue.
- Tiene señal `customer_exit_completed`.
- Tiene `apply_customer_data(data)`.
- customer_manager localiza Customer mediante grupo o búsqueda recursiva, ya que hubo errores con rutas rígidas.

5. PreparationManager.gd
- Tiene señales:
  - preparation_started(order)
  - glass_completed(completed_glasses, total_glasses)
  - preparation_completed(results)
- Mantiene total_glasses, completed_glasses, is_preparing, current_order y glass_results.
- Añade el grupo `preparation_manager`.

6. PreparationUI
- Escucha PreparationManager.
- Muestra pedido y progreso.
- Se oculta al completar el pedido.
- No tiene layout por código.

7. BeerGlass.gd
- Tiene señales:
  - glass_selected
  - glass_fill_changed(liquid_amount, foam_amount)
  - glass_completed(liquid_amount, foam_amount)
- Clic izquierdo sobre el vaso: selección.
- Clic izquierdo sostenido: añade cerveza.
- Clic derecho sostenido: añade espuma.
- Solo funciona durante PREPARATION.
- Ya NO entrega el vaso automáticamente al llenarse.
- `complete_glass()` entrega el vaso manualmente.
- `reset_for_next_glass()` limpia el vaso.
- `glass_fill_changed` todavía no está conectado a LiquidSystem visual.

8. finish_button.gd
- Debe estar asignado a `PreparationUI/PreparationPanel/FinishButton`.
- Al pulsarlo, busca BeerGlass por el grupo `beer_glass` y llama `beer_glass.complete_glass()`.
- FinishButton aún debe verificarse en juego tras crear el nodo y asignar el script.

9. score_manager.gd
- Calcula calidad individual y final.
- Usa la diferencia frente a los objetivos del pedido.
- La evaluación incluye:
  - glass_scores
  - final_score
  - tip_amount
  - result_text
- Propina máxima = max_tip_per_glass × cantidad de vasos.
- Con score 100 se recibe el máximo.

10. resource_manager.gd
- Tiene money, max_daily_beer_stock y beer_stock.
- `start_new_day()` restablece beer_stock; money no cambia.
- `complete_order(order, evaluation)` suma pago base + propina y descuenta cerveza.
- Emite `resources_changed(money, beer_stock)`.
- LiquidBar y HUD escuchan esta señal.

11. LiquidBar
- Es solo visual de recurso diario.
- Ya no debe responder a `use_liquid`.
- Escucha resource_manager.resources_changed.
- Necesita ProgressBar hijo.
- Emite liquid_empty al llegar a cero.

12. TimerBar
- Es temporizador total del día.
- Necesita ProgressBar hijo.
- Timer es opcional: el script lo crea si falta.
- Tiene start_timer(), stop_timer(), pause_timer(), reset_timer().
- Emite timer_completed.
- Se modificó para tolerar que GameManager llame reset_timer() antes de TimerBar._ready().

13. ResultsUI
- Muestra puntaje total, resultado y detalle de vasos.
- ContinueButton emite results_closed.
- No tiene posiciones, tamaños ni estilos definidos desde código.
- GameManager espera esta ruta exacta: UI/ResultsUI.

14. DaySummaryUI
- Muestra número del día, clientes atendidos, puntaje promedio y ganancias.
- ContinueButton emite summary_closed.
- No tiene layout por código.
- GameManager espera esta ruta exacta: UI/DaySummaryUI.

15. HUD
- Muestra dinero y cerveza.
- Escucha resource_manager.resources_changed.
- No tiene layout por código.

16. GameManager
- Controla DayState y GameState.
- Al iniciar un día:
  - reinicia contadores diarios;
  - llama resource_manager.start_new_day();
  - llama timer_bar.reset_timer();
  - muestra narrativa, presentación y tutorial.
- En WORKDAY inicia TimerBar.
- Al recibir timer_completed establece una bandera de cierre, pero no corta al cliente actual.
- Tras la salida de un cliente:
  - si se acabó el tiempo, abre resumen diario;
  - si se atendieron customers_per_day, abre resumen;
  - si no, llega otro cliente.
- Tras cerrar DaySummaryUI muestra DAY_OUTRO.
- Tras cerrar DAY_OUTRO:
  - si es día 5, entra en GAME_COMPLETE;
  - si no, incrementa el día e inicia otro.
- GameManager depende de que existan BeerGlass, TimerBar, ResultsUI, DaySummaryUI, customer_manager, score_manager y resource_manager.

Pendientes recomendados, en orden:
1. Verificar FinishButton: crear el nodo dentro de PreparationPanel, asignarle finish_button.gd y probar entrega manual.
2. Implementar LiquidSystem visual: conectar BeerGlass.glass_fill_changed para que el vaso represente cerveza y espuma.
3. Crear CustomerSpawn y mover CustomerManager de “reutilizar nodo Customer” a instanciar Customer.tscn real.
4. Definir qué sucede si falta cerveza antes de un pedido; hoy se muestra un diálogo, pero no existe aún un sistema de compra/reabastecimiento.
5. Crear un sistema de cinemáticas/narrativa real para reemplazar los diálogos temporales.
6. Añadir una pantalla visual definitiva para GAME_COMPLETE.
7. Agregar semanas y persistencia de progreso después de validar los cinco días.

Errores ya encontrados y cómo diagnosticarlos:
- “Could not find type ScoreManager”: usar referencias sin tipos personalizados o confirmar que el script correcto está asignado.
- “Unexpected extends in class body”: se pegó código debajo de código anterior; borrar archivo completo y reemplazar.
- “No se encontró X dentro de UI”: existe el script, pero falta crear/instanciar el nodo con ese nombre exacto en Game.tscn.
- “Cannot call method stop on null”: TimerBar fue llamado antes de inicializar; la versión actual de timer_bar.gd usa ensure_components().
- Si una UI no avanza, verificar primero que exista su botón, nodo, script y nombres exactos.

Al continuar:
- Primero solicita los scripts actuales involucrados en el siguiente cambio.
- Mantén las decisiones de arquitectura anteriores.
- No volver a implementar layout de UI por código.
---







# WIN/LOSE STATES
Cada día debe terminar con 1 de 2 estados:
## -Ganar suficiente dinero
Se logra dando un mejor servicio, lo que lleva a menos propinas

## -No ganar suficiente dinero
Se logra siguiendo solo las instrucciones del dueño

___

# **4 o 3 ESTACIONES**
## Lavado de loza
**-Lavado a mano**
Graffiti a lo JSR Circular
(rápido y efectivo)

**-Lavado de máquinas / utensilios**
Graffiti a lo JSR Recto
(es crítico para el funcionamiento del bar)

**-Lavado con máquina**
Fallguys + Megaton Punch
Para ingresar las cosas a la maquina hay que esquivar las aspas  y llenar precisamente el detergente. Sino: se rebalsa la maquina o te demoras mucho más en poner las cosas dentro

Ingresar a la máquina
(lento y pero súper efectivo, mayor cooldowns)

__
**-Guardado/secado**
Puzzle de orden, equilibrio
(negociación con los demás bartender/dueño)

**-Cambio de radio / tv**
Megaton punch de Kirby,
(queda lejos de los demás puestos y podría tener un gran impacto en el ambiente del bar)

## Cerveza y piscolas

**Organizar los pedidos**
Tetris horizontal o Yoshi
1.- disponer de los vasos en orden correcto 
(vasos frios de chela vasos con hielo para piscola)


**-Tipo de licor**
Selector
(Es lo que más afecta al dueño)

**-Ángulo de servido**
Péndulo temporal
(Balancín que se mueve y se debe mantener presionado en un ritmo determinado por la botella, vaso. Es distinto en cerveza y en bebida)



__
**-Tipo de bebida**
Selector

**-Velocidad**
Sube la espuma de la cerveza y bebida, similar al megaton punch

(El inicio de la preparación parte con el sonido de agregar hielo al vaso o de aire presurizado para la cerveza)

## Cócteles

**-Tipo de alcohol**
Selector
(Es lo que más afecta al dueño)

**-Tipo de jugo/bebida**
Selector y extraer

**-Agitar**
Graffiti a lo JSR Circular o recto

**-Tipo de copa**
Selector, depende de la disponibilidad



__

**-Tipo de garnish**
Seleccionar + preparar + servir

**-Tipo de hielo**
Selector + picador cortar hielo

## Cócteles de autor
**Tipo de hielo**
**Tipo de alcohol**
**Tipo de jugo/bebida**
**Tipo de copa**
**Tipo de garnish**

(Quizás cambiar el hielo por estilo/tiempo/ángulo)
Sumar posavaso, servilletas, aceituna, charola.



# NARRATIVA
Despiertas después 1 night stand, mientras la persona con la que estabas se está yendo.

Te quedas dormido.

Recuerdas que tienes que ir a una entrevista de trabajo y corres por llegar a tiempo
Cuando llegas al local te encuentras con (el dueño que ya está enojado) o (con el otro Barman, que saluda alguien a lo lejos) y te da la bienvenida y te explica que, se fueron 2 de los barman y pusieron su propio bar, tu estás llegado a trabajar de barman porque ya lo has hecho, pero no te ofrecen buena plata y por ahora te van a probar de copero primero, el dueño se dedicará a los cócteles el primer día hasta que llegue el copero definitivo (si lo haces bien) el otro barman es muy buena onda y se queda por los regulares.

Tu misión es sacar los mejores ingresos y crear el mejor ambiente entre los barman, sin importar lo que diga el dueño, porque eso va a determinar si al bar y a ti te va bien.

Si lo haces bien el primer día, para el segundo día: el dueño solo ronda, el otro barman pasa a los cócteles, tu pasas a las cervezas y piscolas y llega alguien nuevo al puesto de copero.

El otro barman te va a dar tips sobre los regulares y tu te vas a dar cuenta que el nuevo es rápido si lo organizas bien.



# **RECURSOS DE DESARROLLO**

## Referencias:
SPILLED!
Dave the diver
Sprint City: 
---

last round!!
tienes 3 minutos para vender la mayor cantidad de cerveza 
push to lift
Diferentes botellas con diferentes pesos
Lo principal es intentar dejar a los clientes felices, enojando al dueño, llenándote los bolsillos

https://www.youtube.com/@ClearCode/videos
https://www.youtube.com/watch?v=K_mZeYLYpgg

https://www.youtube.com/@uheartbeast

https://www.youtube.com/@Brackeys
Dialog in visual novel:
https://www.youtube.com/watch?v=oN5VTIZjyb0

https://www.youtube.com/watch?v=5Hog6a0EYa0

https://www.youtube.com/watch?v=z6sUvOBYpT4


PixelArt in blender:

https://www.youtube.com/watch?v=PBIPJdEECWg

Assets:

https://www.youtube.com/watch?v=lGC0CvUoFYI


Stylized Low poly
https://www.youtube.com/watch?v=_aJzFbuLi1M

# **DUMP**
-mixing ingredients create new beverages and customers talk to you differently
-Poder dominar el ambiente para manipular a los regulares. Siempre debe afectar tanto a los clientes como al dueño, de manera relacional o no.
-Los barman deben ser los psicólogos de los regular.
-Manejar los diálogos para sacar info
-Quizás tener novia, que sea una femme fatal, quizá
-Aprender los tragos que le gustan a los regulares.
-La presencia o no de algún ingrediente debe afectar tu interacción con los clientes. (Por ejemplo si no hay limón, se debería poder negociar con el cliente para prepararle algo distinto con los ingredientes que si hay)
-Manejar la economía de hacer felices a los regulares (sirviendo les dobles, o triples) vs el enojo de tu jefe por gastar mucho copete. Puedes pagar por servir demás, o romper cosas.    -Lo que podrías cubrir con las propinas extras que te dan los regulares por servirles extra.
-Que el efecto ‘destacado’ sea un borde de línea como si fuera papel animado
~~-5 niveles de acciones con diferentes costos y cooldowns.~~
-La música y la tv funciona como multiplicador a los regulares y al dueño
-Acumulador de comandas/pedidos, y de loza sucia
-Cerrar día con cuenta de propinas, bonus, números teléfonicos, tarjetas etc. Y una viñeta de algún hecho importante del día.
-Definir puntos de error: copa equivocada, receta equivocada, mucha espuma, corte de ingredientes equivocado, tiempo de preparación.
-Libro de recetas, resta o suma puntos, dependiendo de si mejora o no la receta, o si debería saberse la receta.
-Se trabaja de martes a sábado, se empieza con una viñeta de tu hablando con el dueño, citándote para el otro día temprano. Tu debes despertar con un Quicktime event, que va a determinar si llegas a temprano o no. Si llegas temprano el otro barman te va a recibir y te va a ayudar a empezar. En tu preparación matutina vas a ejecutar el tutorial de todas las mecánicas de preparación de tragos, preparando el desayuno
-Dependiendo del tipo de borrachera provocada al cliente: deberá tener una diferente reacción o comportamiento
-El tipo de vaso determina si cabe o no el trago a servir
-Entre más caro el trago, más pasos y mayor tiempo de preparación
____

