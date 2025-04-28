<!--
Meta Description: # require_once in PHP: Verwendung, Beispiele und wichtige Hinweise ## Synopsis `require_once` ist eine der zentralen Anweisungen in PHP, die sicherste...
Meta Keywords: php, require_once, die, wird, datei
-->

# require_once in PHP: Verwendung, Beispiele und wichtige Hinweise

## Synopsis
`require_once` ist eine der zentralen Anweisungen in PHP, die sicherstellt, dass eine Datei nur einmal in einem Skript eingebunden wird. Dies verhindert Mehrfacheinbindungen und mögliche Fehlermeldungen.

## Dokumentation
Die Anweisung `require_once` wird verwendet, um PHP-Dateien in ein Skript zu integrieren. Der Hauptzweck dieser Anweisung besteht darin, die Funktionalität von externen Dateien, wie beispielsweise Klassen oder Funktionen, in das aktuelle Skript zu importieren. Mit `require_once` wird sichergestellt, dass die angegebene Datei nur einmal geladen wird, selbst wenn die Anweisung mehrmals im Code vorkommt.

### Verwendung
Die Syntax von `require_once` ist wie folgt:

```php
require_once 'dateiname.php';
```

Hierbei ist `dateiname.php` der Pfad zur Datei, die eingebunden werden soll. Wenn die angegebene Datei bereits einmal im Skript inkludiert wurde, wird sie bei weiteren Aufrufen von `require_once` ignoriert.

### Details
- **Fehlerbehandlung**: Wenn die Datei, die mit `require_once` eingebunden werden soll, nicht gefunden werden kann, löst PHP einen fatalen Fehler aus und das Skript wird gestoppt.
- **Unterschied zu require**: Im Gegensatz zu `require` wird bei `require_once` die Datei nur einmal geladen, was vor doppelten Definitionen schützt.
- **Unterschied zu include_once**: `include_once` funktioniert ähnlich wie `require_once`, jedoch wird bei einem fehlgeschlagenen Dateizugriff nur eine Warnung ausgegeben, und das Skript wird fortgesetzt.

## Beispiele
### Einfaches Beispiel

```php
// Datei: funktionen.php
function begruessung() {
    echo "Hallo, Welt!";
}

// Hauptdatei: index.php
require_once 'funktionen.php';
begruessung(); // Gibt "Hallo, Welt!" aus
```

### Beispiel mit mehrfacher Einbindung

```php
// Datei: klassen.php
class Beispiel {
    public function sagHallo() {
        echo "Hallo!";
    }
}

// Hauptdatei: index.php
require_once 'klassen.php';
require_once 'klassen.php'; // Wird ignoriert

$beispiel = new Beispiel();
$beispiel->sagHallo(); // Gibt "Hallo!" aus
```

## Erklärung
Ein häufiges Problem bei der Verwendung von `require_once` ist das Verwirrspiel mit Dateipfaden. Stellen Sie sicher, dass die angegebene Datei korrekt ist und der Pfad stimmt, um fatale Fehler zu vermeiden. 

Ein weiterer Punkt ist die Verwendung von `require_once` in großen Projekten. Hier kann eine falsche Struktur oder unklare Organisation zu unnötigen Ladezeiten führen. Achten Sie auf eine klare Struktur, um die Performance zu verbessern.

## Einzeiler Zusammenfassung
`require_once` in PHP ist eine Anweisung, die sicherstellt, dass eine Datei nur einmal in ein Skript eingebunden wird, um Fehler durch Mehrfacheinbindungen zu vermeiden.