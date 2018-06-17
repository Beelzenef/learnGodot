## Apuntando... ¡fuego!

En el proyecto [onceUponATank](https://github.com/keyWorlds/onceUponATank) estamos creando un juego de tanques, en el que hay una intensa batalla de tanques en el que solo puede quedar un equipo.

Para que nuestros enemigos apunten a nuestro tanque de forma paulatina cuando este esté suficientemente cerca, necesitaremos editar el tanque enemigo. Hasta ahora, nuestra jerarquía de nodos es:

```
EnemyTank
         \__ Body
         \__ Turret
             \__ Muzzle
         \__ Timer
         \__ CollisionShape
```
De la estructura inicial que tenemos, añadiremos un par de nodos. El primero que marcará el área de detección para nuestro tanque. Cuando entre en este área, determinada por un _CollisionShape2D_ circular, empezará a buscar a nuestro tanque para apuntar... y disparar.

```
EnemyTank
         \__ Body
         \__ Turret
             \__ Muzzle
         \__ Timer
         \__ CollisionShape
         \__ DetectionArea
             \__ CollisionShape2D
```

Y modificando el _script_ que tenemos:

```py

# Añadimos estas variables, velocidad de giro de la torre,
# área de detección y objetivo al que apuntar
export (float) var turret_speed
export (float) var detection_radius

var target = null

# Añadimos un par de señales del nodo DetectionArea,
# cuando el objetivo entra  cuando este sale
func _on_DetectionArea_body_entered(body):
	if body.name == "Tank":
		target = body

func _on_DetectionArea_body_exited(body):
	if body == target:
		target = null

# A cada tick del juego, si el target es diferente de null
# comienza a apuntar paulatinamente
func _process(delta):
	if target:
		var target_dir = (target.global_position - global_position).normalized()
		var current_dir = Vector2(1, 0).rotated($Turret.global_rotation)
		$Turret.global_rotation = current_dir.linear_interpolate(target_dir, turret_speed * delta).angle()
```