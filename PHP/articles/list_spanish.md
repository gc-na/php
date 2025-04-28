<!--
Meta Description: # Listas en PHP: Uso y Ejemplos Prácticos ## Sinopsis En PHP, la función `list()` permite asignar valores de un array a variables individuales de form...
Meta Keywords: array, list, variables, php, valores
-->

# Listas en PHP: Uso y Ejemplos Prácticos

## Sinopsis
En PHP, la función `list()` permite asignar valores de un array a variables individuales de forma sencilla y efectiva. Esta característica es especialmente útil cuando se trabaja con arrays indexados.

## Documentación
La función `list()` es utilizada para asignar una serie de variables a los valores de un array. Se debe utilizar sólo con arrays indexados, es decir, aquellos que tienen índices numéricos. La función `list()` toma los valores del array en el orden en que están definidos y los asigna a las variables en el mismo orden.

### Propósito
El propósito principal de `list()` es permitir la asignación múltiple de variables desde un array, facilitando así la manipulación de datos.

### Uso
La sintaxis básica de la función es la siguiente:

```php
list($var1, $var2, $var3, ...) = $array;
```

Donde `$var1`, `$var2`, `$var3`, etc., son las variables a las que se les asignarán los valores del array `$array`.

### Detalles
- `list()` solo funciona con arrays que tienen índices numéricos.
- No se puede usar con arrays asociativos.
- Los índices de las variables en `list()` comienzan desde cero.
- La función puede ser utilizada en combinación con otras funciones como `explode()` o `array()`.

## Ejemplos
Aquí se presentan algunos ejemplos de uso de la función `list()` en PHP:

### Ejemplo 1: Asignación básica
```php
$array = array("rojo", "verde", "azul");
list($color1, $color2, $color3) = $array;

echo $color1; // Salida: rojo
echo $color2; // Salida: verde
echo $color3; // Salida: azul
```

### Ejemplo 2: Uso con `explode()`
```php
$string = "manzana,banana,naranja";
$array = explode(",", $string);
list($fruta1, $fruta2, $fruta3) = $array;

echo $fruta1; // Salida: manzana
```

### Ejemplo 3: Ignorar valores
```php
$array = array(1, 2, 3);
list($a, , $c) = $array;

echo $a; // Salida: 1
echo $c; // Salida: 3
```

## Explicación
Un error común al utilizar `list()` es intentar asignar valores desde un array asociativo. Esto no funcionará correctamente, ya que `list()` requiere que el array tenga índices numéricos. Además, es importante recordar que si el número de variables en `list()` no coincide con el número de elementos en el array, las variables no asignadas quedarán como `NULL`. 

Por último, `list()` no puede ser utilizada para asignar valores a variables en un contexto que no sea la declaración directa de variables.

## Resumen en una línea
La función `list()` en PHP permite asignar múltiples valores de un array a variables individuales de manera eficiente.