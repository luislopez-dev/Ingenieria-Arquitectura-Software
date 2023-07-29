# Algorítmo de ordenación por fusión (MergeSort)

Consiste en dividir los elementos de una estructura de datos recursivamente hasta formar nuevas estrucuras conformadas por solo dos o un elemento. La división de los elementos empieza desde el elemento en el centro, separando así los datos en dos nuevas estructuras y repitiendo el proceso de manera recursiva hasta formar estructuras que contengas unicamente dos o un elemento de la estructura de datos inicial.

##  Complejidad algorítmica temporal: <br><br>

| Mejor Caso | Caso promedio | Peor Caso |
| --- | --- | --- |
| Los elementos están ordenados de forma random | Los elementos están ordenados de forma random | Los elementos están ordenados de forma random
| <strong>O (n * log n)</strong> | <strong>O (n * log n)</strong>  | <strong>O (n * log n)</strong> |

## Algorítmo:

```js
function sort(arr) {
  // Si el array tiene menos de 2 elementos, no es necesario ordenarlo, así que devolvemos el array tal cual.
  if (arr.length < 2) {
    return arr;
  }

  // Caso base: Si el array tiene exactamente 2 elementos, los comparamos y los intercambiamos si es necesario.
  if (arr.length === 2) {
    return arr[0] > arr[1] ? [arr[1], arr[0]] : arr;
  }

  // Calculamos el punto medio del array para dividirlo en dos partes iguales.
  const middle = Math.floor(arr.length / 2);

  // Dividimos el array en dos partes: la izquierda y la derecha.
  const leftArray = arr.slice(0, middle);
  const rightArray = arr.slice(middle);

  // Llamamos recursivamente a la función "sort" para ordenar las dos mitades del array.
  const leftSortedArray = sort(leftArray);
  const rightSortedArray = sort(rightArray);

  // Fusionamos las dos mitades ordenadas en un solo array ordenado.
  const mergedArr = [];
  let leftArrIndex = 0;
  let rightArrIndex = 0;

  while (
    leftArrIndex < leftSortedArray.length ||
    rightArrIndex < rightSortedArray.length
  ) {
    // Comparamos los elementos actuales de las dos mitades y los agregamos al array final en orden ascendente.
    if (
      leftArrIndex >= leftSortedArray.length ||
      leftSortedArray[leftArrIndex] > rightSortedArray[rightArrIndex]
    ) {
      mergedArr.push(rightSortedArray[rightArrIndex]);
      rightArrIndex++;
    } else {
      mergedArr.push(leftSortedArray[leftArrIndex]);
      leftArrIndex++;
    }
  }

  // Devolvemos el array final, que contiene los elementos ordenados de manera ascendente.
  return mergedArr;
}

```