# Estructuras de control en Java

Las estructuras de control permiten controlar el flujo de ejecución de un programa, permitiendo que se tomen decisiones y se repitan bloques de código.

## Estructuras de control condicionales:

Permiten ejecutar diferentes bloques de código dependiendo de si se cumple o no una condición.

* **if:** Ejecuta un bloque de código si una condición booleana es verdadera.
    ```java
    int edad = 20;
    if (edad >= 18) {
        System.out.println("Es mayor de edad.");
    }
    ```
* **if-else:** Ejecuta un bloque de código si la condición es verdadera y otro bloque si la condición es falsa.
    ```java
    int edad = 15;
    if (edad >= 18) {
        System.out.println("Es mayor de edad.");
    } else {
        System.out.println("Es menor de edad.");
    }
    ```
* **if-else if-else:** Permite evaluar múltiples condiciones en secuencia. Se ejecuta el bloque de código asociado a la primera condición verdadera. Si ninguna condición es verdadera, se ejecuta el bloque del `else` final (si existe).
    ```java
    int nota = 75;
    if (nota >= 90) {
        System.out.println("Sobresaliente");
    } else if (nota >= 70) {
        System.out.println("Notable");
    } else if (nota >= 50) {
        System.out.println("Aprobado");
    } else {
        System.out.println("Suspenso");
    }
    ```
* **switch:** Permite seleccionar uno de varios bloques de código para ejecutar, basado en el valor de una variable.
    ```java
    int diaSemana = 3;
    switch (diaSemana) {
        case 1:
            System.out.println("Lunes");
            break;
        case 2:
            System.out.println("Martes");
            break;
        case 3:
            System.out.println("Miércoles");
            break;
        default:
            System.out.println("Fin de semana");
    }
    ```

## Estructuras de control de bucles:

Permiten ejecutar un bloque de código repetidamente.

* **for:** Se utiliza cuando se conoce el número de veces que se debe ejecutar el bucle. Consta de una inicialización, una condición y una actualización.
    ```java
    for (int i = 0; i < 5; i++) {
        System.out.println("Iteración número: " + i);
    }
    ```
* **while:** Ejecuta un bloque de código mientras una condición booleana sea verdadera. La condición se evalúa antes de cada iteración.
    ```java
    int contador = 0;
    while (contador < 5) {
        System.out.println("Contador: " + contador);
        contador++;
    }
    ```
* **do-while:** Similar al bucle `while`, pero la condición se evalúa después de la ejecución del bloque de código. Esto asegura que el bloque se ejecute al menos una vez.
    ```java
    int contador = 0;
    do {
        System.out.println("Contador: " + contador);
        contador++;
    } while (contador < 5);
    ```

## Ejemplos:

```java
int edad = 20;
if (edad >= 18) {
    System.out.println("Es mayor de edad.");
} else {
    System.out.println("Es menor de edad.");
}

for (int i = 0; i < 5; i++) {
    System.out.println(i);
}
```

## Curiosidades:

* La sentencia `break` se utiliza para salir inmediatamente de un bucle (`for`, `while`, `do-while`) o de una estructura `switch`.
* La sentencia `continue` se utiliza para saltar el resto del código dentro de la iteración actual de un bucle y pasar directamente a la siguiente iteración.
    ```java
    for (int i = 0; i < 10; i++) {
        if (i % 2 == 0) {
            continue; // Salta los números pares
        }
        System.out.println("Número impar: " + i);
    }