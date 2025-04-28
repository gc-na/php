<!--
Meta Description: # PHP require: Inclusión de Archivos Esenciales en PHP ## Sinopsis El comando `require` en PHP se utiliza para incluir y evaluar un archivo PHP en el ...
Meta Keywords: php, archivo, require, que, script
-->

# PHP require: Inclusión de Archivos Esenciales en PHP

## Sinopsis
El comando `require` en PHP se utiliza para incluir y evaluar un archivo PHP en el contexto del script actual. Si el archivo no se encuentra, se generará un error fatal, lo que detiene la ejecución del script.

## Documentación
El comando `require` es fundamental en PHP para la modularización de código. Permite que los desarrolladores dividan sus aplicaciones en múltiples archivos, facilitando la organización y el mantenimiento del código.

### Propósito
El propósito principal de `require` es incluir archivos que son cruciales para la ejecución de un script. Esto puede incluir archivos de configuración, funciones, clases, entre otros.

### Uso
La sintaxis básica de `require` es la siguiente:
```php
require 'ruta/del/archivo.php';
```

- **ruta/del/archivo.php**: Es la ruta al archivo que se desea incluir. Puede ser una ruta relativa o absoluta.

### Detalles
- Si el archivo especificado en `require` no se encuentra, se producirá un error fatal y el script se detendrá.
- Se puede utilizar `require` múltiples veces para incluir el mismo archivo, pero esto generará un error si el archivo ya ha sido incluido previamente. Para evitarlo, se recomienda usar `require_once`.

## Ejemplos
### Ejemplo 1: Inclusión de un archivo simple
```php
// archivo.php
<?php
echo "¡Hola, mundo!";
?>

// script.php
<?php
require 'archivo.php'; // Esto incluye el contenido de archivo.php
?>
```
**Salida:** `¡Hola, mundo!`

### Ejemplo 2: Uso de require en un archivo de configuración
```php
// config.php
<?php
$databaseHost = 'localhost';
$databaseUser = 'root';
$databasePass = 'password';
?>

// index.php
<?php
require 'config.php'; // Incluyendo la configuración de la base de datos
echo $databaseHost; // Salida: localhost
?>
```

## Explicación
Al usar `require`, es importante tener en cuenta lo siguiente:

- **Errores Fatales**: Si el archivo no se encuentra, se generará un error fatal. Esto es diferente a `include`, que solo genera un aviso y continúa la ejecución del script.
- **Manejo de Rutas**: Asegúrate de que la ruta al archivo sea correcta. Las rutas relativas dependen de la ubicación del script que las llama, lo que puede llevar a confusiones si no se gestiona correctamente.
- **Uso de require_once**: Para evitar problemas de inclusión múltiple, considera usar `require_once`, que asegura que el archivo solo se incluya una vez, incluso si se llama varias veces.

## Resumen en una línea
El comando `require` en PHP es utilizado para incluir archivos esenciales en un script, asegurando que su contenido esté disponible durante la ejecución.