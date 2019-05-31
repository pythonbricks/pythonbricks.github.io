# Python Bricks

### Consejos inciales
Estas actividades se pueden realizar [online](https://repl.it/) o con PyCharm, que ya lo tienen instalado en los portátiles. En ambos casos la versión instalada es Python 3
La idea es que sean capaces de programar ustedes solos. Ánimo!

## 1. Aventura de texto
En este primer ejercicio lo que se busca es ir pillando soltura con Python. Para ello, vamos a hacer una historia o cuento que será como los libros de "Elige tu propia aventura", es decir, contaremos una historia y le haremos preguntas al jugador. Dependiendo de la respuesta que nos de, pasará una cosa u otra

(Sé que no se lo van a leer, pero les dejo [un poquito de historia](https://es.wikipedia.org/wiki/Aventura_conversacional) )

Para poder hacerle preguntas al usuario necesitamos usar la función `input`. Con `input` podemos recoger un valor que le preguntemos al usuario. Sería algo así:

```python
name = input("¿Cómo te llamas? ")
print("Encantado, " + name + "!")
```
Gracias a esta función podemos ir preguntándole cosas al usuario e ir guardando lo que nos responde. Así, podemos ir "personalizando" la historia, y dejando que el usuario participe en ella

Es buena idea dejar siempre un `else` cuando hagamos condicionales. De esta forma conseguimos que el programa no se pare aunque el usuario nos introduzca una respuesta que no se nos haya ocurrido, haciendo así que sea más entretenido

Hemos de tener en cuenta una cosa: En Python, si usamos el comparador `==`, las `string` han de ser exactamente iguales. Es decir, en esta comparación:
```python
respuesta = input("¿Como te llamas?")
if (respuesta == "Javi"):
    print ("Hola, profe")
else:
    print("Oye, tu no eres el profe")
```

En el caso de arriba, si el usuario pone Javi, la respuesta será la frase del `if`, pero si pone Javier, javi o cualquier otra combinación, la respuesta será la del `else`, porque no es exactamente igual. 

Esto es difiícil de evitar, pero para ayudarnos a ello, podemos utilizar las siguientes funciones:

```python
respuesta = respuesta.upper() // Pasamos respuesta a mayúsculas
respuesta = respuesta.lower() // Pasamos la respuesta a minúsculas
respuesta = respuesta.trim()  // Le quitamos los espacios a la repsuesta al principio y al final
```

De esta forma, podemos ir construyendo poco a poco la historia. Para empezar, es buena idea preguntarle al jugador cómo se llama, y utilizarlo más adelante. ¡ A ver que se les ocurre!

## 2. El cadáver exquisito

Suena raro, ya lo sé. Les cuento

El [cadáver exquisito]() es una técnica para escribir historias entre varias personas de forma divertida. Para ello, se escribe en un papel las diferentes partes que puede tener una historia, de la siguiente manera:
```markdown
1. Qué?
2. Cuándo?
3. Cómo?
4. Dónde?
6. Para qué?
```

Una vez escrito esto, cada jugador escribe la pregunta que le toca, la dobla de manera que el siguiente no la pueda ver, y pasa el papel. Así, al final sale una historia que tiene la misma estructura, pero como cada persona no puede saber qué fue lo que escribió la anterior... es una historia sin sentido

En esta actividad vamos a hacer un generador de historias de cadaver exquisito. Para ello, escribiremos una serie de listas que puedan ser (absurdas) respuestas a las preguntas de arriba, y luego usaremos Python para combinarlas de forma aleatoria

Algunas cosillas que nos pueden ser útiles:
```python

\\ 1. Elegimos un personaje
comienzo = "El pequeño Timmy "
\\ 2. Creamos una lista de strings por cada una de las preguntas
lista_que = ["Se cayó por un barranco", "Fue a comer", "Se enfadó porque"]

\\ Las combinamos

def imprime_historia():
    print(comienzo + lista_que[2])
    
imprime_historia()

// ESTE PROGRAMA IMPRIME LO SIGUIENTE
"El pequeño Timmy se enfadó porque ..."
```

Obviamente, si ponemos nosotros los números, ya sabemos que frases van a salir, por lo que la mejor idea en ese caso es imprimir *elementos aleatorios de las listas*, aunque siempre en el mismo orden. Es decir, nos podemos hacer un método que coja una frase de cada una de las listas y las combine. Así, cada vez que ejecutemos el programa tendremos *una historia diferente*

Entre más frases tengan las listas, más posibilidades de historias tendremos

##### Posibles modificaciones
* Diferentes personajes
* Añadir más elementos a las historias
* Permitir al usuario introducir su nombre
* Permitir que el usuario añada nuevas líneas
* Cargar las líneas de un fichero de texto
* Ir guardando las historias generadas como si fuera un resumen


## 3. Calculadora

Una de las primeras actividades que se suele hacer cuando se empieza en un lenguaje nuevo es programar una calculadora. Es decir, vamos a hacer un programa que le pida dos números al usuario, y luego nos permita realizar una operación (Las típicas, suma, resta, multiplicación y división).

En principio vamos a hacer algo sencillo:
1. Le pedimos al usuario que introduzca un número
2. Le pedimos un segundo número
3. Le preguntamos qué operación desea realizar

Y mostramos el resultado, imprimiéndolo en una nueva línea

##### Posibles modificaciones
* Definir los símbolos de las operaciones
* Hacer que entienda operaciones en una sola línea, en vez de pedirlo de forma separada (" 3 / 4", por ejemplo")
* Hacer que pueda hacer más de una operación, guardando el resultado

## 4. Piedra, papel, tijeras
El clásico juego de toda la vida, pero en versión código. Tendremos que preguntarle al usuario qué escoge, y elegir una de las opciones en nuestro programa de forma aleatoria.

Tendremos que hacer un método, que admita dos parámetros (la jugada del usuario y la de la máquina) y nos diga quien es el ganador. Una vez lo sepamos, debemos mostrar el ganador por pantalla

##### Posibles modificaciones
* Que las partidas sean al mejor de tres
* Partidas infinitas por puntos
* Meter un elemento nuevo en la logica del juego
* Definir trucos
* Que el programa se ría de ti cuando pierdas

## 5. Generador de scripts en .bat
Se acuerdan de cuando estuvimos haciendo scripts en .bat o .vbs? También les enseñé el programa que se "inventaba" nombres de personas, y sacaba unas listas para registros. Pues bien, la idea es hacer un generador de Scripts

##### ¿Cómo?
Python tiene módulos que nos permiten generar archivos con texto dentro. Si definimos una serie de funciones que hagan las distintas partes que tiene un archivo .bat, podemos construir varios tipos de scripts sin tener que escribirlos a mano

Por ejemplo:

```python
command = "@echo off";
def google(command):
    command += ("\nstart www.google.com")
   
    
def forocoches(command):
    command +=("\nstart www.forocoches.com")
    print (command)
    
def construye_bat():
    google(command)
    forocoches(command)
    
    
construye_bat()
```

Si en vez de hacer un print lo escribimos a un archivo, podremos después hacer doble click y utilizarlo, siempre que esté bien escrito


```python
#archivo-salida.py
f = open ('script.bat','w')
f.write('lo que vaya en el archivo')
f.close()

```
NOTA: Hay que abrir el archivo (f = open...) y después cerrarlo (f.close()), porque si no se quedará el archivo abierto y tendremos problemas para usarlo


## 6. Guess the number:
La idea es hacer un programa que nos haga adivinar un número aleatorio, elegido por él. Sería algo así como un "Adivina qué numero pienso".
El programa elegirá un número al azar, y nos pedirá que digamos un número. A continuación, comparará el número introducido con el que ha escogido, y nos dirá si es mayor o menor, para que podamos adivinarlo.

Ejemplo:
https://pythonbitsybricks.javiivaj.repl.run/

## 7. Cursos externos:
Fundación Raspberry:
https://projects.raspberrypi.org/es-ES/codeclub/python-module-1
 




