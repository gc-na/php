<!--
Meta Description: # Explode: Função PHP para Dividir Strings em Arrays ## Sinopse A função `explode` no PHP é utilizada para dividir uma string em um array, com base em...
Meta Keywords: string, função, array, explode, php
-->

# Explode: Função PHP para Dividir Strings em Arrays

## Sinopse
A função `explode` no PHP é utilizada para dividir uma string em um array, com base em um delimitador especificado. É uma ferramenta essencial para manipulação de strings em diversas aplicações web.

## Documentação
A função `explode` permite que desenvolvedores que trabalham com PHP quebrem uma string em partes menores, gerando um array. A sintaxe da função é a seguinte:

```php
array explode ( string $delimiter , string $string [, int $limit = PHP_INT_MAX ] )
```

### Parâmetros
- **$delimiter**: O caractere ou sequência de caracteres que será utilizado como delimitador para dividir a string.
- **$string**: A string que se deseja dividir.
- **$limit** (opcional): Um inteiro que determina quantas partes o array resultante pode conter. O padrão é `PHP_INT_MAX`, o que significa que não há limite.

### Retorno
A função retorna um array contendo as partes da string original. Se o delimitador não for encontrado, a função retorna um array contendo a string original.

## Exemplos

### Exemplo Básico
```php
$frase = "PHP é uma linguagem de script";
$partes = explode(" ", $frase);
print_r($partes);
```
**Saída:**
```
Array
(
    [0] => PHP
    [1] => é
    [2] => uma
    [3] => linguagem
    [4] => de
    [5] => script
)
```

### Exemplo com Limite
```php
$dados = "nome;idade;cidade;estado";
$array_dados = explode(";", $dados, 3);
print_r($array_dados);
```
**Saída:**
```
Array
(
    [0] => nome
    [1] => idade
    [2] => cidade;estado
)
```

## Explicação
Ao utilizar a função `explode`, é importante ter em mente algumas armadilhas comuns:
- **Delimitador Inexistente**: Se o delimitador não estiver presente na string, o resultado será um array com a string original como seu único elemento.
- **Limite Negativo**: Se um limite negativo for fornecido, o comportamento pode ser inesperado, pois a função irá ignorar as últimas partes da string.
- **Espaços em Branco**: Se o delimitador for um espaço e houver múltiplos espaços consecutivos, o resultado pode incluir elementos vazios no array. Para evitar isso, considere utilizar a função `array_filter()` após o `explode`.

## Resumo em Uma Linha
A função `explode` no PHP é uma ferramenta poderosa para dividir strings em arrays com base em um delimitador especificado.