# Colisiones

Una colisión se produce cuando dos nodos entran en contacto, en concreto el área definida por sus CollisionShapes (círculos, rectácgulos...).

Las colisiones se pueden producir constantemente, pero podemos detectar algunas de forma concreta con algunos nodos. El nodo _Area2D_ provee funcionalidades para detectar colisiones, y vamos a utilizarlo para el ejemplo.

Pero primero vamos a necesitar identificar de forma concreta el nodo o nodos que va a colisionar, como por ejemplo, el nodo que será nuestro personaje a controlar. Imaginemos un juego en el que hay que coleccionar una serie de objetos de cualquier tipo, y nuestro personaje recorre el escenario para hacerse con ellos.

Seleccionando el nodo principal de nuestro personaje, acudimos a su Inspector, clicando en la pestaña de _Node_.

![](https://steemitimages.com/0x0/https://res.cloudinary.com/hpiynhbhq/image/upload/v1518861926/brivxfm3l7qgdozloy6q.png)

Allí verás un botón llamado "Group". Una vez seleccionado, encontrarás una caja de texto en la que puedes añadir Grupos. Añadiendo un grupo al nodo, como por ejemplo "Player", estamos listos para continuar.

Añadiremos ahora otro nodo a la escena que será nuestro objeto coleccionable. Su tipo será _Area2D_. Cuando tenga su _CollisionShape_ y su _sprite_ asociado, será hora de pasar a la acción con un _script_ adjunto.

Con el nodo de _Area2D_, vuelve a su Inspector, a la pestaña _Node_. Vamos a utilizar las Señales o _Signals_, que son los eventos predefinidos en la _engine_ para personalizar su comportamiento. En las Señales, buscaremos la llamada _"body_entered"_. ¿Sobre qué _script_ vamos a escribir su contenido? Pues nada menos que el que acabamos de crear para este nodo, y veremos código generado automáticamente una vez confirmemos esa ruta.

El código en esa nueva función, probablemente llamada "on_Area2D_body_entered" si no hemos renombrado el nodo, escribiremos el código.

```py
func on_Area2D_body_entered (body):
    if body.is_in_group("Player"):
        print "¡Colisión con nodo jugador!"
    pass
```

El parámetro _body_ no es más que el objeto con el que se produce la colisión. Podría ser cualquier cosa, y es por eso que comprobamos que este pertenece al grupo "Player".

## Destrucción de objetos

Cuando se produce una colisión, es lógico que el collecionable desaparezca de la escena, ¿verdad? Es el momento de destruir objetos gracias a colisiones.

Llamamos al método "queue_free()" que destruye un objeto, en este caso, el propio coleccionable.

```py
func on_Area2D_body_entered (body):
    if body.is_in_group("Player"):
        print "¡Colisión con nodo jugador!"
        queue_free()
    pass
```

Si queremos destruir el objeto jugador, que colisiona con el coleccionable, es tan fácil como agregar:

```py
func on_Area2D_body_entered (body):
    if body.is_in_group("Player"):
        print "¡Colisión con nodo jugador!"
        body.queue_free()
```

Es un código válido para acabar con el personaje jugador si impacta con un enemigo o un proyectil que le hiere.

Por supuesto, _body_ nos permite acceder al nodo del jugador, a todos sus métodos y variables... así pues ¡que comience la diversión!

---
#### [Volver a inicio](../README.md)
#### ← [Página anterior, controles UI](ui.md)