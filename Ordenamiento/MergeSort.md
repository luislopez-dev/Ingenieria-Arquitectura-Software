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

  if (arr.length < 2) {
    return arr;
  }
  if (arr.length === 2) {

    return arr[0] > arr[1] ? [arr[1], arr[0]] : arr;
  }

  const middle = Math.floor(arr.length / 2);
  const leftArray = arr.slice(0, middle);
  const rightArray = arr.slice(middle);

  const leftSortedArray = sort(leftArray);
  const rightSortedArray = sort(rightArray);

  const mergedArr = [];
  let leftArrIndex = 0;
  let rightArrIndex = 0;
  
  while (
    leftArrIndex < leftSortedArray.length ||
    rightArrIndex < rightSortedArray.length
  ) {
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
  return mergedArr;
}
```