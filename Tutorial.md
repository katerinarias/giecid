# Tutorial: Cómo Agregar Nuevos Elementos al Sitio

Este tutorial explica paso a paso cómo agregar nuevos elementos a las diferentes secciones del sitio.

## Agregar un Nuevo Miembro

Para agregar un nuevo miembro al grupo, sigue estos pasos:

1. Crea un nuevo archivo `.qmd` en la carpeta correspondiente:
   - Para miembros actuales: `members/current/nombre.qmd`
   - Para ex-miembros: `members/former/nombre.qmd`

2. Configura los siguientes campos en el archivo:
   ```yaml
   ---
   title: "Nombre Completo del Miembro"
   subtitle: "Cargo/Título Académico"
   image: "nombre.jpg"
   title-block-banner: false
   format: html
   css: ../../styles.css
   listing:
       contents:
           - "../../publications/*.qmd"
       template: ../../custom-listing.ejs
       fields: [title, autores, categories, venue]
       include:
           autores: "{Nombre del Miembro}"
   ---

   ::: {.profile-image}
   ![Nombre del Miembro](nombre.jpg "Nombre del Miembro")
   :::
   <br>

   **Información de Contacto**:

   - Correo electrónico: correo@ejemplo.com
   - Afiliación: Facultad o Departamento
   - Intereses de Investigación: Lista de intereses

   **Sobre mí**:

   Biografía o descripción del miembro aquí.
   ```

3. Crea versiones en otros idiomas si es necesario:
   - `nombre.en.qmd` para inglés
   - `nombre.fr.qmd` para francés

## Agregar una Nueva Noticia

Para agregar una nueva noticia:

1. Crea un nuevo archivo en la carpeta `news/nombre_noticia.qmd`

2. Configura el archivo con la siguiente estructura:
   ```yaml
   ---
   title: "Título de la Noticia"
   date: "2024-01-31"                # Fecha en formato YYYY-MM-DD
   description: "Breve descripción"   # Resumen corto de la noticia
   ---

   Contenido detallado de la noticia.

   Puedes incluir múltiples párrafos y formateo markdown.
   ```

3. Crea las versiones en otros idiomas si es necesario:
   - `nombre_noticia.en.qmd`
   - `nombre_noticia.fr.qmd`

## Agregar un Nuevo Proyecto

Para agregar un nuevo proyecto:

1. Crea un nuevo archivo en `projects/nombre_proyecto.qmd`

2. Utiliza la siguiente estructura:
   ```yaml
   ---
   name: "Título del Proyecto"
   title: "Título del Proyecto"              # Debe ser igual al name
   funding: "Entidad Financiadora"           # Por ejemplo: "ANID"
   start-year: "2024"                        # Año de inicio
   end-year: "2027"                          # Año de finalización
   members: ["Nombre Miembro 1"]             # Lista de miembros
   role: "Rol en el Proyecto"                # Por ejemplo: "Investigador/a"
   link: "#"                                 # Enlace al proyecto
   ---
   **Miembros del Equipo**: [{{< meta members.1 >}}](../members/current/miembro.qmd)
   **Fuente de Financiamiento**: {{< meta funding >}}  
   **Período de ejecución**: {{< meta start-year >}} - {{< meta end-year >}}   
   **Rol en el Proyecto**: {{< meta role >}}   
   **Link de acceso**: [link]({{< meta link >}})   

   **Descripción General del Proyecto**: 
   Descripción detallada aquí...

   **Objetivos Clave**:
   - Objetivo 1
   - Objetivo 2

   **Progreso Actual**:
   - Estado actual del proyecto
   - Logros alcanzados
   ```

3. Crea las versiones en otros idiomas:
   - `nombre_proyecto.en.qmd`
   - `nombre_proyecto.fr.qmd`

## Agregar una Nueva Publicación

Para agregar una nueva publicación:

1. Crea un nuevo archivo en `publications/nombre_publicacion.qmd`

2. Utiliza esta estructura:
   ```yaml
   # Para artículos en revistas:
   ---
   name: "Título de la Publicación"
   title: "Título de la Publicación"         # Debe ser igual al name
   autores: ["Autor 1", "Autor 2"]          # Lista de autores
   venue: "Nombre de la Revista"             # Revista o lugar de publicación
   categories: ["2024", "Revista", "Tema 1", "Tema 2"]  # Año siempre primero
   preprint: "pdfs/ruta/al/archivo.pdf"     # Ruta al archivo PDF
   ---

   # Para capítulos de libro:
   ---
   name: "Título del Capítulo"
   title: "Título del Capítulo"             # Debe ser igual al name
   autores: ["Autor 1", "Autor 2"]          # Lista de autores
   libro: "Título del Libro"                # Nombre del libro
   capitulo: "2"                            # Número del capítulo
   categories: ["2024", "Libro", "Tema 1", "Tema 2"]  # Año siempre primero
   preprint: "pdfs/ruta/al/archivo.pdf"     # Ruta al archivo PDF
   ---
   ```

   Para el contenido del archivo, usa esta estructura:
   ```markdown
   # Para artículos:
   **Autores**: Autor 1, [Autor 2](../members/current/autor2.qmd), Autor 3  
   **Lugar de publicación**: {{< meta venue >}}   
   **Categorias**: [{{< meta categories.1 >}}](../publications.qmd#category=2024), [{{< meta categories.2 >}}](../publications.qmd#category=Revista), [{{< meta categories.3 >}}](../publications.qmd#category=Tema+1)  
   **Pre-print**: [PDF](../{{< meta preprint >}})  

   # Para capítulos de libro:
   **Autores**: Autor 1, [Autor 2](../members/current/autor2.qmd), Autor 3  
   **Libro**: {{< meta libro >}}   
   **Capítulo**: {{< meta capitulo >}}   
   **Categorias**: [{{< meta categories.1 >}}](../publications.qmd#category=2024), [{{< meta categories.2 >}}](../publications.qmd#category=Libro), [{{< meta categories.3 >}}](../publications.qmd#category=Tema+1)  
   **Pre-print**: [PDF](../{{< meta preprint >}})  
   ```

   **Notas sobre las publicaciones**:
   
   1. **Enlaces a autores**:
      - Solo enlaza los autores que son miembros del grupo
      - El enlace debe ser a su archivo en `members/current/` o `members/former/`
      - El orden de los autores debe mantenerse como en la publicación original
      - Ejemplo: `Autor 1, [Miembro del Grupo](../members/current/miembro.qmd), Autor 3`

   2. **Categorías**:
      - La primera categoría siempre debe ser el año
      - La segunda categoría debe ser "Revista" o "Libro" según corresponda
      - Para categorías con espacios o caracteres especiales, usa '+' en el enlace
      - Ejemplos:
        * "Educación Intercultural" → `../publications.qmd#category=Educación+Intercultural`
        * "Pluralismo Epistemológico" → `../publications.qmd#category=Pluralismo+Epistemológico`

   3. **BibTeX**:
   ```bibtex
   # Para artículos:
   @article{ejemplo,
     title = {{< meta title >}},
     author = {{< meta autores.1 >}} and {{< meta autores.2 >}},
     journal = {{< meta venue >}},
     year = {{< meta categories.1 >}},
   }

   # Para capítulos de libro:
   @inbook{ejemplo,
     title = {{< meta title >}},
     author = {{< meta autores.1 >}} and {{< meta autores.2 >}},
     booktitle = {{< meta libro >}},
     chapter = {{< meta capitulo >}},
     year = {{< meta categories.1 >}},
   }
   ```
   ```

3. Crea las versiones en otros idiomas:
   - `nombre_publicacion.en.qmd`
   - `nombre_publicacion.fr.qmd`

## Notas Importantes

- Mantén la consistencia en los nombres utilizados en los campos `autores` para que las publicaciones se vinculen correctamente con los perfiles de los miembros.
- Las imágenes deben estar en un formato web-compatible (jpg, png) y en una resolución adecuada.
- Asegúrate de crear las versiones en todos los idiomas necesarios para mantener la consistencia del sitio.
- Los archivos `.qmd` deben usar codificación UTF-8 para manejar correctamente los caracteres especiales.
