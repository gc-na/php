<!--
Meta Description: # Uso de "yield" en PHP: Generadores y Eficiencia en el Manejo de Datos ## Sinopsis El comando `yield` en PHP permite crear generadores, una forma efi...
Meta Keywords: yield, que, función, php, generadores
-->

# Uso de "yield" en PHP: Generadores y Eficiencia en el Manejo de Datos

## Sinopsis
El comando `yield` en PHP permite crear generadores, una forma eficiente de manejar grandes conjuntos de datos sin necesidad de cargar todo en memoria. Esta característica mejora el rendimiento y la eficiencia del código, especialmente en bucles y procesos de iteración.

## Documentación
### Propósito
`yield` se utiliza en funciones para devolver múltiples valores a lo largo del tiempo, permitiendo que la función se convierta en un generador. Esto es útil cuando se necesita iterar sobre una serie de datos sin tener que almacenarlos todos en la memoria al mismo tiempo.

### Uso
Para utilizar `yield`, se define una función como generador utilizando la palabra clave `function`. Dentro de esta función, se emplea `yield` para devolver un valor en cada iteración. Al invocar la función, no se ejecuta completamente; en su lugar, se retorna un objeto iterable que permite realizar la iteración sobre los valores generados.

**Sintaxis básica:**
```php
function nombreGenerador() {
    yield valor1;
    yield valor2;
    // Más valores...
}
```

### Detalles
- Cada vez que se llama a `yield`, se pausa la ejecución de la función y se almacena el estado actual.
- La próxima llamada a la iteración reanuda la ejecución justo después del `yield`.
- Los generadores son más eficientes en memoria en comparación con las funciones que devuelven un array completo, ya que solo generan un valor a la vez.

## Ejemplos

### Ejemplo básico de generador
```php
function contarHasta($numero) {
    for ($i = 1; $i <= $numero; $i++) {
        yield $i;
    }
}

foreach (contarHasta(5) as $numero) {
    echo $numero . PHP_EOL;
}
```
**Salida:**
```
1
2
3
4
5
```

### Ejemplo con claves y valores
```php
function paresYImpares($limite) {
    for ($i = 1; $i <= $limite; $i++) {
        if ($i % 2 == 0) {
            yield 'par' => $i;
        } else {
            yield 'impar' => $i;
        }
    }
}

foreach (paresYImpares(5) as $tipo => $valor) {
    echo "{$tipo}: {$valor}" . PHP_EOL;
}
```
**Salida:**
```
impar: 1
par: 2
impar: 3
par: 4
impar: 5
```

## Explicación
Al utilizar `yield`, es importante tener en cuenta algunos puntos:

- **Estado de la función:** Cada vez que se utiliza `yield`, se guarda el estado actual de la función. Si dentro del generador hay variables que se modifican, su valor se mantendrá entre iteraciones.
- **Memoria:** `yield` es especialmente útil para trabajar con grandes volúmenes de datos, ya que no requiere almacenar todos los resultados en un array, lo que puede llevar a problemas de memoria.
- **Limitaciones:** No se puede usar `yield` en funciones que no son generadores. Si intentas usarlo en una función normal, generará un error.

## Resumen en una línea
`yield` en PHP permite crear generadores que devuelven valores uno a la vez, mejorando la eficiencia en el manejo de grandes conjuntos de datos.