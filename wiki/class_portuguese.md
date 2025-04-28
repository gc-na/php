<!--
Meta Description: # Classe em PHP: Entenda o Pilar da Programação Orientada a Objetos ## Sinopse A classe em PHP é um dos principais componentes da programação orientad...
Meta Keywords: classe, public, php, modelo, objetos
-->

# Classe em PHP: Entenda o Pilar da Programação Orientada a Objetos

## Sinopse
A classe em PHP é um dos principais componentes da programação orientada a objetos (POO), permitindo a criação de objetos que encapsulam dados e comportamentos, facilitando a organização e reutilização do código.

## Documentação
Uma classe em PHP serve como um molde para a criação de objetos. Ela define propriedades (atributos) e métodos (funções) que os objetos criados a partir dessa classe podem utilizar. A POO em PHP ajuda a estruturar o código de forma modular e intuitiva, aumentando a manutenibilidade e a escalabilidade das aplicações.

### Estrutura Básica de uma Classe
```php
class NomeDaClasse {
    // Atributos
    public $atributo1;
    private $atributo2;

    // Construtor
    public function __construct($valor1, $valor2) {
        $this->atributo1 = $valor1;
        $this->atributo2 = $valor2;
    }

    // Métodos
    public function metodoPublico() {
        return "Este é um método público.";
    }

    private function metodoPrivado() {
        return "Este é um método privado.";
    }
}
```

### Instanciando uma Classe
Para criar um objeto a partir de uma classe, utiliza-se a palavra-chave `new`:
```php
$objeto = new NomeDaClasse('valor1', 'valor2');
```

## Exemplos
### Exemplo 1: Classe Básica
```php
class Carro {
    public $marca;
    public $modelo;

    public function __construct($marca, $modelo) {
        $this->marca = $marca;
        $this->modelo = $modelo;
    }

    public function detalhes() {
        return "Carro: {$this->marca} - Modelo: {$this->modelo}";
    }
}

$meuCarro = new Carro('Toyota', 'Corolla');
echo $meuCarro->detalhes(); // Saída: Carro: Toyota - Modelo: Corolla
```

### Exemplo 2: Herança
```php
class Veiculo {
    public $tipo;

    public function __construct($tipo) {
        $this->tipo = $tipo;
    }

    public function mostrarTipo() {
        return "Tipo: {$this->tipo}";
    }
}

class Moto extends Veiculo {
    public function __construct($modelo) {
        parent::__construct('Moto');
        $this->modelo = $modelo;
    }
}

$moto = new Moto('Yamaha');
echo $moto->mostrarTipo(); // Saída: Tipo: Moto
```

## Explicação
Um dos erros comuns ao trabalhar com classes em PHP é não entender o escopo de visibilidade dos atributos e métodos. Atributos ou métodos definidos como `private` não podem ser acessados fora da classe, o que pode levar a confusões se não for bem compreendido. Além disso, é importante lembrar que uma classe deve ser definida antes de ser utilizada, e que a palavra-chave `new` deve ser utilizada corretamente para instanciar objetos.

Outro ponto a ser destacado é o conceito de herança, que permite criar novas classes a partir de classes existentes, reutilizando código e facilitando a extensão das funcionalidades.

## Resumo em Uma Linha
A classe em PHP é a estrutura fundamental da programação orientada a objetos, permitindo a criação de objetos que encapsulam dados e comportamentos de forma organizada e reutilizável.