# _Grid-based movement_

En un script que hereda de `KinematicBody2D`

```py
var direction = Vector2()

var speed = 0
const MAX_SPEED = 100

const TOP = Vector2(0, -1)
const RIGHT = Vector2(1, 0)
const LEFT = Vector2(0, 1)
const DOWN = Vector2(-1, 0)
```

Detectar input del _user_:

```cs
func _ready():
    set_fixed_process(true)

func _fixed_process(delta):
    var is_moving = Input.is_action_pressed("move_up")
        or Input.is_action_pressed("move_rigt")
        or Input.is_action_pressed("move_down")
        or Input.is_action_pressed("move_left")

    direction = Vector2()
    if is_moving:
        speed = MAX_SPEED
        if Input.is_action_pressed("move_up"):
            direction = UP
        elif Input.is_action_pressed("move_right"):
            direction = RIGHT
        elif Input.is_action_pressed("move_down"):
            direction = DOWN
        elif Input.is_action_pressed("move_left"):
            direction = LEFT
    else:
        speed = 0

    velocity = speed * direction * delta

    move(velocity)
    pass
```

El orden en el que especificas cada movimiento importa, se mapea la primera coincidiencia y genera una prioridad sobre las teclas pulsadas.


```gd

```