<!--
Meta Description: # Protected in PHP: Zugriffsmodifizierer für objektorientierte Programmierung ## Synopsis In PHP ist `protected` ein Zugriffsmodifizierer, der den Zug...
Meta Keywords: der, protected, und, klasse, die
-->

# Protected in PHP: Zugriffsmodifizierer für objektorientierte Programmierung

## Synopsis
In PHP ist `protected` ein Zugriffsmodifizierer, der den Zugriff auf Klassenattribute und -methoden steuert. Er ermöglicht den Zugriff für die Klasse selbst sowie für abgeleitete Klassen.

## Dokumentation
Der `protected` Zugriffsmodifizierer wird verwendet, um die Sichtbarkeit von Variablen und Methoden in einer Klasse zu bestimmen. Er ist ein zentraler Bestandteil der objektorientierten Programmierung in PHP und unterstützt die Prinzipien der Kapselung und Vererbung.

### Verwendung
In PHP kann `protected` vor Variablendeklarationen und Methodendefinitionen verwendet werden. Wenn eine Eigenschaft oder Methode als `protected` deklariert wird, kann sie nur innerhalb der Klasse, in der sie definiert wurde, und in allen Klassen, die von dieser Klasse erben, aufgerufen werden.

### Beispiel:
```php
class Eltern {
    protected $geschuetzteVariable = 'Ich bin geschützt';

    protected function geschuetzteMethode() {
        return 'Dies ist eine geschützte Methode.';
    }
}

class Kind extends Eltern {
    public function anzeigen() {
        // Zugriff auf die geschützte Variable und Methode
        echo $this->geschuetzteVariable; // Ausgabe: Ich bin geschützt
        echo $this->geschuetzteMethode(); // Ausgabe: Dies ist eine geschützte Methode.
    }
}

$kind = new Kind();
$kind->anzeigen();
```

In diesem Beispiel zeigt die Klasse `Kind`, wie auf `protected` Elemente der Elternklasse zugegriffen werden kann.

## Erklärung
Ein häufiger Fehler beim Arbeiten mit `protected` ist der Versuch, von außerhalb der Klasse oder einer abgeleiteten Klasse auf eine geschützte Eigenschaft oder Methode zuzugreifen. Hierbei wird ein Fehler ausgelöst, da der Zugriff verweigert wird. 

Ein weiteres wichtiges Detail ist, dass `protected` Eigenschaften und Methoden nicht von einer Instanz der Klasse direkt aufgerufen werden können, sondern nur innerhalb der Klasse oder von abgeleiteten Klassen. Dies fördert die Kapselung und schützt die Integrität der Daten.

## Einzeilenzusammenfassung
`protected` in PHP ist ein Zugriffsmodifizierer, der den Zugriff auf Klassenmitglieder nur innerhalb der Klasse selbst und von abgeleiteten Klassen erlaubt.