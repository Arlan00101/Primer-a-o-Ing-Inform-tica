# Ejercicios de Introducción a la Programación Orientada a Objetos (POO) en Java

## Ejercicios Prácticos

1. **Clase `Persona`:**
   - Crea una clase llamada `Persona` con los atributos `nombre`, `edad` y `DNI`.
   - Añade un constructor para inicializar los atributos al crear un objeto `Persona`.
   - Implementa métodos `getNombre()`, `getEdad()` y `getDNI()` para acceder a los atributos.
   - Crea un método `imprimirInformacion()` que muestre por consola la información de la persona.
   - Crea varios objetos `Persona` con diferentes valores y prueba los métodos.

2. **Clase `Coche`:**
   - Crea una clase llamada `Coche` con los atributos `marca`, `modelo`, `color` y `velocidadActual`.
   - Añade un constructor para inicializar la marca, modelo y color. La `velocidadActual` debe inicializarse en 0.
   - Implementa los métodos `acelerar(int incremento)` y `frenar(int decremento)` que modifiquen la `velocidadActual`. Asegúrate de que la velocidad no sea negativa.
   - Añade un método `getVelocidadActual()` para obtener la velocidad actual.
   - Crea varios objetos `Coche` y prueba los métodos de aceleración y frenado.

3. **Clase `Rectangulo`:**
   - Crea una clase llamada `Rectangulo` con los atributos `base` y `altura`.
   - Añade un constructor para inicializar la base y la altura.
   - Implementa métodos para calcular el área (`getArea()`) y el perímetro (`getPerimetro()`) del rectángulo.
   - Crea varios objetos `Rectangulo` con diferentes dimensiones y muestra su área y perímetro.

4. **Herencia con `Animal`:**
   - Utiliza la clase `Animal` del ejemplo de la conferencia.
   - Crea al menos dos subclases de `Animal`, por ejemplo, `Perro` y `Gato`.
   - Implementa el método `hacerSonido()` en cada subclase para que emita el sonido característico del animal.
   - Crea objetos de cada subclase y llama al método `hacerSonido()` para comprobar el polimorfismo.

5. **Cuenta Bancaria:**
   - Crea una clase llamada `CuentaBancaria` con un atributo privado `saldo`.
   - Implementa métodos `depositar(double cantidad)` y `retirar(double cantidad)` que actualicen el saldo. Asegúrate de que no se pueda retirar más dinero del que hay en la cuenta.
   - Añade un método `getSaldo()` para consultar el saldo actual.
   - Crea un objeto `CuentaBancaria` y realiza varias operaciones de depósito y retiro.

## Ejercicios Adicionales

6. **Clase `Libro`:**
   - Crea una clase llamada `Libro` con atributos como `titulo`, `autor`, `ISBN` y `numeroPaginas`.
   - Implementa los constructores y métodos getter correspondientes.
   - Añade un método `mostrarInformacion()` que imprima la información del libro.

7. **Clase `Estudiante` y `Profesor`:**
   - Crea una clase base llamada `Persona` con atributos comunes como `nombre` y `edad`.
   - Crea las clases `Estudiante` y `Profesor` que hereden de `Persona`.
   - Añade atributos específicos a cada clase (por ejemplo, `matricula` para `Estudiante` y `departamento` para `Profesor`).
   - Implementa métodos específicos para cada clase (por ejemplo, `estudiar()` para `Estudiante` y `enseñar()` para `Profesor`).

## Pistas y Curiosidades

* Recuerda la importancia de la encapsulación al definir los atributos de tus clases.
* Utiliza modificadores de acceso (`public`, `private`, `protected`) de manera adecuada.
* Piensa en cómo puedes reutilizar código mediante la herencia.
* Experimenta con la creación de diferentes tipos de objetos y la interacción entre ellos.