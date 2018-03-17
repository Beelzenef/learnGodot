# Cámaras

Las cámaras son las que nos permiten visualizar el juego. Tenemos una cámara inicial que viene por defecto en cada proyecto, en cada escena, y que será la visión global.

Pero podemos añadir una nueva cámara para una visión local, centrada quizás en el movimiento del personaje. Sus dimensiones serán menores, con márgenes en cada lado para que el movimiento sea fluido. Y para que siga al personaje:

```py
func _ready():
	set_process(true)

func _process(delta):
	set_pos(get_node(../player).get_pos())
```

---
#### [Volver a inicio](../README.md)
#### ← [Página anterior, animaciones](animaciones.md)
#### [Siguiente página, controles UI](ui.md) →