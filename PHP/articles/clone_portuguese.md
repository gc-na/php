<!--
Meta Description: # Clonagem de Objetos em PHP: Como Usar o Comando clone ## Sinopse O comando `clone` em PHP é utilizado para criar uma cópia superficial de um objeto,...
Meta Keywords: que, clone, original, objetos, objeto
-->

# Clonagem de Objetos em PHP: Como Usar o Comando clone

## Sinopse
O comando `clone` em PHP é utilizado para criar uma cópia superficial de um objeto, permitindo a manipulação de instâncias sem afetar o objeto original.

## Documentação
O `clone` é uma palavra-chave em PHP que permite duplicar objetos. Quando você clona um objeto, o PHP cria uma nova instância do objeto original, porém com as mesmas propriedades e métodos. É importante entender que o `clone` realiza uma cópia superficial, ou seja, se o objeto contém propriedades que são referências a outros objetos, essas referências não são copiadas, mas sim apontam para o mesmo objeto.

### Uso
Para usar o `clone`, você deve simplesmente chamar a palavra-chave seguida da instância do objeto que deseja duplicar. Exemplo básico:

```php
$original = new MinhaClasse();
$novo = clone $original;
```

### Detalhes
- **Método mágico `__clone()`**: Você pode definir um método mágico `__clone()` na sua classe para executar ações adicionais quando um objeto é clonado.
- **Cópia superficial**: Propriedades que contêm objetos não são clonadas, mas referenciadas, o que pode levar a efeitos colaterais indesejados.

## Exemplos
### Exemplo Básico
```php
class Exemplo {
    public $propriedade1;
    public $propriedade2;

    public function __construct($p1, $p2) {
        $this->propriedade1 = $p1;
        $this->propriedade2 = $p2;
    }
}

$original = new Exemplo("Valor 1", "Valor 2");
$clonado = clone $original;

echo $clonado->propriedade1; // Saída: Valor 1
```

### Usando o Método `__clone()`
```php
class ExemploComClone {
    public $propriedade;
    public $objetoInterno;

    public function __construct($valor) {
        $this->propriedade = $valor;
        $this->objetoInterno = new stdClass();
    }

    public function __clone() {
        $this->objetoInterno = new stdClass(); // Cria uma nova instância ao clonar
    }
}

$original = new ExemploComClone("Valor");
$clonado = clone $original;

$clonado->objetoInterno->novaPropriedade = "Nova Propriedade";

echo $original->objetoInterno->novaPropriedade; // Saída: NULL
```

## Explicação
Um erro comum ao trabalhar com `clone` é esquecer que ele faz uma cópia superficial. Se você clona um objeto que contém referências a outros objetos, ambos os objetos (original e clonado) compartilharão essas referências. Isso pode causar comportamentos inesperados se você modificar as propriedades referenciadas. Para evitar isso, você pode implementar o método `__clone()` para garantir que as propriedades referenciadas sejam copiadas corretamente.

### Observações
- Sempre verifique se as propriedades que você deseja clonar são objetos, para garantir que não haverá referências indesejadas.
- O `clone` não é aplicável a tipos que não sejam objetos, como arrays ou tipos primitivos.

## Resumo em Uma Linha
O comando `clone` em PHP permite criar cópias superficiais de objetos, facilitando a manipulação de instâncias sem alterar o original.