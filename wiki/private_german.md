<!--
Meta Description: # Private in PHP: Zugriffskontrolle und Kapselung verstehen ## Synopsis In PHP ermöglicht das Schlüsselwort `private` die Einschränkung des Zugriffs a...
Meta Keywords: private, die, und, der, von
-->

# Private in PHP: Zugriffskontrolle und Kapselung verstehen

## Synopsis
In PHP ermöglicht das Schlüsselwort `private` die Einschränkung des Zugriffs auf Klassenmitglieder (Eigenschaften und Methoden), sodass sie nur innerhalb der Klasse selbst zugänglich sind. Dies fördert die Kapselung und schützt die Integrität der Daten.

## Dokumentation
Das `private`-Schlüsselwort in PHP wird verwendet, um die Sichtbarkeit von Eigenschaften und Methoden innerhalb einer Klasse zu steuern. Wenn ein Mitglieder einer Klasse als `private` deklariert wird, kann es nur von der Klasse selbst, nicht jedoch von abgeleiteten Klassen oder Instanzen der Klasse, zugegriffen werden. Die Verwendung von `private` ist ein wichtiger Bestandteil des objektorientierten Programmierens, da es dazu beiträgt, die Integrität der Objekt-Daten zu wahren und das Design des Codes zu verbessern.

### Verwendung
Um eine Eigenschaft oder Methode als `private` zu deklarieren, wird das Schlüsselwort `private` vor der Deklaration verwendet. Hier ein Beispiel:

```php
class Beispiel {
    private $geheimeDaten;

    public function __construct($daten) {
        $this->geheimeDaten = $daten;
    }

    private function zeigeDaten() {
        return $this->geheimeDaten;
    }

    public function gibDaten() {
        return $this->zeigeDaten();
    }
}
```

In diesem Beispiel kann `geheimeDaten` und die Methode `zeigeDaten()` nur innerhalb der Klasse `Beispiel` aufgerufen werden. Der Zugriff von außen ist nicht möglich.

## Beispiele
### Beispiel 1: Private Eigenschaften

```php
class Konto {
    private $saldo;

    public function __construct($anfangsSaldo) {
        $this->saldo = $anfangsSaldo;
    }

    public function einzahlen($betrag) {
        $this->saldo += $betrag;
    }

    public function abheben($betrag) {
        if ($betrag <= $this->saldo) {
            $this->saldo -= $betrag;
        } else {
            echo "Nicht genügend Guthaben!";
        }
    }

    public function getSaldo() {
        return $this->saldo;
    }
}

$meineKonto = new Konto(100);
$meineKonto->einzahlen(50);
echo $meineKonto->getSaldo(); // Gibt 150 aus
```

### Beispiel 2: Private Methoden

```php
class Rechner {
    private function addiere($a, $b) {
        return $a + $b;
    }

    public function berechneSumme($a, $b) {
        return $this->addiere($a, $b);
    }
}

$rechner = new Rechner();
echo $rechner->berechneSumme(5, 10); // Gibt 15 aus
```

## Erklärung
Ein häufiges Missverständnis ist, dass `private` nur für Eigenschaften gilt. Es kann auch auf Methoden angewendet werden. Ein weiterer häufiger Fehler ist der Versuch, auf private Mitglieder von außerhalb der Klasse zuzugreifen, was zu einem Fehler führt. Entwickler sollten sich bewusst sein, dass die Verwendung von `private` den Zugriff auf wichtige Logik und Daten innerhalb von Klassen beschränken kann, was jedoch in vielen Fällen gewünscht ist, um die Datenintegrität und die Kapselung zu gewährleisten.

Es ist wichtig, `private` mit Bedacht zu verwenden. Wenn eine Methode oder Eigenschaft in Zukunft möglicherweise von abgeleiteten Klassen benötigt wird, sollten stattdessen `protected` oder `public` Verwendung finden.

## Einzeilige Zusammenfassung
Das Schlüsselwort `private` in PHP ermöglicht die Kapselung und den geschützten Zugriff auf Eigenschaften und Methoden innerhalb einer Klasse.