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
