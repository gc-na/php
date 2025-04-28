<!--
Meta Description: # PHP "implements": Schnittstellen in der objektorientierten Programmierung ## Synopsis In PHP wird das Schlüsselwort `implements` verwendet, um anzug...
Meta Keywords: schnittstellen, die, implements, eine, public
-->

# PHP "implements": Schnittstellen in der objektorientierten Programmierung

## Synopsis
In PHP wird das Schlüsselwort `implements` verwendet, um anzugeben, dass eine Klasse eine oder mehrere Schnittstellen (Interfaces) implementiert. Dies ermöglicht es, die Struktur und das Verhalten von Klassen durch definierte Methoden zu standardisieren.

## Dokumentation
Das Schlüsselwort `implements` ist ein zentrales Konzept in der objektorientierten Programmierung mit PHP. Es wird verwendet, um sicherzustellen, dass eine Klasse alle Methoden, die in einer oder mehreren Schnittstellen definiert sind, implementiert. 

### Zweck
Der Hauptzweck von `implements` ist die Förderung von Polymorphismus und die Schaffung von flexiblen, erweiterbaren Code-Strukturen. Schnittstellen ermöglichen es, die vertraglichen Verpflichtungen für Klassen zu definieren, ohne deren Implementierungsdetails vorzugeben.

### Verwendung
Eine Schnittstelle wird mit dem Schlüsselwort `interface` definiert, und eine Klasse, die diese Schnittstelle implementiert, verwendet das Schlüsselwort `implements`. Eine Klasse kann mehrere Schnittstellen implementieren, indem die Namen der Schnittstellen durch Kommas getrennt werden.

### Beispiel
```php
interface Fahrzeug {
    public function fahren();
}

class Auto implements Fahrzeug {
    public function fahren() {
        echo "Das Auto fährt.";
    }
}

$meinAuto = new Auto();
$meinAuto->fahren(); // Ausgabe: Das Auto fährt.
```

## Beispiele
### Beispiel 1: Einfache Implementierung
```php
interface Tier {
    public function machenGeräusch();
}

class Hund implements Tier {
    public function machenGeräusch() {
        return "Wuff!";
    }
}

$meinHund = new Hund();
echo $meinHund->machenGeräusch(); // Ausgabe: Wuff!
```

### Beispiel 2: Mehrere Schnittstellen
```php
interface FliegendesTier {
    public function fliegen();
}

interface Tier {
    public function machenGeräusch();
}

class Vogel implements FliegendesTier, Tier {
    public function fliegen() {
        return "Der Vogel fliegt.";
    }

    public function machenGeräusch() {
        return "Piep!";
    }
}

$meinVogel = new Vogel();
echo $meinVogel->fliegen(); // Ausgabe: Der Vogel fliegt.
echo $meinVogel->machenGeräusch(); // Ausgabe: Piep!
```

## Erklärung
Ein häufiger Stolperstein beim Einsatz von `implements` ist, dass die implementierende Klasse alle Methoden der Schnittstelle(n) vollständig definieren muss. Wenn eine Methode nicht implementiert wird, führt dies zu einem Fehler. Ein weiterer Punkt ist, dass Schnittstellen keine Implementierungen von Methoden enthalten können; sie definieren lediglich die Signaturen.

Zusätzlich können Klassen, die von einer anderen Klasse erben, auch Schnittstellen implementieren. Es ist wichtig, die richtige Kombination aus Vererbung und Schnittstellen zu nutzen, um den Code klar und wartbar zu halten.

## Zusammenfassung in einem Satz
Das Schlüsselwort `implements` in PHP ermöglicht es einer Klasse, eine oder mehrere Schnittstellen zu implementieren, wodurch ein einheitliches Verhalten und Polymorphismus gefördert werden.