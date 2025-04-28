<!--
Meta Description: # Estrutura de Repetição "for" em PHP: Guia Completo ## Sinopse A estrutura de repetição "for" em PHP permite a execução de um bloco de código repetid...
Meta Keywords: que, php, uma, código, loop
-->

# Estrutura de Repetição "for" em PHP: Guia Completo

## Sinopse
A estrutura de repetição "for" em PHP permite a execução de um bloco de código repetidamente, com base em uma condição definida, sendo ideal para iterações que requerem um número específico de repetições.

## Documentação
A estrutura "for" em PHP é uma das formas mais comuns de realizar loops, permitindo que o desenvolvedor execute um bloco de código várias vezes, com controle total sobre o número de iterações. A sintaxe básica do `for` é a seguinte:

```php
for (inicialização; condição; incremento) {
    // bloco de código a ser executado
}
```

### Componentes:
1. **Inicialização**: Define e inicializa uma variável de controle, que geralmente é um contador.
2. **Condição**: Um teste booleano que determina se o loop deve continuar. Se for verdadeiro, o bloco de código dentro do loop é executado.
3. **Incremento**: Atualiza a variável de controle após cada iteração do loop.

### Uso:
O loop `for` é amplamente utilizado quando o número de iterações é conhecido de antemão, como ao percorrer elementos de um array ou executar uma série de instruções repetidamente.

## Exemplos
### Exemplo Básico
```php
for ($i = 0; $i < 5; $i++) {
    echo "Número: $i\n";
}
```
*Este código imprime os números de 0 a 4.*

### Exemplo com Array
```php
$frutas = array("Maçã", "Banana", "Laranja");
for ($i = 0; $i < count($frutas); $i++) {
    echo "Fruta: $frutas[$i]\n";
}
```
*Este exemplo itera sobre um array de frutas e imprime cada uma delas.*

## Explicação
Um erro comum ao usar loops `for` é esquecer de atualizar a variável de controle, o que pode resultar em um loop infinito. Além disso, é importante garantir que a condição de término seja alcançada para evitar travamentos na execução do script. 

Outro ponto a ser observado é a utilização da função `count()`, que deve ser usada corretamente para evitar acesso a índices fora do limite do array. Em casos de arrays multidimensionais ou complexos, sempre verifique se a indexação é correta.

## Resumo em Uma Frase
O loop "for" em PHP é uma estrutura poderosa que permite a execução repetitiva de um bloco de código, ideal para iterações com um número fixo de repetições.