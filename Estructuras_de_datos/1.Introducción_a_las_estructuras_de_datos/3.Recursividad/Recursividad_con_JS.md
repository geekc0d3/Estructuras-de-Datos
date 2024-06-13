# Recursividad con JS

## ¿Qué es la Recursividad?

La recursividad es una técnica de programación en la que una función se llama a sí misma para resolver un problema. Una función recursiva debe tener una **condición base** que determine cuándo dejar de llamarse a sí misma para evitar un bucle infinito.

### Estructura de una Función Recursiva

Una función recursiva generalmente tiene dos partes:

1. **Condición Base**: La condición que permite a la función dejar de llamarse a sí misma.
2. **Caso Recursivo**: La parte donde la función se llama a sí misma con un argumento modificado.

### Ejemplo de Recursividad: Factorial

El factorial de un número `n` (denotado como `n!`) es el producto de todos los enteros positivos menores o iguales a `n`. Por ejemplo, `5! = 5 * 4 * 3 * 2 * 1 = 120`.

```jsx
let parImpar = (numero) => {
    if (numero === 0) {
        return 'Par';
    } else if (numero === 1) {
        return 'Impar';
    } else {
        return parImpar(numero - 2);
    }
};
console.log(parImpar(20)) // Par
console.log(parImpar(75)) // Impar
console.log(parImpar(98)) // Par
console.log(parImpar(113)) // Impar
```

### Implementación Iterativa

```jsx
function factorialIterativo(n) {
    let resultado = 1;
    for (let i = n; i > 0; i--) {
        resultado *= i;
    }
    return resultado;
}

console.log(factorialIterativo(5)); // Output: 120

```

### Implementación Recursiva

```jsx
function factorialRecursivo(n) {
    // Condición Base
    if (n === 0) {
        return 1;
    }
    // Caso Recursivo
    return n * factorialRecursivo(n - 1);
}

console.log(factorialRecursivo(5)); // Output: 120

```

### Ejemplo de Recursividad: Fibonacci

La secuencia de Fibonacci es una serie de números en la que cada número es la suma de los dos anteriores. Los primeros números en la secuencia son `0` y `1`. Por ejemplo, los primeros cinco números de Fibonacci son `0, 1, 1, 2, 3`.

### Implementación Iterativa

```jsx
function fibonacciIterativo(n) {
    let a = 0, b = 1, temp;
    for (let i = 1; i < n; i++) {
        temp = a;
        a = b;
        b = temp + b;
    }
    return a;
}

console.log(fibonacciIterativo(5)); // Output: 3

```

### Implementación Recursiva

```jsx
function fibonacciRecursivo(n) {
    // Condiciones Base
    if (n === 0) {
        return 0;
    }
    if (n === 1) {
        return 1;
    }
    // Caso Recursivo
    return fibonacciRecursivo(n - 1) + fibonacciRecursivo(n - 2);
}

console.log(fibonacciRecursivo(5)); // Output: 3

```

### Ventajas y Desventajas de la Recursividad

### Ventajas

- **Simplicidad**: Algunas soluciones recursivas pueden ser más simples y más fáciles de entender que sus contrapartes iterativas.
- **Elegancia**: Las soluciones recursivas pueden ser más elegantes y concisas.

### Desventajas

- **Rendimiento**: Las soluciones recursivas pueden ser menos eficientes en términos de tiempo y espacio debido a las llamadas de función repetidas y al uso de la pila de llamadas.
- **Riesgo de Desbordamiento de Pila**: Las funciones recursivas pueden provocar un desbordamiento de pila si la recursividad es demasiado profunda.

### Optimización: Recursividad con Memoización

La memoización es una técnica que se utiliza para optimizar las funciones recursivas almacenando los resultados de las subcomputaciones.

### Ejemplo de Fibonacci con Memoización

```jsx
function fibonacciMemoizado(n, memo = {}) {
    // Verificar si el valor ya está calculado
    if (memo[n] !== undefined) {
        return memo[n];
    }
    // Condiciones Base
    if (n === 0) {
        return 0;
    }
    if (n === 1) {
        return 1;
    }
    // Calcular el valor y almacenarlo en el objeto memo
    memo[n] = fibonacciMemoizado(n - 1, memo) + fibonacciMemoizado(n - 2, memo);
    return memo[n];
}

console.log(fibonacciMemoizado(5)); // Output: 3

```

### Resumen

La recursividad es una poderosa técnica de programación que puede simplificar la solución de problemas complejos. Sin embargo, es importante usarla con cuidado y considerar la optimización y las posibles desventajas. Entender y aplicar la recursividad correctamente es una habilidad valiosa en el desarrollo de software.