==========
django-faq
==========

Simple app to create FAQ from flatpages. Documentation in spanish, sorry to non-english speakers =/


Características
===============

* Las preguntas se agrupan por tópicos.
* Las respuestas para cada pregunta se procesan con textile.
* La respuesta también puede ser una página estática existente.
* Si la respuesta se definió para la pregunta, es decir, no es una página estática, se crea un link dentro de la misma página (conocido como anchor o ancla.) En el caso que la respuesta sea una página estática se puede definir que sea un link del mismo tipo o a la propia página estática.
* Se incluye en el código con un simple template tag.


Instalación
===========

* Descargar la última versión del SVN.
* Exportar el código a nuestro proyecto. Por ej, con el nombre “faq”.
* Agregamos la app a la lista de INSTALLED_APPS del archivo settings.py.
* Ejecutamos el comando syncdb.


Forma de uso
============

* Crear los tópicos que se consideren pertinentes.
* Crear las preguntas y asignarle un tópico a cada una.
* Asignarle una respuesta a la pregunta.
    * Se puede crear la respuesta para la pregunta o asignar una de las ya creadas.
    * Se puede también elegir una página estática como respuesta.
* Si la respuesta es una página se puede definir si se linkea a ella o si se procesa y se muestra en la misma página.
* En el template lo cargamos mediante {% load render_faq %} lo que pone a disposición los siguientes tags:
    * {% render_questions %} el cual despliega todas las preguntas, agrupadas por tópico.
    * {% render_answers %} despliega las respuestas, también agrupadas por tema.
    * {% render_subject tópico_1 topico_2 topico_n %} despliega las preguntas y respuestas correspondientes a dichos temas.
