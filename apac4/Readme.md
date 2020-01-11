**TO-DO 1.**

a) Creamos un fichero "hola mundo" al cual con la siguiente estructura:

#include <stdio.h>
int main(void)
{
    printf("Hola Mundo");
    return 0;
    }

b) Posteriormente por la terminal ejecutamos make siguiendo los siguientes comandos:

xubuntu@xubuntu-VirtualBox:~/Documentos/Ejercicios/apac4$ make hola
cc     hola.c   -o hola

Con esta instrucción se genera el fichero ejecutable "hola"

c) Posteriormente ejecutamos el fichero para ver por terminal el mensaje.

xubuntu@xubuntu-VirtualBox:~/Documentos/Ejercicios/apac4$ ./hola
Hola Mundo

**TO-DO 2.**

a)Creamos los fichero calc.c, calcula.c y calc.h siguiendo las indicaciones del ejercicio.

Después de crearlos ejecutamos por terminal el siguiente comando:

gcc -c calc.c -o calc.o

dando como resultado la creación del fichero calc.o.

Por último para conseguir el fichero ejecutable pasamos por terminal la siguiente instrucción.

gcc calc.o calcula.c -o calcula

Para ejecutar el fichero y comprobar que funciona correctamente volvemos introducimos en la terminal.

./calcula

b) Introducimos en los ficheros calc.c, calcula.c y calc.h la función major y repetimos los pasos anteriores para generar el fichero ejecutable.

**TO-DO 3.**

a)Creamos el fichero Makefile introduciendo las órdenes para que genere los ficheros, previamente hemos borrado los ficheros generados en los pasos anteriores.

b)Ejecutamos en la terminal make calcula para que nos genere los ficheros y posteriormente ejecutamos el archivo con la orden ./calcula para verificar que se han generado correctamente los ficheros.

c) Invertirmos el orden de las acciones en lugar de:

calcula: calcula.c calc.o
	gcc -Wall -g calcula.c calc.o -o calcula

calc.o: calc.c calc.h
	gcc -g -Wall -c calc.c -o calc.o

Creamos las instrucciones del Makefile

calc.o: calc.c calc.h
	gcc -g -Wall -c calc.c -o calc.o

calcula: calcula.c calc.o
	gcc -Wall -g calcula.c calc.o -o calcula

Previamente borramos de la carpeta los ficheros calc.o y calcula generados anteriormente y al pasar por la terminal make calcula nos vuelve a generar correctamente los ficheros y se ejecuta sin problemas.