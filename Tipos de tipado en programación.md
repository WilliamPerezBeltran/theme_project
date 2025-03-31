# Tipos de tipado en programación

## 1. Tipado estático vs. Tipado dinámico

- **Tipado estático**: El tipo de una variable se define en tiempo de compilación y no puede cambiar.
  ```java
  int edad = 25; // Java tiene tipado estático, la variable siempre será un entero.
  ```
- **Tipado dinámico**: El tipo de una variable se determina en tiempo de ejecución y puede cambiar.
  ```python
  edad = 25  # En Python, edad es un entero
  edad = "veinticinco"  # Ahora es una cadena, sin errores
  ```

## 2. Tipado fuerte vs. Tipado débil

- **Tipado fuerte**: No permite conversiones implícitas de tipos sin una conversión explícita.
  ```python
  edad = 25 + "años"  # Error, no se puede sumar un número y un string.
  ```
- **Tipado débil**: Permite conversiones implícitas entre tipos.
  ```javascript
  let edad = 25 + " años";  // No da error, convierte 25 a string automáticamente
  ```

## 3. Tipado explícito vs. Tipado implícito

- **Tipado explícito**: Se debe declarar el tipo de la variable al definirla.
  ```c
  int edad = 25;  // En C, siempre se debe especificar el tipo de la variable
  ```
- **Tipado implícito**: El compilador o intérprete infiere el tipo de la variable.
  ```go
  edad := 25  // En Go, el compilador infiere que es un entero
  ```

## 4. Ejemplos en diferentes lenguajes

| Lenguaje       | Tipado estático/dinámico | Tipado fuerte/débil |
|---------------|------------------------|------------------|
| Java          | Estático               | Fuerte          |
| Python        | Dinámico               | Fuerte          |
| JavaScript    | Dinámico               | Débil           |
| C             | Estático               | Fuerte          |
| Go            | Estático               | Fuerte          |
| PHP           | Dinámico               | Débil           |

El sistema de tipado de un lenguaje influye en su seguridad, rendimiento y facilidad de uso. Dependiendo del tipo de aplicación que desarrolles, puede ser más conveniente elegir un lenguaje con tipado estático o dinámico, fuerte o débil.
