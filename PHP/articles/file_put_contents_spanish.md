<!--
Meta Description: # file_put_contents: La función de PHP para escribir en archivos ## Sinopsis La función `file_put_contents` de PHP permite escribir datos en un archiv...
Meta Keywords: archivo, file_put_contents, php, datos, contenido
-->

# file_put_contents: La función de PHP para escribir en archivos

## Sinopsis
La función `file_put_contents` de PHP permite escribir datos en un archivo de manera sencilla y eficiente. Es especialmente útil para guardar contenido en archivos de texto y manejar la creación de archivos en aplicaciones web.

## Documentación

### Propósito
`file_put_contents` se utiliza para escribir datos en un archivo. Si el archivo no existe, se crea automáticamente. Si ya existe, su contenido puede ser reemplazado o se puede agregar al final del archivo, dependiendo de los parámetros utilizados.

### Uso
La sintaxis básica de `file_put_contents` es la siguiente:

```php
file_put_contents(string $filename, mixed $data, int $flags = 0, resource|null $context = null): int|false
```

#### Parámetros
- **$filename**: El nombre del archivo donde se escribirá el contenido. Puede incluir la ruta completa.
- **$data**: Los datos que se escribirán en el archivo. Puede ser una cadena, un array o cualquier otro tipo de datos que se pueda convertir a una cadena.
- **$flags**: (Opcional) Un valor que puede modificar el comportamiento de la función. Los valores comunes son:
  - `FILE_APPEND`: Si se establece, los datos se añadirán al final del archivo en lugar de sobrescribirlo.
  - `LOCK_EX`: Si se establece, se bloqueará el archivo para evitar que otros procesos lo modifiquen mientras se está escribiendo.
- **$context**: (Opcional) Un recurso que puede ser utilizado para modificar el comportamiento de flujo de entrada/salida.

### Retorno
La función devuelve el número de bytes escritos en el archivo o `false` en caso de error.

## Ejemplos

### Ejemplo 1: Escribir en un archivo
```php
$contenido = "Hola, mundo!";
$numeroDeBytes = file_put_contents("archivo.txt", $contenido);

if ($numeroDeBytes === false) {
    echo "Error al escribir en el archivo.";
} else {
    echo "$numeroDeBytes bytes escritos en archivo.txt.";
}
```

### Ejemplo 2: Añadir contenido a un archivo existente
```php
$contenidoAdicional = "\nEsta es una nueva línea.";
file_put_contents("archivo.txt", $contenidoAdicional, FILE_APPEND);
```

### Ejemplo 3: Usar un contexto
```php
$contexto = stream_context_create([
    'http' => [
        'header' => "Content-Type: text/plain\r\n"
    ]
]);

file_put_contents("archivo.txt", "Datos con contexto HTTP.", 0, $contexto);
```

## Explicación
Al utilizar `file_put_contents`, es importante tener en cuenta algunos puntos:

- **Permisos de archivo**: Asegúrate de que el script PHP tenga permisos para escribir en el directorio donde se encuentra el archivo.
- **Manejo de errores**: Siempre es recomendable comprobar el retorno de la función para manejar posibles errores, como la falta de permisos o problemas de ruta.
- **Sobrescritura accidental**: Si no se usa el flag `FILE_APPEND`, el contenido del archivo se sobrescribirá. Esto puede llevar a la pérdida de datos si no se tiene cuidado.

## Resumen en una línea
`file_put_contents` es una función de PHP que permite escribir datos de manera eficiente en archivos, creando nuevos archivos si es necesario y sobrescribiendo o añadiendo contenido según se desee.