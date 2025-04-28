<!--
Meta Description: # Standardwert ("default") in PHP: Eine umfassende Anleitung ## Synopsis Der Begriff "default" bezieht sich in PHP häufig auf Standardwerte in Funktio...
Meta Keywords: php, der, default, die, switch
-->

# Standardwert ("default") in PHP: Eine umfassende Anleitung

## Synopsis
Der Begriff "default" bezieht sich in PHP häufig auf Standardwerte in Funktionen, Switch-Anweisungen und beim Umgang mit Arrays. Diese Funktionalität erleichtert die Programmierung durch das Setzen von Rückfallwerten und erhöht die Lesbarkeit des Codes.

## Dokumentation
In PHP wird der Begriff "default" in mehreren Kontexten verwendet:

1. **Standardwerte für Funktionen**: In PHP können Funktionen Parameter mit Standardwerten definieren. Wenn kein Argument übergeben wird, wird der Standardwert verwendet. Dies verbessert die Flexibilität und Benutzerfreundlichkeit.

   ```php
   function beispielFunktion($wert = "Standardwert") {
       echo $wert;
   }

   beispielFunktion(); // Gibt "Standardwert" aus
   ```

2. **Switch-Anweisungen**: In einer Switch-Anweisung verwendet der "default"-Fall einen Rückfallwert, wenn keine der Bedingungen erfüllt ist. Dies ist besonders nützlich, um unerwartete Eingaben zu behandeln.

   ```php
   $farbe = "blau";

   switch ($farbe) {
       case "rot":
           echo "Die Farbe ist Rot";
           break;
       case "grün":
           echo "Die Farbe ist Grün";
           break;
       default:
           echo "Unbekannte Farbe";
   }
   ```

3. **Arrays**: In Verbindung mit Arrays kann "default" genutzt werden, um Rückfallwerte zu setzen, wenn ein Schlüssel nicht existiert. Dies wird häufig in Kombination mit der Funktion `array_key_exists` oder dem Null-Koaleszenz-Operator `??` verwendet.

   ```php
   $array = ["a" => 1, "b" => 2];
   $wert = $array["c"] ?? "Standardwert"; // Gibt "Standardwert" zurück
   ```

## Beispiele
Hier sind einige einfache Beispiele, die die Verwendung von "default" in PHP verdeutlichen:

1. **Funktionen mit Standardwerten**:
   ```php
   function begruessung($name = "Gast") {
       return "Willkommen, $name!";
   }

   echo begruessung(); // Gibt "Willkommen, Gast!" aus
   ```

2. **Switch-Anweisung**:
   ```php
   $tag = "Montag";

   switch ($tag) {
       case "Samstag":
       case "Sonntag":
           echo "Wochenende!";
           break;
       default:
           echo "Wochentag!";
   }
   ```

3. **Arrays mit Rückfallwerten**:
   ```php
   $person = ["name" => "Max", "alter" => 30];
   $beruf = $person["beruf"] ?? "Unbekannt"; // Gibt "Unbekannt" zurück
   ```

## Erklärung
Ein häufiger Fehler bei der Verwendung von "default" in PHP ist das Vergessen der `break`-Anweisung in Switch-Anweisungen. Ohne `break` wird der Code im nächsten Fall ebenfalls ausgeführt, was zu unerwarteten Ergebnissen führen kann. Außerdem sollten Standardwerte in Funktionen mit Bedacht gewählt werden, um die Klarheit und Absicht des Codes zu bewahren. Bei der Arbeit mit Arrays ist es wichtig zu beachten, dass der Null-Koaleszenz-Operator nur dann einen Wert zurückgibt, wenn der Linke Operand `null` ist. Dies bedeutet, dass falsche Werte wie `0` oder `""` nicht als `null` betrachtet werden und nicht den Standardwert auslösen.

## Ein-Satz-Zusammenfassung
Der Begriff "default" in PHP ermöglicht es Programmierern, Standardwerte für Funktionen, Switch-Anweisungen und Arrays festzulegen, um die Flexibilität und Lesbarkeit des Codes zu erhöhen.