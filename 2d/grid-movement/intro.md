# _Grid-based movement_

Este fichero contiene los pasos para realizar un juego con movimiento basado en casillas en 2D que creó [GdQuest en sus vídeos](https://youtu.be/BWBD3i00AfM), pero algunas líneas han sido modificadas debido a los cambios implementados en Godot 3.1.

## Cambios encontrados

* [Invalid call. Nonexistent function `set_pos()` in base `Node2D`](https://godotengine.org/qa/23044/how-to-change-other-nodes-position-in-godot-3?show=23046#a23046)
* [Invalid call. Nonexistent function `set_fixed_process()` in base `KinematicBody2D`](https://godotengine.org/qa/19576/nonexistent-function-set_fixed_process-kinematicbody2d?show=19582#a19582)

## Arrancando

### Creando _Player_

En un script que hereda de `KinematicBody2D`:

```cs
extends KinematicBody2D

var direction = Vector2()
var velocity = Vector2()

var speed = 0
const MAX_SPEED = 150

const TOP = Vector2(0, -1)
const RIGHT = Vector2(1, 0)
const DOWN = Vector2(0, 1)
const LEFT = Vector2(-1, 0)
```

Detectar _input_ del _user_:

```cs
func _ready():
	set_physics_process(true)

func _physics_process(delta):
	var is_moving = Input.is_action_pressed("ui_up") or Input.is_action_pressed("ui_right") or Input.is_action_pressed("ui_down") or Input.is_action_pressed("ui_left")

	direction = Vector2()
	if is_moving:
		speed = MAX_SPEED
		if Input.is_action_pressed("ui_up"):
			direction = TOP
		elif Input.is_action_pressed("ui_right"):
			direction = RIGHT
		elif Input.is_action_pressed("ui_down"):
			direction = DOWN
		elif Input.is_action_pressed("ui_left"):
			direction = LEFT
	else:
		speed = 0

	velocity = speed * direction.normalized() * delta

	move_and_collide(velocity)
```

El orden en el que especificas cada movimiento importa, se mapea la primera coincidiencia y genera una prioridad sobre las teclas pulsadas.

### Añadiendo _Grid_

Añadir nuevo nodo, _Grid_, de tipo `TileMap`. El nodo _Player_ será ahora hijo de _Grid_, y comienza la acción.

Crearemos una nueva escena, _Obstacle_, de tipo `Node2D`, que solo contendrá un _sprite_ para denotar su posición.

El nodo _Grid_ es el que gestiona todo lo que se mueve en su interior. Genera aleatoriamente _Obstacles_, comprueba si _Player_ puede moverse en su interior...

```cs
extends TileMap

var tile_size = get_cell_size()
var half_tile_size = tile_size / 2

var grid_size = Vector2(16, 16)
var grid = []

enum ELEMENT_TYPES { PLAYER, OBSTACLE }

onready var obstacle = preload("res://Obstacle.tscn")

func _ready():
	for x in range(grid_size.x):
		grid.append([])
		for y in range(grid_size.y):
			grid[x].append(null)
	
	var positions = []
	for n in range(5):
		var grid_pos = Vector2(randi() % int(grid_size.x), randi() % int(grid_size.y))
		
		if not grid_pos in positions:
			positions.append(grid_pos)
	
	for pos in positions:
		var new_obstacle = obstacle.instance()
		new_obstacle.position = map_to_world(pos) + half_tile_size
		grid[pos.x][pos.y] = ELEMENT_TYPES.OBSTACLE
		add_child(new_obstacle)

func is_cell_empty():
	pass

func update_child_pos(child, new_pos, direction):
	pass
```

```cs

```