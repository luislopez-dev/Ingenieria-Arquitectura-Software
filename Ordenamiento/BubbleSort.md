# Ordenamiento burbuja (BubbleSort)

Consiste en comparar cada elemento de una estructura de datos con sus elementos adyacentes (o subyacentes en caso de que el ordenamiento sea descendente), uno por uno hasta que se compare con uno que cumpla con la regla de ordenamiento, cuando se encuentre este elemento, se intercambiarán las posiciones de los dos elementos en comparación, y luego la comparación continuará con el resto de elementos pendientes de ser comparados usando el nuevo elemento posicionado.

<br>
## Complejidad algorítmica temporal: <br><br>

| Mejor Caso | Caso promedio | Peor Caso |
| --- | --- | --- |
| Los elementos ya están ordenados | Los elementos poseen posiciones random y se desconoce la posición de cada uno | Los elementos están ordenados en el orden incorrecto |
| <strong>O (n)</strong> | Tiende a ser <strong>O (n**2)</strong>  | <strong>O (n**2)</strong> |

<br>

## Algorítmo: 

<br>

```js
function sort(arr) {
  // Creamos una copia del array original para evitar modificarlo directamente
  const sortedArray = [...arr];

  // Bucle externo que recorre todo el array (elemento por elemento)
  for (let i = 0; i < sortedArray.length; i++) {
    // Guardamos el valor del elemento actual en la posición "i"
    let currentElement = sortedArray[i];

    // Bucle interno que compara el elemento actual con los elementos restantes
    for (let j = i + 1; j < sortedArray.length; j++) {
      // Guardamos el valor del elemento en la posición "j"
      let nextElement = sortedArray[j];

      // Comparamos si el elemento en la posición "i" es mayor que el elemento en la posición "j"
      if (currentElement > nextElement) {
        // Si la condición es verdadera, intercambiamos los elementos de posición para que el menor quede primero
        sortedArray[i] = nextElement;
        sortedArray[j] = currentElement;

        // Actualizamos los valores de "currentElement" y "nextElement" después del intercambio
        currentElement = sortedArray[i];
        nextElement = sortedArray[j];
      }
    }
  }
  // Devolvemos el array ordenado
  return sortedArray;
}
```

