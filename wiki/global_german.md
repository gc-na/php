<!--
Meta Description: # PHP Global Keyword: Verwendung und Bedeutung in der Programmierung ## Synopsis Das `global`-Schlüsselwort in PHP ermöglicht den Zugriff auf globale ...
Meta Keywords: variablen, global, die, der, sie
-->

# PHP Global Keyword: Verwendung und Bedeutung in der Programmierung

## Synopsis
Das `global`-Schlüsselwort in PHP ermöglicht den Zugriff auf globale Variablen innerhalb von Funktionen und Methoden, die normalerweise nur lokal sind.

## Dokumentation
In PHP ist das `global`-Schlüsselwort ein Mechanismus, der es Entwicklern ermöglicht, auf Variablen zuzugreifen, die außerhalb des aktuellen Gültigkeitsbereichs (Scope) definiert sind. Standardmäßig sind Variablen, die innerhalb einer Funktion definiert werden, lokal und nicht außerhalb der Funktion zugänglich. Mit `global` können Sie jedoch auf Variablen zugreifen, die außerhalb der Funktion deklariert sind.

### Verwendung
Um eine globale Variable in einer Funktion zu verwenden, deklarieren Sie die Variable mit dem Schlüsselwort `global`, gefolgt vom Namen der Variable. Dies ermöglicht es der Funktion, auf die globale Version der Variable zuzugreifen und sie zu modifizieren.

### Details
- **Gültigkeitsbereich**: Globale Variablen sind im gesamten Skript verfügbar, jedoch nicht in Funktionen, es sei denn, sie werden mit `global` deklariert.
- **Mehrere Variablen**: Sie können mehrere globale Variablen in einer Funktion deklarieren, indem Sie sie jeweils mit dem `global`-Schlüsselwort voranstellen.
- **Superglobale Variablen**: Beachten Sie, dass Superglobale wie `$_POST`, `$_GET`, und `$_SESSION` keinen Zugriff auf `global` benötigen, da sie immer verfügbar sind.

## Beispiele
### Beispiel 1: Zugriff auf eine globale Variable
```php
$globalVar = "Hallo, Welt!";

function testGlobal() {
    global $globalVar;
    echo $globalVar; // Gibt "Hallo, Welt!" aus
}

testGlobal();
```

### Beispiel 2: Modifizieren einer globalen Variable
```php
$zahl = 10;

function addiereFuenf() {
    global $zahl;
    $zahl += 5;
}

addiereFuenf();
echo $zahl; // Gibt 15 aus
```

## Erklärung
Ein häufiger Fehler, den Entwickler machen, ist, zu versuchen, auf globale Variablen zuzugreifen, ohne das `global`-Schlüsselwort zu verwenden. In solchen Fällen wird die lokale Version der Variablen verwendet, die nicht den gewünschten Wert enthält. Ein weiterer Punkt ist die Verwirrung über den Gültigkeitsbereich, insbesondere bei der Verwendung von Variablen in verschachtelten Funktionen oder Methoden, was zu unerwartetem Verhalten führen kann.

Zusätzlich sollte beachtet werden, dass übermäßiger Gebrauch von globalen Variablen den Code schwerer wartbar und testbar machen kann. Es ist oft besser, Werte als Parameter zu übergeben oder Rückgabewerte zu verwenden.

## Ein-Satz-Zusammenfassung
Das `global`-Schlüsselwort in PHP ermöglicht den Zugriff auf und die Modifikation von globalen Variablen innerhalb von Funktionen.