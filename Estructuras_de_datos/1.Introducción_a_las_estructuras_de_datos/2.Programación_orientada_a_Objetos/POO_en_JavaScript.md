# POO en JavaScript

## Programación Orientada a Objetos en JavaScript

La Programación Orientada a Objetos (POO) es un paradigma de programación que utiliza "objetos" y sus interacciones para diseñar aplicaciones y programas. JavaScript, aunque es un lenguaje basado en prototipos, soporta la POO a través de funciones constructoras y la palabra clave `class`.

### Conceptos Básicos

1. **Clase**: Una plantilla para crear objetos. Define las propiedades y métodos que los objetos creados a partir de la clase tendrán.
2. **Objeto**: Una instancia de una clase. Tiene sus propios valores para las propiedades definidas en la clase.
3. **Método**: Una función definida dentro de una clase que describe el comportamiento de los objetos creados a partir de la clase.
4. **Herencia**: Un mecanismo para crear una nueva clase a partir de una clase existente. La nueva clase, llamada subclase, hereda propiedades y métodos de la clase existente, llamada superclase.

### Definición de Clases

En JavaScript, las clases se pueden definir usando la sintaxis de `class`.

```jsx
class Persona {
    constructor(nombre, edad) {
        this.nombre = nombre;
        this.edad = edad;
    }

    saludar() {
        console.log(`Hola, me llamo ${this.nombre} y tengo ${this.edad} años.`);
    }
}

// Crear una instancia de la clase Persona
const persona1 = new Persona('Juan', 30);
persona1.saludar(); // Output: Hola, me llamo Juan y tengo 30 años.

```

### Herencia

La herencia permite que una clase (subclase) herede las propiedades y métodos de otra clase (superclase).

```jsx
class Estudiante extends Persona {
    constructor(nombre, edad, grado) {
        super(nombre, edad); // Llama al constructor de la superclase
        this.grado = grado;
    }

    estudiar() {
        console.log(`${this.nombre} está estudiando en el grado ${this.grado}.`);
    }
}

// Crear una instancia de la clase Estudiante
const estudiante1 = new Estudiante('María', 22, 'Ingeniería');
estudiante1.saludar(); // Output: Hola, me llamo María y tengo 22 años.
estudiante1.estudiar(); // Output: María está estudiando en el grado Ingeniería.

```

### Encapsulamiento

El encapsulamiento se refiere a la práctica de restringir el acceso a ciertos detalles de un objeto. En JavaScript, esto se puede lograr usando variables privadas y métodos públicos.

```jsx
class CuentaBancaria {
    #saldo = 0; // Propiedad privada

    constructor(titular) {
        this.titular = titular;
    }

    depositar(cantidad) {
        this.#saldo += cantidad;
    }

    retirar(cantidad) {
        if (cantidad <= this.#saldo) {
            this.#saldo -= cantidad;
        } else {
            console.log('Fondos insuficientes');
        }
    }

    verSaldo() {
        console.log(`Saldo de ${this.titular}: $${this.#saldo}`);
    }
}

// Crear una instancia de la clase CuentaBancaria
const cuenta = new CuentaBancaria('Luis');
cuenta.depositar(100);
cuenta.retirar(50);
cuenta.verSaldo(); // Output: Saldo de Luis: $50

```

### Polimorfismo

El polimorfismo permite que las subclases redefinan métodos de la superclase.

```jsx
class Animal {
    hacerSonido() {
        console.log('El animal hace un sonido.');
    }
}

class Perro extends Animal {
    hacerSonido() {
        console.log('El perro ladra.');
    }
}

class Gato extends Animal {
    hacerSonido() {
        console.log('El gato maúlla.');
    }
}

const perro = new Perro();
const gato = new Gato();

perro.hacerSonido(); // Output: El perro ladra.
gato.hacerSonido(); // Output: El gato maúlla.

```

### Resumen

La Programación Orientada a Objetos en JavaScript permite organizar el código en unidades reutilizables y manejables, utilizando clases para definir la estructura y comportamiento de los objetos. Los conceptos clave incluyen clases, objetos, herencia, encapsulamiento y polimorfismo, que juntos facilitan el desarrollo de aplicaciones complejas y mantenibles.