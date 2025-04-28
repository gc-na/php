<!--
Meta Description: # PHP `empty`: Eine umfassende Anleitung zur Überprüfung von Variablen ## Synopsis Die PHP-Funktion `empty()` wird verwendet, um zu überprüfen, ob ein...
Meta Keywords: variable, empty, ist, die, eine
-->

# PHP `empty`: Eine umfassende Anleitung zur Überprüfung von Variablen

## Synopsis
Die PHP-Funktion `empty()` wird verwendet, um zu überprüfen, ob eine Variable leer ist. Eine leere Variable wird als `false` betrachtet, wenn sie den Wert `false`, `null`, `0`, `0.0`, `""` (leere Zeichenkette), `"0"` (String mit Null) oder ein leeres Array hat.

## Dokumentation
### Zweck
`empty()` ist eine nützliche Funktion in PHP, um schnell zu prüfen, ob eine Variable als "leer" angesehen werden kann. Diese Funktion ist besonders hilfreich in Validierungs- und Bedingungsprüfungen.

### Verwendung
Die Funktion wird wie folgt verwendet:

```php
empty(mixed $var): bool
```

- **$var**: Die zu überprüfende Variable. Dies kann jede Art von PHP-Daten sein, einschließlich Integer, String, Array, Object, etc.
- **Rückgabewert**: Gibt `true` zurück, wenn die Variable leer ist, andernfalls `false`.

### Details
- `empty()` betrachtet die folgenden Werte als leer: `""`, `0`, `0.0`, `false`, `null`, `array()` (leeres Array), und `"0"`.
- Im Gegensatz zur Funktion `isset()` gibt `empty()` auch `true` zurück, wenn die Variable nicht existiert. Dies macht es zu einer praktischen Wahl für Überprüfungen, ohne zusätzliche `isset()`-Aufrufe zu benötigen.
- `empty()` hat keine Nebenwirkungen und verändert den Zustand der übergebenen Variablen nicht.

## Beispiele
### Beispiel 1: Überprüfung einer leeren Variable
```php
$var = "";
if (empty($var)) {
    echo "Die Variable ist leer.";
} else {
    echo "Die Variable hat einen Wert.";
}
```

### Beispiel 2: Überprüfung eines Arrays
```php
$array = [];
if (empty($array)) {
    echo "Das Array ist leer.";
}
```

### Beispiel 3: Überprüfung einer nicht gesetzten Variable
```php
if (empty($undefinedVar)) {
    echo "Die Variable ist nicht gesetzt oder leer.";
}
```

## Erklärung
- **Häufige Fallstricke**: Ein häufiger Fehler ist, `empty()` mit einer Variablen zu verwenden, die absichtlich `0` oder `false` sein soll, um einen Zustand zu repräsentieren. In solchen Fällen könnte man `isset()` oder eine andere Logik verwenden, um den tatsächlichen Wert zu prüfen.
- **Leere vs. Null**: Es ist wichtig, den Unterschied zwischen einer "leeren" Variable und einer `null`-Variable zu verstehen. Eine `null`-Variable wird von `empty()` als leer angesehen, aber nicht alle leeren Variablen sind `null`.
- **Leistung**: Da `empty()` in einigen Fällen eine bessere Leistung als Kombinationen von `isset()` und `==` bieten kann, ist es eine bevorzugte Wahl in vielen kurzlebigen Skripten.

## Ein-Satz-Zusammenfassung
Die PHP-Funktion `empty()` wird verwendet, um zu prüfen, ob eine Variable leer ist, und gibt `true` zurück, wenn dies der Fall ist.