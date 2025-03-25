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

