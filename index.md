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
