# Página Académica de Cursos de CSCI con Jekyll

Este es el template genérico para crear una página de curso de Ciencias de la Computación. Utilicé [Jekyll](https://jekyllrb.com/) y [GitHub Pages](https://pages.github.com/) para la implementación en la web.

## Implementación

Hay solo unos pocos pasos para crear un nuevo sitio web de curso desde este repositorio.

* Determina el subdirectorio que usarás para este curso. 

* Usa este repositorio como el [template](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template) para hacer tu nuevo repositorio, nombrado exactamente con el nombre de subdirectorio que hayas elegido. Tu repositorio puede ser público o privado.

* Edita el archivo `_config.yml` en la línea 27, cambiando `baseurl` para que sea tu subdirectorio elegido, por ejemplo, `/csci150`.

* [Configura el repositorio](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site) para que aparezca como un sitio web de GitHub Pages. 

¡Hurra! Tu sitio web del curso debería ser visible en `https://<username>.github.io/<subdir>`.

## Contenido

Una vez que tu repositorio de curso esté creado y visible en la web, es hora de actualizar el contenido.

### Imagen de Fondo

La forma más fácil de configurar la imagen de jumbotron es copiar una nueva imagen en el `assets/images` directorio, y nombrarla `jumbo-background.jpg`. Imágenes más grandes son mejores y serán menos pixeladas en pantallas grandes.

Para un tipo diferente de imagen o para tenerla con otro nombre, deberás cambiar el nombre del archivo en las definiciones de clase `.jumbotron` en el `assets/css/main.css` archivo para que el atributo src muestre tu archivo.

### Descripción, Número del Curso, Título, y Semestre

El `_config.yml` archivo contiene varios elementos que se pueden editar para personalizar el curso para tu contenido.

Primero, reemplaza la `description` actual con la copia del catálogo de tu descripción de curso. *Asegúrate de que esté indentada para seguir el formato YAML.*

Luego, cambia el `number` del curso para que sea una versión legible por humanos de la numeración del catálogo del curso, por ejemplo, `CSCI 150`, y el `semester` para que sea un indicador legible por humanos del semestre, por ejemplo, `Otoño 2019`. Estos aparecerán en la página web en la parte superior izquierda de la barra de navegación.

Finalmente, el `title` para el curso debería editarse para que coincida con el nombre del catálogo, por ejemplo, `Fundamentos de Ciencias de la Computación`.

### Barra de Navegación

La `navigation` denota los enlaces en la parte superior derecha del encabezado en cada página. Enlaces simples tienen un `page` y `url` campo, mientras que el agrupamiento de enlaces se denota con un `title` campo y un `subfolderitems` lista de enlaces simples.

### Instructores y Ofertas

La próxima sección de `_config.yml` define los `instructors` para el curso. Un instructor tiene un `id`,`name`,`email` dirección, `web` enlace ,`phone` número, y `officehours` enlace. Esta información se muestra ya sea en o cerca del jumbotron en el encabezado de la página principal.

Ahora, se crean `offerings`, a los que se les da un `name`, y lista la sala `loc`, el `time` de la oferta, y el `instructor` para esa oferta usando su `id` de arriba.

Si solo hay una oferta, recomendamos actualizar el `index.md` documento para usar el `course-single.md` diseño en lugar de `course-multi.md`. Se ve mejor.

### Recursos

Recursos proporcionados a los estudiantes, como enlaces a software o libros de texto, se enumeran a continuación en la lista de `resources`. Cada recurso tiene un `name`, una `image` utilizada para una referencia visual fácil, y una
`url` para enlazar al recurso. Estos se pueden mostrar en una fila, con un máximo de cuatro por fila, usando
la plantilla que se encuentra en `_includes\resources.html`.

Recursos adicionales en diferentes categorías se pueden crear siguiendo la misma estructura, como se muestra con la sección `extra-resources` que se muestra en la página `index.md` con el encabezado de Recursos Opcionales.

### Laboratorios, Tareas, y Proyectos

Las asignaciones de los estudiantes, como laboratorios, tareas, y proyectos deben usar el `work.html` diseño. Es útil organizar los laboratorios, tareas, y proyectos en sus propios directorios.

Los archivos `sample-lab.md` y `sample-project.md` son buenos ejemplos de cómo usar markdown para escribir una asignación. El frontmatter al principio de la página es procesado por el diseño para mostrar el título y número en la parte superior de la página web.

    ---
    layout: work
    type: Lab
    num: 4
    worktitle: Adivina Mi Número
    ---

Esto se puede editar para tu asignación específica, y aumentado para incluir cualquier información que desees como variables líquidas dentro de tu asignación, como las fechas de vencimiento en la página de proyecto de muestra.

Hemos incluido cuatro [alert](https://getbootstrap.com/docs/4.0/components/alerts/) contexts para ayudar a resaltar las partes clave de las asignaciones. Pueden ser para secciones `warning`, `tip`, `note`, o `important`, y su fuente se encuentra en la carpeta `_includes`, e incluyen usando la siguiente sintaxis

    {% include important.html content="Asegúrate de que tus ubicaciones estén elegidas para que la cara siempre sea completamente visible en la pantalla." %}

Para hacer que cualquier imagen de tu página sea [responsive](https://getbootstrap.com/docs/5.0/content/images/) para diferentes tamaños de navegador, puedes agregar `{: .img-fluid }` después del enlace de la imagen.

### Colores

Usamos Naranja `#f5822a` como el tema de color principal en el encabezado, pie de página, y enlaces. Esto se define, junto con algunos otros colores, como una variable en la parte superior del archivo `assets/css/main.css`.

### Fuentes

Usamos la fuente [Merriweather Sans](https://fonts.google.com/specimen/Merriweather+Sans) en páginas web. Otras fuentes pueden ser [cambiadas](https://stackoverflow.com/questions/14676613/how-to-import-google-web-font-in-css-file) por tu estilo institucional particular cambiando las líneas `@import` y `font-family`.
