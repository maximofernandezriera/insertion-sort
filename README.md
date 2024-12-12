# insertion-sort

### Inserción

El algoritmo de [insercción](https://es.wikipedia.org/wiki/Ordenamiento_por_inserci%C3%B3n). Inicialmente se tiene un solo elemento, que obviamente es un conjunto ordenado. Después, cuando hay k elementos ordenados de menor a mayor, se toma el elemento k+1 y se compara con todos los elementos ya ordenados, deteniéndose cuando se encuentra un elemento menor (todos los elementos mayores han sido desplazados una posición a la derecha) o cuando ya no se encuentran elementos (todos los elementos fueron desplazados y este es el más pequeño). En este punto se inserta el elemento k+1 debiendo desplazarse los demás elementos. En definitiva, en cada iteración, se selecciona el menor elemento del subvector no ordenado y se intercambia con el primer elemento de este subvector.

- https://es.wikipedia.org/wiki/Ordenamiento_por_inserci%C3%B3n

- https://youtu.be/Fmae5JfYkMg?si=yMPmMXXfCwUtQpHG

  ### Ejercicio 1

Ahora queremos ordenar el array, pero de forma descendente, colocando el elemento más pequeño en la posición más alta (es decir, al final del array). Implementa el método insertionSortDescendingOrder que ordenará arrays de forma descendente.

### Ejercicio 2

Implementa el método insertionSortAlternative, que ordena el array de derecha a izquierda, es decir, la parte ordenada estará en el lado derecho del array, empezando por el último elemento del array, mientras que la parte no ordenada estará en el lado izquierdo del array. El array ordenado debe ser el misma que el resultante cuando la parte ordenada está a la izquierda y la parte no ordenada está a la derecha.

- https://www.youtube.com/watch?v=ROalU379l3U

![imagen](https://upload.wikimedia.org/wikipedia/commons/0/0f/Insertion-sort-example-300px.gif)

```java
public class Insercion {

    public static void insercion(int[] array) {
        int aux;
        int j;
        for (int i = 1; i < array.length; i++) {
            aux = array[i];
            j = i - 1;
            while (j >= 0 && array[j] > aux) {
                array[j + 1] = array[j];
                j--;
            }
            array[j + 1] = aux;
        }
    }

    public static void main(String[] args) {
        int[] array = {5, 2, 9, 1, 5, 6};
        insercion(array);

        for (int num : array) {
            System.out.print(num + " ");
        }
    }
}
```
