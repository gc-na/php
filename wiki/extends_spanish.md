<!--
Meta Description: # Extends en PHP: Herencia de Clases en Programación Orientada a Objetos ## Sinopsis El término "extends" en PHP se utiliza para implementar la herenc...
Meta Keywords: clase, métodos, padre, tipo, extends
-->

# Extends en PHP: Herencia de Clases en Programación Orientada a Objetos

## Sinopsis
El término "extends" en PHP se utiliza para implementar la herencia en la programación orientada a objetos (POO). Permite que una clase derive de otra, reutilizando y extendiendo funcionalidades.

## Documentación
La palabra clave `extends` se utiliza en la declaración de clases para indicar que una clase (subclase o clase hija) hereda los métodos y propiedades de otra clase (superclase o clase padre). La herencia es un pilar fundamental de la POO que permite a los desarrolladores crear jerarquías de clases, facilitando la reutilización de código y la organización de programas complejos.

### Propósito
El propósito de `extends` es promover la reutilización del código, la organización y la creación de relaciones jerárquicas entre clases. A través de la herencia, las clases hijas pueden acceder a los métodos y propiedades públicos y protegidos de la clase padre.

### Uso
La sintaxis para declarar una clase que extiende otra es la siguiente:

```php
class ClasePadre {
    // Métodos y propiedades de la clase padre
}

class ClaseHija extends ClasePadre {
    // Métodos y propiedades de la clase hija
}
```

### Detalles
- **Métodos y Propiedades**: La clase hija hereda todos los métodos y propiedades de la clase padre, lo que le permite utilizarlos directamente.
- **Sobrescritura**: La clase hija puede redefinir métodos de la clase padre, lo que se conoce como sobrescritura de métodos.
- **Constructor**: Si la clase padre tiene un constructor, debe ser llamado explícitamente en la clase hija usando `parent::__construct()`.
- **Visibilidad**: Solo los métodos y propiedades públicos y protegidos de la clase padre son accesibles desde la clase hija.

## Ejemplos
### Ejemplo Básico de Herencia

```php
class Animal {
    public function hacerSonido() {
        return "El animal hace un sonido.";
    }
}

class Perro extends Animal {
    public function hacerSonido() {
        return "El perro ladra.";
    }
}

$miPerro = new Perro();
echo $miPerro->hacerSonido(); // Salida: El perro ladra.
```

### Uso del Constructor

```php
class Vehiculo {
    protected $tipo;

    public function __construct($tipo) {
        $this->tipo = $tipo;
    }
}

class Coche extends Vehiculo {
    private $marca;

    public function __construct($tipo, $marca) {
        parent::__construct($tipo);
        $this->marca = $marca;
    }

    public function mostrarInfo() {
        return "Tipo: $this->tipo, Marca: $this->marca";
    }
}

$miCoche = new Coche("Sedán", "Toyota");
echo $miCoche->mostrarInfo(); // Salida: Tipo: Sedán, Marca: Toyota
```

## Explicación
### Errores Comunes
- **Acceso a Métodos Privados**: La clase hija no puede acceder a métodos privados de la clase padre. Esto puede resultar en errores de visibilidad.
- **No Llamar a `parent::__construct()`**: Si la clase padre tiene un constructor y no se llama desde la clase hija, puede que algunas propiedades no se inicialicen correctamente.
- **Mala Organización**: Abusar de la herencia puede llevar a una jerarquía de clases complicada y difícil de mantener. Se recomienda usarla con moderación y considerar otras alternativas como la composición.

## Resumen en una Sola Línea
La palabra clave `extends` en PHP permite la herencia de clases, facilitando la reutilización de código y la creación de jerarquías en la programación orientada a objetos.