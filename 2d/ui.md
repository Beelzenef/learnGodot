# Controles UI

Los controles UI hacen una interfaz gráfica para nuestros juegos, con los que introducir texto, pulsar botones, realizar guardados de partida...

Existen muchos, todos ellos nodos que podemos añadir a nuestros juegos:

* `Label`, para mostrar textos
* `TextureRect`, para fondos o cualquier cosa que necesite una imagen estática
* `TextureProgress`, para barras de vida, carga... ya sean horizontales, verticales o circulares
* `NinePatchRect`, paneles escalables
* `TextureButton`, para crear botones

![](http://docs.godotengine.org/en/3.0/_images/five_most_common_nodes.png)

Para leer más sobre ellos, un [enlace a la documentación](http://docs.godotengine.org/en/3.0/getting_started/step_by_step/ui_introduction_to_the_ui_system.html).

También encontrarás otros para introducir texto:

* `RichTextBox`
* `TextBox`

Y cuando necesites interacción desde el otro lado de la pantalla, siempre puedes acudir a:

* `Button`
* `TextureButton`
* `Checkbox`
* `CheckButton`
* `ColorPickerButton`
* `ToolButton`
* `LinkButton`
* `ToolButton`
* `OptionButton`
* `MenuButton`

Para comunicarte con el usuario puedes usar:

* `ConfirmationDialog`
* `FileDialog`
* `PopupDialog`

Basta con que te asomes a la sección de `Control` de añadir nuevos nodos, convenientemente señalados en verde. Todo listo para que construyas tu propio sistema de inventario... o no. [Siempre podemos esperar a que lo desarrollen desde GodotEngine](https://twitter.com/reduzio/status/980433952421838848).

---
#### [Volver a inicio](../README.md)
#### ← [Página anterior, cámaras](cameras.md)
#### [Siguiente página, _inputs_](inputs.md) →