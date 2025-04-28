<!--
Meta Description: # array_merge: Combina Arreglos en PHP de Manera Eficiente ## Sinopsis `array_merge` es una función de PHP que permite combinar uno o más arreglos en ...
Meta Keywords: los, arreglos, que, array_merge, arreglo
-->

# array_merge: Combina Arreglos en PHP de Manera Eficiente

## Sinopsis
`array_merge` es una función de PHP que permite combinar uno o más arreglos en un solo arreglo. Esta función toma los elementos de cada arreglo y los une, manteniendo los índices de los elementos numéricos y sobrescribiendo los valores de los índices asociativos en caso de coincidencias.

## Documentación

### Propósito
La función `array_merge` es utilizada para concatenar arreglos en PHP, permitiendo que los elementos de múltiples arreglos se combinen en un único arreglo. Es especialmente útil cuando se trabaja con datos que se agrupan en diferentes arreglos y se requiere unificar esta información.

### Uso
La función tiene la siguiente sintaxis:

```php
array_merge(array $array1, array ...$arrays): array
```

#### Parámetros
- **$array1**: El primer arreglo que se va a combinar.
- **$arrays**: Uno o más arreglos adicionales que se combinarán con el primer arreglo.

#### Retorno
`array_merge` devuelve un nuevo arreglo que contiene todos los elementos de los arreglos proporcionados. Los índices numéricos se reindexan, mientras que los índices asociativos mantienen sus valores, sobrescribiendo aquellos que se repiten.

### Ejemplo de Uso
Aquí hay algunos ejemplos prácticos sobre cómo utilizar `array_merge`:

#### Ejemplo 1: Combinar arreglos simples

```php
$array1 = ['a', 'b', 'c'];
$array2 = ['d', 'e', 'f'];

$resultado = array_merge($array1, $array2);
print_r($resultado);
// Salida: Array ( [0] => a [1] => b [2] => c [3] => d [4] => e [5] => f )
```

#### Ejemplo 2: Combinar arreglos asociativos

```php
$array1 = ['a' => 'manzana', 'b' => 'banana'];
$array2 = ['b' => 'cereza', 'c' => 'durazno'];

$resultado = array_merge($array1, $array2);
print_r($resultado);
// Salida: Array ( [a] => manzana [b] => cereza [c] => durazno )
```

#### Ejemplo 3: Reindexar un arreglo numérico

```php
$array1 = [1, 2];
$array2 = [3, 4];

$resultado = array_merge($array1, $array2);
print_r($resultado);
// Salida: Array ( [0] => 1 [1] => 2 [2] => 3 [3] => 4 )
```

## Explicación
Es importante tener en cuenta que `array_merge` reindexa los arreglos numéricos, lo que puede causar confusión si se espera que los índices originales se mantengan. Por ejemplo, si dos arreglos contienen elementos con índices numéricos, el resultado final siempre será un arreglo con índices comenzando desde 0. Además, en el caso de los índices asociativos, si hay claves duplicadas, el último valor será el que se mantenga en el arreglo resultante.

### Errores comunes
- No se debe esperar que los índices numéricos se mantengan, ya que siempre se reindexan.
- Si se utilizan claves duplicadas en arreglos asociativos, solo se conservará el valor del último arreglo que se haya pasado a la función.

## Resumen en una línea
La función `array_merge` de PHP combina múltiples arreglos en uno solo, reindexando los arreglos numéricos y sobrescribiendo las claves duplicadas en arreglos asociativos.