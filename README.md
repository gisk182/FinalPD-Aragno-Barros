# FinalPD-Aragno-Barros
FinalPD
Sopa de letra

TRABAJO FINAL PROGRAMACION DECLARATIVA

Integrantes: Aragno, Mauricio Barros, Matias

Fecha: 19/2/2021

Tema: Programacion Haskell

Nombre del software: Sopa de letras

El juego contiene 3 clases, La clase Lib.hs, Main.hs y Data.hs 1 – En la clase Data.hs es el lugar donde creamos dos los arreglos de la sopa de letra, en un arreglo tenemos las palabras a buscar, y en el otro las letras.

2 – El juego comienza en la clase Main.hs el cual se encarga de ser el nexo entre las demás clases y llama a la función makeGame que pasa las variables de la clase Lib.hs para que lo transforme en una variable que pueda ser utilizada en el juego, luego inicializa el mismo con la funcion playGame pasando como atributo la variable g creada anteriormente

3 – En la clase Lib.hs se programo la lógica del juego, desde el main.hs lo primero que se llama es a la función makeGame, el cual recibe la matriz de letras y el arreglo de las palabras a buscar, le genera las coordenadas a cada letra de la matriz y inserta las palabras en una variable que es un mapeo donde el key son las palabras y el valor vacio, que se llenara luego de que el usuario adivine las palabras, finalmente se carga la variable Game con la matriz ya con coordenadas y el mapa con las palabras a buscar.

4 – El juego comienza en PlayGame el cual recibe una variable game, primero asigna variables locales, donde consigue por separado la matriz, el listado de palabras, la cantidad de aciertos y el total de palabras a buscar, luego el programa pide que el usuario cargue el nombre de un lenguaje, y con ella y la matriz llama a la función playWord. Si la cantidad de palabras encontradas es igual al total de palabras, se termina el juego con un mensaje de felicitación.

5 – la función totalWords toma la cantidad de elementos que tiene el mapa, esto da la cantidad de palabras en total a buscar, y la función score toma la cantidad de elementos que tiene cargado el mapa, ósea las palabras encontradas, porque al encontrarse una palabra se carga en el mapa un arreglo con las coordenadas de la misma.

6 – esta función detecta si ingreso una palabra incorrecta, y además define variables como foundWord que se utiliza para el case donde si esta cargada founWord entonces se actualiza el mapa insertando el arreglo de coordenadas de la palabra encontrada, se actualiza la variable Game y se devuelve, si no encuentra la palabra no modifica nada y devuelve la variable Game como estaba.

7 – la función findWord llama a la función getLines para obtener la matriz con todas las posibles formas para luego hacer la búsqueda llamando a la función findWordInCellInFix

8 – la función getLines va a generar las distintas formas para recorrer la matriz, de la forma horizontal, vertical y de las dos formas diagonales, para luego juntarlas y sumar la inversa de la misma. La función diagonalize realiza la transpuesta de la función skew la cual se encarga de hacer la diagonalización.

9 – esta función resuelve posibles casos, si se vació el arreglo al recorrerlo no devuelve nada, si se ejecuta findWordInCellPrefix y no encuentra en la línea la palabra entonces se vuelve a llamar findWordInCellInfix para que saque el header y tome el resto del cuerpo, en el caso que se encuentre y se llene foundWord lo devuelve

10 – la función que esta debajo cell2char es una función que nos ayuda a mostrar el contenido char de una determinada coordenada.

11 – la función findWordInCellPrefix es la encargada de buscar las letras de la palabra en la matriz, definiendo un acumulador (acc) para ir guardando las coordenadas, esta función va recorriendo la lista de letras hasta que coincida una y pasa a la siguiente letra de la palabra, cuando este cargado el acumulador y el arreglo de la palabra este vacio, entonces significa que se tiene el conjunto de puntos para devolver, por lo que se realiza la inversa del acumulador, porque guarda cada nuevo elemento al comienzo del mismo en vez de hacerlo al final, y en cualquier otro caso no devuelve nada.

12 – la función gridWithCoords es utilizada por la función makeGame para asignarle unas coordenadas x e y a la matriz de letras, y la función formatGrid se utiliza para transformar la matriz con coordenadas en un string para mostrarlo en pantalla en la función playGame.
