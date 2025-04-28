<!--
Meta Description: # Const: Definição e Uso em PHP ## Sinopse A palavra-chave `const` em PHP é utilizada para definir constantes de forma eficiente e segura, permitindo ...
Meta Keywords: const, constantes, php, que, são
-->

# Const: Definição e Uso em PHP

## Sinopse
A palavra-chave `const` em PHP é utilizada para definir constantes de forma eficiente e segura, permitindo que valores imutáveis sejam utilizados ao longo da execução do código.

## Documentação
### Propósito
A palavra-chave `const` é empregada para declarar constantes em PHP. Constantes são identificadores que possuem um valor fixo e não podem ser alterados após a sua declaração. Diferentemente das variáveis, as constantes são acessíveis em qualquer lugar do seu script, desde que estejam no mesmo contexto de escopo.

### Uso
A sintaxe básica para definir uma constante utilizando `const` é:

```php
const NOME_CONSTANTE = 'valor';
```

As constantes devem seguir algumas regras:
- O nome da constante deve começar com uma letra ou um sublinhado.
- O nome pode conter letras, números e sublinhados, mas não pode conter espaços.
- As constantes são case-sensitive, ou seja, `NOME_CONSTANTE` e `nome_constante` são consideradas diferentes.

### Detalhes
As constantes definidas com `const` são automaticamente globais e podem ser acessadas em qualquer parte do script. Além disso, `const` pode ser usado apenas em escopos de classe, ao contrário da função `define()`, que pode ser utilizada em qualquer lugar do código.

## Exemplos

### Exemplo Básico
```php
const PI = 3.14;

echo PI; // Saída: 3.14
```

### Exemplo em Classe
```php
class Circulo {
    const PI = 3.14;

    public function calcularArea($raio) {
        return self::PI * ($raio ** 2);
    }
}

$circulo = new Circulo();
echo $circulo->calcularArea(5); // Saída: 78.5
```

## Explicação
### Armadilhas Comuns
- **Escopo**: Lembre-se de que constantes definidas com `const` em uma classe só podem ser acessadas usando `self::` ou `NomeDaClasse::`. Se você tentar acessar diretamente, ocorrerá um erro.
- **Valores Dinâmicos**: Constantes não podem ser definidas com valores que dependem de variáveis ou expressões dinâmicas. Elas devem ser definidas com valores literais.
  
### Observações Adicionais
- A partir do PHP 7, é possível definir constantes de array utilizando a função `define()`, mas `const` ainda não suporta esta funcionalidade.
- As constantes são frequentemente utilizadas para valores que não devem mudar ao longo da execução, como configurações de ambiente e parâmetros de configuração.

## Resumo em Uma Frase
A palavra-chave `const` em PHP é utilizada para declarar constantes que possuem valores imutáveis e são acessíveis globalmente no contexto de escopo.