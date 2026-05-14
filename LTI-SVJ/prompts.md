# Instructions
You are an expert in prompt engineering.
Given the following prompt, prepare it using best-practice structure (role, objective, etc.) and formatting to achieve a precise and comprehensive result. Stick strictly to the requested objective by carefully analyzing what is asked in the original prompt. Make it in mark down so it's easier to copy-paste.

# Original Prompt:
now I need you to create a user story  for me. Find one that is simples and not complex. 
Take into account the following:
Enfocarse en el usuario:

Las user stories deben estar escritas desde la perspectiva del usuario final, no desde la perspectiva interna de la organización.

Utilizar personajes o "personas" para entender mejor las necesidades y objetivos de los usuarios.

Mantener un formato simple y conciso:

Seguir el formato estándar: "Como [tipo de usuario], quiero [realizar una acción] para [obtener un beneficio]".

Evitar detalles técnicos o instrucciones de implementación.

Mantener las historias lo suficientemente pequeñas y entregables en un sprint.

Priorizar y estimar:

Priorizar las historias de usuario en función de su valor para el negocio y el usuario.

Estimar el esfuerzo requerido para implementar cada historia.

Fomentar la colaboración:

Escribir las historias de usuario de manera colaborativa con el equipo de desarrollo.

Usar las historias de usuario como punto de partida para conversaciones más profundas.

Incluir criterios de aceptación:

Definir claramente los criterios que deben cumplirse para considerar una historia "terminada".

Evitar centrarse en cómo se construirá la funcionalidad.

Mantener las historias actualizadas:

Estar preparado para evolucionar y refinar las historias a medida que el proyecto avanza.

Utilizar técnicas como el User Story Mapping para organizar y priorizar las historias.

Also take into account the framsework INVEST

This is an example of a user story
Título: Búsqueda inteligente de cursos con sugerencias
Historia de Usuario:

1. Como estudiante de la plataforma de e-learning,
2. quiero buscar cursos por palabra clave y recibir sugerencias relevantes mientras escribo,
3. para que pueda encontrar rápidamente el curso que necesito sin navegar por todo el catálogo.
Criterios de Aceptación (formato BDD):

1. Dado que estoy en la página principal, cuando escribo al menos 3 caracteres en el buscador, entonces aparecen sugerencias de cursos en tiempo real (máximo 500ms).
2. Dado que veo los resultados de búsqueda, cuando hago clic en un curso, entonces navego a la página de detalle del curso.
3. Dado que busco un término que no coincide con ningún curso, cuando se muestran los resultados, entonces veo un mensaje de "Sin resultados" con cursos sugeridos por categoría.
Notas Adicionales:

* El buscador debe soportar búsqueda por título, descripción e instructor.
* Considerar integración con algún servicio de búsqueda como Algolia o ElasticSearch.
* Accesibilidad: el componente debe ser navegable con teclado.



==================================================================
==================================================================


# Instructions
You are an expert in prompt engineering.
Given the following prompt, prepare it using best-practice structure (role, objective, etc.) and formatting to achieve a precise and comprehensive result. Stick strictly to the requested objective by carefully analyzing what is asked in the original prompt. Make it in md so it's easier to copy-paste.

# Original Prompt:
Now consider all the following to create all the tickets/tasks necessary for the first user story
1. Título Claro y Conciso
Un resumen breve que refleje la esencia de la tarea. Debe ser lo suficientemente descriptivo para que cualquier miembro del equipo entienda rápidamente de qué se trata el ticket.
2. Descripción Detallada

* Propósito: Explicación de por qué es necesaria la tarea y qué problema resuelve.
* Detalles Específicos: Información adicional sobre requerimientos específicos, restricciones, o condiciones necesarias para la realización de la tarea.
3. Criterios de Aceptación

* Expectativas Claras: Lista detallada de condiciones que deben cumplirse para que el trabajo en el ticket se considere completado.
* Pruebas de Validación: Pasos o pruebas específicas que se deben realizar para verificar que la tarea se ha completado correctamente.
4. Prioridad

* Nivel de Urgencia: Una clasificación de la importancia y la urgencia de la tarea, lo cual ayuda a determinar el orden en que deben ser abordadas las tareas dentro del backlog.
5. Estimación de Esfuerzo

* Puntos de Historia o Tiempo Estimado: Una evaluación del tiempo o esfuerzo que se espera que tome completar el ticket. Esto es esencial para la planificación y gestión del tiempo del equipo.
6. Asignación

* Responsable: Quién o qué equipo será responsable de completar la tarea. Esto asegura que todos los involucrados entiendan quién está a cargo de cada parte del proyecto.
7. Etiquetas o Tags

* Categorización: Etiquetas que ayudan a clasificar el ticket por tipo (bug, mejora, tarea, etc.), por características del producto (UI, backend, etc.), o por sprint/versión.
8. Comentarios y Notas

* Colaboración: Espacio para que los miembros del equipo agreguen información relevante, hagan preguntas, o proporcionen actualizaciones sobre el progreso de la tarea.
9. Enlaces o Referencias

* Documentación Relacionada: Enlaces a documentos, diseños, especificaciones o tickets relacionados que proporcionen contexto adicional o información necesaria para la ejecución de la tarea.
10. Historial de Cambios

* Rastreo de Modificaciones: Un registro de todos los cambios realizados en el ticket, incluyendo actualizaciones de estado, reasignaciones y modificaciones en los detalles o prioridades.




==================================================================
==================================================================

# INTENTO 1 GENERAR BACKLOG - copilot - github projects


## PROMPT:

# Instructions
You are an expert in prompt engineering.
Given the following prompt, prepare it using best-practice structure (role, objective, etc.) and formatting to achieve a precise and comprehensive result. Stick strictly to the requested objective by carefully analyzing what is asked in the original prompt. Make it in md so it's easier to copy-paste.

# Original Prompt:
Take all the info in the file named LTI-SVJ.md in this repository do the following:
Create a github project calles ATS
Create the User stories in the file.
Create all the tasks in the file and make sure they properly linked to their user story.
Do whatever you think it0s best to create a great backlog based on kanban metodology.

## CONCLUSIONES:
No funció por temas de que Tenia las issues disabled y de todas formas, una vez enabled  se quedó sin token y no hizo ningun delivery al final. 










# INTENTO 2 GENERAR BACKLOG - OpenCode - Linear

## PROMPT:

# Instructions
You are an expert in prompt engineering.
Given the following prompt, prepare it using best-practice structure (role, objective, etc.) and formatting to achieve a precise and comprehensive result. Stick strictly to the requested objective by carefully analyzing what is asked in the original prompt. Make it in md so it's easier to copy-paste.

# Original Prompt:
I want you to create a backlog in Linear (you can use the MCP already configured) with the proper user stories and tasks  based on the following  markdown. Ask me anything you need to do it properly. Create a new project called ATS and create them there. 
[markdown]


(The [markdown] was the LTI-SVJ.md)

## CONCLUSIONES:
Funciono perfecto. Me hizo algunas preguntas antes de implementar y luego creo todo tal cual en linear ya que tenia el MCP conectado Y fue bastante rapido. 

