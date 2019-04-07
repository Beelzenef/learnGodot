# Seleccionando nodos

## Recoge un nodo

Mientras navegas por scripts, es posible que necesites referenciarlo para invocar los métodos que tenga en su _script_ asociado. Cuando lo necesites, escribe:

```py
var nodo = get_node("ruta/nodoACoger")
```

La ruta del nodo se basa en la jerarquía de nodos que exista en la escena. Esta puede variar o ser muy compleja, así que estructurala y ordénala convenientemente.

¿Y si quiero eliminar un nodo? El método se basa en la liberación de memoria, así que "liberamos" esa memoria que está ocupando el nodo en cuestión... y desaparecerá. Los nodos son volátiles, algunos pueden desaparecer y reconstruirse constatemente y otros serán perennes, pero no temas eliminar nodos.

```py
get_node("ruta/nodo").queue_free()
```

## Selecciona un nodo _in-game_:

En ocasiones necesitarás seleccionar un nodo. Quizás necesites identificarlo, ver su información, ir hacia él, que este se mueva hacia donde desees... ¿pero cómo hacerlo?

Creando un `KinematicBody2D`, asociarás al mismo una `CollisionShape2D` con su respectiva _shape_. Añadirás un _sprite_ para poder visualizarlo, e incluso otro más como una caja de selección, dependiendo de cuantas veces hagas _click_ sobre el nodo.

En la `CollisionShape2D` tienes que buscar entonces la propiedad `Pickable`, y activarla. Sin esta propiedad, no habrá forma de que la operación funcione. Una vez activada, debemos buscar la `signal _input_event`, que enlazaremos al _script_ del `KinematicBody2D`.

Entonces llega la hora del código:

```py
func _input_event(viewport, event, shape_idx):
    if event.type == InputEvent.MOUSE_BUTTON and event.button_index == BUTTON_LEFT and event.pressed:
        print("Click!")
```

Si llega un evento, es un evento del ratón, es el botón izquierdo del ratón y ha sido pulsado, entonces ¡realiza la magia!

Las condiciones pueden simplificarse o elegir otras, pudiendo ser otro botón.

---
#### [Volver a inicio](../README.md)
#### ← [Página anterior, importación de escenas y nodos](import.md)
#### [Página siguiente, `AnimationPlayer`](animationplayer.md)  →
