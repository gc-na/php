<!--
Meta Description: # Comando "require" em PHP: Importando Arquivos de Forma Eficiente ## Sinopse O comando `require` em PHP é utilizado para incluir e avaliar um arquivo...
Meta Keywords: php, arquivo, require, que, script
-->

# Comando "require" em PHP: Importando Arquivos de Forma Eficiente

## Sinopse
O comando `require` em PHP é utilizado para incluir e avaliar um arquivo PHP em outro. Se o arquivo especificado não for encontrado, o `require` gera um erro fatal e interrompe a execução do script.

## Documentação
O `require` é uma das formas de inclusão de arquivos em PHP, permitindo que você modularize seu código e reutilize funções, classes e variáveis. Ele é especialmente útil para carregar arquivos de configuração, bibliotecas e outras partes do seu código que são necessárias para a execução do script.

### Propósito
O principal propósito do `require` é garantir que um arquivo seja incluído no seu script antes que ele continue sua execução. Isso é crucial quando o arquivo contém definições de funções ou classes que são necessárias para o funcionamento do código.

### Uso
A sintaxe básica do `require` é a seguinte:

```php
require 'caminho/para/o/arquivo.php';
```

Você pode usar caminhos relativos ou absolutos para especificar a localização do arquivo a ser incluído. É importante notar que, ao contrário do `include`, o `require` não continua a execução do script se o arquivo não for encontrado.

### Detalhes
- **Erros**: Um erro fatal será gerado se o arquivo não puder ser encontrado, interrompendo a execução do script.
- **Inclusão Múltipla**: Para evitar a inclusão de um arquivo mais de uma vez, você pode usar `require_once`, que inclui o arquivo apenas uma vez.
- **Escopo**: As variáveis definidas no arquivo incluído estarão disponíveis no escopo do arquivo que faz a inclusão.

## Exemplos
### Exemplo Básico
```php
// arquivo.php
function ola() {
    echo "Olá, Mundo!";
}

// script.php
require 'arquivo.php';
ola(); // Saída: Olá, Mundo!
```

### Uso de require em um Arquivo de Configuração
```php
// config.php
$db_host = 'localhost';
$db_user = 'root';
$db_pass = 'senha';

// index.php
require 'config.php';
echo $db_host; // Saída: localhost
```

### Diferenciando require e include
```php
// exemplo.php
require 'arquivo_inexistente.php'; // Gera um erro fatal
include 'arquivo_inexistente.php'; // Gera um aviso, mas o script continua
```

## Explicação
Um dos principais cuidados ao usar o `require` é garantir que o caminho do arquivo esteja correto. Um erro comum é esquecer de usar a extensão do arquivo (por exemplo, `.php`) ou especificar um caminho incorreto. Além disso, é importante considerar que o uso excessivo de `require` pode impactar a performance do seu script, especialmente se muitos arquivos forem incluídos desnecessariamente.

### Gotchas
- **Caminhos Relativos**: O caminho do arquivo é relativo ao diretório do script que está sendo executado, não ao diretório do arquivo que está fazendo a inclusão.
- **Performance**: O `require` pode impactar a performance se usado em loops ou em funções que são chamadas repetidamente.

## Resumo em Uma Linha
O comando `require` em PHP é utilizado para incluir arquivos necessários no script, interrompendo a execução se o arquivo não for encontrado.