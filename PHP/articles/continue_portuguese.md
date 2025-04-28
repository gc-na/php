<!--
Meta Description: # A Instrução "continue" no PHP: Controle de Fluxo em Laços ## Sinopse A instrução `continue` no PHP é utilizada para interromper a iteração atual de ...
Meta Keywords: continue, loop, instrução, php, que
-->

# A Instrução "continue" no PHP: Controle de Fluxo em Laços

## Sinopse
A instrução `continue` no PHP é utilizada para interromper a iteração atual de um loop e avançar para a próxima iteração, permitindo um controle mais preciso sobre a execução de loops como `for`, `foreach`, `while` e `do-while`.

## Documentação
A instrução `continue` é um comando de controle de fluxo que permite pular a execução do restante do código dentro do loop atual e iniciar a próxima iteração. Isso é útil quando se deseja ignorar certas condições em um loop sem sair completamente dele.

### Uso
A sintaxe básica da instrução `continue` é a seguinte:

```php
continue;
```

Você também pode usar a instrução `continue` com um número opcional, que indica quantas iterações do loop devem ser puladas. Por exemplo, `continue 2;` fará com que o loop avance duas iterações.

### Detalhes
- **Tipo de Loop**: A instrução `continue` pode ser utilizada em loops `for`, `foreach`, `while` e `do-while`.
- **Nível de Continuação**: Se um número for especificado, ele deve ser um inteiro positivo e representa o número de níveis de loops a serem continuados. Isso é particularmente útil em loops aninhados.

## Exemplos
### Exemplo 1: Usando `continue` em um loop `for`
```php
for ($i = 0; $i < 10; $i++) {
    if ($i % 2 == 0) {
        continue; // Ignora os números pares
    }
    echo $i; // Exibe apenas números ímpares
}
```

### Exemplo 2: Usando `continue` em um loop `foreach`
```php
$array = [1, 2, 3, 4, 5];
foreach ($array as $value) {
    if ($value == 3) {
        continue; // Ignora o número 3
    }
    echo $value; // Exibe 1, 2, 4, 5
}
```

### Exemplo 3: Usando `continue` em um loop `while`
```php
$i = 0;
while ($i < 5) {
    $i++;
    if ($i == 2) {
        continue; // Ignora a iteração em que $i é 2
    }
    echo $i; // Exibe 1, 3, 4, 5
}
```

## Explicação
Embora a instrução `continue` seja bastante útil, existem algumas considerações a ter em mente:

- **Loop Aninhado**: Ao usar `continue` em loops aninhados, o número especificado (se houver) deve ser cuidadosamente considerado, pois ele se aplica ao nível do loop atual. Por exemplo, `continue 2;` em um loop interno fará com que o PHP pule duas iterações, indo para o loop externo.
- **Condicionais**: Sempre que `continue` é utilizado, deve-se garantir que a condição que está causando a interrupção da iteração seja bem definida, para evitar loops infinitos ou comportamentos inesperados.
- **Desempenho**: Em loops grandes, o uso excessivo de `continue` pode impactar o desempenho, especialmente se aplicado em condições complexas.

## Resumo em Uma Frase
A instrução `continue` no PHP permite pular a iteração atual de um loop e prosseguir para a próxima, facilitando o controle do fluxo de execução.