<!--
Meta Description: # PHP `instanceof`: Überprüfung von Objekttypen ## Synopsis Der `instanceof` Operator in PHP wird verwendet, um zu überprüfen, ob ein Objekt eine Inst...
Meta Keywords: instanceof, ist, ein, objekt, der
-->

# PHP `instanceof`: Überprüfung von Objekttypen

## Synopsis
Der `instanceof` Operator in PHP wird verwendet, um zu überprüfen, ob ein Objekt eine Instanz einer bestimmten Klasse oder eines Interfaces ist. Er ist entscheidend für die objektorientierte Programmierung, da er die Typüberprüfung und die Vererbung unterstützt.

## Dokumentation
Der `instanceof` Operator ist ein binärer Operator, der zwei Operanden erwartet: einen Objekt-Operand und einen Klassennamen oder ein Interface. Er gibt `true` zurück, wenn das Objekt eine Instanz der angegebenen Klasse oder eines ihrer Vorfahren ist, andernfalls `false`.

### Verwendung
Die grundlegende Syntax lautet:

```php
$object instanceof ClassName;
```

### Details
- **Klassenspezifität**: `instanceof` berücksichtigt die Vererbung, d.h. wenn `$object` eine Instanz von `ChildClass` ist und `ChildClass` von `ParentClass` erbt, wird `$object instanceof ParentClass` `true` ergeben.
- **Interfaces**: `instanceof` funktioniert auch mit Interfaces. Wenn eine Klasse ein Interface implementiert, gibt `instanceof` für dieses Interface `true` zurück.
- **Null-Werte**: Wenn der Objekt-Operand `null` ist, gibt `instanceof` immer `false` zurück.

## Beispiele
### Beispiel 1: Grundlegende Anwendung
```php
class Tier {}
class Hund extends Tier {}

$hund = new Hund();

if ($hund instanceof Hund) {
    echo "Das Objekt ist ein Hund.";
}

if ($hund instanceof Tier) {
    echo "Das Objekt ist ein Tier.";
}
```

### Beispiel 2: Verwendung mit Interfaces
```php
interface Lebewesen {}
class Pflanze implements Lebewesen {}

$pflanze = new Pflanze();

if ($pflanze instanceof Lebewesen) {
    echo "Das Objekt ist ein Lebewesen.";
}
```

### Beispiel 3: Null-Überprüfung
```php
$objekt = null;

if ($objekt instanceof Tier) {
    echo "Das Objekt ist ein Tier.";
} else {
    echo "Das Objekt ist null.";
}
```

## Erklärung
Ein häufiger Fehler bei der Verwendung von `instanceof` ist die Annahme, dass es für primitive Datentypen wie Strings oder Integers funktioniert. `instanceof` funktioniert nur mit Objekten. Ein weiterer Punkt ist die korrekte Schreibweise von Klassennamen, da PHP case-sensitive ist. 

Zusätzlich kann es zu Verwirrung kommen, wenn man versucht, `instanceof` mit Namen von Klassen zu verwenden, die nicht im aktuellen Namensraum definiert sind. In solchen Fällen sollte der vollständige Namensraum angegeben werden.

## Ein-Satz-Zusammenfassung
Der `instanceof` Operator in PHP ermöglicht es Entwicklern, zu überprüfen, ob ein Objekt eine Instanz einer bestimmten Klasse oder eines Interfaces ist und unterstützt so die Typüberprüfung in der objektorientierten Programmierung.