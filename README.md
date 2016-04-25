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

## Proyecto 2

### Objetivo
uno de los mayores componentes de un sistema operativo es su interfaz de llamadas al sistema. Esta interfaz permite a los programas de usuario solicitar servicios del sistema operativo. En este proyecto aprenderá como usar algunas de estas llamadas al sistema proveidas por el BIOS. También creará sus propias llamadas al sistema para imprimir una cadena de texto en la pantalla, leer texto desde el teclado y leer un sector del disco. Estas llamadas se usarán en proyectos posteriores para crear un shell interactivo y un sistema de archivos.

### Shell Script
1. Modificarl el shell script compileOS para copiar el archivo de texto `message.txt` que se incluye al sector 30 del disco.

### Kernel
1. Crear una función llamada `printString` que reciba como argumento una cadena de texto (char *), imprima el contenido de la cadena en la pantalla y retorne el número de caracteres que imprimió. La función debe imprimir cada caracter de la cadena exepto el caracter de `null` al final de la cadena.
2. Crear una función llamada `readChar` que lea un caracter del teclado usando la interrupción `0x16` y retorne el caracter leído.
3. Crear una función llamada `readString` que reciba como argumento una cadena de texto (char *), lea una cadena de caracteres del teclado y la almacene en la cadena recibida como argumento y retorne el número de caracteres leído.
4. Crear una función `readSector` que reciba como argumentos una dirección de memoria y un número de sector, convierta ese número de sector en una dirección T:H:S, lea el sector indicado del disco usando la interrupción `0x13` y coloque el sector leído en la dirección de memoria recibida como argumento. La función debe retornar 1 si se leyó el sector correctamente y cualquier otro valor en caso contrario.
5. Crear la interfaz de llamadas al sistema.
6. Crear las llamadas al sistema para `printString`, `readChar` y `readString`
7. La función `readString` debe manejar adecuadamente las teclas `backspace` y `delete`.

[Aquí](http://users.dickinson.edu/~braught/courses/cs354s12/proj/p2.pdf) puede encontrar la definición completa del proyecto 2.

### Evaluación
1. Modificar el script compileOS para copiar el archivo messages.txt en el sector 30 del disco: 10%
2. Kernel
    1. La función `printString` imprime el texto correctamente en la pantalla usando la interrupción `0x10`, retorna el número de caracteres impresos y no imprime el caracter `null`: 10%
    2. La función `readChar` lee correctamente un caracter del teclado usando la interrupción `0x16`, retorna el caracter ASCII leído, el scan code y devuelve 1 si el caracter se leyó correctamente: 15%
    3. La función `readString` lee correctamente una cadena de texto del teclado usando la interrupción `0x16` hasta que la tecla ENTER sea presionada, no incluye el caracter ENTER en la cadena leída, agrega el caracter `null` al final de la cadena leída y retorna el número de caracteres leídos y maneja adecuadamente los caracteres `backspace` y `delete`: 15% 
    4. La función `readSector` lee correctamente un sector del disco usando la interrupción `0x13`, calculando correctamente la dirección T:HS y devuelve 1 si se leyó el sector correctamente: 20%
    5. Se implementó correctamente la interfaz de llamadas al sistema, modificando correctamente los archivos asm según se indica, invocando las funciones `printString`, `readChar` y `readString` usando las interrupciones indicadas: 30%
