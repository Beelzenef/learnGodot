# GodotCon Poznan 2019

## Vídeos

* [GodotCon Poznań 2019 – Livestream Wed 16 Oct](https://youtu.be/cSn8jeheG0E)
* [GodotCon Poznań 2019 – Livestream Thur 17 Oct](https://www.youtube.com/watch?v=I2OW-kx3u_4)

## Charlas

### _Coding styleguide in Godot_

Para ficheros de _scripts_, deberíamos seguir el siguiente orden de sus elementos:

* Comentario para nombre de fichero
* Herencia si existe
* Nombre de clase
* `docstring`
* _Signals_
* Variables `onready`
* `export`s
* `enum`s
* Constantes
* Variables públicas
* Variables privadas
* Código _built-in_
* _Callbacks_ para _signals_
* Otros métodos _built-in_
* Métodos públicos
* Métodos privados

Y esta es la estructura aconsejable de directorios para organizar nuestros recursos:

```yaml
root
    \_ assets
            \_ art
            \_ fonts
    \_ src
        \_ autoload
        \_ HUD
```

Por supuesto, puedes tener tu propia convención siempre que la cumplas.

También es buena práctica gestionar los eventos desde un _singleton_, desde el cual tener métodos para hacer `connect` y `emit_signal` desde cualquier _script_... y así gestionarlos de forma unificada.

Como dicta el código limpo, escribe métodos pequeños. Facilitarás su mantenimiento y legibilidad.

El autor de esta charla es programador funcional, por lo que recomienda aprovechar al máximo los principios de la programación funcional.

### _Game programming patterns_

Un buen diseño de nuestro proyecto es (o debería ser):

* Mantenible
* Extensible
* Modular
* Con alta cohesión
* Con bajo acoplamiento
* SOLID
* Aplica patrones de programación

Escribe código limpio y no hagas sobreingeniería. No hay _silver bullets_ para el _gamedev_ solo mucha práctica.

Utiliza la herencia para no duplicar código y _singletons_ para los siguientes casos:

* Level Manager
* Audio Manager
* Time Manager
* Dialogue Manger
* Activity Manager

Puedes seguir también el patrón _façade_.

Recuerda que estos son consejos, no reglas a seguir a rajatabla.
