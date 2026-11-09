https://www.canva.com/design/DAGCKuNN5TQ/Kw127k-u7nQS7c1V3uvV6g/view?utm_content=DAGCKuNN5TQ&utm_campaign=designshare&utm_medium=link&utm_source=editor#1



https://thegodotbarn.com/snippets


# Var Creation


```

var variable_name

var variable_name = initial_value

@export var variable_name = start value

@export var variable_name : NodeType

@onready var variable_name = variable
```
  
```
# Var Types ex.

String: “im a StRing, y010”, “12”, ‘lo’

Float: 1.23400, 0.0, 0.09123041

int: 123, 1, 0

bool: false(0, null, false),

true(anything that's not false)

Array: [1,5.2], [’string’], [[],1,true]

Dictionary: {}, {’key’: ‘value’, 1: 2}

Vector2: Vector2(1,2), Vector2(0.1, 3)

```

```
# If Creation

if variable == 12: #if statement

print(‘varible is cooler than 12’)

elif variable > 12: #else if statement

print(‘it aint = but its greater’)

else: #else statement

print(‘nothing above was true’)
```
  

# Func Creation
```
func function_name(): #no parameter

pass

func function_with_param(param_name):

param_name += 1

return param_name #optional
```
  
```
using the function

function_name()

function_with_param(variable)
```
# Example Code

var le_number = 12

if le_number == 12:

le_number += 1

elif le_number > 12:

le_number = 12

le_number = function_name(le_number)

else:

le_number = 13

print(le_number) #should only print 13

func function_name(param):

param += 1

return param

```
# For Loop Creation

for i in for_loop_variable:

print(i)

  

#the i, is a “new” variable created for

every item in for_loop_variable

  

#Arrays are commonly used with for loops

# Operators

a + b #addition

a - b #subtraction

a * b #multiplication

a / b #division

a % b #modulus

a ** b #power


# Assignment

= #var = new_var

-= #var = var - new_var

+= #var = var + new_var

*= #var = var * new_var

/= #var = var / new_var

**= #var = var ** new_var

%= #var = var % new_var
```


# Comparison
```
a == b #equal

a != b #not equal

a < b #less than

a <= b #less than or equal

a > b #greater than

a >= b #greater than or equal
```


# Math
```
sin(angle),cos(angle),tan(angle) #radian

asin(cord), acos(cord), atan(cord)

atan2(cord_y, cord_x) #very useful

clamp(variable, max, min)

floor(variable) #rounds down

max(var1, var2, var3, etc...)

min(var1, var2, var3, etc...)

abs(variable)

round(variable)

sign(variable)

randi()

randf()

randf_range(from, to)

lerp(from, to, weight)

move_toward(from, to, amount)
```


# Vector2D Funcs
```
distance_to(Vector2)

normalized()

length()

limit_length(length)

move_toward(Vector2, delta)
```

# Node2D Funcs
```
move_local_x(variable)

#similar to position += transform.x * variable

refer to graphic

move_local_y(variable)

look_at(Vector2)
```

# Rotation
```
angle_difference(from, to, delta)

rotate_toward(from, to, delta)

lerp_angle(from, to, weight)

rad_to_deg(radian angle)

deg_to_rad(degree angle)

from_angle(angle)

#same as Vector2(cos(angle), sin(angle))

angle()

angle_to(Vector2 to)

angle_to_point(Vector to)

rotated(angle)
```






# Shortcuts

UNIVERSAL
```
ctrl+S #SAVE GAME!!!

f5 #run game

f6 #run current scene

ctrl+z #undo

ctrl+shift+z #redo

ctrl+f1 #scene editor

ctrl+shift+alt+s #saves all
```


# SCENE EDITOR
```
Q #select mode

W #move mode

E #rotate mote

S #scale mode

G #pan mode, or use mm button

ctrl+L #lock node

ctrl+A #create new node
```
  

# CODE EDITOR
```
ctrl+k #line/selection comment

ctrl+f #search

ctrl+left/right arrow key #jump word

tab #indent

shift+tab #un-indent

ctrl+click #open docs
```


# Common Actions

CREATING A NODE
```
node.instantiate()

add_child(node)
```


ACCESS NODES
```
get_parent()

get_node(‘NodeName’) OR $NodeName

get_children(﻿)
```
PAUSING CODE EXAMPLES
```
await get_tree().create_timer(1).timeout

#pauses code for time

await animation_player.animation_finished

#waits for an animation to finish
```
RANDOM TIPS
```
bool = !bool #toggles boolean

Engine.set_time_scale(.1) #slows game
```

# Input
```
if Input.is_action_pressed(‘input’):

if Input.is_action_just_pressed(‘input’):

if Input.is_anything_pressed():

if Input.is_mouse_button_pressed(CONST):

if Input.is_action_just_released(‘input’):
```
# Tween Creation
```
var tween = get_tree().create_tween()

tween.set_ease(ease type) #optional

tween.set_trans(trans type) #optional

tween.tween_property(Node, ‘property’, wanted value, time)
```



