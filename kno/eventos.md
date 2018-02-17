# Eventos

Los eventos, como su definición dice, son cosas que ocurren en un determinado momento.

Los eventos en una _engine_ son acciones, generalmente producidas por la persona que juega: pulsar una tecla es el evento básico en el desarrollo de videojuegos, y en ellos se basan el progreso del juego.

Estos eventos pueden ser "capturados", expresión que se repite en otros lenguajes y en otros entornos de programación. Por capturar entendemos que, cuando usuario pulsa un botón, el programa lo percibe y actúa en consecuencia.

## ¿Cómo capturar eventos?

Vamos a realizar un sencillo ejemplo en el que podemos poner en práctica alguna de las lecciones aprendidas.

Añadiremos un botón, una etiqueta o _label_ y a cada pulsación del botón, el texto de la etiqueta cambiará.

Para eso vamos a añadir un nodo inicial, y de él colgaremos dos nodos más: tipo _Button_ y tipo _Label_. Del nodo inicial, seleccionamos la opción _Attach or add script_. Es ahí donde sucederá la magia de la programación.

Ahora seleccioanmos el botón, acudimos al inspector y veremos dos pestañas: Inspector, donde podemos editar el botón en su aspecto, y Nodo, donde se encuentran todos los eventos que podemos capturar:

* _Pressed_
* _Down_
* _Released_
* _Mouse enter_
* ...

Podemos detectar que se puede ser tan específico en los eventos, en las acciones, como deseemos. En concreto, seleccionaremos _Pressed_, que será cuando el botón sea pulsado.

Nos ofrece una opción llamada "Conectar", que pulsaremos. La engine en ese momento nos está diciendo "Cuando el botón sea pulsado, ¿qué código quieres ejecutar?". Y es entonces cuando seleccionamos el _script_ creado en el nodo inicial.

Volveremos al _script_, para empezar a programar. Recuerda que si intentas conectar el evento a un nodo sin _script_, saltará un error que no nos permitirá avanzar.

Así que vamos al código, donde inicializamos una variable a 0, y a cada pulsación se aumentará en uno, cambiando el texto del nodo etiqueta.

```py
extends Node

var nVeces = 0

func _ready():
	pass

func _on_btn_Unico_pressed():
	nVeces = nVeces + 1
	get_node("Label").set_text(String(nVeces))
	print("hey")
```

Se nos pedirá que seleccionemos una escena principal, y de momento será la única que tenemos en nuestro proyecto.

De forma sencilla, hemos creado nuestro primer proyecto, nuestra primer código y nuestras primeras acciones con la _engine_.

---
#### [Volver a inicio](../README.md)
#### ← [Página anterior, _scripting_](scripts.md)
#### [Siguiente página, aleatoriedad](random.md) →