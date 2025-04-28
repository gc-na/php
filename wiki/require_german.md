<!--
Meta Description: # require in PHP: Eine umfassende Anleitung ## Synopsis Das `require`-Kommando in PHP wird verwendet, um externe Dateien in das aktuelle Skript einzuf...
Meta Keywords: php, die, require, datei, dateipfad
-->

# require in PHP: Eine umfassende Anleitung

## Synopsis
Das `require`-Kommando in PHP wird verwendet, um externe Dateien in das aktuelle Skript einzufügen. Es ist besonders nützlich zum Einbinden von Funktionen, Klassen oder Konfigurationen, die in separaten Dateien gespeichert sind.

## Dokumentation
### Zweck
Das `require`-Statement ermöglicht es Entwicklern, Inhalte aus einer anderen Datei in das aktuelle PHP-Skript zu importieren. Dies fördert die Wiederverwendbarkeit von Code und sorgt für eine bessere Strukturierung von Projekten.

### Verwendung
Die grundlegende Syntax für `require` lautet:

```php
require 'dateipfad.php';
```

Hierbei ist `dateipfad.php` der Pfad zur Datei, die eingebunden werden soll. Wenn die Datei nicht gefunden wird, erzeugt `require` einen fatalen Fehler und stoppt die Ausführung des Skripts.

### Details
- **Unterschied zu `include`:** Der Hauptunterschied zwischen `require` und `include` besteht darin, dass `require` einen kritischen Fehler erzeugt, wenn die Datei nicht gefunden wird, während `include` nur eine Warnung ausgibt und die Ausführung des Skripts fortsetzt.
- **Mehrfache Einbindung:** Wenn eine Datei mehrmals eingebunden werden soll, sollte `require_once` stattdessen verwendet werden. Dieses Kommando verhindert, dass die Datei mehr als einmal eingebunden wird, was zu Problemen führen kann.

## Beispiele
### Beispiel 1: Einfache Verwendung von `require`

```php
// dateipfad.php
function hallo() {
    echo "Hallo, Welt!";
}

// main.php
require 'dateipfad.php';
hallo(); // Ausgabe: Hallo, Welt!
```

### Beispiel 2: Verwendung von `require_once`

```php
// dateipfad.php
$zahl = 42;

// main.php
require_once 'dateipfad.php';
echo $zahl; // Ausgabe: 42

// Ein weiterer Versuch, die Datei einzubinden
require_once 'dateipfad.php'; // Nichts passiert, da die Datei bereits eingebunden wurde
```

## Erklärung
### Häufige Fallstricke
- **Falscher Dateipfad:** Ein häufiger Fehler besteht darin, den falschen Pfad zur Datei anzugeben. Dies führt zu einem fatalen Fehler. Es ist ratsam, relative oder absolute Pfade zu überprüfen.
- **Dateirechte:** Stellen Sie sicher, dass die Datei, die Sie einbinden möchten, die richtigen Berechtigungen hat, damit sie vom Skript gelesen werden kann.
- **Namenskonflikte:** Bei der Verwendung von `require` können Namenskonflikte auftreten, wenn zwei Dateien Funktionen oder Variablen mit demselben Namen definieren. Hier kann `require_once` helfen, Konflikte zu vermeiden.

## Ein-Satz-Zusammenfassung
Das `require`-Kommando in PHP dient zum Einfügen von externen Dateien in ein Skript und erzeugt einen fatalen Fehler, wenn die Datei nicht gefunden wird.