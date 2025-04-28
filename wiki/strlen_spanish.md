<!--
Meta Description: # Función `strlen` en PHP: Cómo Medir la Longitud de Cadenas de Texto ## Sinopsis La función `strlen` en PHP se utiliza para obtener la longitud de un...
Meta Keywords: caracteres, strlen, php, cadena, una
-->

# Función `strlen` en PHP: Cómo Medir la Longitud de Cadenas de Texto

## Sinopsis
La función `strlen` en PHP se utiliza para obtener la longitud de una cadena de texto, devolviendo el número de caracteres presentes en ella, incluidos espacios y caracteres especiales.

## Documentación
La función `strlen` es una de las funciones más utilizadas en PHP para manipulación de cadenas. Su propósito principal es contar y devolver el número de caracteres que componen una cadena dada.

### Sintaxis
```php
int strlen ( string $string )
```

### Parámetros
- **$string**: La cadena cuyo tamaño se desea medir. Este parámetro es obligatorio.

### Valor de Retorno
La función devuelve un entero que representa la longitud de la cadena en caracteres. Si la cadena está vacía, se devolverá `0`.

### Ejemplo de Uso
```php
$cadena = "Hola, mundo!";
$longitud = strlen($cadena);
echo $longitud; // Salida: 13
```

En este ejemplo, la cadena `"Hola, mundo!"` contiene 13 caracteres, incluyendo la coma y el espacio.

## Ejemplos
### Ejemplo 1: Contar caracteres en una cadena simple
```php
$cadena1 = "PHP es genial";
echo strlen($cadena1); // Salida: 14
```

### Ejemplo 2: Contar caracteres en una cadena vacía
```php
$cadena2 = "";
echo strlen($cadena2); // Salida: 0
```

### Ejemplo 3: Contar caracteres con espacios
```php
$cadena3 = "   Espacios   ";
echo strlen($cadena3); // Salida: 15
```

### Ejemplo 4: Contar caracteres con caracteres especiales
```php
$cadena4 = "¡Hola! ¿Cómo estás?";
echo strlen($cadena4); // Salida: 22
```

## Explicación
Aunque `strlen` es una función sencilla, es importante tener en cuenta algunos aspectos:

- **Codificación de caracteres**: `strlen` cuenta bytes, no caracteres. Por ejemplo, en cadenas UTF-8 que contienen caracteres multibyte, la longitud puede no reflejar el número de caracteres visualmente. Para manejar cadenas multibyte, se recomienda utilizar `mb_strlen`.
  
- **Espacios y caracteres especiales**: `strlen` cuenta todos los caracteres, incluidos espacios, signos de puntuación y caracteres de control, lo que puede ser confuso si se espera que algunos de estos no se cuenten.

- **Rendimiento**: La función es bastante rápida y eficiente, pero en escenarios donde se requiere contar caracteres de forma frecuente en grandes volúmenes de texto, el rendimiento puede ser un factor a considerar.

## Resumen en una línea
La función `strlen` en PHP permite obtener la longitud de una cadena de texto, contando todos los caracteres, incluidos espacios y caracteres especiales.