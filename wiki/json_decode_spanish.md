<!--
Meta Description: # json_decode: Decodificación de JSON en PHP ## Sinopsis La función `json_decode` de PHP permite convertir cadenas JSON en estructuras de datos PHP, f...
Meta Keywords: json, php, datos, json_decode, decodificación
-->

# json_decode: Decodificación de JSON en PHP

## Sinopsis
La función `json_decode` de PHP permite convertir cadenas JSON en estructuras de datos PHP, facilitando la manipulación y uso de datos en formato JSON.

## Documentación
La función `json_decode` se utiliza para transformar una cadena JSON en un objeto o un array asociativo en PHP. Es especialmente útil al trabajar con APIs y servicios web que utilizan JSON como formato de intercambio de datos.

### Sintaxis
```php
json_decode(string $json, bool $assoc = false, int $depth = 512, int $options = 0): mixed
```

### Parámetros
- **$json**: La cadena JSON que se desea decodificar.
- **$assoc**: (Opcional) Si se establece en `true`, la función devolverá un array asociativo en lugar de un objeto. Por defecto, es `false`.
- **$depth**: (Opcional) La profundidad máxima de la decodificación. Por defecto, es 512.
- **$options**: (Opcional) Opciones para controlar el comportamiento de la decodificación. Puede ser una combinación de constantes de opciones.

### Valor de retorno
Devuelve el valor del tipo correspondiente (array o objeto) en función de los parámetros proporcionados. Si la cadena JSON es inválida, devolverá `null`.

## Ejemplos

### Ejemplo 1: Decodificación básica
```php
$json = '{"nombre": "Juan", "edad": 30}';
$datos = json_decode($json);
echo $datos->nombre; // Salida: Juan
```

### Ejemplo 2: Decodificación como array asociativo
```php
$json = '{"nombre": "María", "edad": 25}';
$datos = json_decode($json, true);
echo $datos['nombre']; // Salida: María
```

### Ejemplo 3: Manejo de errores
```php
$json = '{"nombre": "Carlos", "edad": "treinta"}'; // "edad" debería ser un número
$datos = json_decode($json);

if (json_last_error() !== JSON_ERROR_NONE) {
    echo "Error en la decodificación JSON: " . json_last_error_msg();
}
```

## Explicación
Es importante tener en cuenta que `json_decode` puede fallar si se le pasa una cadena JSON mal formada. En tal caso, es recomendable utilizar `json_last_error` y `json_last_error_msg` para obtener información sobre el error ocurrido. Además, al decodificar JSON, es esencial asegurarse de que los datos están en el formato correcto para evitar problemas de tipo en PHP.

Otro punto a considerar es el parámetro `depth`, que limita cuán profundos pueden ser los objetos anidados en el JSON. Si se excede esta profundidad, se generará un error.

## Resumen en una línea
`json_decode` es una función de PHP que convierte cadenas JSON en objetos o arrays, facilitando la manipulación de datos en formato JSON.