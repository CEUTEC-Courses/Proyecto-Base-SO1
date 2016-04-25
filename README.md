# Sistemas Operativos I - Proyecto

## Proyecto 1

### Objetivo
Este es primordialmente un proyecto *de entrenamiento* cuyo objetivo es que te familiarices con el proceso de arranque y con las herramientas y el simulador que se usará en el resto de proyectos. El producto final para este proyecto sera un kernel muy pequeño que imprimirá "Hello World" en la pantalla y luego se detentrá (entrará en un ciclo infinito) y un shell script para crear una imagen de disco bootable conteniendo ese kernel.

### Shell script
1. Crear un shell script llamado compileOS que:
    1. Compile el bootloader.
    2. Compile el kernel (ensamblador y c)
    3. Enlace el kernel ensamblador y el kernel c
    4. Cree una imagen de disco en blanco.
    5. Copie el bootloader en el sector 0.
    6. Copie el kernel en el sector 3.

### Mejoras al Kernel
1. Usando la función `putInMemory`, imprima la frase "Hello World" en la esquina superior izquierda de la pantalla.
2. Crear una función `putChar` que muestre un caracter en un color especificado en una posición específica de la pantalla. La funcion `putChar` debe aceptar como argumentos el caracter a ser impreso, la fila y columna donde imprimirlo y el color en que se debe imprimir. Se debe imprimir "Hello World" en la esquina superior izquierda de la pantalla y usar el método `putChar` para imprimir "Hello World" de color blanco sobre fondo rojo en el centro de la pantalla.
3. Crear una función `putStr` que muestre una cadena de texto de un color especificado en una posición específica de la pantalla. La función `putStr` debe aceptar como argumentos la cadena de texto a ser impreso, la fila y columna donde se va a imprimir el primer caracter de la cadena y el color en que se debe imprimir. Cada caracter sucesivo en la cadena se debe imprimir una columna a la derecha. Si se llega al final de la línea se debe saltar a la línea siguiente. No se debe imprimir ningún caracter más allá del final de la pantalla. Se debe imprimir "Hello World" en blanco sobre fondo rojo en la esquina inferior derecha de la pantalla usando el método `putStr`.

[Aquí](http://users.dickinson.edu/~braught/courses/cs354s12/proj/p1.pdf) puede encontrar la definición completa del proyecto 1.

### Evaluación
1. Shell script: 30%
2. Kernel
    1. Compila correctamente y bootea el bootloader y el kernel: 5%
    2. Imprimir "Hello World" usando la función `putInMemory`: 10% 
    3. Crear función `putChar` y usarla para imprimir "Hello World" en el centro de la pantalla: 20%
    4. Crear funcion `putStr` y usarla para imprimir "Hello World" en la esquina inferior derecha de la pantalla: 35% 
