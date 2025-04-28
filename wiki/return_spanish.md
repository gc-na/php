<!--
Meta Description: # La instrucción "return" en PHP: Guía Completa ## Sinopsis La instrucción `return` en PHP es fundamental para el desarrollo de funciones, ya que perm...
Meta Keywords: return, php, que, una, instrucción
-->

# La instrucción "return" en PHP: Guía Completa

## Sinopsis
La instrucción `return` en PHP es fundamental para el desarrollo de funciones, ya que permite devolver un valor desde una función hacia el contexto que la llamó. Esto es esencial para la manipulación de datos y el flujo de control en las aplicaciones PHP.

## Documentación
La instrucción `return` en PHP se utiliza dentro de las funciones para finalizar su ejecución y devolver un valor. Cuando se llama a una función que contiene una instrucción `return`, el flujo del programa se interrumpe y se devuelve el valor especificado a la línea de código que realizó la llamada.

### Propósito
El propósito principal de `return` es proporcionar un mecanismo para enviar datos de una función de vuelta al lugar donde fue llamada, permitiendo así que esos datos sean utilizados en otras partes del código.

### Uso
La sintaxis básica de la instrucción `return` es la siguiente:

```php
return [valor];
```

Donde `[valor]` puede ser cualquier expresión válida en PHP (números, cadenas, arrays, objetos, etc.).

### Detalles
- Si no se especifica un valor en la instrucción `return`, PHP devolverá `NULL` por defecto.
- La instrucción `return` no solo termina la ejecución de la función, sino que también puede ser utilizada para salir de un script en caso de que se necesite.
- Las funciones en PHP pueden devolver un solo valor, por lo que es común devolver arrays o objetos para devolver múltiples valores.

## Ejemplos

### Ejemplo 1: Retornando un número
```php
function sumar($a, $b) {
    return $a + $b;
}

$resultado = sumar(5, 10);
echo $resultado; // Salida: 15
```

### Ejemplo 2: Retornando una cadena
```php
function saludar($nombre) {
    return "Hola, " . $nombre;
}

echo saludar("Juan"); // Salida: Hola, Juan
```

### Ejemplo 3: Retornando un array
```php
function obtenerDatos() {
    return ["nombre" => "Ana", "edad" => 25];
}

$datos = obtenerDatos();
print_r($datos); 
// Salida: Array ( [nombre] => Ana [edad] => 25 )
```

## Explicación
### Errores Comunes
1. **No usar return**: Olvidar incluir una instrucción `return` en una función puede llevar a resultados inesperados, ya que la función devolverá `NULL` en su lugar.
2. **Retornar múltiples valores**: Intentar retornar múltiples valores separados por comas no funcionará. En su lugar, se debe utilizar un array o un objeto para agrupar los valores.
3. **Uso fuera de funciones**: Intentar usar `return` fuera del contexto de una función generará un error de sintaxis.

### Notas Adicionales
- Dentro de una misma función, se pueden tener múltiples instrucciones `return`, pero solo se ejecutará la primera que se encuentre. Las restantes serán ignoradas.
- La instrucción `return` también puede ser utilizada para detener la ejecución de un script en ciertos casos, especialmente en funciones de validación o control de errores.

## Resumen en una línea
La instrucción `return` en PHP permite finalizar la ejecución de una función y devolver un valor al contexto que la llamó, siendo esencial para la manipulación de datos y el flujo de control en el código.