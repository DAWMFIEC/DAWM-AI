..
   Copyright (c) 2025 Allan Avendaño Sudario
   Licensed under Creative Commons Attribution-ShareAlike 4.0 International License
   SPDX-License-Identifier: CC-BY-SA-4.0

===============================
Guía 06: TailwindCSS + Flowbite
===============================

.. topic:: Objetivo específico
    :class: objetivo

    Evaluar el uso de clases utilitarias de TailwindCSS y Flowbite en la creación de una landing page funcional y atractiva considerando su adecuación a los requerimientos específicos del diseño.

Actividades previas
=====================

Diseño
------

1. Defina el objetivo de su :term:`landing page`, p.e.: venta de productos de belleza, información de un grupo estudiantil, datos de una veterinaria, noticias de KPOP, etc.
2. Organice el contenido de su landing page en secciones, p.e.: encabezado, presentación, servicios, testimonios, contacto, etc.

Ambiente de desarrollo
----------------------

1. Cree un repositorio en GitHub con el nombre *landing*.

   a) Agregue un archivo README.md con el título de su landing page y una breve descripción del objetivo de su proyecto.
   b) Agregue un archivo :term:`.gitignore` con la plantilla de :term:`Node`.
   
2. Acceda a su proyecto *landing* en Codespaces o en su máquina local.

Actividades en clases
=====================

Vite
----

.. include:: ../../tutoriales/vite.rst

TailwindCSS
-----------

.. sidebar::
   
   Revise la documentación en `TailwindCSS <https://tailwindcss.com/>`_.

:term:`TailwindCSS` es un framework de CSS que utiliza un enfoque de clases utilitarias para aplicar estilos a los elementos HTML. 

Play CDN
^^^^^^^^

1. Agregue la etiqueta de script Play CDN al `<head>` de su archivo HTML.

   .. code-block:: html
       :caption: Agregue la etiqueta script con la referencia al archivo js en el Play CDN
       :linenos:
       :emphasize-lines: 7

       <!doctype html>
       <html>
         <head>
            
            ...

            <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
         
         </head>
         <body> ... </body>
       </html>

Sección Principal (Hero Section)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. Utilice un cliente de IAG para generar el contenido de su sección principal o :term:`hero section` de su landing page, p.e.: título, subtítulo, párrafo introductorio, botón de llamada a la acción, etc.

   .. admonition:: Prompt sugerido

        Genera el contenido de una sección principal para una landing page de [tema] que incluya un título atractivo, un subtítulo descriptivo, un párrafo introductorio y un botón de llamada a la acción. El título debe ser breve y llamativo, el subtítulo debe complementar el título y el párrafo debe explicar brevemente el propósito de la landing page. El botón debe tener un texto claro que invite al usuario a realizar una acción específica.

2. Agregue el contenido generado a su archivo HTML dentro de la etiqueta `<main>`.

Barra de navegación
^^^^^^^^^^^^^^^^^^^

Flowbite
--------

CDN
^^^

Vercel
------

.. include:: ../../tutoriales/vercel.rst

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

    Tailwind CSS

    <blockquote class="twitter-tweet"><p lang="en" dir="ltr">✨ Tailwind CSS v4.0 is here!<br><br>Huge performance improvements, radically simplified setup experience, CSS-first configuration, modernized P3 color palette, container queries, 3D transforms, expanded gradient APIs, @​starting-style support…<br><br>…and tons, tons more. <a href="https://t.co/zBSfm6IOf7">pic.twitter.com/zBSfm6IOf7</a></p>&mdash; Adam Wathan (@adamwathan) <a href="https://twitter.com/adamwathan/status/1882219476600635677?ref_src=twsrc%5Etfw">January 23, 2025</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

    Stitch - Google

    <blockquote class="twitter-tweet"><p lang="en" dir="ltr">Meet Stitch by <a href="https://twitter.com/GoogleLabs?ref_src=twsrc%5Etfw">@GoogleLabs</a>, the easiest and fastest product to generate great designs and UIs. 🧵<a href="https://t.co/xYj6Gyi5NS">https://t.co/xYj6Gyi5NS</a> <a href="https://t.co/zdmtl3okH5">pic.twitter.com/zdmtl3okH5</a></p>&mdash; Stitch by Google (@stitchbygoogle) <a href="https://twitter.com/stitchbygoogle/status/1924947794034622614?ref_src=twsrc%5Etfw">May 20, 2025</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>