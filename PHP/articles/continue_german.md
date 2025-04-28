<!--
Meta Description: # PHP "continue": Steuerung der Schleifenflusslogik ## Synopsis Das `continue`-Statement in PHP ermöglicht es, die aktuelle Iteration einer Schleife z...
Meta Keywords: continue, die, der, schleife, iteration
-->

# PHP "continue": Steuerung der Schleifenflusslogik

## Synopsis
Das `continue`-Statement in PHP ermöglicht es, die aktuelle Iteration einer Schleife zu beenden und mit der nächsten Iteration fortzufahren. Es wird häufig verwendet, um bestimmte Bedingungen zu überspringen und die Ausführung der Schleife effizienter zu gestalten.

## Dokumentation
Das `continue`-Statement wird innerhalb von Schleifen wie `for`, `foreach`, `while` und `do...while` verwendet. Wenn das `continue`-Statement erreicht wird, wird der restliche Code innerhalb der Schleife für die aktuelle Iteration übersprungen, und die Schleife fährt mit der nächsten Iteration fort.

### Verwendung
Die allgemeine Syntax des `continue`-Statements lautet:

```php
continue;
```

In einer geschachtelten Schleife kann auch ein optionaler numerischer Wert angegeben werden, um anzugeben, wie viele Schleifenebenen übersprungen werden sollen:

```php
continue 2; // Überspringt die nächste Iteration der äußeren Schleife
```

### Details
- **Gültige Schleifen**: `continue` kann in `for`, `foreach`, `while` und `do...while` Schleifen verwendet werden.
- **Steuerung des Flusses**: Das `continue`-Statement ist nützlich, um Bedingungen zu überprüfen und nur dann zur nächsten Iteration zu wechseln, wenn bestimmte Kriterien nicht erfüllt sind.

## Beispiele
### Beispiel 1: Grundlegende Verwendung von `continue`
```php
for ($i = 1; $i <= 5; $i++) {
    if ($i == 3) {
        continue; // Überspringt die Iteration, wenn $i gleich 3 ist
    }
    echo $i . PHP_EOL; // Gibt 1, 2, 4, 5 aus
}
```

### Beispiel 2: Verwendung von `continue` in einer `while`-Schleife
```php
$i = 0;
while ($i < 5) {
    $i++;
    if ($i == 2) {
        continue; // Überspringt die Iteration, wenn $i gleich 2 ist
    }
    echo $i . PHP_EOL; // Gibt 1, 3, 4, 5 aus
}
```

### Beispiel 3: Verwendung von `continue` in einer geschachtelten Schleife
```php
for ($i = 0; $i < 3; $i++) {
    for ($j = 0; $j < 3; $j++) {
        if ($j == 1) {
            continue 2; // Überspringt die aktuelle Iteration der äußeren Schleife
        }
        echo "i: $i, j: $j" . PHP_EOL; // Gibt nur i: 0, j: 0; i: 1, j: 0; und i: 2, j: 0 aus
    }
}
```

## Erklärung
Ein häufiger Fehler besteht darin, das `continue`-Statement in einer falschen Schleifenstruktur zu verwenden. Wenn `continue` in einer Schleife aufgerufen wird, die bereits beendet ist, hat es keine Wirkung und kann zu Verwirrung führen. Zudem ist es wichtig, darauf zu achten, dass `continue` nur innerhalb der Schleifen verwendet wird, für die es definiert ist. 

Ein weiteres wichtiges Detail ist, dass das `continue`-Statement keine Rückgabewerte liefert oder die Schleife vollständig beendet, sondern lediglich zur nächsten Iteration übergeht. Daher sollte es mit Bedacht eingesetzt werden, um die Lesbarkeit und Wartbarkeit des Codes nicht zu beeinträchtigen.

## Ein-Satz-Zusammenfassung
Das `continue`-Statement in PHP ermöglicht es, die aktuelle Schleifeniteration zu überspringen und mit der nächsten fortzufahren, um den Fluss der Programmausführung zu steuern.