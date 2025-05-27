..
   Copyright (c) 2025 Allan Avendaño Sudario
   Licensed under Creative Commons Attribution-ShareAlike 4.0 International License
   SPDX-License-Identifier: CC-BY-SA-4.0

===========================
Guía 06: TailwindCSS y Vite 
===========================

.. topic:: Objetivo específico
    :class: objetivo

    Evaluar el uso de clases utilitarias de TailwindCSS en la creación de una landing page funcional y atractiva considerando su adecuación a los requerimientos específicos del diseño.

Actividades previas
=====================

Diseño
------

1. Defina el objetivo de su :term:`landing page`, p.e.: venta de productos de belleza, información de un grupo estudiantil, datos de una veterinaria, noticias de KPOP, etc.
2. Identifique una plantilla de diseño que se ajuste al objetivo de su landing page. Puede buscar plantillas gratuitas en sitios como `Theme Wagon - Frameworks Tailwind CSS <https://themewagon.com/theme-framework/tailwind-css/?swoof=1&pa_price=free&paged=1&product_cat=landing-website,landing-website&really_curr_tax=400-pa_frameworks>`_ o puede generar una plantilla con `Stitch <https://stitch.withgoogle.com/>`_.

Ambiente de desarrollo
----------------------

1. Cree un repositorio en GitHub con el nombre *landing*.

   a) Agregue un archivo README.md con el título de su landing page y una breve descripción del objetivo de su proyecto.
   b) Agregue un archivo .gitignore con la plantilla de `Node`.
   
2. Acceda a su proyecto *landing* en Codespaces o en su máquina local.

Actividades en clases
=====================

Vite
----

.. sidebar:: 
   
   :term:`Vite` es un entorno de desarrollo rápido y moderno que permite crear aplicaciones web con facilidad mediante con recarga en caliente, optimización de recursos y soporte para módulos ES. Más información en el sitio de `Vite <https://vite.dev/>`_.

1. Utilice la terminal para crear un proyecto Vite con el comando:

   .. code-block:: bash

      npm create vite@latest .

   a) Para `Ok to proceed? (y)` ingrese `y`.
   b) Para `Current directory is not empty. Please choose how to proceed:` seleccione la opción `Ignore files and continue`.
   c) Seleccione el framework como `Vanilla`.
   d) Seleccione la variante como `JavaScript`.

2. Instale las dependencias del proyecto con el comando:

   .. code-block:: bash

      npm install

3. Inicie el servidor de desarrollo con el comando:

   .. code-block:: bash

      npm run dev

4. Abra su navegador y acceda a la dirección `http://localhost:5173/` para ver su proyecto Vite en funcionamiento.
5. Detenga el servidor de desarrollo con `Ctrl + C` en la terminal.
6. Limpie la terminal con el comando:

   .. code-block:: bash

      clear

TailwindCSS
-----------

.. sidebar::
   
   :term:`TailwindCSS` es un framework de CSS que utiliza un enfoque de clases utilitarias para aplicar estilos a los elementos HTML. Más información en el sitio de `TailwindCSS <https://tailwindcss.com/>`_.

Clases utilitarias
^^^^^^^^^^^^^^^^^^

Vercel
------

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