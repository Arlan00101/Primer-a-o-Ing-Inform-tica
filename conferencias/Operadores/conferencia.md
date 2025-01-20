# Operadores en Java

Los operadores son símbolos especiales que realizan operaciones específicas sobre uno, dos o tres operandos (variables o valores). Java proporciona una rica variedad de operadores para realizar diversas tareas.

## Tipos de operadores:

* **Operadores aritméticos:** Se utilizan para realizar cálculos matemáticos.
    * `+` (Suma): Suma dos operandos. Ejemplo: `int suma = 5 + 3;`
    * `-` (Resta): Resta el segundo operando del primero. Ejemplo: `int resta = 10 - 4;`
    * `*` (Multiplicación): Multiplica dos operandos. Ejemplo: `int producto = 6 * 7;`
    * `/` (División): Divide el primer operando por el segundo. Si ambos son enteros, el resultado es entero (se trunca la parte decimal). Ejemplo: `int division = 15 / 2; // Resultado: 7`
    * `%` (Módulo): Devuelve el resto de la división del primer operando por el segundo. Ejemplo: `int resto = 16 % 5; // Resultado: 1`
* **Operadores de asignación:** Asignan un valor a una variable.
    * `=` (Asignación simple): Asigna el valor del operando derecho al operando izquierdo. Ejemplo: `int edad = 25;`
    * `+=` (Suma y asignación): Suma el operando derecho al operando izquierdo y asigna el resultado al operando izquierdo. Ejemplo: `int contador = 0; contador += 5; // contador ahora es 5`
    * `-=` (Resta y asignación): Resta el operando derecho del operando izquierdo y asigna el resultado. Ejemplo: `int saldo = 100; saldo -= 20; // saldo ahora es 80`
    * `*=` (Multiplicación y asignación): Multiplica el operando izquierdo por el operando derecho y asigna el resultado. Ejemplo: `int cantidad = 10; cantidad *= 2; // cantidad ahora es 20`
    * `/=` (División y asignación): Divide el operando izquierdo por el operando derecho y asigna el resultado. Ejemplo: `int puntaje = 100; puntaje /= 4; // puntaje ahora es 25`
    * `%=` (Módulo y asignación): Calcula el módulo y lo asigna al operando izquierdo. Ejemplo: `int numero = 7; numero %= 3; // numero ahora es 1`
* **Operadores de comparación:** Comparan dos operandos y devuelven un valor booleano (`true` o `false`).
    * `==` (Igual a): Devuelve `true` si los operandos son iguales. Ejemplo: `boolean iguales = (5 == 5); // true`
    * `!=` (No igual a): Devuelve `true` si los operandos no son iguales. Ejemplo: `boolean diferente = (10 != 5); // true`
    * `>` (Mayor que): Devuelve `true` si el operando izquierdo es mayor que el derecho. Ejemplo: `boolean mayor = (8 > 3); // true`
    * `<` (Menor que): Devuelve `true` si el operando izquierdo es menor que el derecho. Ejemplo: `boolean menor = (2 < 7); // true`
    * `>=` (Mayor o igual que): Devuelve `true` si el operando izquierdo es mayor o igual que el derecho. Ejemplo: `boolean mayorOIgual = (5 >= 5); // true`
    * `<=` (Menor o igual que): Devuelve `true` si el operando izquierdo es menor o igual que el derecho. Ejemplo: `boolean menorOIgual = (4 <= 6); // true`
* **Operadores lógicos:** Se utilizan para combinar o negar expresiones booleanas.
    * `&&` (AND lógico): Devuelve `true` si ambos operandos son `true`. Ejemplo: `boolean resultadoAnd = (true && true); // true`
    * `||` (OR lógico): Devuelve `true` si al menos uno de los operandos es `true`. Ejemplo: `boolean resultadoOr = (true || false); // true`
    * `!` (NOT lógico): Invierte el valor booleano del operando. Si el operando es `true`, devuelve `false`, y viceversa. Ejemplo: `boolean resultadoNot = !true; // false`
* **Operadores bit a bit:** Realizan operaciones en los bits individuales de los operandos enteros.
    * `&` (AND bit a bit): Realiza un AND bit a bit entre dos operandos.
    * `|` (OR bit a bit): Realiza un OR bit a bit entre dos operandos.
    * `^` (XOR bit a bit): Realiza un XOR bit a bit entre dos operandos.
    * `~` (NOT bit a bit): Invierte los bits de un operando.
    * `<<` (Desplazamiento a la izquierda): Desplaza los bits del operando izquierdo hacia la izquierda el número de veces especificado por el operando derecho.
    * `>>` (Desplazamiento a la derecha con signo): Desplaza los bits del operando izquierdo hacia la derecha, manteniendo el signo.
    * `>>>` (Desplazamiento a la derecha sin signo): Desplaza los bits del operando izquierdo hacia la derecha, rellenando con ceros.

## Precedencia de operadores:

La precedencia de operadores determina el orden en que se evalúan las expresiones. Por ejemplo, la multiplicación y la división tienen mayor precedencia que la suma y la resta. Se pueden usar paréntesis para alterar el orden de evaluación.

## Ejemplos:

```java
int a = 10;
int b = 5;
int suma = a + b; // 15
int resta = a - b; // 5
int multiplicacion = a * b; // 50
int division = a / b; // 2
int modulo = a % b; // 0

boolean resultado = (a > b) && (suma == 15); // true

int x = 8;
int y = 2;
int resultadoPrecedencia = x + y * 3; // Primero se multiplica y luego se suma (8 + 6 = 14)
int resultadoParentesis = (x + y) * 3; // Primero se suma por los paréntesis (10 * 3 = 30)
```

## Curiosidades:

* El operador `%` es especialmente útil para determinar si un número es par o impar (si el número % 2 es 0, es par).
* Los operadores lógicos `&&` y `||` tienen "cortocircuito". Esto significa que si el resultado de la expresión se puede determinar con el primer operando, el segundo operando no se evalúa. Por ejemplo, en `(a > b) && (suma == 15)`, si `a` no es mayor que `b`, entonces la segunda condición (`suma == 15`) no se verifica.