<!--
Meta Description: # Uso de Static em PHP: O Guia Completo ## Sinopse O termo "static" em PHP refere-se a um modificador que permite que propriedades e métodos de uma cl...
Meta Keywords: static, classe, que, php, uma
-->

# Uso de Static em PHP: O Guia Completo

## Sinopse
O termo "static" em PHP refere-se a um modificador que permite que propriedades e métodos de uma classe sejam acessados sem a necessidade de instanciar a classe. Isso é útil para criar métodos e variáveis que são compartilhados entre todas as instâncias de uma classe.

## Documentação
O modificador `static` em PHP serve para definir propriedades e métodos que pertencem à classe em si, e não a uma instância específica da classe. Isso significa que você pode acessar esses membros usando o operador de resolução de escopo `::`, sem precisar instanciar a classe.

### Propósito
O objetivo do `static` é permitir que desenvolvedores criem membros de classe que são comuns a todas as instâncias, facilitando o compartilhamento de dados e comportamentos.

### Uso
Para declarar uma propriedade ou método como `static`, você deve preceder a declaração com a palavra-chave `static`. 

**Exemplo de declaração de método e propriedade estáticos:**

```php
class Contador {
    public static $contador = 0;

    public static function incrementar() {
        self::$contador++;
    }
}
```

### Acesso
Os membros estáticos podem ser acessados da seguinte forma:

```php
Contador::incrementar();
echo Contador::$contador; // Saída: 1
```

## Exemplos

### Exemplo 1: Propriedades Estáticas
```php
class ExemploStatic {
    public static $mensagem = "Olá, Mundo!";

    public static function mostrarMensagem() {
        echo self::$mensagem;
    }
}

ExemploStatic::mostrarMensagem(); // Saída: Olá, Mundo!
```

### Exemplo 2: Contador de Instâncias
```php
class Instancia {
    public static $numeroDeInstancias = 0;

    public function __construct() {
        self::$numeroDeInstancias++;
    }

    public static function getNumeroDeInstancias() {
        return self::$numeroDeInstancias;
    }
}

new Instancia();
new Instancia();
echo Instancia::getNumeroDeInstancias(); // Saída: 2
```

## Explicação
Embora o uso de `static` seja bastante útil, existem algumas considerações a serem feitas:

- **Escopo**: Membros estáticos não podem acessar diretamente `$this`, pois não pertencem a uma instância da classe.
- **Herança**: Métodos estáticos podem ser sobrescritos em classes filhas, mas o comportamento pode ser diferente do esperado ao chamar métodos estáticos da classe pai.
- **Testes**: Membros estáticos podem dificultar testes unitários, uma vez que seu estado é compartilhado entre todas as instâncias.

## Resumo em Uma Linha
O modificador `static` em PHP permite que propriedades e métodos de uma classe sejam acessados sem a necessidade de instanciar a classe, promovendo a reutilização e o compartilhamento de dados.