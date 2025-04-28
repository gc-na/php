<!--
Meta Description: # Operador XOR en PHP: Guía Completa y Ejemplos Prácticos ## Sinopsis El operador XOR en PHP es un operador lógico que permite realizar la operación d...
Meta Keywords: xor, resultado, true, php, false
-->

# Operador XOR en PHP: Guía Completa y Ejemplos Prácticos

## Sinopsis
El operador XOR en PHP es un operador lógico que permite realizar la operación de disyunción exclusiva entre dos valores booleanos. Su función principal es devolver verdadero si uno y solo uno de los operandos es verdadero.

## Documentación
El operador XOR, que se representa como `xor` en PHP, se utiliza para evaluar expresiones booleanas. Funciona de la siguiente manera:

- **Sintaxis**: 
  ```php
  $resultado = $valor1 xor $valor2;
  ```

- **Propósito**: El operador `xor` evalúa dos condiciones y retorna `true` si exactamente una de las condiciones es verdadera. Si ambas son verdaderas o ambas son falsas, el resultado es `false`.

- **Uso**: Este operador es útil en situaciones donde se necesita determinar si solo uno de los dos estados es verdadero, como en la validación de condiciones exclusivas.

### Detalles
- **Precedencia**: El operador `xor` tiene una menor precedencia que otros operadores lógicos, como `&&` y `||`. Esto puede requerir el uso de paréntesis para asegurar la evaluación correcta de las expresiones.
- **Tipo de Datos**: Los operandos pueden ser de tipo booleano o expresiones que se evalúan a booleanos.

## Ejemplos
### Ejemplo 1: Uso básico
```php
$a = true;
$b = false;

$resultado = $a xor $b; // Resultado: true
```

### Ejemplo 2: Ambas condiciones verdaderas
```php
$a = true;
$b = true;

$resultado = $a xor $b; // Resultado: false
```

### Ejemplo 3: Ambas condiciones falsas
```php
$a = false;
$b = false;

$resultado = $a xor $b; // Resultado: false
```

### Ejemplo 4: Uso con expresiones
```php
$a = (5 > 3); // true
$b = (2 < 1); // false

$resultado = $a xor $b; // Resultado: true
```

## Explicación
Un error común al usar el operador `xor` es no entender su precedencia. Por ejemplo:
```php
$resultado = false xor true and true; // Resultado: true
```
Debería usarse paréntesis para garantizar la evaluación deseada:
```php
$resultado = (false xor true) and true; // Resultado: false
```
En este caso, como `xor` tiene menor precedencia que `and`, la expresión se evalúa de forma inesperada.

## Resumen en una línea
El operador XOR en PHP devuelve verdadero si solo uno de los operandos es verdadero, facilitando la evaluación de condiciones exclusivas.