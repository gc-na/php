<!--
Meta Description: # Acesso Protegido em PHP: Entenda o Modificador "protected" ## Sinopse O modificador de acesso "protected" em PHP permite que propriedades e métodos ...
Meta Keywords: protected, que, classe, php, acesso
-->

# Acesso Protegido em PHP: Entenda o Modificador "protected"

## Sinopse
O modificador de acesso "protected" em PHP permite que propriedades e métodos de uma classe sejam acessíveis apenas dentro da própria classe e em classes derivadas, promovendo um encapsulamento eficiente e controlado.

## Documentação
O modificador "protected" é uma das três visibilidades que o PHP oferece (as outras são "public" e "private"). Quando um método ou propriedade é declarado como "protected", ele pode ser acessado:

- Dentro da classe em que foi definido.
- Por classes que herdam da classe onde o método ou propriedade foi declarado.

### Finalidade
O uso do "protected" é essencial para o design orientado a objetos, pois permite que subclasses tenham acesso a métodos e propriedades que não devem ser expostos publicamente, mas que ainda são relevantes para a implementação da subclasse.

### Uso
Para declarar um método ou propriedade como "protected", utiliza-se a palavra-chave "protected" antes da declaração. Aqui está um exemplo básico:

```php
class Animal {
    protected $nome;

    protected function emitirSom() {
        return "Som do animal";
    }
}

class Cachorro extends Animal {
    public function getSom() {
        return $this->emitirSom();
    }
}
```

No exemplo acima, a propriedade `$nome` e o método `emitirSom()` são acessíveis apenas dentro da classe `Animal` e da classe `Cachorro`, que a estende.

## Exemplos
### Exemplo 1: Propriedade Protected
```php
class Carro {
    protected $modelo;

    public function __construct($modelo) {
        $this->modelo = $modelo;
    }
}

class Esportivo extends Carro {
    public function getModelo() {
        return $this->modelo; // Acesso permitido
    }
}

$carro = new Esportivo("Ferrari");
echo $carro->getModelo(); // Saída: Ferrari
```

### Exemplo 2: Método Protected
```php
class Conta {
    protected $saldo;

    public function __construct($saldoInicial) {
        $this->saldo = $saldoInicial;
    }

    protected function adicionarSaldo($valor) {
        $this->saldo += $valor;
    }
}

class ContaCorrente extends Conta {
    public function depositar($valor) {
        $this->adicionarSaldo($valor); // Acesso permitido
    }
}

$conta = new ContaCorrente(100);
$conta->depositar(50); // Acesso permitido, mas saldo não é acessível diretamente
```

## Explicação
Um erro comum ao usar "protected" é tentar acessar propriedades ou métodos protegidos de fora da classe ou de instâncias diretas, o que resultará em um erro. Além disso, a herança deve ser corretamente implementada para que subclasses possam acessar os membros protegidos.

### Armadilhas e Observações
- **Herança Múltipla**: O PHP não suporta herança múltipla. Portanto, se uma classe herdar de uma classe com métodos/propriedades "protected", ela não pode herdar de outra classe que também tenha membros "protected" com o mesmo nome.
- **Visibilidade**: É importante notar que "protected" não oferece segurança total, pois membros "protected" ainda podem ser acessados por subclasses, o que pode ser um ponto a considerar em projetos complexos.

## Resumo em Uma Linha
O modificador "protected" em PHP permite o acesso controlado a propriedades e métodos de uma classe apenas dentro da própria classe e suas subclasses.