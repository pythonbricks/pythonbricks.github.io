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

#### Posibles modificaciones
* Diferentes personajes
* Añadir más elementos a las historias
* Permitir al usuario introducir su nombre
* Permitir que el usuario añada nuevas líneas
* Cargar las líneas de un fichero de texto
* Ir guardando las historias generadas como si fuera un resumen
