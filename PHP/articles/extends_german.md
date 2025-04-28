<!--
Meta Description: # Das Schlüsselwort "extends" in PHP: Vererbung in der objektorientierten Programmierung ## Synopsis Das Schlüsselwort "extends" in PHP ermöglicht die...
Meta Keywords: der, die, und, klasse, das
-->

# Das Schlüsselwort "extends" in PHP: Vererbung in der objektorientierten Programmierung

## Synopsis
Das Schlüsselwort "extends" in PHP ermöglicht die Vererbung von Klassen und ist ein zentrales Element der objektorientierten Programmierung (OOP). Es ermöglicht einer Klasse, die Eigenschaften und Methoden einer anderen Klasse zu übernehmen und zu erweitern.

## Dokumentation
### Zweck
Das Schlüsselwort "extends" wird verwendet, um eine neue Klasse zu definieren, die von einer bestehenden Klasse erbt. Diese Vererbung ermöglicht es, Code wiederzuverwenden und die Funktionalität zu erweitern, ohne redundanten Code zu schreiben.

### Verwendung
Um eine Klasse zu erstellen, die von einer anderen Klasse erbt, verwenden Sie die folgende Syntax:

```php
class KindKlasse extends ElternKlasse {
    // Neue Eigenschaften und Methoden
}
```

Hierbei wird `KindKlasse` zur abgeleiteten Klasse, die alle öffentlichen und geschützten Eigenschaften und Methoden der `ElternKlasse` erbt.

### Details
- **Zugriffsmodifizierer**: Die Sichtbarkeit der geerbten Eigenschaften und Methoden hängt von ihrem Zugriffsmodifizierer ab (public, protected, private). Nur `public` und `protected` Mitglieder sind in der abgeleiteten Klasse zugänglich.
- **Methodenüberschreibung**: Die abgeleitete Klasse kann Methoden der Elternklasse überschreiben, um spezifisches Verhalten zu implementieren.
- **Konstruktoren**: Wenn die Elternklasse einen Konstruktor hat, muss der Konstruktor der Kindklasse diesen explizit aufrufen, um die Initialisierung der Elternklasse zu gewährleisten.

## Beispiele
### Einfaches Beispiel der Vererbung
```php
class Fahrzeug {
    public function fahren() {
        return "Das Fahrzeug fährt.";
    }
}

class Auto extends Fahrzeug {
    public function hupen() {
        return "Das Auto hupt.";
    }
}

$meinAuto = new Auto();
echo $meinAuto->fahren(); // Ausgabe: Das Fahrzeug fährt.
echo $meinAuto->hupen();  // Ausgabe: Das Auto hupt.
```

### Methodenüberschreibung
```php
class Tier {
    public function lautGeben() {
        return "Das Tier macht ein Geräusch.";
    }
}

class Hund extends Tier {
    public function lautGeben() {
        return "Der Hund bellt.";
    }
}

$meinHund = new Hund();
echo $meinHund->lautGeben(); // Ausgabe: Der Hund bellt.
```

## Erklärung
### Häufige Fallstricke
- **Private Mitglieder**: Private Eigenschaften und Methoden der Elternklasse sind in der Kindklasse nicht zugänglich. Dies kann zu Verwirrung führen, wenn Entwickler erwarten, dass sie diese Mitglieder erben können.
- **Konstruktoren**: Vergessen, den Konstruktor der Elternklasse aufzurufen, kann dazu führen, dass die Elternklasse nicht korrekt initialisiert wird, was zu unerwartetem Verhalten führen kann.
- **Mehrfachvererbung**: PHP unterstützt keine Mehrfachvererbung, was bedeutet, dass eine Klasse nur von einer anderen Klasse erben kann. Dies kann die Struktur des Codes beeinflussen und sollte bei der Planung der Klassenhierarchie berücksichtigt werden.

## Ein-Satz-Zusammenfassung
Das Schlüsselwort "extends" in PHP ermöglicht die Vererbung von Klassen, was die Wiederverwendbarkeit und Erweiterbarkeit von Code in der objektorientierten Programmierung fördert.