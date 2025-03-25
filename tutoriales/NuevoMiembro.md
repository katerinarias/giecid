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
