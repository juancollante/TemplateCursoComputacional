---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

# For courses with a single offering in the _config.yml,
# uncomment the following line and comment out the course-multi line

#layout: course-single
layout: course-multi
---
<br/>

# <a name="description">Descripción</a>

{{ site.description }}

## <a name="goals">Metas de aprendizaje</a>

Al completar este curso, nuestra meta es que usted sea capaz de:

* Construir programas computacionales para:
  * Resolver efectivamente problemas realistas.
  * Organizar, analisar y resumir conjuntos de datos reales.
* Leer, comprender y explicar programas computacionales.
* Comprender y explicar la logica computacional a traves de:
  * Pensamiento logico y correcto.
  * Postulado y testeo de hipotesis.
* Usa componentes modulares para descomponer problemas y ensamblar soluciones.
* Crear modelos abstractos y generalizables, a partir de ejemplos especificos y complejos.

## <a name="resources">Recursos</a>

{% include resources.html content=site.resources %}

## <a name="additional-resources">Optional Resources</a>

{% include resources.html content=site.extra-resources %}

## Laptop Policy

Por favor **No traiga su Laptop a las clases**. Esto puede parecer extraño en una clase de ciencias computacionales. Pero los laboratorios serán los espacios donde usted obtendrá mucha experiencia trabajando con computadores; Las clases son un tiempo para pensar y aprender sin las distracciones de un computador.

Pueden hacerse excepciones individuales en base a si usted me puede demostrar que su aprendizaje realmente se beneficia de manejar su laptop en clase.

<hr>

# <a name="inclasscode">Codigo Desarrollado en Clase</a>

Cuando nosotros escribimos codigo en clase, se publicará aqui!

| Fecha | Tema | Codigo |
| F 30 Aug | Introducción a Python | [Intro Notebook](https://pythonintro-yorgey.notebooks.azure.com/j/notebooks/PythonIntro.ipynb) |
| W 4 Sep | Matematica y Funciones | [Box Math](https://boxmath-yorgey.notebooks.azure.com/j/notebooks/BoxMath.ipynb) |
| F 6 Sep | Cadena y Booleano | [Booleans](https://booleans-yorgey.notebooks.azure.com/j/notebooks/Strings%20and%20Booleans.ipynb)

<hr>
# Coursework

Cada estudiante tiene **cuatro días de plazo adicional** para gastar a lo largo del semestre como deseé.
Simplemente deben informar al instructor en cualquier momento antes de la fecha limite de entrega para el trabajo que requiera postergar. Una vez solicitado el plazo adicional, usted puede entregar el trabajo hasta 24 horas despues de la fecha limite. No se admite el uso parcial de un día de plazo, si usted entrega 2 o 20 horas tarde un trabajo, se le descontará el día de plazo completo.Tenga en cuenta que los días de plazo estan hechos para cubrir circunstancias normales (quiere mas tiempo para terminar) o anormales (esta enfermo, tiene un problema familiar, etc). Despues de haber agotado todos los días de plazo, los trabajos que se entreguen tarde tendran un nota no superior a la mitad de los creditos.

## <a name="hwqz">Tareas y Quices</a>: 
| #  | Nombre | Inicio | Fin |
|0 | [Boolean](homework\booleans.md) | V Sep 27 | W Oct 2 |
|1 | [Tarea de muestra]({{site.baseurl}}/homework/function-reading.pdf) | V Sep 27 | W Oct 2 |
|2 | [Tarea de muestra]({{site.baseurl}}/homework/function-reading.pdf) | V Sep 27 | W Oct 2 |

Se asignaran tareas cortas para ser completadas cada fin de semana, iniciando el viernes y finalizando el lunes, muchas veces con un quiz al inicio de las clases de los lunes. 

## <a name="labs">Laboratorios</a>: 

| #  | Nombre | Inicio | Fin |
|1 | [Ciclo While](labs\guess.md) | Ago 28-29 | Sep 4-5 |
|2 | [Laboratorio de muestra]({{site.baseurl}}/labs/sample-lab.html) | Sep 4-5 | Sep 11-12 |
|3 | [Laboratorio de muestra]({{site.baseurl}}/labs/sample-lab.html) | Sep 11-12 | Sep 18-19 |

La mayor parte de la experiencia en programación de este curso se obtendrá a traves de laboratorios semanales. Cada laboratorio será ubicado en la carpeta de laboratorios de este curso y tednran el tiempo suficiente para trabajar a en él con los materiales entregados. El tiempo de final de entrega para cada laboratorio será hasta  **el inicio del siguiente laboratorio**. Todos los laboratorios tendrán el mismo porcentaje de la nota final de laboratorios. 

En estos laboratorios, usted trabajara con un compañero. Los codigos enviados deben tener el nombre de los dos compañeros que hacen parte del grupo. Cada pareja enviará una **unica copia** de la tarea. 

**La asistencia a los laboratorios es obligatoria**. Los labora torios se desarrollarán los viernes **en el aula virtual**.

## <a name="projects">Proyectos</a>:

| #  | Nombre | Inicio | Fin |
|:--:|-----||:------:|:--------:|:---:|
|1 | [Proyecto 1](projects/project2.md)  | 50  | Sep 21 | Sep 30 |
|2 | [Proyecto de muestra]({{site.baseurl}}/projects/sample-project.html) | Oct 16 | Nov 1 |
|3 | [Proyecto de muestra]({{site.baseurl}}/projects/sample-project.html) | Nov 18 | Proyecto Final |

You will have three projects in this course, one about every five weeks. These projects will cover concepts we have discussed in class and in labs, and will be due approximately one week after they are assigned.

**Debes trabajar individualmente en los dos primeros proyectos**. Puedes discutir conceptos e ideas con tus compañeros de clase, pero el código que entregues debe ser tuyo. Serás evaluado no solo por la corrección, sino también por la técnica, la documentación y la evaluación de tu solución. Se proporcionarán más detalles sobre los estándares de calificación y las instrucciones de entrega para cada proyecto cuando sean asignados.

## <a name="exams">Examenes</a>: 

Habrá tres exámenes en clase, el primero valdrá 50 puntos y el segundo y tercero valdrán 100 puntos de tu nota final. Consistirán en preguntas de respuesta corta, así como en la redacción y depuración de código.

* Exam 1: Sep 20, Funciones, matematicas, tipos de datos numericos, condicionales y codigo binario
* Exam 2: Oct 16, input/output, ciclo while, listsa, tipos de datos String
* Exam 3: Nov 25, ciclo for, diccionarios, clases y objetos

No hay examen final; en su lugar, completarás un proyecto final, como se describe arriba en Proyectos.
