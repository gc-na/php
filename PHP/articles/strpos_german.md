<!--
Meta Description: # strpos – Die PHP-Funktion zur Zeichenketten-Suche ## Synopsis Die `strpos`-Funktion in PHP ermöglicht es Entwicklern, die Position des ersten Vorkom...
Meta Keywords: position, die, strpos, php, der
-->

# strpos – Die PHP-Funktion zur Zeichenketten-Suche

## Synopsis
Die `strpos`-Funktion in PHP ermöglicht es Entwicklern, die Position des ersten Vorkommens eines Teilstrings innerhalb einer Zeichenkette zu ermitteln. Diese Funktion ist besonders nützlich zur Analyse und Manipulation von Strings.

## Dokumentation
Die `strpos`-Funktion hat die folgende Syntax:

```php
int strpos ( string $haystack , mixed $needle [, int $offset = 0 ] )
```

### Parameter
- **$haystack**: Die Eingabe-Zeichenkette, in der gesucht wird.
- **$needle**: Der Teilstring, dessen Position gesucht wird. Dieser kann ein einzelnes Zeichen oder eine ganze Zeichenkette sein.
- **$offset** (optional): Ein optionaler Parameter, der angibt, an welcher Position in der Zeichenkette `$haystack` die Suche beginnen soll. Der Standardwert ist 0.

### Rückgabewert
Die Funktion gibt die Position des ersten Vorkommens von `$needle` in `$haystack` zurück. Beachte, dass die Position nullbasiert ist. Wenn `$needle` nicht gefunden wird, gibt die Funktion `false` zurück.

### Anmerkungen
- `strpos` ist case-sensitive, d.h., die Groß- und Kleinschreibung wird berücksichtigt.
- Wenn `$needle` ein leerer String ist, wird 0 zurückgegeben, da der leere String an jeder Position in `$haystack` gefunden werden kann.

## Beispiele
Hier sind einige grundlegende Beispiele zur Verwendung von `strpos`:

### Beispiel 1: Einfaches Vorkommen finden
```php
<?php
$myString = "Hallo Welt";
$position = strpos($myString, "Welt");
echo $position; // Ausgabe: 6
?>
```

### Beispiel 2: Nicht gefundener Teilstring
```php
<?php
$myString = "Hallo Welt";
$position = strpos($myString, "PHP");
var_dump($position); // Ausgabe: bool(false)
?>
```

### Beispiel 3: Suche ab einem bestimmten Offset
```php
<?php
$myString = "Hallo Welt, Willkommen in der Welt der PHP!";
$position = strpos($myString, "Welt", 10);
echo $position; // Ausgabe: 25
?>
```

## Erklärung
Ein häufiger Stolperstein bei der Verwendung von `strpos` ist die Unterscheidung zwischen `false` und `0`. Da der Rückgabewert von `strpos` die Position angibt und 0 eine gültige Position ist, muss bei der Überprüfung des Ergebnisses `===` verwendet werden, um sowohl den Typ als auch den Wert zu vergleichen:

```php
<?php
$myString = "Hallo Welt";
$position = strpos($myString, "Hallo");

if ($position === false) {
    echo "Nicht gefunden!";
} else {
    echo "Gefunden an Position: " . $position;
}
?>
```

Ein weiterer Punkt ist, dass `strpos` keine Regex-Suche unterstützt. Für komplexere Suchmuster sollte die Funktion `preg_match` verwendet werden.

## Eine-Satz-Zusammenfassung
Die `strpos`-Funktion in PHP ist ein leistungsstarkes Tool zur Ermittlung der Position eines Teilstrings innerhalb einer Zeichenkette, das Entwicklern hilft, Strings effizient zu analysieren und zu manipulieren.