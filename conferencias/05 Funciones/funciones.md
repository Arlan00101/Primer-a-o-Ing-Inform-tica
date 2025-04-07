# Conferencia para estudiantes de 1er año de Ingeniería Informática: Funciones en Java

## Introducción a las Funciones

¡Hola a todos! En esta conferencia, vamos a explorar un concepto fundamental en programación: las **funciones**. Las funciones son bloques de código reutilizables que realizan una tarea específica. Son esenciales para escribir programas organizados, eficientes y fáciles de entender.

### ¿Qué son las Funciones?

Imagina que tienes una tarea que necesitas realizar varias veces en tu programa, como calcular el área de un círculo o validar si un número es par. En lugar de escribir el mismo código repetidamente, puedes crear una función que realice esta tarea y luego llamarla cuando la necesites.

**Beneficios de usar funciones:**

* **Reutilización de código:** Escribe el código una vez y úsalo muchas veces.
* **Organización:** Divide programas complejos en partes más pequeñas y manejables.
* **Legibilidad:** Facilita la comprensión del código al darle nombres descriptivos a las tareas.
* **Mantenimiento:** Simplifica la modificación y corrección de errores, ya que los cambios se hacen en un solo lugar (la función).

### Sintaxis de una Función en Java

En Java, la estructura básica de una función (también llamada **método** en el contexto de clases) es la siguiente:

```java
[modificador_de_acceso] [tipo_de_retorno] nombreDeLaFuncion([parametros]) {
    // Cuerpo de la función: código que se ejecuta
    [return valor_de_retorno;] // Opcional, dependiendo del tipo de retorno
}
```

**Desglosando cada parte:**

* **`[modificador_de_acceso]`:**  Define la visibilidad de la función (por ejemplo, `public`, `private`, `protected`). Para empezar, usaremos `public` (accesible desde cualquier parte).
* **`[tipo_de_retorno]`:** Especifica el tipo de dato que la función devuelve después de ejecutar su tarea. Si la función no devuelve nada, se usa `void`. Ejemplos: `int`, `double`, `String`, `boolean`, `void`.
* **`nombreDeLaFuncion`:** El nombre que le das a la función. Debe ser descriptivo y seguir las convenciones de nomenclatura de Java (camelCase).
* **`([parametros])`:**  Lista opcional de variables que la función recibe como entrada para realizar su tarea. Cada parámetro tiene un tipo y un nombre. Si no recibe parámetros, se dejan los paréntesis vacíos `()`.
* **`{ // Cuerpo de la función ... }`:**  Bloque de código que contiene las instrucciones que la función ejecuta.
* **`[return valor_de_retorno;]`:**  (Opcional) Si la función tiene un tipo de retorno diferente a `void`, debe usar la palabra clave `return` para devolver un valor del tipo especificado.

### Ejemplo Práctico: Función para Sumar dos Números

Vamos a crear una función simple en Java que sume dos números enteros y devuelva el resultado:

```java
public class EjemploFunciones {

    public static int sumar(int num1, int num2) {
        int resultado = num1 + num2;
        return resultado;
    }

    public static void main(String[] args) {
        int a = 5;
        int b = 3;
        int suma = sumar(a, b); // Llamamos a la función sumar
        System.out.println("La suma de " + a + " y " + b + " es: " + suma); // Imprime: La suma de 5 y 3 es: 8
    }
}
```

**Explicación del ejemplo:**

1. **`public static int sumar(int num1, int num2)`:**
   - `public`:  La función es accesible desde cualquier parte.
   - `static`:  Por ahora, ignora esto. Lo entenderemos mejor más adelante cuando veamos clases y objetos.
   - `int`:  La función devolverá un valor de tipo entero (`int`).
   - `sumar`:  El nombre de la función.
   - `(int num1, int num2)`:  La función recibe dos parámetros de tipo entero: `num1` y `num2`.

2. **`int resultado = num1 + num2;`:**  Dentro del cuerpo de la función, calculamos la suma de `num1` y `num2` y la guardamos en la variable `resultado`.

3. **`return resultado;`:**  Devolvemos el valor de `resultado`.

4. **`main` function:**  The `main` function is the entry point of the program.
   - `int suma = sumar(a, b);`:  Llamamos a la función `sumar` pasándole los valores de `a` y `b` como argumentos. El valor que devuelve la función `sumar` (la suma) se guarda en la variable `suma`.
   - `System.out.println(...)`: Imprimimos el resultado.

### Tipos de Funciones

* **Funciones con retorno de valor:**  Devuelven un valor usando `return` (como el ejemplo de `sumar`).
* **Funciones sin retorno de valor (void):**  No devuelven ningún valor explícitamente. Se usan para realizar acciones, como imprimir algo en la pantalla.

   ```java
   public static void saludar(String nombre) {
       System.out.println("¡Hola, " + nombre + "!");
   }
   ```

### Llamando a una Función

Para usar una función, simplemente la **llamas** por su nombre y le pasas los argumentos necesarios (si los tiene).

```java
nombreDeLaFuncion(argumento1, argumento2, ...);
```

### Práctica

1. Escribe una función en Java llamada `esPar` que reciba un número entero y devuelva `true` si el número es par, y `false` si es impar.
2. Escribe una función llamada `calcularAreaCirculo` que reciba el radio de un círculo (como un `double`) y devuelva su área (también como un `double`). (Área del círculo = π * radio * radio, puedes usar `Math.PI` para el valor de π).

### Recursividad

La **recursividad** es una técnica de programación donde una función se llama a sí misma para resolver un problema.  Es como definir algo en términos de sí mismo. Para que una función recursiva funcione correctamente, debe tener dos partes importantes:

1. **Caso Base:** Una condición que detiene la recursión. Es el caso más simple que se puede resolver directamente sin llamar a la función de nuevo. Sin un caso base, la función se llamaría a sí misma infinitamente, causando un error llamado "desbordamiento de pila" (StackOverflowError).
2. **Caso Recursivo:** La función se llama a sí misma, pero con un problema más pequeño o simplificado que se acerca al caso base.

**Ejemplo: Factorial de un número**

El factorial de un número entero positivo `n` (n!) se define como el producto de todos los enteros positivos desde 1 hasta `n`. Por ejemplo, 5! = 5 * 4 * 3 * 2 * 1 = 120.

Podemos calcular el factorial de forma recursiva:

* Caso base: Si n = 0, el factorial es 1 (0! = 1).
* Caso recursivo: Si n > 0, el factorial de n es n * (n-1)!.

```java
public class EjemploRecursividad {

    public static int factorialRecursivo(int n) {
        if (n == 0) { // Caso base
            return 1;
        } else { // Caso recursivo
            return n * factorialRecursivo(n - 1); // La función se llama a sí misma
        }
    }

    public static void main(String[] args) {
        int numero = 5;
        int resultadoFactorial = factorialRecursivo(numero);
        System.out.println("El factorial de " + numero + " es: " + resultadoFactorial); // Imprime: El factorial de 5 es: 120
    }
}
```

**Explicación del ejemplo:**

1. **`public static int factorialRecursivo(int n)`:**  Función recursiva para calcular el factorial.
2. **`if (n == 0) { return 1; }`:** Caso base: si `n` es 0, devuelve 1.
3. **`else { return n * factorialRecursivo(n - 1); }`:** Caso recursivo: si `n` es mayor que 0, devuelve `n` multiplicado por el factorial de `n-1`.  ¡Aquí está la llamada recursiva!

**Otro Ejemplo: Serie de Fibonacci**

La serie de Fibonacci es una secuencia de números donde cada número es la suma de los dos anteriores: 0, 1, 1, 2, 3, 5, 8, 13, ...

Podemos calcular el n-ésimo número de Fibonacci recursivamente:

* Caso base: Si n = 0, el número de Fibonacci es 0. Si n = 1, el número de Fibonacci es 1.
* Caso recursivo: Si n > 1, el n-ésimo número de Fibonacci es la suma de los (n-1)-ésimo y (n-2)-ésimo números de Fibonacci.

```java
public class EjemploFibonacciRecursivo {

    public static int fibonacciRecursivo(int n) {
        if (n == 0) { // Caso base 1
            return 0;
        } else if (n == 1) { // Caso base 2
            return 1;
        } else { // Caso recursivo
            return fibonacciRecursivo(n - 1) + fibonacciRecursivo(n - 2); // Doble llamada recursiva
        }
    }

    public static void main(String[] args) {
        int n = 7; // Calcular el 7mo número de Fibonacci (índice 7)
        int resultadoFibonacci = fibonacciRecursivo(n);
        System.out.println("El número de Fibonacci en la posición " + n + " es: " + resultadoFibonacci); // Imprime: El número de Fibonacci en la posición 7 es: 13
    }
}
```

**Puntos a tener en cuenta sobre la recursividad:**

* **Elegancia y claridad:** La recursividad puede hacer que el código sea más elegante y fácil de entender para ciertos problemas, especialmente aquellos que tienen una naturaleza recursiva inherente (como el factorial, la serie de Fibonacci, recorridos de árboles, etc.).
* **Rendimiento:**  Las llamadas recursivas pueden ser costosas en términos de tiempo y memoria, ya que cada llamada agrega un nuevo marco a la pila de llamadas. Para algunos problemas, una solución iterativa (con bucles) puede ser más eficiente.
* **Desbordamiento de pila:** Si no se define correctamente un caso base o si la recursión es demasiado profunda, puede ocurrir un desbordamiento de pila (StackOverflowError), lo que detiene el programa.

Es importante entender cuándo la recursividad es una buena opción y cuándo es mejor usar un enfoque iterativo.  En muchos casos, ambas soluciones son posibles, pero una puede ser más clara o eficiente que la otra.

### Conclusión

Las funciones son una herramienta poderosa para escribir código Java de manera eficiente y organizada. La recursividad es una técnica avanzada dentro de las funciones que permite resolver problemas de manera elegante, aunque requiere cuidado para evitar problemas de rendimiento y desbordamiento de pila. Dominar el concepto de funciones y la recursividad es un paso crucial en tu camino para convertirte en un programador de Java. ¡Sigue practicando y experimentando!