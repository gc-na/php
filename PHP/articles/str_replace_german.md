<!--
Meta Description: # str_replace in PHP: Effiziente Textbearbeitung und -manipulation ## Synopsis Die PHP-Funktion `str_replace` ermöglicht es Entwicklern, bestimmte Tei...
Meta Keywords: die, str_replace, ist, php, strings
-->

# str_replace in PHP: Effiziente Textbearbeitung und -manipulation

## Synopsis
Die PHP-Funktion `str_replace` ermöglicht es Entwicklern, bestimmte Teile eines Strings durch andere Strings zu ersetzen. Diese Funktion ist besonders nützlich in der Textmanipulation und wird häufig zur Datenbereinigung oder -formatierung eingesetzt.

## Dokumentation
### Zweck
Die `str_replace`-Funktion wird verwendet, um alle Vorkommen eines Suchstrings in einem Zielstring durch einen Ersetzungsstring zu ersetzen. Sie ist einfach zu verwenden und bietet eine effiziente Möglichkeit, Textersetzungen vorzunehmen.

### Verwendung
Die allgemeine Syntax der `str_replace`-Funktion lautet:

```php
string str_replace(mixed $search, mixed $replace, mixed $subject, int &$count = null);
```

- **$search**: Der String oder ein Array von Strings, die ersetzt werden sollen.
- **$replace**: Der String oder ein Array von Strings, die als Ersatz dienen sollen.
- **$subject**: Der Zielstring oder ein Array von Strings, in dem die Ersetzungen vorgenommen werden sollen.
- **$count** (optional): Eine Variable, die die Anzahl der vorgenommenen Ersetzungen speichert.

### Rückgabewert
Die Funktion gibt den bearbeiteten String zurück, in dem alle Vorkommen des Suchstrings durch den Ersetzungsstring ersetzt wurden. Wenn `$subject` ein Array ist, wird ein Array zurückgegeben, das die bearbeiteten Strings enthält.

## Beispiele
### Beispiel 1: Einfache Ersetzung
```php
$text = "Hallo Welt!";
$result = str_replace("Welt", "PHP", $text);
echo $result; // Ausgabe: Hallo PHP!
```

### Beispiel 2: Ersetzung mit Arrays
```php
$text = "Ich mag Äpfel und Birnen.";
$search = ["Äpfel", "Birnen"];
$replace = ["Bananen", "Kirschen"];
$result = str_replace($search, $replace, $text);
echo $result; // Ausgabe: Ich mag Bananen und Kirschen.
```

### Beispiel 3: Zählen der Ersetzungen
```php
$text = "Das ist ein Test. Test ist wichtig.";
$count = 0;
$result = str_replace("Test", "Beispiel", $text, $count);
echo $result; // Ausgabe: Das ist ein Beispiel. Beispiel ist wichtig.
echo $count; // Ausgabe: 2
```

## Erklärung
1. **Groß-/Kleinschreibung**: `str_replace` ist nicht case-sensitive, d.h. es ersetzt sowohl "Test" als auch "test".
2. **Array-Handling**: Wenn sowohl `$search` als auch `$replace` Arrays sind, müssen sie die gleiche Anzahl an Elementen haben. Andernfalls wird es zu unerwarteten Ergebnissen kommen.
3. **Performance**: Bei großen Strings oder vielen Ersetzungen kann die Leistung beeinträchtigt werden. In solchen Fällen sollte die Verwendung von `str_ireplace` in Betracht gezogen werden, wenn eine case-insensitive Ersetzung erforderlich ist.

## Ein-Satz-Zusammenfassung
Die `str_replace`-Funktion in PHP ermöglicht eine einfache und effiziente Möglichkeit, Teile eines Strings durch andere zu ersetzen, und ist eine essentielle Funktion für die Textbearbeitung.