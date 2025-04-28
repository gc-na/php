<!--
Meta Description: # PHP `endforeach`: Verwendung und Beispiele ## Synopsis Der Befehl `endforeach` in PHP ist eine Steueranweisung, die das Ende einer `foreach`-Schleif...
Meta Keywords: die, endforeach, foreach, php, der
-->

# PHP `endforeach`: Verwendung und Beispiele

## Synopsis
Der Befehl `endforeach` in PHP ist eine Steueranweisung, die das Ende einer `foreach`-Schleife markiert. Er wird verwendet, um über Arrays zu iterieren und deren Elemente zu verarbeiten.

## Dokumentation
### Zweck
`endforeach` dient zur Beendigung einer `foreach`-Schleife in PHP. Diese Schleife ist besonders nützlich, um alle Elemente eines Arrays zu durchlaufen und sie in einer lesbaren Struktur darzustellen oder zu verarbeiten.

### Verwendung
In PHP wird die `foreach`-Schleife verwendet, um durch jedes Element eines Arrays zu iterieren. Die Syntax für die Verwendung der `foreach`-Schleife ist wie folgt:

```php
foreach ($array as $value) {
    // Code, der für jedes Element ausgeführt wird
}
```

Um die Schleife mit der `endforeach`-Anweisung zu beenden, kann die alternative Syntax verwendet werden:

```php
foreach ($array as $value):
    // Code, der für jedes Element ausgeführt wird
endforeach;
```

### Details
- `endforeach` wird häufig in Kombination mit der alternativen Syntax verwendet, die insbesondere in HTML-Templates nützlich ist, da sie die Lesbarkeit verbessert.
- Es ist wichtig, dass `endforeach` keine Semikolons (`;`) erfordert, im Gegensatz zu den meisten anderen PHP-Anweisungen.

## Beispiele
### Einfaches Beispiel
Hier ist ein einfaches Beispiel für die Verwendung von `foreach` mit `endforeach`:

```php
$fruits = array("Äpfel", "Bananen", "Kirschen");

foreach ($fruits as $fruit):
    echo $fruit . "<br>";
endforeach;
```

### Beispiel mit Schlüssel-Wert-Paaren
Das folgende Beispiel zeigt, wie man mit `foreach` über ein assoziatives Array iteriert:

```php
$person = array("Name" => "Hans", "Alter" => 30, "Stadt" => "Berlin");

foreach ($person as $key => $value):
    echo $key . ": " . $value . "<br>";
endforeach;
```

## Erklärung
### Häufige Stolpersteine
- Die `endforeach`-Anweisung muss genau mit der `foreach`-Anweisung übereinstimmen, sowohl in Bezug auf die Syntax als auch auf die Verwendung von Doppelpunkten (`:`) und Semikolons.
- Verwechslungen können auftreten, wenn Entwickler versuchen, `endforeach` in einer Standard-Syntax zu verwenden, wo ein Semikolon benötigt wird.

### Zusätzliche Hinweise
- Die Verwendung von `foreach` mit `endforeach` ist eine bevorzugte Methode, wenn man Code in Templates oder bei der Ausgabe von HTML verwenden möchte, da sie die Struktur klarer und leichter lesbar macht.
- In PHP 7 und höher sind `foreach`-Schleifen effizient und sicher, was bedeutet, dass sie auch bei großen Arrays gut funktionieren.

## Ein Satz Zusammenfassung
`endforeach` ist ein Befehl in PHP, der das Ende einer `foreach`-Schleife markiert und die Verarbeitung von Array-Elementen in einer alternativen, lesbaren Syntax ermöglicht.