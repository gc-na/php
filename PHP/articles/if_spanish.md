<!--
Meta Description: # La declaración "if" en PHP: Control de flujo condicional ## Sinopsis La declaración "if" en PHP es una estructura de control que permite ejecutar un...
Meta Keywords: una, condición, php, código, edad
-->

# La declaración "if" en PHP: Control de flujo condicional

## Sinopsis
La declaración "if" en PHP es una estructura de control que permite ejecutar un bloque de código solo si se cumple una condición específica. Es fundamental en la programación para tomar decisiones y controlar el flujo del programa.

## Documentación
### Propósito
La declaración "if" se utiliza para evaluar una condición booleana y, en función de su resultado (verdadero o falso), decidir si ejecutar o no un bloque de código. Es una de las estructuras de control más utilizadas en PHP, permitiendo crear lógica condicional en aplicaciones web y scripts.

### Uso
La sintaxis básica de la declaración "if" es la siguiente:

```php
if (condición) {
    // Código a ejecutar si la condición es verdadera
}
```

### Detalles
- **Condición**: Debe ser una expresión que se evalúe como verdadera (`true`) o falsa (`false`).
- **Bloque de código**: El código dentro de las llaves (`{}`) se ejecutará solo si la condición es verdadera.
- Se pueden incluir declaraciones `else` o `elseif` para manejar diferentes resultados de la condición.

### Ejemplo básico
```php
$edad = 18;

if ($edad >= 18) {
    echo "Eres mayor de edad.";
} else {
    echo "Eres menor de edad.";
}
```

En este ejemplo, se verifica si la variable `$edad` es mayor o igual a 18. Si es verdadero, se imprime "Eres mayor de edad." Si no, se imprime "Eres menor de edad."

## Explicación
### Errores comunes y notas
- **Olvidar las llaves**: En PHP, si solo hay una línea de código a ejecutar, se pueden omitir las llaves. Sin embargo, es recomendable usarlas para evitar errores cuando se añade más código en el futuro.
  
  ```php
  if ($condicion)
      echo "Solo una línea"; // Correcto, pero poco claro.
  ```

- **Operadores de comparación**: Asegúrate de usar correctamente los operadores de comparación (`==`, `===`, `!=`, `!==`, `<`, `>`, `<=`, `>=`). Confundirlos puede llevar a resultados inesperados.
  
- **Variables no inicializadas**: Si la variable utilizada en la condición no está inicializada, PHP generará un aviso. Es buena práctica asegurarse de que todas las variables estén definidas antes de usarlas en una condición.

## Resumen en una línea
La declaración "if" en PHP permite ejecutar código condicionalmente, evaluando si una condición es verdadera.