# Introducción a Java

## ¿Qué es Java?

Java es un lenguaje de programación de alto nivel, orientado a objetos y de propósito general. Fue diseñado por James Gosling en Sun Microsystems (ahora parte de Oracle) y lanzado en 1995. Una de sus características fundamentales es la portabilidad, lograda gracias a la Java Virtual Machine (JVM), que permite que el código Java ("escribe una vez, ejecuta en cualquier lugar") se ejecute en diversas plataformas sin necesidad de recompilación.

## Características clave de Java:

* **Simple:** Java elimina características complejas presentes en otros lenguajes, como la gestión manual de memoria (a través de punteros), lo que facilita su aprendizaje y uso.
    * **Ejemplo:** La recolección de basura automática libera al programador de tener que preocuparse por la asignación y liberación de memoria.
* **Orientado a objetos:** Java se basa en el paradigma de la programación orientada a objetos (POO), que organiza el software alrededor de "objetos" que combinan datos y comportamientos.
    * **Ejemplo:** Clases como `Coche` y `Persona` pueden modelar entidades del mundo real con sus propios atributos (color, nombre) y métodos (acelerar, hablar).
* **Independiente de la plataforma:** El código fuente de Java se compila en bytecode, que luego es ejecutado por la JVM. Esta máquina virtual actúa como una capa de abstracción entre el código y el sistema operativo subyacente.
    * **Ejemplo:** Un programa Java compilado puede ejecutarse tanto en Windows como en macOS o Linux, siempre que tengan una JVM instalada.
* **Robusto:** Java pone un fuerte énfasis en la detección de errores, tanto en tiempo de compilación como en tiempo de ejecución. Incluye características como el manejo de excepciones para gestionar situaciones inesperadas.
    * **Ejemplo:** El manejo de excepciones con bloques `try-catch` permite que un programa se recupere de errores en lugar de fallar abruptamente.
* **Seguro:** Java proporciona seguridad a través de su entorno de ejecución (la JVM) y características del lenguaje. Por ejemplo, la ausencia de punteros reduce el riesgo de acceso indebido a la memoria.
    * **Ejemplo:** El bytecode de Java pasa por un proceso de verificación antes de su ejecución para asegurar que no viole las reglas de seguridad.
* **De alto rendimiento:** Aunque inicialmente interpretado, Java utiliza un compilador Just-In-Time (JIT) que compila el bytecode en código nativo durante la ejecución, mejorando significativamente el rendimiento.
    * **Ejemplo:** Las aplicaciones Java modernas pueden alcanzar un rendimiento comparable al de las aplicaciones escritas en lenguajes compilados como C++.
* **Multihilo:** Java facilita la creación de aplicaciones multihilo, permitiendo que diferentes partes de un programa se ejecuten concurrentemente.
    * **Ejemplo:** Un servidor de aplicaciones puede manejar múltiples peticiones de clientes simultáneamente utilizando hilos.
* **Interpretado:** El código Java se compila a un formato intermedio llamado bytecode, que luego es interpretado por la JVM. Esto contribuye a la portabilidad del lenguaje.
    * **Ejemplo:** El bytecode es independiente de la arquitectura del procesador, lo que permite su ejecución en cualquier máquina con una JVM.

## Ejemplos básicos:

```java
public class HolaMundo {
    public static void main(String[] args) {
        System.out.println("¡Hola, Mundo!");
    }
}
```
Este programa sencillo imprime el texto "¡Hola, Mundo!" en la consola. La estructura básica incluye la declaración de una clase (`HolaMundo`) y un método principal (`main`), que es el punto de entrada de la aplicación.

```java
public class Suma {
    public static void main(String[] args) {
        int numero1 = 5;
        int numero2 = 10;
        int suma = numero1 + numero2;
        System.out.println("La suma es: " + suma);
    }
}
```
Este ejemplo muestra la declaración de variables (`numero1`, `numero2`, `suma`) y la realización de una operación aritmética.

## Curiosidades:

* El nombre original de Java era "Oak", en referencia a un roble que había fuera de la oficina de James Gosling. Posteriormente, fue renombrado a "Java", que es un término para el café.
* Java fue desarrollado originalmente por James Gosling en Sun Microsystems (ahora Oracle). El lema original de Java era "Write Once, Run Anywhere" (WORA), que subraya su independencia de la plataforma.