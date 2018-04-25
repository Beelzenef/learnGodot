# _Inputs_

Pulsando teclas:

```py
if Input.is_action_pressed("ui_left"):
	// Acción de pulsar a la izquierda
```

## Movimiento con _mouse_

Obtener posición absoluta del ratón, para utilizarla con un nodo específico:

```py
var posMouse = get_global_mouse_pos()
set_pos(posMouse)
```

## Movimiento con cruceta

Movimiento 2D a través de un Vector2, a velocidad 50, gestionando movimiento en los ejes X e Y.

```py

var movimiento
var velocidad

func _ready():
	movimiento = Vector2()
	velocidad = 50
	
	set_physics_process(true)
	
	pass

func _physics_process(delta):
	
	if Input.is_action_pressed("ui_left"):
		movimiento.x = -velocidad
	elif Input.is_action_pressed("ui_right"):
		movimiento.x = velocidad
	elif Input.is_action_pressed("ui_up"):
		movimiento.y = -velocidad
	elif Input.is_action_pressed("ui_down"):
		movimiento.y = velocidad
	else:
		movimiento.x = 0
		movimiento.y = 0

	move_and_slide(movimiento)
	
	pass
```py

---
#### [Volver a inicio](../README.md)
#### ← [Página anterior, controles UI](ui.md)
#### [Siguiente página, colisiones](colisiones.md) →
