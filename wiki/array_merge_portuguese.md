<!--
Meta Description: # array_merge: Função PHP para Mesclar Arrays de Forma Eficiente ## Sinopse A função `array_merge` do PHP é utilizada para combinar dois ou mais array...
Meta Keywords: array, arrays, array_merge, chaves, função
-->

# array_merge: Função PHP para Mesclar Arrays de Forma Eficiente

## Sinopse
A função `array_merge` do PHP é utilizada para combinar dois ou mais arrays em um único array, mesclando seus elementos e preservando os valores de chaves numéricas.

## Documentação
A função `array_merge` é uma ferramenta fundamental na manipulação de arrays em PHP. Sua principal finalidade é unir múltiplos arrays, concatenando seus elementos. Essa função é especialmente útil quando se lida com dados que precisam ser combinados em uma única estrutura.

### Uso
A sintaxe básica da função `array_merge` é a seguinte:

```php
array_merge(array $array1, array $array2, array ...$arrays): array
```

- **$array1**: O primeiro array a ser mesclado.
- **$array2**: O segundo array a ser mesclado.
- **$arrays**: Um número variável de outros arrays que podem ser mesclados.

### Detalhes
- Se duas ou mais arrays tiverem chaves numéricas, os valores de ambas as arrays serão renumerados de forma sequencial.
- Se houver chaves associativas duplicadas, os valores do último array sobrescreverão os valores anteriores.
- A função retorna um novo array que contém todos os elementos dos arrays passados como argumentos.

## Exemplos

### Exemplo 1: Mesclando Arrays Simples
```php
$array1 = array("a" => "maçã", "b" => "banana");
$array2 = array("c" => "cereja", "d" => "damasco");

$resultado = array_merge($array1, $array2);
print_r($resultado);
```
**Saída:**
```
Array
(
    [a] => maçã
    [b] => banana
    [c] => cereja
    [d] => damasco
)
```

### Exemplo 2: Sobrescrita de Chaves
```php
$array1 = array("a" => "maçã", "b" => "banana");
$array2 = array("b" => "laranja", "c" => "cereja");

$resultado = array_merge($array1, $array2);
print_r($resultado);
```
**Saída:**
```
Array
(
    [a] => maçã
    [b] => laranja
    [c] => cereja
)
```

### Exemplo 3: Mesclando Vários Arrays
```php
$array1 = array("a" => "maçã");
$array2 = array("b" => "banana");
$array3 = array("c" => "cereja");

$resultado = array_merge($array1, $array2, $array3);
print_r($resultado);
```
**Saída:**
```
Array
(
    [a] => maçã
    [b] => banana
    [c] => cereja
)
```

## Explicação
Um dos principais pontos a se ter em mente ao utilizar `array_merge` é o comportamento em relação às chaves. Quando arrays com chaves numéricas são mesclados, os índices não se mantêm; ao invés disso, os elementos são renumerados a partir de zero. Para arrays com chaves associativas, a última chave encontrada na mesclagem prevalece. Isso pode levar a resultados inesperados se não for cuidadosamente considerado.

Além disso, se nenhum array for fornecido à função, `array_merge` retorna um array vazio. E, caso apenas um array seja fornecido, ele retorna uma cópia desse array sem qualquer modificação.

## Resumo em Uma Frase
A função `array_merge` em PHP permite combinar múltiplos arrays em um único array, renumerando chaves numéricas e sobrescrevendo valores de chaves associativas duplicadas.