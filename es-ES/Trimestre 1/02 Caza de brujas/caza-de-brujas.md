---
title: Cazafantasmas
level: Nivel 1
language: es-ES
stylesheet: scratch
embeds: "*.png"
note: "notas para coordinadores.md"
...

# Introducción { .intro}
En este proyecto vamos a __Cazar Fantasmas__. Consigues puntos por golpear a los fantasmas que aparecen en la pantalla. ¡La meta es conseguir todos los puntos que puedas en 30 segundos!

![screenshot](ghostbusters_screenshot.png)

#PASO 1: Crea un fantasma volador { .activity}

## Progreso { .check}

+ __Crea un nuevo proyecto scratch.__
+ __Borra el objeto gato__ (haciendo click con el botón derecho y pulsando borrar)
+ __Cambia el fondo__ por  __naturaleza/woods__. Pulsa sobre el Escenario, ve a la pestaña Fondos y pulsa `Elegir un fondo desde la biblioteca` {.blockgrey}
+ Ahora, __Crea un nuevo objeto__. Usando el botón `Elegir un objeto desde la biblioteca` {.blockgrey} añade un nuevo fantasma al proyecto (usa el disfraz __fantasía/ghost1__). 
+ Cambia el nombre del nuevo objeto por __Fantasma1__

__Ahora queremos que nuestro fantasma se mueva__

+ Queremos que el fantasma se empiece a mover cuando inicia el juego, así que vamos a darle __un programa como este__:

```blocks

	al presionar BANDERA VERDE
	por siempre
		mover (5) pasos
```
		
##Prueba tu proyecto { .flag}
__Pulsa la bandera verde__ y mira qué hace tu fantasma. ¿Por qué se queda parado en el borde de la pantalla? 

## Progreso { .check}

+ Para conseguir que el fantasma no se pare necesitamos que cambie de dirección cuando toque un borde de la pantalla. Edita tu script para añadir un bloque `rebotar si toca un borde` {.blockblue} justo después del bloque `mover 5 pasos` {.blockblue}.

```blocks

	al presionar BANDERA VERDE
	por siempre
		mover (5) pasos
		rebotar si toca un borde
```
+ Para que el fantasma deje de ponerse boca abajo, haz click en `estilo de rotación: izquierda-derecha` {.blockgrey} en las propiedades del objeto.

##Prueba tu proyecto { .flag}
__Pulsa la bandera verde.__
¿Se mueve el fantasma de un lado a otro de la pantalla?

##Guarda tu proyecto { .save}

##Cosas para probar { .try}
+ __¿Cómo harías que el fantasma vuele más deprisa o más despacio?__

#PASO 2: Hacer que el fantasma aparezca al azar { .activity}

Para que el juego sea más divertido, queremos que el fantasma aparezca en una posición al azar. Conseguiremos esto con otro programa que se ejecuta a la vez que el que mueve el fantasma. Este nuevo programa necesita esconder el fantasma durante un tiempo aleatorio y repetirlo por siempre (o hasta que el juego se acabe).

## Progreso { .check}

+ __Crea este programa para el fantasma:__ (¡sin borrar el programa que ya tienes!)

```blocks

	al presionar BANDERA VERDE
	por siempre
		esconder
		esperar (número al azar entre (2) y (5)) segundos
		mostrar
		esperar (número al azar entre (2) y (10)) segundos

```
##Prueba tu proyecto { .flag}
__Pulsa la bandera verde.__
¿Se mueve el fantasma de un lado a otro de la pantalla y aparece/desaparece al azar?

##Guarda tu proyecto { .save}

##Cosas para probar { .try}
+ __Cambia el rango de los números al azar. ¿Qué pasa si pones números muy grandes o muy pequeños?__

#PASO 3: Hacer que el fantasma desaparezca al pulsarlo { .activity}

Para convertir esto en un juego, necesitamos que el jugador haga algo. Necesitan hacer click en el fantasma para que desaparezca. Cuando el fantasma sea pulsado queremos que desaparezca y suene un sonido. 

## Progreso { .check}

+ En la pestaña __Sonidos__, añade un nuevo sonido __Electrónica/fairydust__, usando el botón `Elegir un sonido desde la biblioteca` {.blockgrey}. 

+ __Añade este programa al fantasma__:

```blocks

	al clickear este objeto
	esconder
	tocar sonido [Fairydust v]
```
##Prueba tu proyecto { .flag}
__Pulsa la bandera verde.__

¿Desaparece el fantasma y se oye un sonido cuando lo pulsas?


##Guarda tu proyecto { .save}

#PASO 4: Añadir la puntuación y el tiempo { .activity}

Tenemos un fantasma, pero ¡queremos hacer un juego! Queremos ganar puntos cada vez que pulsemos el fantasma pero también queremos tener un límite de tiempo. Podemos usar variables para la puntuación y el tiempo.

## Progreso { .check}

+ Crea una nueva `Variable` {.blockgrey} para todos los objetos llamada __puntos__, y cambia el script del fantasma para que aumente la puntuación cada vez que pulsas.

```blocks

	al clickear este objeto
	esconder
	tocar sonido [Fairydust v]
	cambiar [puntos v] por (1)
```
+ Cambia al __Escenario__ y crea una __nueva variable__ llamada __tiempo__. Añade un nuevo programa que se ejecuta al pulsar la bandera verde para poner la variable `tiempo` {.blockorange} a __30__ y poner los puntos a __0__. Luego usa un bloque `repetir hasta que` {.blockyellow} para esperar un segundo y luego restar 1 a `tiempo` {.blockorange}. 

Esto se tiene que repetir hasta que el tiempo sea 0. En ese punto usaremos `detener todo` {.blockyellow} para parar el juego.

```blocks

	al presionar BANDERA VERDE
	fijar [tiempo v] a (30)
	fijar [puntos v] a (0)
	repetir hasta que <(tiempo) = [0]>
		esperar (1) segundos
		cambiar [tiempo v] por (-1)
	fin	
	detener [todos v]
```


##Prueba tu proyecto { .flag}
__Pulsa la bandera verde.__

##Guarda tu proyecto { .save}

##Cosas que probar { .try}
1. __¡Bien hecho! Has terminado el juego básico. Hay muchas más cosas que puedes hacer en tu juego ¿Te atreves con el resto?__

##Reto: Añadir más fantasmas { .challenge}
¡Si un fantasma es divertido, más será mejor! __Vamos a crear tres fantasmas.__
1. Duplica el fantasma haciendo __click con el botón derecho__ en la lista de objetos.
2. Cambia el __tamaño de cada objeto__ para que cada fantasma sea distinto.
3. Para cada fantasma cambia la __velocidad__ y así volarán a velocidades distintas.
4. Mueve los fantasmas en el dibujo para que no estén todos juntos, también puedes probar a girarlos. 

##Prueba tu proyecto { .flag}
__Pulsa la bandera verde.__

¿Tienes tres fantasmas moviéndose de un lado a otro de la pantalla, apareciendo y desapareciendo y que desaparecen cuando pulsas sobre ellos? 

##Guarda tu proyecto { .save}

##Cosas para probar { .try}

1. __¿Cual es el mejor número de fantasmas en el juego?__
2. __¿Puedes hacer que cada fantasma sea distinto? También puedes cambiar sus disfraces, o usar algunas opciones de la pestaña Apariencia para que cambien.__
3. __¿Puedes hacer que cada fantasma tenga una puntuación distinta? ¿Qué te parece si los más rapidos valen 10 puntos?__


__¡Bien hecho, has acabado! Ahora ¡Disfruta de tu juego!__
No olvides que puedes compartir el juego con tu familia y amigos pulsando el botón __Compartir__ en la barra de herramientas
