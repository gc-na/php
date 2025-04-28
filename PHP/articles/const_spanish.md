<!--
Meta Description: # Uso de "const" en PHP: Definición y Ejemplos ## Sinopsis La palabra clave `const` en PHP se utiliza para definir constantes, es decir, valores que n...
Meta Keywords: constantes, const, php, que, las
-->

# Uso de "const" en PHP: Definición y Ejemplos

## Sinopsis
La palabra clave `const` en PHP se utiliza para definir constantes, es decir, valores que no cambian durante la ejecución del script. Estas constantes son útiles para almacenar configuraciones y parámetros que permanecen fijos.

## Documentación
La declaración de constantes en PHP se realiza mediante la palabra clave `const`. A diferencia de las variables, las constantes deben ser declaradas con un valor inicial, el cual no puede ser modificado una vez asignado. Las constantes son globales y pueden ser accedidas desde cualquier parte del script.

### Propósito
El propósito de `const` es proporcionar una forma de definir valores que no cambian a lo largo de la ejecución del programa, lo que permite mejorar la legibilidad y la mantenibilidad del código.

### Uso
Para declarar una constante en PHP, se utiliza la sintaxis:

```php
const NOMBRE_CONSTANTE = 'valor';
```

- `NOMBRE_CONSTANTE` debe ser un identificador válido y por convención se recomienda usar mayúsculas.
- `valor` puede ser un número, cadena de texto, o cualquier expresión que resulte en un valor constante.

### Detalles
- Las constantes declaradas con `const` siempre son accesibles como globales.
- No requieren el uso del signo `$` que se utiliza para las variables.
- Se pueden definir constantes en el ámbito de una clase, donde se convierten en constantes de clase.

## Ejemplos

### Ejemplo Básico de Definición de Constante
```php
const PI = 3.14159;
echo PI; // Salida: 3.14159
```

### Uso de Constantes en Clases
```php
class Circulo {
    const PI = 3.14;

    public static function area($radio) {
        return self::PI * ($radio ** 2);
    }
}

echo Circulo::area(5); // Salida: 78.5
```

### Definición de Múltiples Constantes
```php
const NOMBRE = 'Juan';
const EDAD = 30;

echo NOMBRE; // Salida: Juan
echo EDAD;   // Salida: 30
```

## Explicación
Al usar `const`, es importante tener en cuenta que:
- Las constantes no pueden ser redefinidas, lo que puede llevar a errores si se intenta hacerlo.
- Las constantes de clase deben ser accedidas utilizando la sintaxis `self::CONSTANTE` o `NombreClase::CONSTANTE`.
- No se puede declarar una constante dentro de un bloque condicional (if, switch, etc.).

## Resumen en una línea
La palabra clave `const` en PHP permite definir constantes que son valores inmutables accesibles globalmente o en el ámbito de clases.