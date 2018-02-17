# Aleatoriedad

Los valores aleatorios pueden ser muy valiosos en nuestros proyectos.

### Generando aleatoriedad

Para generarlos, tenemos un sencillo método que genera un número aleatorio entre un mínimo y un máximo establecido.

```py
var minimo = 1;
var maximo = 6;

var numero = rand_range(minimo, maximo)
```

Para redondear el resultado obtenido:

```py
var otroNumero = round(rand_range(minimo, maximo))
```

### Semillas

Los números aleatorios se generan a través de una semilla o _seed_. Por lo que, si necesitamos una nueva semilla para generar aleatoriedad, basta con llamar a:

```py
randomize()
```

Si queremos generar una semilla a través de un número propio, ¡también es posible!

```py
rand_seed(numeroBase)
```

---
#### [Volver a inicio](../README.md)
#### ← [Página anterior, eventos](eventos.md)
#### [Siguiente página, ficheros](ficheros.md) →
