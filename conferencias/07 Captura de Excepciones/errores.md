# Conferencia para estudiantes de 1er año de Ingeniería Informática: Captura de Errores en Java

## Introducción a la Captura de Errores

¡Bienvenidos de nuevo! En esta segunda conferencia, nos centraremos en un aspecto crucial de la programación: la **captura de errores**, también conocida como **manejo de excepciones**.  En cualquier programa, es inevitable que ocurran errores. Aprender a anticiparlos, manejarlos y recuperarse de ellos es fundamental para escribir código robusto y confiable.

### ¿Por qué es importante la Captura de Errores?

Imagina un programa que se detiene abruptamente cada vez que encuentra un pequeño problema, como un archivo que no se encuentra o una división por cero. Sería frustrante para el usuario y poco profesional. La captura de errores nos permite:

* **Prevenir la terminación abrupta del programa:** En lugar de "estrellarse", el programa puede manejar el error y continuar funcionando (si es posible) o terminar de manera controlada.
* **Proporcionar información útil al usuario:**  Podemos mostrar mensajes de error claros y descriptivos para ayudar al usuario a entender qué salió mal y cómo solucionarlo (si es un error del usuario).
* **Facilitar la depuración:**  Un buen manejo de errores puede ayudarnos a identificar y corregir problemas en nuestro código más fácilmente.
* **Escribir código más robusto y confiable:**  Los programas que manejan errores son más resistentes a situaciones inesperadas y menos propensos a fallar.

### Tipos de Errores en Java

En Java, podemos clasificar los errores en dos categorías principales:

1. **Errores de Compilación (Compile-time Errors):**
   - Ocurren cuando el compilador de Java (javac) detecta problemas en tu código fuente **antes** de que se ejecute.
   - Suelen ser errores de sintaxis, como escribir mal una palabra clave, olvidar un punto y coma, o usar variables no declaradas.
   - El compilador te indicará la línea y el tipo de error, lo que facilita su corrección.
   - **Ejemplo:**

     ```java
     public class ErrorCompilacion {
         public static void main(String[] args) {
             System.out.println("Hola mundo")
         }
     }
     ```
     El compilador detectará el paréntesis faltante y no generará el archivo `.class` ejecutable hasta que se corrija el error.

2. **Errores de Ejecución (Runtime Errors) o Excepciones:**
   - Ocurren **durante** la ejecución del programa, cuando el código está corriendo.
   - Son situaciones inesperadas que el programa no puede manejar de manera "normal".
   - Ejemplos comunes:
     - **`ArithmeticException`:** División por cero.
     - **`NullPointerException`:** Intentar acceder a un objeto que es `null` (no apunta a ningún objeto).
     - **`ArrayIndexOutOfBoundsException`:** Intentar acceder a un índice inválido en un array.
     - **`FileNotFoundException`:** Intentar abrir un archivo que no existe.

### Manejo de Excepciones con `try-catch`

Java proporciona un mecanismo poderoso para manejar excepciones: los bloques `try-catch`.

**Estructura `try-catch`:**

```java
try {
    // Código que puede lanzar una excepción (código "protegido")

} catch (TipoDeExcepcion1 nombreVariableExcepcion1) {
    // Código para manejar la excepción TipoDeExcepcion1

} catch (TipoDeExcepcion2 nombreVariableExcepcion2) {
    // Código para manejar la excepción TipoDeExcepcion2

} finally {
    // (Opcional) Código que se ejecuta SIEMPRE, haya o no excepción

}
```

**Explicación:**

1. **`try { ... }`:**  Encierra el bloque de código que creemos que podría lanzar una excepción. Es el código que queremos "proteger".
2. **`catch (TipoDeExcepcion nombreVariableExcepcion) { ... }`:**
   - Define un bloque `catch` para cada tipo de excepción que queremos manejar específicamente.
   - `TipoDeExcepcion`:  Especifica el tipo de excepción que este bloque `catch` puede manejar (ej: `ArithmeticException`, `NullPointerException`, etc.).
   - `nombreVariableExcepcion`:  Es el nombre de una variable que se usará para referirse al objeto excepción capturado dentro del bloque `catch`. Este objeto contiene información sobre el error.
   - Si ocurre una excepción dentro del bloque `try` **y** su tipo coincide con el `TipoDeExcepcion` del bloque `catch`, la ejecución del programa **salta** al bloque `catch` correspondiente. El código dentro del `catch` se ejecuta para manejar la excepción.
3. **`finally { ... }`:** (Opcional)
   - El bloque `finally` se ejecuta **siempre**, sin importar si ocurrió o no una excepción en el bloque `try` y si fue capturada o no.
   - Se usa típicamente para código de "limpieza" que debe ejecutarse siempre, como cerrar archivos, liberar recursos, etc.

### Ejemplo Práctico: Manejo de `ArithmeticException` (División por Cero)

```java
public class EjemploExcepciones {
    public static void main(String[] args) {
        int numerador = 10;
        int denominador = 0;
        int resultado;

        try {
            resultado = numerador / denominador; // ¡Potencial ArithmeticException!
            System.out.println("El resultado es: " + resultado); // ¡Esta línea NO se ejecutará si hay excepción!
        } catch (ArithmeticException e) {
            System.out.println("¡Error! No se puede dividir por cero.");
            System.out.println("Mensaje de la excepción: " + e.getMessage()); // Imprime detalles del error
        } finally {
            System.out.println("Bloque finally: ¡Siempre me ejecuto!");
        }

        System.out.println("El programa continúa después del manejo de la excepción.");
    }
}
```

**Salida del ejemplo:**

```
¡Error! No se puede dividir por cero.
Mensaje de la excepción: / by zero
Bloque finally: ¡Siempre me ejecuto!
El programa continúa después del manejo de la excepción.
```

**Explicación:**

1. El código `numerador / denominador` dentro del `try` intenta dividir por cero, lo que lanza una `ArithmeticException`.
2. El bloque `catch (ArithmeticException e)` **captura** esta excepción porque coincide con el tipo de excepción lanzada.
3. Se ejecuta el código dentro del bloque `catch`: se imprime un mensaje de error y el mensaje específico de la excepción (`e.getMessage()`).
4. Luego, se ejecuta el bloque `finally`.
5. Finalmente, el programa continúa su ejecución normalmente después del bloque `try-catch`.

### Lanzando Excepciones (`throw`)

Además de capturar excepciones, también podemos **lanzar** excepciones manualmente en nuestro código usando la palabra clave `throw`. Esto es útil para indicar que algo salió mal en nuestra función o método y que no podemos continuar de manera normal.

```java
public static int dividir(int a, int b) {
    if (b == 0) {
        throw new ArithmeticException("¡No se puede dividir por cero!"); // Lanzamos la excepción
    }
    return a / b;
}
```

Cuando se lanza una excepción con `throw`, la ejecución del método actual se detiene inmediatamente y la excepción se propaga hacia arriba en la pila de llamadas (a quien llamó a este método). Si no se captura en algún bloque `try-catch` superior, eventualmente puede terminar causando la terminación del programa.

### Excepciones Personalizadas

Java ya proporciona muchos tipos de excepciones predefinidas, pero a veces necesitamos crear nuestras propias **excepciones personalizadas** para representar errores específicos de nuestra aplicación. Para hacer esto, creamos una nueva clase que herede de la clase `Exception` (o `RuntimeException`).

```java
// Ejemplo de excepción personalizada
class SaldoInsuficienteException extends Exception {
    public SaldoInsuficienteException(String mensaje) {
        super(mensaje); // Llama al constructor de la clase Exception con el mensaje
    }
}

public class CuentaBancaria {
    private double saldo;

    public void retirar(double cantidad) throws SaldoInsuficienteException { // Indica que este método puede lanzar esta excepción
        if (cantidad > saldo) {
            throw new SaldoInsuficienteException("Saldo insuficiente para retirar " + cantidad);
        }
        saldo -= cantidad;
        System.out.println("Retiro exitoso. Nuevo saldo: " + saldo);
    }

    public static void main(String[] args) {
        CuentaBancaria cuenta = new CuentaBancaria();
        cuenta.saldo = 100;

        try {
            cuenta.retirar(150); // ¡Lanzará SaldoInsuficienteException!
        } catch (SaldoInsuficienteException e) {
            System.out.println("Error al retirar: " + e.getMessage());
        }
    }
}
```

### Buenas Prácticas para la Captura de Errores

* **Sé específico al capturar excepciones:**  Intenta capturar tipos de excepciones específicos (`ArithmeticException`, `NullPointerException`, etc.) en lugar de usar un `catch (Exception e)` genérico (a menos que realmente quieras manejar cualquier tipo de excepción de la misma manera). Esto hace que tu código sea más claro y te permite manejar diferentes tipos de errores de forma diferente si es necesario.
* **Proporciona mensajes de error útiles:**  Los mensajes de error deben ser informativos y ayudar al usuario (o a ti mismo durante la depuración) a entender qué salió mal y cómo solucionarlo.
* **No ignores las excepciones silenciosamente:**  Evita bloques `catch` vacíos que simplemente "tragan" la excepción sin hacer nada. Esto puede ocultar problemas importantes y dificultar la depuración. Al menos, registra la excepción (por ejemplo, imprimiéndola en la consola o en un archivo de registro).
* **Usa `finally` para la limpieza:**  Asegúrate de liberar recursos (cerrar archivos, conexiones, etc.) en el bloque `finally` para evitar fugas de recursos, incluso si ocurren excepciones.
* **Piensa en qué excepciones pueden ocurrir:**  Anticipa las posibles excepciones que tu código podría lanzar y decide cómo manejarlas de manera adecuada.

### Práctica

1. Modifica el ejemplo de la función `dividir` para que lance una excepción personalizada llamada `DivisionPorCeroException` si el denominador es cero. Crea la clase `DivisionPorCeroException` que herede de `Exception`.
2. Escribe un programa que pida al usuario que introduzca dos números y realice la división. Usa `try-catch` para manejar la posible `ArithmeticException` si el usuario introduce cero como denominador. Muestra un mensaje de error amigable al usuario en caso de división por cero.

### Conclusión

La captura de errores es una habilidad esencial para cualquier programador. Dominar el uso de `try-catch`, entender los tipos de excepciones y seguir las buenas prácticas te permitirá escribir programas Java más robustos, confiables y fáciles de mantener. ¡Sigue practicando y experimentando con el manejo de excepciones en tus proyectos!

---

Espero que esta conferencia sobre captura de errores en Java haya sido instructiva. ¡No dudes en hacer preguntas y seguir explorando este importante tema! ¡Hasta la próxima!