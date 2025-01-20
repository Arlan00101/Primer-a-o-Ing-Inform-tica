# Arrays en Java

## ¿Qué es un array?

Un array en Java es una estructura de datos que almacena una colección de elementos del mismo tipo de dato, como `int`, `String` o incluso objetos de una clase definida por el usuario. Estos elementos se almacenan en ubicaciones de memoria contiguas, lo que permite un acceso eficiente a cada elemento mediante su índice. La longitud de un array se establece al crearlo y no puede modificarse posteriormente.

## Declaración de arrays:

Para declarar un array, se especifica el tipo de dato de los elementos seguido de corchetes `[]` y el nombre del array.

```java
tipoDato[] nombreArray;
```
**Ejemplo:** `int[] numeros;` declara un array que contendrá números enteros.

## Creación de arrays:

La declaración por sí sola no crea el array en la memoria. Para ello, se utiliza la palabra clave `new` seguida del tipo de dato y la longitud del array entre corchetes.

```java
nombreArray = new tipoDato[longitud];
```
**Ejemplo:** `numeros = new int[10];` crea un array de 10 enteros.

## Declaración y creación en una sola línea:

Es posible declarar y crear un array en una sola línea.

```java
tipoDato[] nombreArray = new tipoDato[longitud];
```
**Ejemplo:** `double[] precios = new double[5];` declara y crea un array de 5 números de tipo double.

## Inicialización de arrays:

Los elementos de un array se pueden inicializar al momento de la creación o posteriormente accediendo a cada elemento por su índice.

```java
nombreArray[indice] = valor;
```
**Ejemplo:** `numeros[0] = 5;` asigna el valor 5 al primer elemento del array `numeros`.

También se puede inicializar un array al momento de su declaración:

```java
tipoDato[] nombreArray = {valor1, valor2, valor3, ...};
```
**Ejemplo:** `String[] nombres = {"Ana", "Luis", "Sofía"};`

## Acceso a los elementos de un array:

Se accede a los elementos de un array utilizando su índice, que comienza en 0 para el primer elemento, 1 para el segundo, y así sucesivamente hasta `longitud - 1` para el último elemento.

**Ejemplo:** Para acceder al primer elemento del array `numeros`: `int primerNumero = numeros[0];`

## Ejemplos:

```java
// Declaración y creación de un array de enteros con 5 elementos
int[] numeros = new int[5];
// Inicialización de los elementos del array
numeros[0] = 10;
numeros[1] = 20;
numeros[2] = 30;
numeros[3] = 40;
numeros[4] = 50;

// Acceso al primer elemento
int primerNumero = numeros[0]; // El valor de primerNumero será 10

// Creación e inicialización directa de un array de strings
String[] colores = {"rojo", "verde", "azul"};
// Acceso al segundo elemento
String segundoColor = colores[1]; // El valor de segundoColor será "verde"
```

## Curiosidades:

* Los arrays en Java son objetos, aunque se declaran y manipulan con una sintaxis especial. Esto significa que un array es una instancia de una clase array.
* La longitud de un array se puede obtener mediante la propiedad `length`. Por ejemplo, `numeros.length` devolverá 5 para el array `numeros` del ejemplo anterior.
* Si intentas acceder a un índice que está fuera del rango válido del array (es decir, un índice negativo o mayor o igual a la longitud del array), se produce una excepción en tiempo de ejecución llamada `ArrayIndexOutOfBoundsException`.