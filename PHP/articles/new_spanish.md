<!--
Meta Description: # La palabra clave "new" en PHP: Creación de Objetos de Clases ## Sinopsis La palabra clave `new` en PHP se utiliza para instanciar nuevas clases, per...
Meta Keywords: new, php, clase, objetos, que
-->

# La palabra clave "new" en PHP: Creación de Objetos de Clases

## Sinopsis
La palabra clave `new` en PHP se utiliza para instanciar nuevas clases, permitiendo la creación de objetos basados en definiciones de clase. Es un componente fundamental de la programación orientada a objetos en PHP.

## Documentación
La palabra clave `new` permite crear instancias de clases en PHP. Cuando se utiliza, PHP reserva espacio en memoria para un nuevo objeto y llama al constructor de la clase, si está definido. Esto es esencial para trabajar con objetos y sus métodos y propiedades.

### Uso
Para utilizar `new`, se debe tener una clase definida. La sintaxis básica es la siguiente:

```php
$miObjeto = new NombreDeLaClase();
```

Donde `NombreDeLaClase` es el nombre de la clase que deseas instanciar. Si la clase tiene un constructor, puedes pasarle parámetros de la siguiente manera:

```php
$miObjeto = new NombreDeLaClase($parametro1, $parametro2);
```

### Detalles
- **Constructores y Destructores**: Al crear un objeto utilizando `new`, se ejecuta automáticamente el constructor de la clase. Si el objeto ya no es necesario, se puede utilizar el destructor para liberar recursos.
- **Visibilidad**: Asegúrate de que el constructor de la clase sea público para poder instanciar objetos fuera de la clase.

## Ejemplos
Aquí hay algunos ejemplos básicos de cómo se usa `new` en PHP:

### Ejemplo 1: Creación de un objeto simple
```php
class Persona {
    public $nombre;

    public function __construct($nombre) {
        $this->nombre = $nombre;
    }
}

$persona = new Persona("Juan");
echo $persona->nombre; // Salida: Juan
```

### Ejemplo 2: Uso de un método en un objeto
```php
class Coche {
    public $marca;

    public function __construct($marca) {
        $this->marca = $marca;
    }

    public function mostrarMarca() {
        return "La marca del coche es: " . $this->marca;
    }
}

$coche = new Coche("Toyota");
echo $coche->mostrarMarca(); // Salida: La marca del coche es: Toyota
```

## Explicación
Al utilizar `new`, es importante tener en cuenta lo siguiente:

- **Errores de Instanciación**: Si intentas instanciar una clase que no está definida o que tiene un constructor protegido o privado, PHP lanzará un error. 
- **Referencias a Objetos**: Los objetos en PHP se manejan como referencias. Esto significa que si asignas un objeto a otra variable, ambas variables apuntarán al mismo objeto en memoria.
- **Espacio en Memoria**: Cada vez que instancias una clase con `new`, estás creando un nuevo objeto que ocupa espacio en memoria, por lo que es recomendable liberar objetos que ya no se necesiten.

## Resumen en una Línea
La palabra clave `new` en PHP se utiliza para crear instancias de clases, permitiendo la programación orientada a objetos eficazmente.