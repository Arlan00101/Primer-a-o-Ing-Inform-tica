# Tipos de datos y variables en Java

## Tipos de datos primitivos:

Java ofrece ocho tipos de datos primitivos, que son los bloques de construcción fundamentales para manipular información. Cada tipo tiene un tamaño y rango específico:

* **byte:** Representa un entero de 8 bits con signo. Su rango es de -128 a 127. Se utiliza para ahorrar memoria en arrays grandes.
    * **Ejemplo:** `byte edad = 25;`
* **short:** Representa un entero de 16 bits con signo. Su rango es de -32,768 a 32,767. Menos común en el uso diario.
    * **Ejemplo:** `short cantidadProductos = 15000;`
* **int:** Representa un entero de 32 bits con signo. Su rango es de -2,147,483,648 a 2,147,483,647. Es el tipo de dato entero más utilizado.
    * **Ejemplo:** `int numeroEstudiantes = 100;`
* **long:** Representa un entero de 64 bits con signo. Su rango es muy amplio, de -9,223,372,036,854,775,808 a 9,223,372,036,854,775,807. Se utiliza cuando se necesitan valores enteros muy grandes.
    * **Ejemplo:** `long poblacionMundial = 7000000000L;` (La 'L' al final indica que es un literal long).
* **float:** Representa un número de punto flotante de precisión simple de 32 bits (IEEE 754). Se utiliza para números decimales.
    * **Ejemplo:** `float precioProducto = 19.99f;` (La 'f' al final indica que es un literal float).
* **double:** Representa un número de punto flotante de precisión doble de 64 bits (IEEE 754). Ofrece mayor precisión que float y es el tipo de dato por defecto para números decimales.
    * **Ejemplo:** `double valorPi = 3.14159265359;`
* **boolean:** Representa un valor lógico que puede ser `true` o `false`. Se utiliza en estructuras de control y lógica.
    * **Ejemplo:** `boolean esValido = true;`
* **char:** Representa un único carácter Unicode de 16 bits.
    * **Ejemplo:** `char grupoSanguineo = 'A';`

## Variables:

Una variable es un nombre asociado a una ubicación de memoria que almacena un valor. En Java, cada variable debe ser declarada con un tipo de datos específico, lo que determina el tipo de valor que puede almacenar.

### Declaración de variables:

Se especifica el tipo de dato seguido del nombre de la variable.

```java
tipoDato nombreVariable;
```
**Ejemplo:** `int contador;`

### Inicialización de variables:

Se asigna un valor a la variable después de su declaración.

```java
nombreVariable = valor;
```
**Ejemplo:** `contador = 0;`

### Declaración e inicialización en una sola línea:

Es una forma común y concisa de declarar y asignar un valor inicial a una variable.

```java
tipoDato nombreVariable = valor;
```
**Ejemplo:** `int limite = 100;`

## Ejemplos:

```java
int edad = 30; // Declara e inicializa una variable de tipo int.
double salario = 50000.50; // Declara e inicializa una variable de tipo double.
char inicial = 'J'; // Declara e inicializa una variable de tipo char.
boolean esMayorDeEdad = true; // Declara e inicializa una variable de tipo boolean.
String nombre = "Juan"; // String no es un tipo primitivo, pero es muy utilizado.
```

## Curiosidades:

* Java es un lenguaje de tipado estático, lo que significa que el tipo de una variable se verifica en tiempo de compilación. Esto ayuda a prevenir errores en tiempo de ejecución.
* Los tipos primitivos en Java tienen valores por defecto si no se inicializan explícitamente (excepto las variables locales dentro de métodos). Por ejemplo, `int` tiene un valor por defecto de 0, `boolean` de `false`, etc.