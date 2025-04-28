<!--
Meta Description: # "implements" en PHP: Comprendiendo la Interfaz en Programación Orientada a Objetos ## Sinopsis La palabra clave `implements` en PHP se utiliza para ...
Meta Keywords: interfaz, una, que, interfaces, métodos
-->

# "implements" en PHP: Comprendiendo la Interfaz en Programación Orientada a Objetos

## Sinopsis
La palabra clave `implements` en PHP se utiliza para indicar que una clase implementa una o más interfaces, permitiendo la creación de clases que cumplen con un contrato específico de métodos definidos en dichas interfaces.

## Documentación
En PHP, las interfaces son un componente fundamental de la Programación Orientada a Objetos (POO). Una interfaz es un conjunto de métodos que una clase debe implementar. La palabra clave `implements` se utiliza en la declaración de clases para especificar que la clase en cuestión está comprometiéndose a implementar los métodos definidos en la interfaz.

### Propósito
El uso de interfaces proporciona un medio para definir un comportamiento que debe ser compartido por diferentes clases, promoviendo la reutilización del código y la flexibilidad en el diseño del software.

### Uso
Para utilizar `implements`, primero se debe definir una interfaz utilizando la palabra clave `interface`. Luego, una clase puede ser declarada para implementar esa interfaz usando `implements` seguido del nombre de la interfaz.

### Detalles
- Una clase puede implementar múltiples interfaces separando los nombres de las mismas con comas.
- Las interfaces no pueden contener implementaciones de métodos, solo las declaraciones.
- Las clases que implementan una interfaz deben definir todos los métodos declarados en la interfaz, de lo contrario, se producirá un error.

## Ejemplos

### Ejemplo 1: Implementar una sola interfaz
```php
interface Vehiculo {
    public function acelerar();
    public function frenar();
}

class Coche implements Vehiculo {
    public function acelerar() {
        echo "El coche está acelerando.";
    }

    public function frenar() {
        echo "El coche está frenando.";
    }
}
```

### Ejemplo 2: Implementar múltiples interfaces
```php
interface Volador {
    public function volar();
}

interface Acuatico {
    public function nadar();
}

class Pato implements Volador, Acuatico {
    public function volar() {
        echo "El pato está volando.";
    }

    public function nadar() {
        echo "El pato está nadando.";
    }
}
```

## Explicación
Al implementar interfaces, es importante tener en cuenta que:

- **Métodos Obligatorios**: Todos los métodos declarados en la interfaz deben ser implementados en la clase. Si falta alguno, PHP lanzará un error de tiempo de compilación.
- **Visibilidad de Métodos**: Los métodos de la interfaz deben ser públicos en la clase que los implementa.
- **Herencia de Interfaces**: Una interfaz puede extender otra interfaz, lo que permite la creación de jerarquías de interfaces. Las clases que implementan la interfaz hija también deben implementar los métodos de la interfaz padre.

## Resumen en una Línea
La palabra clave `implements` en PHP permite que una clase cumpla con el contrato de métodos definidos en una o más interfaces, facilitando la programación orientada a objetos.