# _Scripting_

GDScript es el lenguaje oficial de _scripting_ para Godot _engine_, y que vamos a conocer a grandes rasgos aquí. Siempre podéis consultar [la documentación oficial](http://docs.godotengine.org/en/stable/learning/scripting/gdscript/gdscript_basics.html) para resolver vuestras dudas.

¡Empezamos!

## Variables

Como lenguaje de programación no tipado, las variables se declaran únicamente con una palabra clave y el nombre de la variable en cuestión:

```py
var nombrePersonaje = "Nombre aleatorio"
```

A partir de ahora podemos acceder a esa variable y a su contenido, para consultarlo o para cambiarlo en el futuro si es necesario.

Contamos con estos tipos de datos:

* Números enteros
* Números con decimales
* Cadenas de texto
* _Booleans_
* Arrays
* Diccionarios

Los arrays son listas de datos de diferentes tipos, que podemos recorrer, consultar en qué posiciones, cambiar sus valores... y se declaran de la siguiente forma:

```py
var listaDatos = ["Godot", 34, 13.4, true, "otro dato", 3]
``` 

Los diccionarios son más complejos, pero en resumidas cuentas es una lista de pares clave-valor. En todas sus posiciones, encuentras una clave o identificador, asociado a un valor. Se declaran:

```py
var datosPersonaje = { "nombre" : "Abraxas", "salud" : 20, "mana" : 45 }
```

Así podremos acceder a los diferentes valores, como el nombre, la salud o el maná... a través de esos mismos nombres, que serán sus claves. De forma sencilla, aunque no la más óptima, hemos creado unas estadísticas de personaje para nuestras aventuras.

En el futuro conoceremos otros muchos tipos de datos más complejos, pero que no resultan necesarios ahora.

También podemos declarar constantes, nombres para valores que no cambiarán nunca durante la ejecución de nuestro 

```py
const numeroPI = 3.1416
```

## Funciones

Las funciones son fragmentos de código que puede ser invocados para su ejecución. Reciben parámetros y pueden devolver valores.

Una declaración de una función sencilla puede ser, sin parámetros y devolviendo un número entero:

```gd
func unaFuncion():
	return 0
```

Existe una función principal, llamada `_ready`, que se ejecuta cuando un nodo y todos sus hijos entran en la escena activa. Es como si el nodo "despertase" y ejecutase su código.

```gd
func _ready():
	# Tu código viene aquí :D
```

Entonces, una vez tenemos nuestros nodos con su respectivo código, podríamos iniciar el juego de esta forma

```gd
func _ready():
	inicioJuego()
	nombrarPersonaje()
	saludarAPersonaje(nombre)
```

## Estructuras condicionales

Las estructuras condicionales, básicas y eternas para los lenguajes, se formulan de la siguiente forma:

```py
if 1 > 2:
	print("Primer camino")
elif 2 > 3:
	print("Segundo camino")
else:
	print("Último camino")
```

## Bucles

### Bucle `WHILE`:

Este bucle se ejecuta mientras la condición expuesta en su declaración sea cierta. Si se rompe, saldrá del bucle.

```py
while (true):
	print("¡Bucle infinito!")
```

### Bucle `FOR`:

Este bucle tiene un componente numérico, donde se espera que empiece en un valor inicial y finalice en el final, aumentando a cada vuelta en un número que también puede ser especificado.

Para empezar, un simple bucle que viaja desde 0 a 10:

```py
for i in range(10):
	print i
```

Este será un bucle que avance desde 1 a 10, aumentando en uno a cada vuelta de bucle. Similar al anterior, pero especificando en qué valor se inicia el bucle.

```py
for i in range(1, 10):
	print i
```

Ahora un bucle `FOR` que avance desde 4 a 20, aumentando en 2 a cada vuelta de bucle:

```py
for i in range(4, 20, 2):
	print i
```

Y también es posible que ocurra a la inversa, empezando en 10 hasta 0:

```py
for i in range(10, 0, 2):
	print i
```

### Bucle `FOREACH`:

Este tipo de bucle está orientado a listas de datos, como los _arrays_, pero sin tener en cuenta sus posiciones. Un ejemplo de su declaración:

```py
for item in listaDatos:
	print(item)
```

## Programación Orientada a Objetos

Próximamente...

## Nodos y la programación

¿Por qué hace falta programar en esta _engine_? ¿Por qué aprender su lenguaje de programación? Los nodos no tienen funcionamiento propio más allá del que se le ha definido por tipo. Un nodo de caja de texto o `EditText` está preparado para recibir el texto que introduzcamos por teclado, pero nada más aparte de eso.

Como bien aparece en la documentación oficial de Godot, un nodo es...

![La verdad sobre los nodos](http://docs.godotengine.org/en/stable/_images/brainslug.jpg)

Si queremos que operen de forma diferente, que proyecten animaciones en movimiento, que se guarde nuestra partida... es necesario inculcarles un código a ejecutar para lograr los efectos deseados.

## Herencia de _scripts_

En ocasiones, para evitar la duplicación de código, necesitaremos hacer uso de la herencia de _scripts_. Crearemos desde la _tab_ de _scripting_ un nuevo _script_, que no asociaremos a ningún nodo, no tendrá _attachs_.

En lugar de aparecer con la herencia básica en nuestro nuevo script, para asociar a un nodo concreto:

```gd
extends KinematicBody2D
```

Elegiremos que tenga con una herencia más concreta:

```gd
extends "res://scripts/ScriptComun.gd"
```

Ahora podremos usar las variables definidas en el primer _script_, y sobreescribir sus métodos. Esto último no requiere ninguna indicación especial, solo utilizar el mismo nombre y crear el código que necesitemos.

```gd
func metodoSobreescrito():
	print "¡Soy un método sobreescrito!"
```

## Variables para el IDE

Es posible en Godot crear variables a las que puedes acceder desde el IDE, para asociarle un valor determinado. Es más cómodo y ofrece más velocidad a la hora de ajustar valores necesarios a un nodo, mucho mejor opción que modificar el código constantemente.

Para crear variables accesibles, con un tipo asociado, escribiremos en nuestros _scripts_:

```gd
export (int) var speed
export (float) var rotation_speed
export (int) var health
```

Ahora prueba a asignar valores hasta encontrar el deseado.

---
#### [Volver a inicio](../README.md)
#### ← [Página anterior, nodos](nodos.md)
#### [Siguiente página, eventos](eventos.md) →