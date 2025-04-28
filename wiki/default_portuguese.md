<!--
Meta Description: # Default em PHP: Compreendendo o Comportamento de Valores Padrão ## Sinopse O termo "default" em PHP refere-se à atribuição de valores padrão a parâm...
Meta Keywords: padrão, valores, php, função, parâmetros
-->

# Default em PHP: Compreendendo o Comportamento de Valores Padrão

## Sinopse
O termo "default" em PHP refere-se à atribuição de valores padrão a parâmetros de funções, permitindo que desenvolvedores definam um comportamento esperado quando argumentos não são fornecidos.

## Documentação
Em PHP, os parâmetros de função podem ter valores padrão, que são utilizados quando nenhum argumento correspondente é passado na chamada da função. Isso é particularmente útil para simplificar o uso de funções e garantir que elas funcionem corretamente mesmo com entradas incompletas.

### Propósito
O objetivo de usar valores padrão é tornar as funções mais flexíveis e reduzir a necessidade de sobrecarga, permitindo que os desenvolvedores especifiquem comportamentos padrão que serão aplicados automaticamente.

### Uso
Para definir um valor padrão em um parâmetro de função, basta atribuí-lo na declaração da função. A sintaxe básica é a seguinte:

```php
function nomeDaFuncao($parametro1 = valorPadrao) {
    // corpo da função
}
```

### Detalhes
- Valores padrão podem ser de qualquer tipo de dado, incluindo strings, números, arrays, e até mesmo objetos.
- Se um valor padrão não for fornecido e o parâmetro for omitido na chamada da função, o PHP emitirá um erro fatal.
- Valores padrão devem ser especificados à direita dos parâmetros na lista de parâmetros.

## Exemplos

### Exemplo 1: Função Simples com Valor Padrão
```php
function saudacao($nome = "Visitante") {
    return "Olá, $nome!";
}

echo saudacao(); // Saída: Olá, Visitante!
echo saudacao("Maria"); // Saída: Olá, Maria!
```

### Exemplo 2: Valores Padrão em Funções com Múltiplos Parâmetros
```php
function calcularPreco($preco, $desconto = 0) {
    return $preco - ($preco * $desconto);
}

echo calcularPreco(100); // Saída: 100
echo calcularPreco(100, 0.2); // Saída: 80
```

### Exemplo 3: Usando Arrays como Valores Padrão
```php
function listarFrutas($frutas = ["Maçã", "Banana", "Laranja"]) {
    return implode(", ", $frutas);
}

echo listarFrutas(); // Saída: Maçã, Banana, Laranja
echo listarFrutas(["Uva", "Pera"]); // Saída: Uva, Pera
```

## Explicação
Um erro comum ao trabalhar com valores padrão é tentar usar uma variável que não foi inicializada como valor padrão. Isso resultará em um erro. Além disso, é importante lembrar que todos os parâmetros com valor padrão devem ser definidos após os parâmetros obrigatórios. Ignorar essa regra resultará em um erro de sintaxe.

Outro ponto a considerar é a mutabilidade de tipos. Quando um array é usado como valor padrão, qualquer modificação desse array dentro da função afetará o valor padrão em chamadas subsequentes, pois ele é referenciado.

## Resumo em Uma Linha
O "default" em PHP permite definir valores padrão para parâmetros de funções, garantindo flexibilidade e simplificação no uso de chamadas de função.