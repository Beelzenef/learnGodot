# Nodos y estructura de proyectos

## ¿Qué es un nodo?

Un nodo es la unidad básica con la que se opera en Godot. Un nodo puede ser una escena, un objeto con colisiones, el mundo sobre el cual se agrupan los niveles de nuestro juego, un _sprite_...

A través de esta estructura de árboles (o raíces, ya que los nodos cuelgan hacia abajo desde el nodo principal o _top_).

Existen nodos de diferentes tipos, como los que hemos menciondo anteriormente como ejemplos, y que cuentan con diferentes características. Posición, transparencia, colores... que pueden ser modificables. Algunas de estas características o propiedades son relativas al nodo desde el cual cuelga el nodo en cuestión.

Los nodos tienen nombre, tienen sus características, sirven para muchos propósitos

## Escenas

Las escenas pueden ser entendidas como niveles, "pantallas" en nuestros juegos. 

Cuando ejecutas el juego, estás iniciando una escena. Así que vamos a operar con los nodos escena para organizar y crear nuestro juego.

## Creando un nuevo proyecto

Una vez seleccionamos la creación y nombramos el nuevo proyecto, la interfaz de Godot se presenta así:

![Godot editor](http://docs.godotengine.org/en/stable/_images/empty_editor.png)

En la sección _Scene_ podemos añadir o visualizar los nodos que ya hemos creado.

En la sección _Inspector_, veremos las características, generalmente editables, del elemento que tengamos seleccionado.

En la región principal es donde volcamos los diferentes nodos de forma gráfica, localizando las plataformas, los _sprites_, los botones de nuestra interfaz...

## ¿Cómo crear un nodo?

Cuando en la sección de _Scene_ seleccionas _New node_, aparece este cuadro de diálogo. Aquí vemos todos los tipos de nodos que podemos añadir a nuestra escena (con diferenciables iconos incluso), incluso con un buscador integrado:

![](http://docs.godotengine.org/en/stable/_images/node_classes.png)

Podemos ver los diferentes iconos, nombres... y las diferentes funcionalidades que podemos llegar a tener.

---
#### :house: [Volver a inicio](../README.md)
#### ← [Página anterior, introducción](intro.md)
#### [Siguiente página, _scripting_](scripts.md) →