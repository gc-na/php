<!--
Meta Description: # "protected" en PHP: Acceso Controlado en Programación Orientada a Objetos ## Sinopsis El modificador de acceso `protected` en PHP es fundamental par...
Meta Keywords: protected, clase, que, acceso, php
-->

# "protected" en PHP: Acceso Controlado en Programación Orientada a Objetos

## Sinopsis
El modificador de acceso `protected` en PHP es fundamental para la programación orientada a objetos, ya que permite restringir el acceso a propiedades y métodos de una clase, asegurando que solo sean accesibles dentro de la propia clase y por clases que heredan de ella.

## Documentación
El modificador `protected` se utiliza para definir la visibilidad de propiedades y métodos en una clase de PHP. A diferencia de `public`, que permite el acceso desde cualquier parte del código, y `private`, que limita el acceso a la propia clase, `protected` permite que las propiedades y métodos sean accesibles en la clase que los define y en cualquier subclase que herede de ella.

### Propósito
El uso de `protected` es esencial para la encapsulación en la programación orientada a objetos. Al restringir el acceso a ciertas partes de una clase, se protege la integridad de los datos y se fomenta el uso de métodos de acceso (getters y setters) para manipular esos datos.

### Uso
Para declarar una propiedad o método como `protected`, simplemente se antepone la palabra clave `protected` en la declaración. Aquí tienes un ejemplo básico:

```php
class Base {
    protected $valor;

    protected function mostrarValor() {
        return $this->valor;
    }
}

class Derivada extends Base {
    public function establecerValor($nuevoValor) {
        $this->valor = $nuevoValor;
    }

    public function obtenerValor() {
        return $this->mostrarValor();
    }
}
```

## Ejemplos
### Ejemplo 1: Propiedad `protected`
```php
class Animal {
    protected $nombre;

    public function __construct($nombre) {
        $this->nombre = $nombre;
    }
}

class Perro extends Animal {
    public function ladrar() {
        return "¡Guau! Soy " . $this->nombre;
    }
}

$miPerro = new Perro("Rex");
echo $miPerro->ladrar(); // Salida: ¡Guau! Soy Rex
```

### Ejemplo 2: Método `protected`
```php
class Vehiculo {
    protected function iniciar() {
        return "Vehículo iniciado.";
    }
}

class Coche extends Vehiculo {
    public function conducir() {
        return $this->iniciar() . " Listo para conducir.";
    }
}

$miCoche = new Coche();
echo $miCoche->conducir(); // Salida: Vehículo iniciado. Listo para conducir.
```

## Explicación
Al utilizar `protected`, es importante tener en cuenta:
- **Acceso Limitado**: Los métodos y propiedades protegidos no son accesibles desde fuera de la clase o de las subclases. Intentar acceder a ellos desde un objeto de la clase base dará lugar a un error.
- **Herencia**: `protected` es especialmente útil en la herencia, ya que permite que las subclases accedan a los métodos y propiedades de la clase base sin exponerlos a todo el mundo.
- **No se puede acceder directamente**: Si intentas acceder a una propiedad o método `protected` desde una instancia de la clase base, recibirás un error de visibilidad.

## Resumen en una línea
El modificador `protected` en PHP permite restringir el acceso a propiedades y métodos a la propia clase y sus subclases, promoviendo la encapsulación en la programación orientada a objetos.