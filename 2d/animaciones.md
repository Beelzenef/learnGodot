# Animaciones

Las animaciones son imágenes divididas en _frames_ para simular el movimiento de nuestros personajes, objetos y demás en el juego. En universos 2D, se realizan mediante _sprites_.

Generaremos, dependiendo de las necesidades de nuestro proyecto, tantas animaciones como necesitemos para nuestros personajes:

* _Idle_, para un objeto que no se mueve, permaneciendo estático.
* Movimiento, caminar o correr, si es que puede hacer cualquiera de las dos acciones.
* Salto, si es que puede realizar la acción, con la consecuente caída (si es que existe gravedad en el universo).

Podemos crear una animación en todas las direcciones en las que se mueva nuestro personaje, o bien cambiar el sentido en que la imagen de la animación se muestra:

```py
set_scale(Vector2(X, Y))
set_scale(Vector2(-X, Y))
set_scale(Vector2(X, -Y))
set_scale(Vector2(-X, -Y))
```

---

## [Volver a inicio](../README.md)

## ← [Página anterior, ficheros](ficheros.md)

## [Siguiente página, cámaras](cameras.md) →
