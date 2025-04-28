<!--
Meta Description: # Rückgabewert in PHP: Verwendung des "return"-Befehls ## Synopsis Der `return`-Befehl in PHP wird verwendet, um den Rückgabewert einer Funktion zu de...
Meta Keywords: return, funktion, der, die, und
-->

# Rückgabewert in PHP: Verwendung des "return"-Befehls

## Synopsis
Der `return`-Befehl in PHP wird verwendet, um den Rückgabewert einer Funktion zu definieren und die Ausführung der Funktion zu beenden. Er ermöglicht es, Daten von einer Funktion zurück an den Aufrufer zu senden, was für die Modularität und Wiederverwendbarkeit von Code entscheidend ist.

## Dokumentation
### Zweck
Der `return`-Befehl gibt den Wert zurück, den eine Funktion produziert, und beendet die Funktion. Dies ist wichtig, um Ergebnisse von Funktionen an den Aufrufer zurückzugeben und den Fluss des Programms zu steuern.

### Verwendung
Der `return`-Befehl wird innerhalb einer Funktion verwendet, gefolgt von dem Wert oder der Variable, die zurückgegeben werden soll. Wenn `return` ohne einen Wert verwendet wird, wird `NULL` zurückgegeben.

#### Syntax
```php
return [Wert];
```

### Details
- Der `return`-Befehl kann in jeder Funktion verwendet werden.
- Nach einem `return` wird die Funktion sofort beendet, und nachfolgender Code innerhalb der Funktion wird nicht mehr ausgeführt.
- Es können beliebige Datentypen zurückgegeben werden, einschließlich Integer, Strings, Arrays und Objekte.

## Beispiele
### Einfaches Beispiel
```php
function addiere($a, $b) {
    return $a + $b;
}

$resultat = addiere(5, 10);
echo $resultat; // Ausgabe: 15
```

### Rückgabe eines Arrays
```php
function erstelleArray() {
    return array(1, 2, 3);
}

$meinArray = erstelleArray();
print_r($meinArray); // Ausgabe: Array ( [0] => 1 [1] => 2 [2] => 3 )
```

### Rückgabe von NULL
```php
function keineRückgabe() {
    return; // Gibt NULL zurück
}

$resultat = keineRückgabe();
var_dump($resultat); // Ausgabe: NULL
```

## Erklärung
Ein häufiger Fehler beim Umgang mit `return` ist das Vergessen, den Befehl zu verwenden, wenn ein Wert von einer Funktion zurückgegeben werden soll. In einem solchen Fall gibt die Funktion `NULL` zurück, was zu unerwarteten Ergebnissen führen kann. Zudem kann es zu Verwirrung führen, wenn man einen Rückgabewert erwartet, aber die Funktion `return` nicht verwendet. 

Ein weiterer wichtiger Punkt ist, dass alle nachfolgenden Anweisungen in einer Funktion nach einem `return`-Befehl ignoriert werden. Es ist daher wichtig, die Position des `return`-Befehls strategisch zu planen, um sicherzustellen, dass der gewünschte Code ausgeführt wird.

## Ein-Satz-Zusammenfassung
Der `return`-Befehl in PHP ermöglicht es Funktionen, Werte zurückzugeben und die Ausführung der Funktion zu beenden, was für die Effektivität und Strukturierung des Codes unerlässlich ist.