<!--
Meta Description: # PHP array_merge: Eine umfassende Anleitung zur Zusammenführung von Arrays ## Synopsis Die Funktion `array_merge` in PHP dient dazu, mehrere Arrays z...
Meta Keywords: arrays, array, die, array_merge, werden
-->

# PHP array_merge: Eine umfassende Anleitung zur Zusammenführung von Arrays

## Synopsis
Die Funktion `array_merge` in PHP dient dazu, mehrere Arrays zu einem einzigen Array zu kombinieren. Diese Funktion ist besonders nützlich, um Daten aus verschiedenen Quellen zusammenzuführen.

## Dokumentation
### Zweck
Die `array_merge`-Funktion wird verwendet, um zwei oder mehr Arrays zu einem neuen Array zu kombinieren. Sie vereinfacht die Zusammenführung von Daten und ermöglicht es, Duplikate zu entfernen oder Schlüssel zu überschreiben, je nach den Anforderungen des Entwicklers.

### Verwendung
Die Grundsyntax der Funktion lautet:

```php
array_merge(array $array1, array ...$arrays): array
```

- **$array1**: Das erste Array, das mit anderen Arrays kombiniert werden soll.
- **$arrays**: Ein oder mehrere weitere Arrays, die zusammengeführt werden sollen.

### Rückgabewert
`array_merge` gibt ein neues Array zurück, das die Werte der übergebenen Arrays enthält. Bei numerischen Indizes werden die Werte der Arrays in der Reihenfolge hinzugefügt, in der sie übergeben werden. Bei assoziativen Indizes werden die Werte des letzten Arrays, das einen bestimmten Schlüssel enthält, verwendet.

## Beispiele
Hier sind einige einfache Beispiele zur Veranschaulichung der Verwendung von `array_merge`:

### Beispiel 1: Zusammenführen von zwei Arrays
```php
$array1 = ['a' => 'Apfel', 'b' => 'Banane'];
$array2 = ['c' => 'Kirsche', 'd' => 'Dattel'];
$result = array_merge($array1, $array2);
print_r($result);
```
**Ausgabe:**
```
Array
(
    [a] => Apfel
    [b] => Banane
    [c] => Kirsche
    [d] => Dattel
)
```

### Beispiel 2: Überschreiben von Werten
```php
$array1 = ['a' => 'Apfel', 'b' => 'Banane'];
$array2 = ['b' => 'Birne', 'c' => 'Kirsche'];
$result = array_merge($array1, $array2);
print_r($result);
```
**Ausgabe:**
```
Array
(
    [a] => Apfel
    [b] => Birne
    [c] => Kirsche
)
```

### Beispiel 3: Zusammenführen von mehreren Arrays
```php
$array1 = ['a' => 'Apfel'];
$array2 = ['b' => 'Banane'];
$array3 = ['c' => 'Kirsche'];
$result = array_merge($array1, $array2, $array3);
print_r($result);
```
**Ausgabe:**
```
Array
(
    [a] => Apfel
    [b] => Banane
    [c] => Kirsche
)
```

## Erklärung
### Häufige Stolpersteine
- **Numerische Indizes**: Bei der Verwendung von numerischen Indizes in den Arrays werden die Indizes nicht neu indiziert. Stattdessen werden die Werte einfach ans Ende des Ergebnisses angehängt. Dies kann zu unerwartetem Verhalten führen, wenn Sie erwarten, dass die Indizes fortlaufend sind.
- **Assoziative Indizes**: Bei assoziativen Arrays wird der Wert des letzten Arrays mit einem bestimmten Schlüssel verwendet. Dies bedeutet, dass vorherige Werte mit demselben Schlüssel überschrieben werden.
- **Nicht-array-Werte**: Wenn ein Argument kein Array ist, wird es in ein Array umgewandelt, was möglicherweise zu unerwarteten Ergebnissen führen kann.

## Ein-Satz-Zusammenfassung
Die PHP-Funktion `array_merge` kombiniert mehrere Arrays zu einem neuen Array, wobei Schlüsselüberschreibungen und die Beibehaltung von Werten berücksichtigt werden.