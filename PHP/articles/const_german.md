<!--
Meta Description: # PHP "const": Konstanten in PHP erstellen und verwenden ## Synopsis In PHP ermöglicht das Schlüsselwort `const` die Definition von Konstanten, die zu...
Meta Keywords: konstanten, const, werden, der, sie
-->

# PHP "const": Konstanten in PHP erstellen und verwenden

## Synopsis
In PHP ermöglicht das Schlüsselwort `const` die Definition von Konstanten, die zur Compile-Zeit festgelegt werden und während der gesamten Ausführung des Skripts unverändert bleiben.

## Dokumentation
Das Schlüsselwort `const` wird in PHP verwendet, um Konstanten zu deklarieren. Eine Konstante ist ein Bezeichner (Name), der einen Wert speichert, der nicht mehr verändert werden kann. Konstanten sind besonders nützlich, um Werte zu definieren, die im gesamten Code verwendet werden sollen, ohne dass diese versehentlich geändert werden können.

### Zweck
Der Hauptzweck von Konstanten besteht darin, unveränderliche Werte zu speichern, die für die Programmlogik von entscheidender Bedeutung sind, wie z.B. Konfigurationsparameter, URLs oder feste mathematische Werte.

### Verwendung
Eine Konstante wird mit dem `const`-Schlüsselwort gefolgt von dem Namen der Konstante und dem zugewiesenen Wert definiert. Der Name einer Konstante muss immer mit einem Buchstaben oder Unterstrich beginnen und kann Buchstaben, Zahlen und Unterstriche enthalten.

```php
const PI = 3.14;
const SERVER_NAME = "localhost";
```

Konstanten sind im gesamten Skript verfügbar und müssen nicht mit dem Dollarzeichen (`$`) angesprochen werden.

### Details
- Konstanten sind global verfügbar, sobald sie definiert sind.
- Sie können nur Skalare (integers, floats, strings, booleans) oder Arrays als Werte verwenden.
- Konstanten können nicht innerhalb einer Funktion oder einer Klasse definiert werden, es sei denn, sie sind Teil einer Klasse (dann verwenden Sie `define()` oder `const` innerhalb der Klasse).

## Beispiele
### Beispiel 1: Einfache Konstanten
```php
const GREETING = "Hallo Welt!";
echo GREETING; // Ausgabe: Hallo Welt!
```

### Beispiel 2: Konstanten mit Zahlen
```php
const MAX_USERS = 100;
echo MAX_USERS; // Ausgabe: 100
```

### Beispiel 3: Konstanten in einer Klasse
```php
class MyClass {
    const VERSION = '1.0';
}

echo MyClass::VERSION; // Ausgabe: 1.0
```

## Erklärung
Ein häufiges Missverständnis über Konstanten ist, dass sie dynamisch geändert werden können. Einmal definiert, sind Konstanten unveränderlich. Ein weiterer häufiger Fehler ist die falsche Schreibweise der Konstantennamen, da sie in der Regel in Großbuchstaben geschrieben werden, um sie von Variablen zu unterscheiden.

Zusätzlich ist zu beachten, dass Konstanten nicht gelöscht werden können, nachdem sie erstellt wurden, und dass sie nicht mit dem `unset()`-Befehl entfernt werden können. Daher sollten Sie sicherstellen, dass der gewählte Name für die Konstante tatsächlich einzigartig und sinnvoll ist.

## Eine Zeile Zusammenfassung
Das `const`-Schlüsselwort in PHP wird verwendet, um Konstanten zu definieren, die unveränderliche Werte zur Verfügung stellen, die im gesamten Skript verwendet werden können.