<!--
Meta Description: # Interfaces en PHP: Definición y Uso ## Sinopsis Las interfaces en PHP son contratos que permiten definir métodos que las clases deben implementar, p...
Meta Keywords: las, que, una, interfaz, public
-->

# Interfaces en PHP: Definición y Uso

## Sinopsis
Las interfaces en PHP son contratos que permiten definir métodos que las clases deben implementar, promoviendo así una arquitectura de código más limpia y mantenible.

## Documentación
Las interfaces en PHP son una característica fundamental del lenguaje que permite la creación de un conjunto de métodos que las clases que implementan la interfaz deben definir. Esto es útil para garantizar que diferentes clases tengan un conjunto común de métodos, facilitando la interacción y el uso de polimorfismo.

### Propósito
El propósito de las interfaces es establecer un contrato que las clases deben seguir, sin proporcionar una implementación concreta. Esto es especialmente útil en la programación orientada a objetos (OOP) para crear aplicaciones modulares y reutilizables.

### Uso
Para definir una interfaz en PHP, se utiliza la palabra clave `interface`, seguida de su nombre. Las interfaces pueden contener métodos, pero no pueden contener propiedades. Todos los métodos de una interfaz son públicos y no pueden tener implementación. Las clases que implementen la interfaz deben proporcionar la implementación de todos sus métodos.

### Sintaxis
```php
interface NombreDeLaInterfaz {
    public function metodo1();
    public function metodo2($param);
}
```

Para implementar una interfaz en una clase, se utiliza la palabra clave `implements`:

```php
class ClaseEjemplo implements NombreDeLaInterfaz {
    public function metodo1() {
        // implementación del método 1
    }

    public function metodo2($param) {
        // implementación del método 2
    }
}
```

## Ejemplos
### Ejemplo 1: Definición y uso básico de una interfaz
```php
interface Vehiculo {
    public function arrancar();
    public function detener();
}

class Coche implements Vehiculo {
    public function arrancar() {
        echo "El coche ha arrancado.";
    }
    
    public function detener() {
        echo "El coche se ha detenido.";
    }
}

$coche = new Coche();
$coche->arrancar(); // Salida: El coche ha arrancado.
$coche->detener();  // Salida: El coche se ha detenido.
```

### Ejemplo 2: Múltiples clases que implementan la misma interfaz
```php
class Bicicleta implements Vehiculo {
    public function arrancar() {
        echo "La bicicleta ha comenzado a moverse.";
    }
    
    public function detener() {
        echo "La bicicleta se ha detenido.";
    }
}

class Moto implements Vehiculo {
    public function arrancar() {
        echo "La moto ha arrancado.";
    }
    
    public function detener() {
        echo "La moto se ha detenido.";
    }
}

$vehiculos = [new Coche(), new Bicicleta(), new Moto()];

foreach ($vehiculos as $vehiculo) {
    $vehiculo->arrancar();
}
```

## Explicación
### Errores comunes y consideraciones
- **Implementación incompleta:** Si una clase que implementa una interfaz no proporciona implementación para todos los métodos de la interfaz, PHP generará un error fatal.
- **Herencia de interfaces:** Una interfaz puede extender otra interfaz, lo que permite crear jerarquías de interfaces. Esto es útil para organizar métodos relacionados.
- **Interfaz vs Clase abstracta:** A diferencia de las clases abstractas, las interfaces no pueden contener ninguna implementación de métodos. Utiliza interfaces cuando desees definir un contrato sin lógica, y clases abstractas cuando necesites compartir código común.

## Resumen en Una Línea
Las interfaces en PHP permiten definir contratos que las clases deben implementar, promoviendo un diseño de código limpio y modular.