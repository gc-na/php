<!--
Meta Description: # json_decode: Descodificando JSON em PHP ## Sinopse A função `json_decode` em PHP é utilizada para converter strings JSON em variáveis do tipo PHP, p...
Meta Keywords: json, php, dados, json_decode, função
-->

# json_decode: Descodificando JSON em PHP

## Sinopse
A função `json_decode` em PHP é utilizada para converter strings JSON em variáveis do tipo PHP, permitindo a manipulação de dados estruturados de forma simples e eficaz.

## Documentação
A função `json_decode` é fundamental no processamento de dados JSON em aplicações PHP. O JSON (JavaScript Object Notation) é um formato leve e amplamente utilizado para troca de dados entre servidores e clientes. A função `json_decode` transforma uma string JSON em um objeto ou array associativo do PHP, facilitando o acesso e a manipulação dos dados.

### Sintaxe
```php
json_decode(string $json, bool $associative = false, int $depth = 512, int $options = 0);
```

### Parâmetros
- **string $json**: A string JSON que você deseja decodificar.
- **bool $associative**: Se definido como `true`, a função retornará um array associativo. Se `false`, retornará um objeto. O padrão é `false`.
- **int $depth**: Profundidade máxima da decodificação. O padrão é 512.
- **int $options**: Um conjunto de opções de decodificação. O padrão é 0.

### Retorno
A função retorna um objeto ou um array associativo, dependendo do segundo parâmetro. Se a string JSON não puder ser decodificada, a função retornará `null`.

## Exemplos

### Exemplo 1: Decodificando um JSON simples
```php
$json = '{"nome": "João", "idade": 30}';
$dados = json_decode($json);
echo $dados->nome; // Saída: João
```

### Exemplo 2: Decodificando um JSON em um array associativo
```php
$json = '{"nome": "Maria", "idade": 25}';
$dados = json_decode($json, true);
echo $dados['nome']; // Saída: Maria
```

### Exemplo 3: Erro na decodificação
```php
$json = '{"nome": "Carlos", "idade": 28'; // JSON inválido
$dados = json_decode($json);
if (json_last_error() !== JSON_ERROR_NONE) {
    echo 'Erro na decodificação: ' . json_last_error_msg(); // Saída: Erro na decodificação: Sintaxe JSON inválida
}
```

## Explicação
Um dos erros mais comuns ao usar `json_decode` é fornecer uma string JSON malformada, resultando em um retorno `null` e um código de erro que pode ser verificado com a função `json_last_error()`. Além disso, ao decodificar JSON com objetos, é importante lembrar que, se não for utilizado o parâmetro `$associative`, o resultado será um objeto PHP, e não um array. Isso pode levar a confusões ao acessar os dados.

Outro ponto a ser considerado é a profundidade da estrutura JSON. Estruturas muito complexas podem ultrapassar a profundidade padrão e requerer um ajuste no parâmetro `$depth`.

## Resumo em uma Linha
A função `json_decode` em PHP é uma ferramenta essencial para converter strings JSON em variáveis PHP, permitindo fácil manipulação de dados.