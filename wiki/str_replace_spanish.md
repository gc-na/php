<!--
Meta Description: # str_replace: Función Esencial de PHP para Reemplazar Cadenas ## Sinopsis La función `str_replace` en PHP es una herramienta fundamental para realiza...
Meta Keywords: str_replace, php, texto, que, array
-->

# str_replace: Función Esencial de PHP para Reemplazar Cadenas

## Sinopsis
La función `str_replace` en PHP es una herramienta fundamental para realizar reemplazos de subcadenas dentro de una cadena de texto. Se utiliza comúnmente en el desarrollo web para manipular y modificar cadenas de manera eficiente.

## Documentación
### Propósito
`str_replace` permite buscar y reemplazar todas las apariciones de una subcadena específica en una cadena de texto con otra subcadena. Es particularmente útil para limpiar datos, formatear salidas y realizar modificaciones en textos.

### Uso
La sintaxis básica de `str_replace` es la siguiente:

```php
str_replace(mixed $search, mixed $replace, mixed $subject, int &$count = null): mixed
```

- **$search**: La subcadena que se desea buscar. Puede ser una cadena o un array de cadenas.
- **$replace**: La subcadena con la que se desea reemplazar. Al igual que `$search`, puede ser una cadena o un array de cadenas.
- **$subject**: La cadena en la que se realizará la búsqueda y el reemplazo. También puede ser un array de cadenas.
- **$count**: (opcional) Si se proporciona, esta variable se llenará con el número de reemplazos realizados.

### Detalles
- La función es *case-sensitive*, lo que significa que distinguirá entre mayúsculas y minúsculas.
- Si `$search` y `$replace` son arrays, `str_replace` realizará las sustituciones en orden, utilizando el primer elemento de `$search` para reemplazar el primer elemento de `$replace`, y así sucesivamente.
- Si la longitud de `$search` y `$replace` no coincide, PHP utilizará el tamaño del array más pequeño.

## Ejemplos
### Ejemplo 1: Reemplazo simple
```php
$texto = "Hola mundo";
$texto_modificado = str_replace("mundo", "PHP", $texto);
echo $texto_modificado; // Salida: Hola PHP
```

### Ejemplo 2: Uso con arrays
```php
$texto = "Uno dos tres";
$busqueda = array("Uno", "dos");
$reemplazo = array("1", "2");
$texto_modificado = str_replace($busqueda, $reemplazo, $texto);
echo $texto_modificado; // Salida: 1 2 tres
```

### Ejemplo 3: Contando reemplazos
```php
$texto = "La casa es blanca. La casa es grande.";
$count = 0;
$texto_modificado = str_replace("casa", "hogar", $texto, $count);
echo $texto_modificado; // Salida: La hogar es blanca. La hogar es grande.
echo $count; // Salida: 2
```

## Explicación
Al usar `str_replace`, es importante tener en cuenta que:

- **Distinción de mayúsculas y minúsculas**: La función no reemplazará "Mundo" si se busca "mundo".
- **Arrays de búsqueda y reemplazo**: Si se pasan arrays de diferentes longitudes, los elementos en el array más corto se usarán para todos los elementos restantes en el array más largo.
- **Rendimiento**: Para cadenas largas o grandes cantidades de datos, considerar el impacto en el rendimiento es crucial, ya que `str_replace` recorrerá toda la cadena cada vez que se llame.

## Resumen en una línea
La función `str_replace` en PHP permite reemplazar eficientemente subcadenas dentro de cadenas de texto, facilitando la manipulación de datos en aplicaciones web.