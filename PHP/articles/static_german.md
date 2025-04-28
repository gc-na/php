<!--
Meta Description: # Static in PHP: Verwendung von statischen Methoden und Eigenschaften ## Synopsis In PHP ermöglicht das Schlüsselwort `static` die Definition von stat...
Meta Keywords: statische, static, die, methoden, der
-->

# Static in PHP: Verwendung von statischen Methoden und Eigenschaften

## Synopsis
In PHP ermöglicht das Schlüsselwort `static` die Definition von statischen Eigenschaften und Methoden innerhalb von Klassen, die ohne Instanziierung der Klasse aufgerufen werden können. Dies ist besonders nützlich für Utility-Methoden und Singleton-Designmuster.

## Dokumentation
Das Schlüsselwort `static` wird in PHP verwendet, um Eigenschaften und Methoden zu definieren, die zur Klasse selbst gehören, anstatt zu einer Instanz der Klasse. Statische Mitglieder können über den Klassennamen aufgerufen werden, was bedeutet, dass sie keinen Zugriff auf `$this` haben. 

### Zweck
- **Speicherplatz sparen**: Statische Eigenschaften teilen sich den gleichen Speicherplatz und sind für alle Instanzen der Klasse gleich.
- **Zugänglichkeit**: Statische Methoden können aufgerufen werden, ohne dass eine Instanz der Klasse erstellt werden muss.
- **Utility-Funktionen**: Ideal für Helper-Methoden oder Funktionen, die nicht von spezifischen Instanzdaten abhängen.

### Verwendung
Um eine statische Methode oder Eigenschaft zu deklarieren, verwenden Sie das Schlüsselwort `static` vor der Definition. Der Zugriff erfolgt über den Scope-Operator `::`.

#### Beispiel:
```php
class Beispiel {
    public static $staticEigenschaft = 'Ich bin statisch!';

    public static function statischeMethode() {
        return 'Ich bin eine statische Methode!';
    }
}

// Zugriff auf die statische Eigenschaft
echo Beispiel::$staticEigenschaft; // Ausgabe: Ich bin statisch!

// Aufruf der statischen Methode
echo Beispiel::statischeMethode(); // Ausgabe: Ich bin eine statische Methode!
```

## Beispiele
### 1. Statische Eigenschaft
```php
class Zähler {
    public static $anzahl = 0;

    public static function inkrementiere() {
        self::$anzahl++;
    }
}

Zähler::inkrementiere();
echo Zähler::$anzahl; // Ausgabe: 1
```

### 2. Statische Methode
```php
class Math {
    public static function quadriere($zahl) {
        return $zahl * $zahl;
    }
}

echo Math::quadriere(4); // Ausgabe: 16
```

### 3. Statische Methode mit Zugriff auf andere statische Eigenschaften
```php
class Konstante {
    public static $pi = 3.14;

    public static function umfang($radius) {
        return 2 * self::$pi * $radius;
    }
}

echo Konstante::umfang(5); // Ausgabe: 31.400000000000002
```

## Erklärung
- **Zugriff auf Instanzvariablen**: Statische Methoden können nicht auf Instanzvariablen zugreifen, da sie nicht Teil einer Instanz sind. Dies kann zu Verwirrung führen, wenn Entwickler versuchen, auf `$this` innerhalb einer statischen Methode zuzugreifen.
- **Statische vs. Instanzmethoden**: Statische Methoden sind nicht polymorph, was bedeutet, dass sie nicht überschrieben werden können, wenn eine Klasse von einer anderen erbt.
- **Initialisierung**: Statische Eigenschaften werden nur einmal initialisiert, was bedeutet, dass der Wert über alle Instanzen hinweg geteilt wird.
- **Verwendung von `self` und `static`**: `self` verweist auf die Klasse, in der die Methode aufgerufen wird, während `static` die Klasse referenziert, die zur Laufzeit instanziiert wird (späteste Bindung).

## Eine Zeile Zusammenfassung
Das Schlüsselwort `static` in PHP ermöglicht die Definition von Eigenschaften und Methoden, die direkt über die Klasse aufgerufen werden können, ohne eine Instanz erstellen zu müssen.