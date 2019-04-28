# Nodos y estructura de proyectos

## Explicando los nodos

Un nodo es la unidad básica con la que se opera en Godot. Un nodo puede ser una escena, un objeto con colisiones, el mundo sobre el cual se agrupan los niveles de nuestro juego, un _sprite_...

A través de esta estructura de árboles (o raíces, ya que los nodos cuelgan hacia abajo desde el nodo principal o _top_).

Existen nodos de diferentes tipos, como los que hemos menciondo anteriormente como ejemplos, y que cuentan con diferentes características. Posición, transparencia, colores... que pueden ser modificables. Algunas de estas características o propiedades son relativas al nodo desde el cual cuelga el nodo en cuestión.

Los nodos tienen nombre, tienen sus características, sirven para muchos propósitos. Una vez empieces a manejar tus propios proyectos, es posible que [esta guía en forma de infografía](https://i.imgur.com/JDUcBiE.jpg) te sea útil. ¡No te pierdas entre nodos!

## Escenas

Las escenas pueden ser entendidas como niveles, "pantallas" en nuestros juegos... ¡aunque también zonas de trabajo para objetos! Si estás creando al malvado NPC que va a subir la dificultad del juego, crea una escena individualmente para ese NPC. ¡Y con cualquier elemento que necesites! Personajes, obstáculos, enemigos...

Cuando ejecutas el juego, estás iniciando una escena. Puedes iniciar una escena que es un nivel, para comprobar los progresos del mismo, así como puedes iniciar una escena que es el modelado de tu personaje, para comprobar que funciona tal y como esperas.

### Herencia de escenas

Con el fin de reutilizar código

Una vez has creado tu escena base, ve al menú principal de Godot y selecciona `Scene`. Después, clica en `New Inherited Scene...` y selecciona la escena de la cual quieres heredar.

![New inherited scene...](https://www.gotut.net/wp-content/uploads/2019/01/Screenshot_2019-01-06_11-20-42.png)

Eso nos ahorrará tiempo, código y nos ayudará a organizar mejor nuestro proyecto. Ahora continuaremos con nuestro proyecto inicial, aprendiendo a operar con los nodos escena para organizar y crear nuestro juego.

## Creando un nuevo proyecto

Una vez seleccionamos la creación y nombramos el nuevo proyecto, la interfaz de Godot se presenta así:

![Godot editor](http://docs.godotengine.org/en/stable/_images/empty_editor.png)

En la sección _Scene_ podemos añadir o visualizar los nodos que ya hemos creado.

En la sección _Inspector_, veremos las características, generalmente editables, del elemento que tengamos seleccionado.

En la sección _FileSystem_ estarán todos los ficheros que hemos añadido para nuestro proyecto. _Sprites_, modelos, _scripts_, escenas, ficheros de fuentes... en el que podrás navegar y organizar bien todo lo que tu juego necesite.

En la región principal es donde volcamos los diferentes nodos de forma gráfica, localizando las plataformas, los _sprites_, los botones de nuestra interfaz...

En la parte superior central verás varias pestañas, muy útiles:

* 2D, para navegar a tus escenas 2D.
* 3D, para navegar a tus escenas 3D.
* Scripts, para navegar a tu editor de _scripting_ y gestionar el código.

## Creando nodos

Cuando en la sección de _Scene_ seleccionas _New node_, aparece este cuadro de diálogo. Aquí vemos todos los tipos de nodos que podemos añadir a nuestra escena (con diferenciables iconos incluso), incluso con un buscador integrado:

![Nodes](http://docs.godotengine.org/en/stable/_images/node_classes.png)

Podemos ver los diferentes iconos, nombres... y las diferentes funcionalidades que podemos llegar a tener.

---

### [Volver a inicio](../README.md)

### ← [Página anterior, introducción](intro.md)

### [Siguiente página, _scripting_](scripts.md) →