---
title: Máquina de Frutas
level: Nivel 2
stylesheet: scratch
language: es-ES
embeds: "*.png"
note: "notas para coordinadores.md"
materials: "*.sb2"
...

# Introducción {.intro}
En este juego tenemos tres objetos que van cambiando sus disfraces. Tienes que pararlos cuando sean iguales!.

![screenshot](fruitmachine_screenshot.png)

# PASO 1: Crear un objeto que va cambiando de disfraz { .activity}

## Progreso { .check}

__Vamos a cargar las imágenes que necesitamos para el juego__

+ Crea un nuevo proyecto Scratch. Borra el gato haciendo click con el botón derecho y pulsando Borrar. 
+ Lo primero de todo, vamos a añadir un nuevo fondo desde la biblioteca. Escoje el fondo **rays** de la categoría **Otros** y después borra el fondo blanco original.  
+ Ahora añade un objeto nuevo desde la biblioteca. 
+ Escoje una imagen desde cualquier carpeta. En el ejemplo hemos usado **Cosas/Bananas**, pero puedes usar cualquier imágen que te guste.
+ Haz click en la '**i**' azul al lado de la imagen del objeto en la ventana Objetos. Cambia el nombre del objeto a 'Fruta'.
+ Ahora pulsaen la pestaña Disfraces y carga dos nuevas imágenes para que haya un total de tres disfraces (en el ejemplo hemos usado **cosas/apple** y **cosas/watermelon-a**, pero puedes usar las que más te gusten).

__Ahora que tenemos varios disfraces queremos que el objeto vaya cambiando de uno a otro.__

# PASO 2: Hacer que la imagen cambie { .activity}

## Progreso { .check}

+ Pulsa en la pestaña `Programas` {.blocklightgrey}.
+ Pulsa en `Eventos`{.blockgrey} y arrastra un `al presionar BANDERA` { .blockyellow} a la zona de programas.
+ Pulsa en Control y añade un bloque `por siempre` { .blockyellow} y ponlo debajo, encajado con el bloque anterior.
+ **Pulsa la bandera verde**. Fíjate que aparece un borde amarillo alrededor del programa. Está ejecutándose porque hemos pulsado la bandera, que esel evento que lo desencadena. 
+ Ahora pulsa `Apariencia`{.blockgrey} y arrastra `siguiente disfraz` { .blockpurple}
+ ¿Cómo hacemos que los disfraces cambien maś despacio? Pulsa en `Control`{.blockgrey} y añade un `esperar 1 segundos` { .blockyellow}
+ Ajusta el tiempo hasta que los disfraces cambien a un ritmo más rápido (prueba con 0.5s, parece una buena velocidad). ¿Qué pasaría si no ponemos el bloque `esperar 1 segundos` { .blockyellow}?

    ```blocks
    Al presionar BANDERA VERDE
    por siempre    	
        siguiente disfraz
        esperar (0.5) segundos
    ```

## Prueba tu proyecto { .flag}
__Pulsa la bandera verde.__ 
¿Cambian los disfraces a buen ritmo?

##Guarda tu proyecto { .save}

##Cosas para probar { .try}

Prueba distintos tiempos en el bloque `esperar 1 segundos` {.blockyellow}. ¿Qué numeros crees que harán el juego muy fácil o muy difícil?

# PASO 3: Hacer que se pare al pulsar {.activity}

## Progreso { .check}

**¡Qué bien! Ahora podemos hacer que el objeto cambie los disfraces todo el rato, pero ¿cómo hacemos que se pare al pulsar?**
Una forma de hacerlo es usar una variable para guardar el estado del Objeto. Además, esto nos será útil después...

+ Crea una nueva variable pulsando en `Datos` {.blockorange} y `Crear una variable`{.blocklightgrey}. Llámala `parado`{.blockorange} y haz que sea sólo para éste objeto. Luego desmarca la casilla que aparece a la izquierda para que no aparezca en el escenario. 
+ Al empezar el juego, el objeto aún no habrá sido pulsado así que pondremos el valor de la variable a **"NO"**. 

    ```blocks
    Al presionar BANDERA VERDE
    fijar [parado v] a (NO)
    por siempre     
        siguiente disfraz
        esperar (0.1) segundos
    ```
+ Ahora vamos a cambiar el valor de la variable `parado`{.blockorange} a **"YSI"** cuando alguien pulse en el objeto.  

    ```blocks
    al clikear este objeto
    fijar [parado v] a (SI)
    ```
+ Por último, tenemos que hacer que el objeto deje de cambiar de disfraz cuando la variable `parado`{.blockorange} cambie a "SI". Añade un `si...entonces`{ .blockyellow} y usa un bloque **es igual a** `[] = []` {.blockgreen} (que encontrarás dentro de la pestaña *Operadores*) para comprobar si `parado`{.blockorange} tiene aún el valor "NO".

    ```blocks
    Al presionar BANDERA VERDE
    fijar [parado v] a (NO)
    por siempre     
        si <(parado) = [NO]> entonces	
            siguiente disfraz
            esperar (0.5) segundos
    ```

## Prueba tu proyecto { .flag}
__Pulsa la bandera verde, espera un poco, y haz click sobre el objeto.__ 

¿Cambia de disfraz antes de que hagas click?

¿Se para cuando pulsas?

__Arranca el programa otra vez.__ ¿Se para cuando pones el puntero del ratón encima, sin hacer click? ¿Se para cuando haces click en cualquier otro sitio en el escenario? 

##Guarda tu proyecto { .save}

# PASO 4: Creando otro objeto {.activity}
__Ahora necesitamos añadir más objeto, ¡para poder jugar!__

## Progreso { .check}

+ **Duplica el objeto** (Fruta) haciendo click con el botón derecho sobre él.
+ Duplicalo otra vez para tener **3** objetos en la pantalla.
+ Mueve cada objeto de manera que queden en línea. Hazlos más pequeños o más grandes si crees que es necesario.

## Prueba tu proyecto { .flag}
__Pulsa la bandera verde.__ Todos los objetos deberían cambiar. ¡Intenta pararlos todos con la misma imagen haciendo click en cada uno!

##Guarda tu proyecto { .save}

# PASO 5: Inicia cada objeto con un disfraz al azar { .activity}
__Vamos a hacer que los objetos cambien a un disfraz aleatorio al pulsar la bandera verde.__

La primera vez que juegas, justo despues de cargar, todos los objetos empiezan con el mismo disfraz y cambian a la vez. 
El juego sería más interesante (y difícil) si cambiaran de una forma menos predecible. 

## Progreso { .check}

+ Si miras en la pestaña `disfraces`{.blocklightgrey} de un objeto verás que cada disfraz tiene un número. Puedes decir qué disfraz quieres que un objeto use mediante ese número o usando el nombre del disfraz. 
+ Para hacer que el objeto se inicie con un disfraz aleatorio, vamos a añadir un bloque `cambiar disfraz a` { .blockpurple} con un `número al azar entre (1) y (3)` { .blockgreen} para elegir el número de disfraz. 
+ Podemos usar exactamente el mismo bloque dentro del bucle `por siempre`{.blockyellow} para que el objeto cambie a un disfraz distinto cada vez durante el juego. 

    ```blocks
    Al presionar BANDERA VERDE
    fijar [parado v] a (NO)
    cambiar disfraz a <número al azar entre (1) y (3)>
    por siempre	
       si <(parado) = [NO]> entonces    
            siguiente disfraz
            esperar (0.5) segundos
    ```
+ Haz lo mismo para los demás objetos. 

## Prueba tu proyecto { .flag}
__Pulsa la bandera verde.__ Todos los objetos deberián cambiar los disfraces en un orden distinto, *al azar*. 

¿Cómo tendrías que cambiar el programa si añadieramos otro disfraz? 
 
##Guarda tu proyecto { .save}

##Cosas para probar { .try}
 
 __Haz el juego más dificil__ 

Cambia la dificultad del juego de alguna manera. Hacer que los disfraces cambien más deprisa es sencillo ¿verdad?. ¿Se te ocurre alguna otra forma? Algunas cosas que puedes probar son:

+ Cambia el número de disfraces que tiene cada objeto. 
+ Haz que algunos objetos tengan disfraces distintos y únicos.
+ Haz que cada objeto cambie de disfraces a una velocidad distinta. 

__¡Disfruta pensando en tus propias mejoras!__

Cada vez que hagas un cambio piensa si hace que el juego sea más fácil o más difícil. Ajusta la dificultad a lo que a ti te parezca razonable. 

## PASO 6: Muestra un mensaje cuando el juego se termine { .activity}
__Vamos a mostrar un mensaje "Game Over" cuando el juego se acabe__

## Progreso { .check}

Lo primero, vamos a crear un fondo distinto para mostrar cuando el juego haya terminado.
+ Pulsa en el escenario, y ve a la pestaña `Fondos`{.blocklightgrey}. Cambia el nombre del fondo que ya tenemos a **"Jugando"**. 
+ Duplica el fondo y añade un texto que diga **"Juego Terminado"**. Puedes cambiar el tamaño del texto pulsando sobre él y arrastrando una de las esquinas. Renombra este fondo a **"JuegoTerminado"**.
+ Haz click en la pestaña `Programas`{.blocklightgrey} del escenario y haz que el fondo "Jugando" sea el que se muestra cuando se inicia el juego. 	
+ ¿Cómo podemos detectar cuando todos los objetos se han parado? ¿Recuerdas que usamos la variable `parado`{.blockorange} para guardar cuando cada objeto había sido pulsado? Vamos a comprobar el valor de la variable `parado`{.blockorange} para el objeto **Fruta3** para ver si el juego se ha terminado. Vamos a usar un bloque `posición x de Fruta3` { .blockblue}, dentro de `Sensores`{.blocklightgrey}, pero cambiando **posición x** to `stopped`{.blockorange}.
	
    ```blocks
    Al presionar BANDERA VERDE
    cambiar fondo a [Jugando v]
    por siempre
        si <([parado v] de [Fruta3 v]) = [SI]> entonces
            cambiar fondo a [JuegoTerminado v]
    ```

## Prueba tu proyecto { .flag}
__Pulsa la bandera verde.__ ¿Aparece el mensaje "Juego Terminado" cuando pulsas en Fruta3? 

¿Qué pasa si paras Fruta3 antes de haber pulsado los otros dos objetos? Vamos a cambiar nuestro programa para que funcione independientemente del orden en el que pulsemos los objetos. 

+ Para comprobar que __los tres__ objetos tienen sus variables `parado`{.blockorange} puestas a **SI**, podemos usar un bloque operador `y` {. blockgreen}. Este bloque es complicado, y puede ser difícil de hacer así que vamos a intentar hacerlo paso a paso. 

    ```blocks
    Al presionar BANDERA VERDE
    cambiar fondo a [Jugando v]
    por siempre
        si <<<([parado v] de [Fruta1 v]) = [SI]> y <([parado v] de [Fruta2 v]) = [SI]>> y <([parado v] de [Fruta3 v]) = [SI]>> entonces
            cambiar fondo a [JuegoTerminado v]
    ```

## Prueba tu proyecto { .flag}
__Pulsa la bandera verde.__ ¿Aparece el mensaje "Juego Terminado" cuando pulsas en las tres frutas, sin importar el orden?

##Guarda tu proyecto { .save}

# PASO 7. Dile al jugador si ha ganado o perdido { .activity}

__La meta del juego es pulsar en los objetos para que se paren cuando son iguales. Estaría bien poder decirle al jugador si ha ganado o perdido.__

## Progreso { .check}

+ En el __paso 6__ escribimos el código para comprobar si el juego ha terminado. Sólo nos queda comprobar si el jugador ha ganado. Vuelve a los fondos y añade un texto al fondo "JuegoTerminado", para que también diga **¡HAS GANADO!"**. Cambia el nombre del fondo a **"JuegoGanado"**.
+ Duplica el fondo anterior para crear uno con el texto **"¡HAS PERDIDO!"**. Llámalo **"JuegoPerdido"**.
+ Ahora necesitamos algo de código para enseñar el fondo adecuado cuando termina el juego. Podemos usar un bloque `si...entonces...si no` { .blockyellow} para comprobar si el jugador ha ganado comparando el `# de disfraz`{.blockpurple} de cada objeto. Vamos a usar para eso un bloque `posición x de objeto`{.blockblue} como hicimos antes. Esta vez, en vez de comprobar la variable `parado`{.blockorange} podemos comprobar `# de disfraz`{.blockpurple} y ver si Fruta1 tiene el mismo disfraz que Fruta2, y si Fruta2 tiene el mismo que Fruta3. 


    ```blocks
    Al presionar BANDERA VERDE
    cambiar fondo a [Jugando v]
    por siempre
        si <<<([parado v] de [Fruta1 v]) = [SI]> y <([parado v] de [Fruta2 v]) = [SI]>> y <([parado v] de [Fruta3 v]) = [SI]>> entonces
            si <<([# de disfraz v] de [Fruta1 v]) = ([# de disfraz v] de [Fruta2 v])> y <([# de disfraz v] de [Fruta2 v]) = ([# de disfraz v] de [Fruta3 v])>> entonces
                cambiar fondo a [JuegoGanado v]
            si no    
                cambiar fondo a [JuegoPerdido v]
    ```
 
## Prueba tu proyecto { .flag}
__Pulsa la bandera verde.__ ¿Aparece el mensaje correcto cuando termina el juego? ¿Qué pasa si los disfraces de todos los objetos no coinciden? (por ejemplo, el número de disfraz 3 de Fruta2 es una manzana y el disfraz 3 de Fruta3 es un melón)? 

##Guarda tu proyecto { .save}
   
__¡Bien hecho! Has terminado el juego básico. Pero hay un montón de cosas que puedes hacer para que el juego sea más difícil. ¿Aceptas el reto?__

##Reto: Hacer que el juego sea más dificil según pasa el tiempo{ .challenge}

Cada persona tendrá un nivel distinto jugando. __¿Cómo podrías hacer que el juego adapte el nivel de dificultad dependiendo del jugador?__

Una forma de conseguirlo es __ajustar la velocidad a la que cambian los disfraces__. Puedes usar una variable, por ejemplo `retraso`{.blockorange}, para configurar la duración del bloque "esperar" de cada objeto. Si el jugador gana, el retraso se reduce (para hacer el juego más difícil). Si el jugador pierde el retraso de incrementa un poco (para hacer el juego más fácil). 

Seguramente tengas que pensar en que el juego empiece de una manera distinta, en vez de usando el `al pulsar BANDERA VERDE`{.blockyellow}. Podrías guardar los valores de las variables entre cada ronda del juego.game. 

##Guarda tu proyecto { .save}

__¡Bien hecho, has acabado! Ahora ¡Disfruta de tu juego!__

No olvides que puedes compartir el juego con tu familia y amigos pulsando el botón __Compartir__ en la barra de herramientas
