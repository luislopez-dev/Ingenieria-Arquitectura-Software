# Ordenamiento por burbuja (BubbleSort)

Consiste en comparar cada elemento, uno por uno, con los elementos adyacentes (o subyacente en caso de que el ordenamiento sea descendente), hasta que se encuentre uno que cumpla con la regla de ordenamiento, se intercambien las posiciones de los dos elementos y la comparación continúe los próximos elementos adyacentes.  
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

  const resultArray = [...arr];

  for (let outer = 0; outer < resultArray.length; outer++) {

    let outerEl = resultArray[outer];

    for (let inner = outer + 1; inner < resultArray.length; inner++) {

      let innerEl = resultArray[inner];

      if (outerEl > innerEl) {

        resultArray[outer] = innerEl;
        resultArray[inner] = outerEl;

        outerEl = resultArray[outer];
        innerEl = resultArray[inner];

      }
    }
  }

  return resultArray;
}

const sortedArray = sort([5, 10, -3, -10, 1, 100, 99]);
```

