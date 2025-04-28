<!--
Meta Description: # PHP: Uso de la instrucción "continue" ## Sinopsis La instrucción `continue` en PHP se utiliza dentro de estructuras de control de bucle (como `for`,...
Meta Keywords: continue, bucle, que, del, iteración
-->

# PHP: Uso de la instrucción "continue"

## Sinopsis
La instrucción `continue` en PHP se utiliza dentro de estructuras de control de bucle (como `for`, `foreach`, `while` y `do...while`) para saltar la iteración actual y continuar con la siguiente, permitiendo una mayor flexibilidad en la ejecución de bucles.

## Documentación
### Propósito
La instrucción `continue` permite omitir el resto del código en la iteración actual de un bucle y proceder directamente a la siguiente iteración. Esto es útil cuando se quiere evitar la ejecución de ciertas partes del bucle bajo condiciones específicas.

### Uso
La sintaxis básica de `continue` es la siguiente:

```php
continue;
```

En el caso de bucles anidados, se puede especificar el nivel del bucle al que se desea continuar, utilizando un número entero. Por ejemplo, `continue 2;` saltará la iteración actual del bucle más interno y pasará a la siguiente iteración del bucle que está un nivel más arriba.

### Detalles
- `continue` se puede utilizar en bucles `for`, `foreach`, `while` y `do...while`.
- Al usar `continue` dentro de bucles anidados, el número especificado indica el nivel de bucle que se desea afectar.
- Si no se especifica un número, `continue` afecta solo al bucle más interno.

## Ejemplos
### Ejemplo básico de `continue`
```php
for ($i = 1; $i <= 10; $i++) {
    if ($i % 2 == 0) {
        continue; // Salta los números pares
    }
    echo $i . " "; // Imprime números impares
}
```
**Salida:** `1 3 5 7 9`

### Ejemplo de `continue` en bucles anidados
```php
for ($i = 1; $i <= 3; $i++) {
    for ($j = 1; $j <= 3; $j++) {
        if ($j == 2) {
            continue 2; // Salta a la siguiente iteración del bucle externo
        }
        echo "i = $i, j = $j\n";
    }
}
```
**Salida:**
```
i = 1, j = 1
i = 2, j = 1
i = 3, j = 1
```

## Explicación
Al utilizar `continue`, es importante tener en cuenta que puede causar confusión si no se entiende que el flujo de ejecución se salta el resto del código dentro del bucle actual. Además, al utilizar `continue` con un número, se debe ser cuidadoso para no superar el nivel de bucle existente, ya que esto generará un error en tiempo de ejecución.

Un error común es olvidar que `continue` solo se aplica al bucle más interno a menos que se especifique lo contrario. Además, es recomendable no abusar de `continue`, ya que puede hacer que el código sea menos legible si se usa en exceso.

## Resumen en una línea
La instrucción `continue` en PHP permite saltar la iteración actual de un bucle y proceder a la siguiente, facilitando un control más preciso del flujo de ejecución en los bucles.