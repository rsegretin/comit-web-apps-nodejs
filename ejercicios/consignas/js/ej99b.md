# Ejercicio 99b

* Crear un documento con el nombre ej99b.js
* Declarar un array vacío.
* Agregar en el array (push) todos los números entre 1 y 200 que sean múltiplos de 11.
* Mostrar ese array por consola.
* Generar a partir de ese array un string, concatenando todos sus elementos (sin ningún caracter en el medio).
* A partir de ese string obtenido, generar un array donde cada caracter de ese string sea un elemento, previamente convirtiéndolo en número (parseInt). Eso debería resultar en un array así:
```
[ 1, 1, 2, 2, 3, 3, 4, 4, 5, 5, 6, 6, 7, 7, 8, 8, 9, 9, 1, 1, 0, 1, 2, 1 ... (etc)]
```
* Recorrer ese array acumulando en una nueva variable la suma de cada elemento multiplicado por su ordinal de posición. Es decir, el resultado sería ```1*0 + 1*1 + 2*2 + 2*3 + 3*4 + 3*5 + 4*6 + 4*7 + .... etc```.
* Mostrar ese valor obtenido por consola.
