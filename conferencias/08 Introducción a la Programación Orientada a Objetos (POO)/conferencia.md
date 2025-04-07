# Introducción a la Programación Orientada a Objetos (POO) en Java

## ¿Qué es la POO?

La Programación Orientada a Objetos (POO) es un paradigma de programación fundamental en Java que organiza el software en torno a "objetos" en lugar de "acciones". Un objeto es una entidad que encapsula datos (atributos o propiedades) y el código que opera sobre esos datos (métodos o comportamientos). La POO busca modelar el mundo real de una manera más intuitiva y facilita la creación de software modular, reutilizable y mantenible.

## Conceptos clave de la POO:

* **Clase:** Una clase es una plantilla o un plano para crear objetos. Define la estructura y el comportamiento que compartirán los objetos de ese tipo. Es una abstracción que define los atributos (variables) y los métodos (funciones) que caracterizan a los objetos.
    ```java
    class Coche {
        String marca;
        String modelo;
        String color;

        void acelerar() {
            System.out.println("El coche está acelerando.");
        }
    }
    ```
* **Objeto:** Un objeto es una instancia específica de una clase. Cuando se crea un objeto, se reserva espacio en la memoria para almacenar sus atributos y se puede interactuar con él a través de sus métodos.
    ```java
    Coche miCoche = new Coche();
    miCoche.marca = "Toyota";
    miCoche.acelerar();
    ```
* **Encapsulamiento:** El encapsulamiento es el principio de ocultar el estado interno (atributos) de un objeto y permitir el acceso a él solo a través de métodos definidos (getters y setters). Esto protege la integridad de los datos y facilita la modificación del código interno sin afectar a otras partes del programa.
    ```java
    class CuentaBancaria {
        private double saldo; // Atributo privado (encapsulado)

        public double getSaldo() {
            return saldo;
        }

        public void depositar(double cantidad) {
            saldo += cantidad;
        }
    }
    ```
* **Herencia:** La herencia es un mecanismo que permite crear nuevas clases (subclases o clases hijas) basadas en clases existentes (superclases o clases padre). La subclase hereda los atributos y métodos de la superclase, lo que fomenta la reutilización del código y la creación de jerarquías de clases.
    ```java
    class Animal {
        String nombre;
        public void hacerSonido() {
            System.out.println("Sonido genérico.");
        }
    }

    class Perro extends Animal {
        @Override
        public void hacerSonido() {
            System.out.println("Guau!");
        }
    }
    ```
* **Polimorfismo:** El polimorfismo (que significa "muchas formas") es la capacidad de un objeto de tomar muchas formas. En Java, se manifiesta a través de la sobrecarga de métodos (mismo nombre, diferentes parámetros) y la sobrescritura de métodos (una subclase proporciona una implementación específica para un método heredado de su superclase).
    ```java
    class Figura {
        public void dibujar() {
            System.out.println("Dibujando figura.");
        }
    }

    class Circulo extends Figura {
        @Override
        public void dibujar() {
            System.out.println("Dibujando círculo.");
        }
    }

    class Rectangulo extends Figura {
        @Override
        public void dibujar() {
            System.out.println("Dibujando rectángulo.");
        }
    }
    ```

## Ejemplos:

```java
// Clase
class Animal {
    String nombre;

    public Animal(String nombre) {
        this.nombre = nombre;
    }

    public void hacerSonido() {
        System.out.println("Sonido genérico de animal.");
    }
}

// Objeto
Animal miPerro = new Animal("Buddy");
miPerro.hacerSonido();
```

```java
// Ejemplo de herencia
class Vehiculo {
    String marca;
    public void acelerar() {
        System.out.println("Vehículo acelerando.");
    }
}

class Coche extends Vehiculo {
    int numeroPuertas;
}

Coche miCoche = new Coche();
miCoche.acelerar(); // Hereda el método de Vehiculo
```

## Curiosidades:

* Java es considerado un lenguaje puramente orientado a objetos, aunque incluye tipos de datos primitivos que no son objetos.
* La POO facilita el desarrollo de aplicaciones complejas al dividir el problema en partes más pequeñas y manejables (objetos).
* Los principios SOLID (Single Responsibility, Open/Closed, Liskov Substitution, Interface Segregation, Dependency Inversion) son un conjunto de directrices que ayudan a diseñar software orientado a objetos robusto y mantenible.