# Arreglos en JavaScript

¿Qué es un Array?

Un array es una estructura de datos que puede contener múltiples valores en una sola variable. Los arrays en JavaScript son dinámicos, lo que significa que puedes cambiar su tamaño y almacenar cualquier tipo de dato, incluyendo otros arrays.

## Creación de Arrays

Puedes crear un array de varias maneras:

### Usando la sintaxis literal de arrays

```jsx
let frutas = ["Manzana", "Banana", "Naranja"];

```

### Usando el constructor `Array`

```jsx
let frutas = new Array("Manzana", "Banana", "Naranja");

```

## Acceso a los Elementos del Array

Puedes acceder a los elementos de un array utilizando índices, que empiezan desde 0.

```jsx
let primeraFruta = frutas[0]; // "Manzana"
let segundaFruta = frutas[1]; // "Banana"

```

## Modificar Elementos del Array

Puedes cambiar los elementos de un array asignándoles nuevos valores.

```jsx
frutas[1] = "Pera";
console.log(frutas); // ["Manzana", "Pera", "Naranja"]

```

## Propiedades y Métodos de los Arrays

### `length`

La propiedad `length` devuelve el número de elementos en un array.

```jsx
let numeroDeFrutas = frutas.length; // 3

```

### Métodos comunes

### `push()`

Añade uno o más elementos al final del array.

```jsx
frutas.push("Uva");
console.log(frutas); // ["Manzana", "Pera", "Naranja", "Uva"]

```

### `pop()`

Elimina el último elemento del array y lo devuelve.

```jsx
let ultimaFruta = frutas.pop();
console.log(ultimaFruta); // "Uva"
console.log(frutas); // ["Manzana", "Pera", "Naranja"]

```

### `shift()`

Elimina el primer elemento del array y lo devuelve.

```jsx
let primeraFrutaEliminada = frutas.shift();
console.log(primeraFrutaEliminada); // "Manzana"
console.log(frutas); // ["Pera", "Naranja"]

```

### `unshift()`

Añade uno o más elementos al inicio del array.

```jsx
frutas.unshift("Fresa");
console.log(frutas); // ["Fresa", "Pera", "Naranja"]

```

### `indexOf()`

Devuelve el primer índice en el que se encuentra un elemento dado, o -1 si el elemento no está presente.

```jsx
let indiceDePera = frutas.indexOf("Pera"); // 1
let indiceDeUva = frutas.indexOf("Uva"); // -1

```

### `splice()`

Cambia el contenido de un array eliminando, reemplazando o añadiendo nuevos elementos.

```jsx
// Elimina 1 elemento en el índice 1
frutas.splice(1, 1);
console.log(frutas); // ["Fresa", "Naranja"]

// Añade "Limón" en el índice 1
frutas.splice(1, 0, "Limón");
console.log(frutas); // ["Fresa", "Limón", "Naranja"]

```

## Iterar sobre un Array

Puedes usar varios métodos para iterar sobre los elementos de un array.

### Usando un bucle `for`

```jsx
for (let i = 0; i < frutas.length; i++) {
  console.log(frutas[i]);
}

```

### Usando el método `forEach`

```jsx
frutas.forEach(function(fruta) {
  console.log(fruta);
});

```

### Usando `for...of`

```jsx
for (let fruta of frutas) {
  console.log(fruta);
}

```

## Conclusión

Los arrays son una parte fundamental de JavaScript y te permiten manejar colecciones de datos de manera eficiente. Existen muchos métodos y propiedades que puedes utilizar para manipular arrays según tus necesidades.

Espero que esta explicación te haya sido útil para comprender los arrays en JavaScript. ¡Feliz programación!