<!--
Meta Description: # strlen: Função PHP para Calcular o Comprimento de Strings ## Sinopse A função `strlen` em PHP é utilizada para determinar o comprimento de uma strin...
Meta Keywords: string, strlen, função, comprimento, caracteres
-->

# strlen: Função PHP para Calcular o Comprimento de Strings

## Sinopse
A função `strlen` em PHP é utilizada para determinar o comprimento de uma string, ou seja, o número de caracteres que ela contém. Essa função é essencial para manipulação de strings e validação de dados.

## Documentação
A função `strlen` recebe uma string como parâmetro e retorna um inteiro que representa a quantidade de caracteres presentes nessa string.

### Sintaxe
```php
int strlen(string $string);
```

### Parâmetros
- **$string**: A string cuja extensão você deseja calcular. Este parâmetro é obrigatório.

### Retorno
A função retorna um inteiro que representa o número de caracteres na string. Se a string estiver vazia, o retorno será 0.

### Exceções
A função `strlen` não gera erros, mesmo que a string fornecida seja `null`. Nesse caso, o retorno será 0.

## Exemplos

### Exemplo 1: Uso básico da função strlen
```php
$texto = "Olá, Mundo!";
$comprimento = strlen($texto);
echo "O comprimento da string é: " . $comprimento; // Saída: O comprimento da string é: 12
```

### Exemplo 2: String vazia
```php
$textoVazio = "";
$comprimentoVazio = strlen($textoVazio);
echo "O comprimento da string vazia é: " . $comprimentoVazio; // Saída: O comprimento da string vazia é: 0
```

### Exemplo 3: Contando caracteres especiais
```php
$textoComEspeciais = "Olá! Como você está?";
$comprimentoEspeciais = strlen($textoComEspeciais);
echo "O comprimento da string com caracteres especiais é: " . $comprimentoEspeciais; // Saída: O comprimento da string com caracteres especiais é: 23
```

## Explicação
Embora a função `strlen` seja bastante simples de usar, existem alguns pontos a serem observados:

1. **Codificação de Caracteres**: A função `strlen` conta o número de bytes, não o número de caracteres em codificações multibyte (como UTF-8). Por exemplo, um caractere acentuado pode ser representado por mais de um byte.
   
2. **Strings Nulas**: Se você passar uma variável que não foi inicializada, `strlen` irá retornar 0, pois a variável é considerada uma string vazia.

3. **Strings em Branco**: Strings que consistem apenas em espaços em branco também são contabilizadas. Por exemplo, `strlen("   ")` retornará 3.

4. **Performance**: A função é bastante eficiente para strings curtas; no entanto, seu desempenho pode ser afetado por strings extremamente longas ou em loops que chamam a função repetidamente.

## Resumo em Uma Linha
A função `strlen` em PHP retorna o número de caracteres de uma string, sendo crucial para manipulação e validação de dados.