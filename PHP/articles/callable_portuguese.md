<!--
Meta Description: # Callable em PHP: Entenda como Funciona e Como Utilizá-lo ## Sinopse O termo "callable" em PHP refere-se a qualquer coisa que pode ser chamada como u...
Meta Keywords: php, funções, callable, objetos, como
-->

# Callable em PHP: Entenda como Funciona e Como Utilizá-lo

## Sinopse
O termo "callable" em PHP refere-se a qualquer coisa que pode ser chamada como uma função. Isso inclui funções globais, métodos de classe, e objetos que implementam a interface `__invoke`. Neste artigo, vamos explorar a definição, uso e exemplos práticos de como utilizar callables em PHP.

## Documentação
### O que é Callable?
Em PHP, um callable é um tipo de dado que representa uma função ou método que pode ser invocado. A verificação de um callable pode ser feita usando a função `is_callable()`. O uso de callables é comum em programação orientada a objetos e em funções de alta ordem, onde funções podem ser passadas como argumentos.

### Como Usar Callable
Um callable pode ser usado de várias formas:
1. **Funções Globais**: Você pode referenciar funções definidas no escopo global.
2. **Métodos de Classe**: Referenciar métodos de uma classe usando arrays.
3. **Objetos Invocáveis**: Objetos que implementam a interface `__invoke` podem ser chamados como funções.

#### Sintaxe
- Para funções globais:
  ```php
  function minhaFuncao() {
      return "Olá, Mundo!";
  }
  ```

- Para métodos de classe:
  ```php
  class MinhaClasse {
      public function meuMetodo() {
          return "Olá, Classe!";
      }
  }
  ```

- Para objetos invocáveis:
  ```php
  class MeuObjeto {
      public function __invoke() {
          return "Olá, Objeto!";
      }
  }
  ```

## Exemplos
### 1. Usando uma Função Global
```php
function somar($a, $b) {
    return $a + $b;
}

$funcao = 'somar';
echo $funcao(2, 3); // Saída: 5
```

### 2. Usando um Método de Classe
```php
class Calculadora {
    public function multiplicar($a, $b) {
        return $a * $b;
    }
}

$calculadora = new Calculadora();
$metodo = [$calculadora, 'multiplicar'];
echo $metodo(4, 5); // Saída: 20
```

### 3. Usando um Objeto Invocável
```php
class Saudar {
    public function __invoke($nome) {
        return "Olá, " . $nome;
    }
}

$saudacao = new Saudar();
echo $saudacao("Maria"); // Saída: Olá, Maria
```

## Explicação
### Armadilhas Comuns e Dicas
- **Verificação de Callable**: Sempre verifique se um callable é válido usando `is_callable()` antes de chamá-lo para evitar erros de tempo de execução.
- **Escopo de Funções**: Funções definidas em classes não podem ser chamadas diretamente pelo nome; você deve referenciá-las através de uma instância da classe.
- **Objetos Invocáveis**: Certifique-se de implementar corretamente o método `__invoke` em objetos que você deseja chamar como funções.

## Resumo em Uma Frase
O callable em PHP permite a invocação de funções, métodos e objetos invocáveis, proporcionando flexibilidade em programação funcional e orientada a objetos.