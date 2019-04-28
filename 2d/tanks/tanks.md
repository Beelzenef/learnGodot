# onceUponATank

Creando nuestro tanque, con una jerarquía de nodos como se expone:

```py
Tank
    \__ Body
    \__ Turret
        \__ Muzzle
    \__ Timer
    \__ CollisionShape2D
```

## Seleccionando _sprite_

Utilizando gráficos de Kenney2D:

## Movimiento para el tanque

El código, simplificado y en un único _script_, se visualiza así:

```py
extends KinematicBody2D

export (int) var health
export (int) var speed
export (float) var rotation_speed

var velocity = Vector2()
var alive = true

# magic goes here!

func _ready():
    pass

func control(delta):
    var rot_dir = 0
    if Input.is_action_pressed("ui_right"):
        rot_dir += 1
    if Input.is_action_pressed("ui_left"):
        rot_dir -= 1
    rotation += rotation_speed * rot_dir * delta
    velocity = Vector2()
    if Input.is_action_pressed("ui_up"):
        velocity = Vector2(speed, 0).rotated(rotation)
    if Input.is_action_pressed("ui_down"):
        velocity = Vector2(-speed/2, 0).rotated(rotation)

func _physics_process(delta):
    if not alive:
        return
    control(delta)
    move_and_slide(velocity)
```

Si comenzamos a aplicar herencia, cada escena y cada _script_ implementa solo lo que necesita de forma específica. Los valores iniciales para las variables exportadas pueden ser:

| Variable  | Valor  |
|---|---|
|  `health` |  3 |
| `speed`  |  100 |
| `rotation speed`  |  5 |

---

### [Volver a inicio](../../README.md)

### [Siguiente página, apuntando y disparando](aiming.md) →
