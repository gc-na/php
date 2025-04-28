<!--
Meta Description: # strpos: Função PHP para Localizar a Posição de uma Substring ## Sinopse A função `strpos` em PHP é utilizada para localizar a posição da primeira oc...
Meta Keywords: posição, php, strpos, uma, false
-->

# strpos: Função PHP para Localizar a Posição de uma Substring

## Sinopse
A função `strpos` em PHP é utilizada para localizar a posição da primeira ocorrência de uma substring dentro de uma string. É uma ferramenta essencial para manipulação de strings e análise de dados textuais.

## Documentação
A função `strpos` é definida na linguagem PHP como:

```php
strpos(string $haystack, string $needle, int $offset = 0): int|false
```

### Propósito
`strpos` serve para encontrar a posição em que uma substring (`needle`) aparece dentro de uma string maior (`haystack`). Caso a substring não seja encontrada, a função retorna `false`.

### Uso
- **$haystack**: A string onde você deseja procurar.
- **$needle**: A substring que você está tentando localizar.
- **$offset**: Opcional. Um valor inteiro que determina a partir de qual posição da string `haystack` a busca deve começar. O padrão é 0, ou seja, o início da string.

### Detalhes
- A posição retornada é baseada em zero. Isso significa que a primeira posição é 0, a segunda é 1, e assim por diante.
- Se a substring não for encontrada, a função retorna `false`, portanto, é importante tratar o retorno corretamente para evitar erros.

## Exemplos
### Exemplo Básico
```php
$frase = "Aprendendo PHP é divertido!";
$posição = strpos($frase, "PHP");

if ($posição !== false) {
    echo "A palavra 'PHP' foi encontrada na posição: $posição";
} else {
    echo "A palavra 'PHP' não foi encontrada.";
}
```

### Exemplo com Offset
```php
$frase = "Aprendendo PHP é divertido!";
$posição = strpos($frase, "e", 5); // Procura a letra 'e' a partir da posição 5

if ($posição !== false) {
    echo "A letra 'e' foi encontrada na posição: $posição";
} else {
    echo "A letra 'e' não foi encontrada.";
}
```

## Explicação
Ao usar a função `strpos`, um dos erros comuns é não verificar se o retorno é `false` corretamente. Como o valor 0 também é uma posição válida, é importante usar a comparação estrita (`!== false`) para garantir que a função não retorne falsos negativos.

Outro ponto a ser observado é que `strpos` é sensível a maiúsculas e minúsculas. Portanto, `strpos("Hello", "h")` retornará `false`, pois "H" e "h" são considerados diferentes.

## Resumo em Uma Linha
A função `strpos` em PHP localiza a posição da primeira ocorrência de uma substring em uma string, retornando `false` se não encontrada.