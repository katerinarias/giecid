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
