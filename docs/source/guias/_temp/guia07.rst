..
   Copyright (c) 2025 Allan Avendaño Sudario
   Licensed under Creative Commons Attribution-ShareAlike 4.0 International License
   SPDX-License-Identifier: CC-BY-SA-4.0

====================================
Guía 07: Responsividad y Componentes 
====================================

.. topic:: Objetivo específico
    :class: objetivo

    Aplicar principios de diseño responsivo y reutilización de componentes utilizando TailwindCSS para estructurar una landing page de una sola página (SPA) que se adapte correctamente a diferentes dispositivos y mantenga coherencia visual y funcional en toda la interfaz.
    

Actividades previas
=====================

Diseño
------

1. Organice el contenido de su landing page en secciones, p.e.: encabezado, presentación, servicios, testimonios, contacto, etc.
2. Diseñe cada una de las secciones de la landing page. Primero, considere la versión para la resolución de un dispositivo móvil (640px). Luego para la resolución de una computadora (1280px), p.e.: 

Ambiente de desarrollo
----------------------

1. Acceda a su proyecto *landing* en Codespaces o en su máquina local.
2. Cree y utilice la(s) rama(s) de desarrollo.

Actividades en clases
=====================

TailwindCSS
-----------

Viewport
^^^^^^^^

1. Identifique si el *index.html* contiene la etiqueta `<meta>`:

    .. code-block:: html
        :linenos:
        :emphasize-lines: 3

        <head>
            ...
            <meta name="viewport" content="width=device-width, initial-scale=1.0" />
            ...
        </head>

2. Utilice un cliente de IAG para justificar la importancia de la etiqueta `<meta>`.

Diseño Responsivo
^^^^^^^^^^^^^^^^^

1. `Simula dispositivos móviles con el modo de dispositivo <https://developer.chrome.com/docs/devtools/device-mode?hl=es-419>`_ de la landing page.

2. Utilice la documentación de `TailwindCSS - Responsive Design <https://tailwindcss.com/docs/responsive-design>`_ y el inspector del navegador para cada uno de los siguientes cambios:

   a) 
   b) 'max-w-screen md:max-w-screen-lg'

3. Compruebe el resultado en el navegador. 

Flowbite
--------

Componentes
^^^^^^^^^^^

Versionamiento
--------------

1. Versione local y remotamente la(s) rama(s) de desarrollo en el repositorio *landing*.
2. Genere la(s) solicitud(es) de cambios (pull request) para la rama principal y apruebe los cambios.

Vercel
------

1. Revise   

Conclusiones
============

.. topic:: Preguntas de cierre

    ¿Qué?

Actividades autónomas
=====================

Recursos extras
------------------------------

En redes:

.. raw:: html

    Diseño responsivo

    <blockquote class="twitter-tweet"><p lang="en" dir="ltr">Happy 11th Birthday Responsive Web Design! On May 25, 2010, web designer Ethan Marcotte published an article entitled &quot;Responsive Web Design&quot; in the online magazine A List Apart. <a href="https://t.co/vjK4affT5b">https://t.co/vjK4affT5b</a><a href="https://twitter.com/hashtag/WebDesignHistory?src=hash&amp;ref_src=twsrc%5Etfw">#WebDesignHistory</a> <a href="https://t.co/2Crd5GZ4qC">pic.twitter.com/2Crd5GZ4qC</a></p>&mdash; Web Design Museum (@WebDesignMuseum) <a href="https://twitter.com/WebDesignMuseum/status/1397228466693681163?ref_src=twsrc%5Etfw">May 25, 2021</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>