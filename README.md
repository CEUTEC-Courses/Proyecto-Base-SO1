# Sistemas Operativos I - Proyecto

## Proyecto 1

### Objetivo
Este es primordialmente un proyecto *de entrenamiento* cuyo objetivo es que te familiarices con el proceso de arranque y con las herramientas y el simulador que se usará en el resto de proyectos. El producto final para este proyecto sera un kernel muy pequeño que imprimirá "Hello World" en la pantalla y luego se detentrá (entrará en un ciclo infinito) y un shell script para crear una imagen de disco bootable conteniendo ese kernel.

### Mejoras al Kernel
1. Crear una función `putChar` que muestre un caracter en un color especificado en una posición específica de la pantalla. La funcion `putChar` debe aceptar como argumentos el caracter a ser impreso, la fila y columna donde imprimirlo y el color en que se debe imprimir. Se debe imprimir "Hello World" en la esquina superior izquierda de la pantalla y usar el método `putChar` para imprimir "Hello World" de color blanco sobre fondo rojo en el centro de la pantalla.
2. Crear una función `putStr` que muestre una cadena de texto de un color especificado en una posición específica de la pantalla. La función `putStr` debe aceptar como argumentos la cadena de texto a ser impreso, la fila y columna donde se va a imprimir el primer caracter de la cadena y el color en que se debe imprimir. Cada caracter sucesivo en la cadena se debe imprimir una columna a la derecha. Si se llega al final de la línea se debe saltar a la línea siguiente. No se debe imprimir ningún caracter más allá del final de la pantalla. Se debe imprimir "Hello World" en blanco sobre fondo rojo en la esquina inferior derecha de la pantalla usando el método `putStr`.

[Aquí](http://users.dickinson.edu/~braught/courses/cs354s12/proj/p1.pdf) puede encontrar la definición completa del proyecto 1.
