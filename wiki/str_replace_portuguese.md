<!--
Meta Description: # str_replace: A Função PHP para Substituição de Strings ## Sinopse A função `str_replace` em PHP é amplamente utilizada para substituir todas as ocor...
Meta Keywords: uma, str_replace, php, texto, função
-->

# str_replace: A Função PHP para Substituição de Strings

## Sinopse
A função `str_replace` em PHP é amplamente utilizada para substituir todas as ocorrências de uma substring específica dentro de uma string por outra substring, facilitando a manipulação de texto em aplicações web.

## Documentação

### Propósito
A função `str_replace` é projetada para substituir uma ou mais ocorrências de uma substring em uma string por outra substring. É uma ferramenta poderosa para a limpeza e formatação de dados textuais.

### Uso
A sintaxe da função `str_replace` é a seguinte:

```php
str_replace(mixed $search, mixed $replace, mixed $subject, int &$count = null): mixed
```

#### Parâmetros:
- **$search**: A substring ou um array de substrings que você deseja substituir.
- **$replace**: A substring ou um array de substrings que irá substituir o valor de `$search`. O número de elementos em `$replace` deve ser igual ao número de elementos em `$search`.
- **$subject**: A string ou um array de strings onde as substituições serão realizadas.
- **$count** (opcional): Se fornecido, será preenchido com o número de substituições realizadas.

#### Retorno:
A função retorna a string resultante após a substituição, ou um array de strings se o parâmetro `$subject` for um array.

## Exemplos

### Exemplo 1: Substituindo uma única ocorrência
```php
$texto = "Olá, Mundo!";
$resultado = str_replace("Mundo", "PHP", $texto);
echo $resultado; // Saída: Olá, PHP!
```

### Exemplo 2: Substituindo múltiplas ocorrências
```php
$texto = "A maçã é uma fruta. A maçã é deliciosa.";
$resultado = str_replace("maçã", "banana", $texto);
echo $resultado; // Saída: A banana é uma fruta. A banana é deliciosa.
```

### Exemplo 3: Usando arrays para substituições
```php
$texto = "As flores são bonitas.";
$resultado = str_replace(["flores", "bonitas"], ["árvores", "verdes"], $texto);
echo $resultado; // Saída: As árvores são verdes.
```

## Explicação
Um erro comum ao usar `str_replace` é não considerar a sensibilidade a maiúsculas e minúsculas. A função é sensível, portanto, "maçã" e "Maçã" são considerados diferentes. Além disso, ao substituir substrings em um array, é importante garantir que o número de elementos em `$search` e `$replace` seja o mesmo para evitar resultados inesperados.

É também importante notar que `str_replace` não modifica a string original; ela retorna uma nova string com as substituições realizadas. Portanto, se você quiser armazenar o resultado, deve atribuí-lo a uma nova variável ou à mesma variável.

## Resumo em Uma Frase
A função `str_replace` em PHP é uma ferramenta eficaz para substituir substrings em uma string, permitindo fácil manipulação e formatação de texto.