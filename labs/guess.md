---
layout: work
type: Lab
num: 4
worktitle: Adivina como me llamo
---

## Descripción

En este laboratorio usted practicará el uso del ciclo `while` en Python, implementando el clasico juego "adivina mi nombre".

Asegurese de **leer cuidadosamente!** las instrucciones del laboratorio, las cuales tienen la información necesaria para ayudarle a resolverlo.

## Criterios de evaluación

Para aprobar el laboratorio, cada grupo debera completar dos archivos Python (`.py`):
* `guess_number.py` El cual debe incluir las funciones definidas para los pasos 1, 2 y 3.
* `computer_guess.py` El cual debe incluir las funciones definidas para los puntos 4 y 4.

## Paso 0: Preparatorios

En este laboratorio y en los siguientes, nosotros crearemos programas interactivos que reciben entradas por parte del usuario. [PyCharm](https://www.jetbrains.com/pycharm/) Es un
[IDE](https://en.wikipedia.org/wiki/Integrated_development_environment)
Que nos facilita la elaboración de este tipo de programas en Python.

Abra PyCharm y cree un nuevo proyecto (va primero al boton <kbd>File</kbd> menu
y selecciona <kbd>New Project</kbd>).  Nombre su archivo como `labo_150`.
seleccione las otras opciones en default y dele click sobre <kbd>Create</kbd>.

En este punto usted tendrá un nuevo proyecto vacio. Cada proyecto puede contener multiples archivos en Python. Para crear un nuevo archivo de Python, usted puede seleccionar <kbd>New...</kbd> debajo de la opcion <kbd>File</kbd> menu, O darle click derecho sobre la carpeta del proyecto y seleccionar<kbd>New...</kbd>.  Asegurese de seleccionar <kbd>New Python File</kbd>. Despues de eso usted puede ingresar el nombre del archivo. Tenga en cuenta que no debe incluir la extención `.py` al final del nombre, ya que PyCharm agregará `.py` por usted.

## Paso 1

En la primera parte del proyecto usted implementará una versión basica del juego.
A continuación presentamos una descripción del funcionamiento del programa:

    Bienvenido a "adivina el numero"!
    Yo elegire un número del 1-100 y ustedes tratará de adivinar que número es.
    Cada vez que usted postule un número, yo le dire si es demasiado alto o demasiado bajo, comparado con el número que yo elejí.
    ... OK, Yo ya elegí un número.
    Tu suposición? 50
    50 es muy bajo.
    Tu suposición? 60
    60 es muy alto.
    Tu suposición? 65
    65 es muy alto.
    Tu suposición? 61
    61 es muy alto.
    Tu suposición? 55
    55 es muy alto.
    Tu suposición? 51
    Lo lograste!  Te tomó 6 intentos.

Empieza creando un archivo que se llame `guess_number.py` y **pega el siguiente codigo dentro de el**:

    ######################################
    # Copyright (c) 2024 TU NOMBRE AQUI
    # PENSAMIENTO COMPUTACIONAL, MES 2024
    # Lab 1: Guess My Number
    ######################################

    import random


    def main():
        # Escriba su codigo aquí


    # Call main() como la ultima acción en el archivo
    main()

Actualizalo con tu nombre. **Adentro de la función `main()`**,
Usted debe implementar el juegom descrito arriba.

* Use el metodo `random.randint(1, 100)` para un número al azar entre 1 y 100.
* Por su puesto, usted necesitará un ciclo `while` para repetir las solicitudes de números al usuario hasta que encuentre el número correcto.  Como la variable de control del ciclo, usted puede usar las suposiciones del usuario como variable en si misma o crear una variable bandera que empiece en `False` y se vuelva `True` una vez que la suposición del usuario sea correcta.
* Como se vio en los ejemplos en clase, usted necesitará una variable contador para llevar la cuenta del número de suposiciones hechas por el usuario.

## Paso 2

Su juego esta funcionando ahora, pero hay un problema: 

    Bienvenido a adivina el número!
    Yo elegire un número del 1-100 y ustedes tratará de adivinar que número es.
    Cada vez que usted postule un número, yo le dire si es demasiado alto o demasiado bajo, comparado con el número que yo elejí.
    ... OK, Yo ya elegí un número.
    Tu suposición? cincuenta
    Aparecerá el siguiente error:
    ValueError: invalid literal for int() with base 10: 'fifty'

Si es usuario ingresa un input invalido, el programa colapsará. Nosotros hemos revisado este problema en clase, pero ahora que sabemos como utilizar el ciclo while, podemos abordarlo de una forma diferente.

Usted debe escribir una funcion nueva denominada `input_guess()`. A continuación encontrará un template que sirve como punto de partida; copielo en su archivo despues de `import random` and antes de `def main():`:

    def input_guess() -> int:
        # input_guess seguira solicitando numeros al usuario hasta que el número ingresado sea valido.
        #
        # Input:  numero en forma de String
        # Output: casting que convierte numero en string a entero (int)
    
        # AGREGUE SU CODIGO ACA

        # Solo haremos esta conversión al final, cuando estemos seguros de que el numero en formato String parece un numero entero valido. 

        # Finalmente retorna el número entero postulado

Asegúrate de que los comentarios y el def empiecen desde la columna más a la izquierda de tu archivo (¡**no** lo pongas dentro de tu función `main()`!).

Si la entrada del usuario se almacena como una cadena en la variable `guess_str`, puedes verificar si es válida usando `guess_str.isdigit()`, que es un valor `True` o `False` que te dice si la cadena `guess_str` consiste solo de dígitos o no.

Finalmente, reemplaza la parte de tu función `main()` que pregunta al usuario por su entrada con una llamada a tu nueva función `input_guess()`. Es decir, en lugar de algo como

    suposicion = int(input("Tu suposición? "))

Usted deberia tener ahora: 

    suposicion = input_guess()

Así es como podría verse la salida de tu programa una vez que completes este paso:

    Bienvenido a adivina el número!
    Elegiré un número del 1 al 100, y tú intenta adivinarlo.
    Te diré si cada suposición es demasiado baja o demasiado alta.
    ...OK, he elegido un número.
    Tu suposición? cincuenta
    cincuenta no es un número. Inténtalo de nuevo.
    Tu suposición? iuerhuheg
    iuerhuheg no es un número. Inténtalo de nuevo.
    Tu suposición? 20
    20 es demasiado bajo.

Si quieres, también puedes modificar `input_guess()` para que garantice que la suposición del usuario esté entre 1 y 100, pero esto no es necesario.

## Paso 3

Paso 3

Dado que este juego es tan adictivo, es inconveniente volver a ejecutarlo cada vez que queramos jugar. En este paso, modificarás el juego para que el usuario pueda seguir jugando múltiples rondas hasta que decida detenerse.

Primero, crea una nueva función llamada `run_game()`. No tendrá parámetros ni devolverá ningún valor. Corta y pega la parte de `main()` que comienza con la generación del número aleatorio a adivinar y termina con la impresión del número de suposiciones en esta nueva función. Luego, coloca una llamada a `run_game()` en `main()` donde solía estar ese código. Prueba el programa y asegúrate de que siga funcionando.

A continuación, escribe un nuevo bucle `while` en `main()`. Dentro del bucle, llama a `run_game()` para jugar una ronda del juego. Luego, pregunta al usuario si desea jugar de nuevo. El bucle debe terminar si el usuario no desea jugar de nuevo. Así es como podría verse la salida de tu programa una vez que logres que funcione:


    ¡Bienvenido a adivina el número!
    Elegiré un número del 1 al 100, y tú intenta adivinarlo.
    Te diré si cada suposición es demasiado baja o demasiado alta.
    ...OK, he elegido un número.
    Tu suposición? 50
    50 es demasiado bajo.
    Tu suposición? 70
    70 es demasiado alto.
    Tu suposición? 60
    60 es demasiado alto.
    Tu suposición? 55
    ¡Lo lograste! Te tomó 4 suposiciones.
    ¿Te gustaría jugar de nuevo? (sí/no) sí
    ...OK, he elegido un número.
    Tu suposición? 20
    20 es demasiado bajo.
    Tu suposición? 80
    80 es demasiado alto.
    Tu suposición? 05
    5 es demasiado bajo.
    Tu suposición? 50
    50 es demasiado alto.
    Tu suposición? 30
    30 es demasiado alto.
    Tu suposición? 25
    25 es demasiado alto.
    Tu suposición? 23
    ¡Lo lograste! Te tomó 7 suposiciones.
    ¿Te gustaría jugar de nuevo? (sí/no) no

## Paso 4

Finalmente, crea un nuevo archivo llamado `computer_guess.py`. A partir del
plantilla proporcionada en el paso 1, implementa el mismo juego, ¡pero con los roles invertidos! Es decir, el usuario humano elige un número, y la computadora intenta adivinarlo. Aquí hay un ejemplo de cómo podría verse la salida de tu programa:

    ¡Bienvenido a adivina el número! Tú eliges un número del 1 al 100
    y yo intentaré adivinarlo. Por favor, dime si mis suposiciones son
    "correctas", "bajas" o "altas".
    ¿Es tu número 50? demasiado alto
    Por favor, responde con "correcto", "bajo" o "alto".
    ¿Es tu número 50? erogiherg
    Por favor, responde con "correcto", "bajo" o "alto".
    ¿Es tu número 50? alto
    ¿Es tu número 25? alto
    ¿Es tu número 12? bajo
    ¿Es tu número 18? bajo
    ¿Es tu número 21? alto
    ¿Es tu número 19? bajo
    ¿Es tu número 20? correcto
    ¡Yay! ¡Gané! Solo me tomó 7 suposiciones.
    ¿Quieres jugar de nuevo? (sí/no) sí
    ¿Es tu número 50? bajo
    ¿Es tu número 75? bajo
    ¿Es tu número 88? alto
    ¿Es tu número 81? alto
    ¿Es tu número 78? correcto
    ¡Yay! ¡Gané! Solo me tomó 5 suposiciones.
    ¿Quieres jugar de nuevo? (sí/no) no
    
    
Algunos consejos:
Asegúrate de que tu programa responda adecuadamente si el usuario ingresa algo inesperado, como en el ejemplo anterior.
Tu programa debería ofrecer la opción de jugar de nuevo siempre que el usuario quiera continuar jugando.
Escribe una función `play_once()` que juegue una ronda del juego.
En `main()`, llama a `play_once()` desde dentro de un bucle `while` que pregunte al usuario si desea jugar de nuevo, de la misma manera que hicimos en el Paso 3.
No uses un número aleatorio para generar la suposición de la computadora. La estrategia de la computadora debe ser sistemática y determinista.

## Step 5:

Modifica tu estrategia del Paso 4 para asegurar que la computadora nunca necesite más de 7 suposiciones para ganar.
