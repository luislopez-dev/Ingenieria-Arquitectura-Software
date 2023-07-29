# Algorítmo de búsqueda rápida (QuickSort)

Consiste en utiliza a un elemento pivote (el primer elemento en el array) para repartir el resto de elementos en tres diferentes categorías: "elementos más grandes", "elementos más pequeños" y "elementos iguales al elemento pivote". Se repite ese proceso de forma recursiva para todos las estructuras de elementos divididos y se concatenan los elementos ordenados.

<br> 

##  Complejidad algorítmica temporal: <br><br>

| Mejor Caso | Caso promedio | Peor Caso |
| --- | --- | --- |
| Los elementos están ordenados de forma random (no en el orden correcto) | Los elementos están ordenados de forma random (no en el orden correcto) | Los elementos ya están ordenados (el orden no importa) |
| <strong>O (n * log n)</strong> | <strong>O (n * log n)</strong>  | <strong>O (n**2)</strong> |

<br>


## Algorítmo:

```js
function sort(arr) {
  // Hacemos una copia del array de entrada para evitar modificar el array original
  const copiedArray = [...arr];

  // Si el copiedArray contiene 0 o 1 elemento, ya está ordenado, así que lo retornamos
  if (copiedArray.length <= 1) {
    return copiedArray;
  }

  // Inicializamos tres arreglos para almacenar elementos menores, iguales y mayores que el pivote
  const smallerElementsArray = [];
  const biggerElementsArray = [];
  const pivotElement = copiedArray.shift(); // Seleccionamos el elemento pivote (en este caso, el primer elemento)
  const centerElementsArray = [pivotElement]; // El elemento pivote es considerado inicialmente como el elemento central

  // Iteramos a través de los elementos restantes en copiedArray
  while (copiedArray.length) {
    const currentElement = copiedArray.shift();

    // Comparamos cada elemento con el elemento pivote y lo colocamos en el arreglo apropiado
    if (currentElement === pivotElement) {
      centerElementsArray.push(currentElement); // Si el elemento es igual al pivote, lo agregamos al arreglo centerElementsArray
    } else if (currentElement < pivotElement) {
      smallerElementsArray.push(currentElement); // Si el elemento es menor que el pivote, lo agregamos al arreglo smallerElementsArray
    } else {
      biggerElementsArray.push(currentElement); // Si el elemento es mayor que el pivote, lo agregamos al arreglo biggerElementsArray
    }
  }

  // Ordenamos de forma recursiva los arreglos de elementos menores y mayores utilizando el mismo algoritmo Quicksort
  const smallerElementsSortedArray = sort(smallerElementsArray);
  const biggerElementsSortedArray = sort(biggerElementsArray);

  // Concatenamos los elementos ordenados menores, los elementos centrales (iguales al pivote) y los elementos ordenados mayores para formar el arreglo final ordenado
  return smallerElementsSortedArray.concat(
    centerElementsArray,
    biggerElementsSortedArray
  );
}
```