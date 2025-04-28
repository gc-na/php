<!--
Meta Description: # strpos: Función de PHP para Buscar la Posición de una Subcadena ## Sinopsis La función `strpos` en PHP se utiliza para encontrar la posición de la p...
Meta Keywords: strpos, php, cadena, que, subcadena
-->

# strpos: Función de PHP para Buscar la Posición de una Subcadena

## Sinopsis
La función `strpos` en PHP se utiliza para encontrar la posición de la primera aparición de una subcadena dentro de una cadena más grande. Es una herramienta esencial para manipulación de cadenas y análisis de texto en aplicaciones PHP.

## Documentación

### Propósito
La función `strpos` permite localizar la posición de una subcadena específica en una cadena. Esta función es sensible a mayúsculas y minúsculas, lo que significa que `strpos` diferenciará entre letras mayúsculas y minúsculas al realizar la búsqueda.

### Uso
La sintaxis básica de `strpos` es la siguiente:

```php
int strpos(string $haystack, string $needle, int $offset = 0)
```

- **$haystack**: La cadena en la que se buscará la subcadena.
- **$needle**: La subcadena que se desea buscar.
- **$offset**: (Opcional) La posición desde la que se comenzará la búsqueda. Por defecto es 0.

### Retorno
La función devuelve la posición numérica de la primera aparición de `$needle` en `$haystack`. Si la subcadena no se encuentra, se devuelve `FALSE`.

## Ejemplos

### Ejemplo 1: Búsqueda básica
```php
$cadena = "Hola Mundo";
$pos = strpos($cadena, "Mundo");
echo $pos; // Salida: 5
```

### Ejemplo 2: Subcadena no encontrada
```php
$cadena = "Hola Mundo";
$pos = strpos($cadena, "PHP");
var_dump($pos); // Salida: bool(false)
```

### Ejemplo 3: Usando el parámetro offset
```php
$cadena = "Hola Mundo. Hola PHP.";
$pos = strpos($cadena, "Hola", 5);
echo $pos; // Salida: 13
```

## Explicación
Al utilizar `strpos`, es importante tener en cuenta que la función devuelve `FALSE` si la subcadena no se encuentra. Sin embargo, si la subcadena se encuentra en la posición 0, esto puede llevar a confusiones, ya que `0` es evaluado como `FALSE` en un contexto booleano. Para evitar esto, siempre se debe usar la comparación estricta (===) cuando se evalúa el retorno de `strpos`.

```php
$pos = strpos("Hola", "H");
if ($pos === false) {
    echo "No encontrado";
} else {
    echo "Encontrado en la posición: " . $pos;
}
```

### Errores Comunes
- **Confusión con el retorno**: Como se mencionó, es crucial utilizar `===` para verificar el resultado de la función.
- **Sensibilidad a mayúsculas**: Recuerda que `strpos` es sensible a las letras, así que "hola" y "Hola" se consideran diferentes.
- **Uso incorrecto del offset**: Asegúrate de que el offset no esté fuera del rango de la cadena `haystack`, ya que esto puede llevar a resultados inesperados.

## Resumen en una línea
La función `strpos` en PHP se utiliza para encontrar la posición de la primera aparición de una subcadena dentro de una cadena, siendo sensible a mayúsculas y minúsculas.