<!--
Meta Description: # O Comando "extends" em PHP: Herança de Classes na Programação Orientada a Objetos ## Sinopse O comando `extends` em PHP é fundamental para a impleme...
Meta Keywords: classe, uma, extends, php, métodos
-->

# O Comando "extends" em PHP: Herança de Classes na Programação Orientada a Objetos

## Sinopse
O comando `extends` em PHP é fundamental para a implementação da herança na programação orientada a objetos. Ele permite que uma classe herde propriedades e métodos de outra, promovendo reutilização de código e organização em projetos de software.

## Documentação
O `extends` é usado na definição de classes em PHP para criar uma relação de herança entre uma classe pai (ou superclasse) e uma classe filha (ou subclasse). Quando uma classe herda de outra, ela obtém todos os métodos e propriedades da classe pai, podendo também adicionar novos ou sobrescrever os existentes.

### Propósito
O principal propósito do `extends` é permitir a criação de hierarquias de classes que facilitam a reutilização de código e a implementação de funcionalidades comuns.

### Uso
Para utilizar o `extends`, a sintaxe básica é a seguinte:

```php
class ClassePai {
    // Propriedades e métodos da classe pai
}

class ClasseFilha extends ClassePai {
    // Propriedades e métodos da classe filha
}
```

Com isso, `ClasseFilha` terá acesso a todos os métodos e propriedades definidos em `ClassePai`.

### Detalhes
- A herança em PHP é unidirecional; uma classe pode estender apenas uma classe pai.
- O PHP suporta herança múltipla através de interfaces, mas uma classe não pode estender mais de uma classe ao mesmo tempo.
- Métodos da classe pai podem ser acessados na classe filha usando `parent::nomeDoMetodo()`.

## Exemplos
### Exemplo Básico de Herança

```php
class Animal {
    public function fazerSom() {
        return "Som do animal";
    }
}

class Cachorro extends Animal {
    public function fazerSom() {
        return "Au Au";
    }
}

$cachorro = new Cachorro();
echo $cachorro->fazerSom(); // Saída: Au Au
```

### Exemplo com Propriedades

```php
class Veiculo {
    public $cor;

    public function __construct($cor) {
        $this->cor = $cor;
    }
}

class Carro extends Veiculo {
    public $modelo;

    public function __construct($cor, $modelo) {
        parent::__construct($cor);
        $this->modelo = $modelo;
    }
}

$carro = new Carro("vermelho", "Fusca");
echo $carro->cor; // Saída: vermelho
echo $carro->modelo; // Saída: Fusca
```

## Explicação
### Armadilhas Comuns
- **Sobrescrita de Métodos**: Ao sobrescrever métodos da classe pai, é importante usar `parent::` se você precisar manter a funcionalidade original do método. Isso evita perda de comportamento desejado.
- **Construtores**: Se a classe pai possui um construtor, a classe filha deve chamar `parent::__construct()` para garantir que a inicialização ocorra corretamente.
- **Visibilidade**: Métodos e propriedades com visibilidade `private` na classe pai não podem ser acessados diretamente na classe filha.

## Resumo em Uma Linha
O comando `extends` em PHP permite a herança de classes, promovendo a reutilização de código e a organização na programação orientada a objetos.