# Operando con ficheros

Godot, en su lenguaje de programación, nos permite también operar con ficheros.

Para operar con un fichero, necesitamos crear una instancia de la Clase File que va a contener nuestras ejecuciones sobre el fichero.

```py
var fichero = File.new()
```

### Leyendo del fichero

Si vamos a leer el texto de un fichero, podemos almacenarlo en una variable, o cualquier otra acción necesaria.

```py
var textoLeido;

fichero.open("rutaFichero", fichero.READ)
textoLeido = fichero.get_as_text()
fichero.close()
```

Se abre el fichero, se recoge el texto y después se cierra el fichero... ¡recogiendo todo lo que se usa! Recuerda usar el modo `READ` cuando abres el fichero, para indicar al sistema qué harás con él al operar.

### Escribiendo en un fichero:

Escribir un fichero puede tomar varias formas. Observa que también se especifica un modo `WRITE` cuando se abre el fichero.

```py
fichero.open("rutaFichero", fichero.WRITE)
fichero.store_string("texto")
fichero.close()
```

Si vamos a obtener el texto de, por ejemplo, una caja de texto o `EditText` como se llaman en la _engine_, el código cambia para ser:

```py
fichero.open("rutaFichero", fichero.WRITE)
fichero.store_string(get_node("edT_NombrePJ").get_text())
fichero.close()
```

Nunca olvides cerrar ficheros para evitar problemas en tu aplicación o videojuego.

### Pero... ¿existe el fichero que buscamos?

Existe un método que devuelve un valor _boolean_, determinando si en la ruta especificada existe o no un fichero. A partir de ese resultado, tomamos acción.

```py
if fichero.file_exists("rutaFichero"):
    leyendoDatosDeFichero()
```

---
#### :house: [Volver a inicio](../README.md)
#### ← [Página anterior, aleatoriedad](random.md)
#### [Siguiente página, animaciones](animaciones.md) →