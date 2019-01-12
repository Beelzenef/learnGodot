# AudioStreamPlayer

Existen tres nodos relacionados con el audio:

```
____ AudioStreamPlayer
    \__ AudioStreamPlayer2D
    \__ AudioStreamPlayer3D
```

La diferencia entre estos nodos se basa en la información de la posición. El nodo `AudioStreamPlayer` no tiene información sobre la posición, el audio se propaga a partes iguales entre los _speakers_ en el dispositivo. No tiene en cuenta la distancia de la fuente de sonido, sobre el _stereo_ ni nada parecido.

Los dos nodos hijos sí tienen esa información de posición, siendo coherente con el universo 2D o 3D.

Añadir audio es tan sencillo como añadir tantos `AudioStreamPlayer` como sonidos necesites y asociarles un sonido. ¡Cuidado con los ficheros `.ogg`! Puede que, al importar, se marquen como _loop_ de forma automática.

Selecciona el `AudioStreamPlayer`, ve a la pestaña _Import_ y verás que el _loop_ aparece activado. Desmarca la casilla y _Reimport_. El _auto loop_ debería haber desaparecido.

En nuestro juego, [hoppyDays junto a GameDev.tv](https://github.com/KeyWorlds/hoppyDays), hemos añadido una variable por cada SFX en `Global.gd`, para acceder a los sonidos desde cualquier fichero de nuestro proyecto.

Cada SFX tiene asociado un _script_, cuyo único contenido es:

```py
JumpSFX.gd

extends AudioStreamPlayer2D

func _ready():
    Global.JumpSFX = self
```

Cuando llegue el momento de reproducir, simplemente:

```py
Global.JumpSFX.play()
```

---
#### [Volver a inicio](../README.md)
#### ← [Página anterior, animaciones](animationplayer.md)
