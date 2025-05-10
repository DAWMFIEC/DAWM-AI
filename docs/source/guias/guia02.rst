..
   Copyright (c) 2025 Allan Avendaño Sudario
   Licensed under Creative Commons Attribution-ShareAlike 4.0 International License
   SPDX-License-Identifier: CC-BY-SA-4.0

========================================================
Guía 02: HTML - Estructura global y estructura semántica
========================================================

.. topic:: Objetivo específico
    :class: objetivo

    Justificar el uso de etiquetas HTML en la estructura general y de etiquetas semánticas mediante el desarrollo de un currículum vitae digital para la presentación de información profesional de manera organizada y accesible en línea.

Actividades previas
=====================

Diseño
------

1. Decide el contenido de su CV. Puedes considerar la recomendación de diseño para :download:`diseñar el contenido de un CV <./pdfs/guia02-disenocv.pdf>`.
2. Elije la estructura del contenido de su CV, p.e.: el orden de las secciones, título de cada sección, uso de listas numeradas o listas no numeradas de elementos, etc.

Github
------

1. Cree un repositorio en GitHub con el nombre *curriculum*.
2. Clone localmente tu repositorio *curriculum*.
3. Verifique que el correo electrónico de su cuenta de GitHub esté configurado con su proyecto, de acuerdo con la `Documentación de GitHub <https://docs.github.com/es/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-email-preferences/setting-your-commit-email-address#setting-your-email-address-for-a-single-repository>`_. 
   
   a) Para ello, ejecute el siguiente comando en la terminal de VSCode:

      .. code-block:: bash

         git config --global user.email 

   b) Si el correo electrónico no coincide con el de su cuenta de GitHub, ejecute el siguiente comando en la terminal de VSCode:

      .. code-block:: bash

         git config --local user.email "su correo electrónico"
         

Actividades en clases
=====================

Archivos y estructura
----------------------

1. Cree el documento :term:`HTML` *index.html* en el :term:`directorio raíz` de tu proyecto.

Estructura general y semántica
------------------------------

1. Utilice :term:`Copilot` de :term:`VSCode` para generar las :term:`etiquetas` HTML en el documento *index.html*, con:

   a) La :term:`estructura general` que incluya la etiqueta <title> y las etiquetas <meta> (para keywords, description y author). Valide su respuesta con la guía para :download:`crear una página HTML con la estructura general <./pdfs/guia02-estructurageneral.pdf>`.

      .. admonition:: Prompt sugerido

         Genera una estructura HTML básica con las etiquetas <head>, <title>, <meta> y <body>. 
         La etiqueta <head> debe contener la etiqueta <title> con el nombre de mi CV, y las etiquetas <meta> para keywords, description y author.

   b) La :term:`estructura semántica` que contenga 1 etiqueta <header>, 1 etiqueta <main>, 5 etiquetas <section>, 1 etiqueta <nav> y 1 etiqueta <footer>. El documento HTML debe contener un título (<h1>) con su nombre. Cada sección debe contener un subtítulo (<h2>). Valide su respuesta con la guía para :download:`crear una página HTML con la estructura semántica <./pdfs/guia02-estructurasemántica.pdf>`.

2. Redacte el contenido de tu CV con los datos de contacto, estudios, experiencia, habilidades. Valida y mejora la redacción con ayuda de un cliente de :term:`IAG`.

Vista Previa
------------

1. En VSCode, acceda a la opción **Extensión** en la barra lateral izquierda (o presione Ctrl+Shift+X).
2. Busque e instale la extensión `Live Preview` en el Marketplace de VSCode.
3. Habilite la opción `Show Preview` 
   
   a) En `View` > `Command Palette`, busque y seleccione `Live Preview: Show Preview (Internal Browser)`, o
   
   b) Haga clic en el icono de `Show Preview` junto al nombre del documento.

Despliegue con GitHub Pages
---------------------------

1. Versione local y remotamente el repositorio *curriculum*.
2. Despliegue el sitio del repositorio *curriculum* de acuerdo la guía para :download:`publicar la rama main con GitHub Pages <./pdfs/guia02-maingithubpages.pdf>`.
3. Compruebe el resultado en el navegador.

Conclusiones
============

.. topic:: Preguntas de cierre

   * ¿Cómo te ayudó la inteligencia artificial generativa a identificar y comprender las diferencias entre una estructura general HTML válida y una estructura semántica adecuada al momento de diseñar tu currículum vitae?
   * Al utilizar IA para generar tu currículum vitae en HTML, ¿cómo puedes garantizar que el resultado refleje tus habilidades reales como desarrollador web, manteniendo la integridad académica y profesional en el uso de etiquetas semánticas?
  

Actividades autónomas
=====================

Estándar HTML	
------------------------------

* Revisa el :term:`estándar` del `HTML Living Standard <https://html.spec.whatwg.org/multipage/>`_.
* Valida el soporte de las etiquetas HTML en el navegador, con `HTML5 Test <https://html5test.co/>`_ o con `Can I Use <https://caniuse.com/>`_.
* Valida el anidamiento de etiquetas con `Can I Include <https://caninclude.glitch.me/>`_.


Recursos extras
------------------------------

En redes:

.. raw:: html

    <blockquote class="twitter-tweet"><p lang="en" dir="ltr">Semantic HTML elements play a crucial role in improving website SEO and its accessibility.<br><br>Replacing non-semantic elements makes code more readable and maintainable.<br><br>HTML Semantic Elements:<br>→ Carry inherent meanings;<br>→ Make web content more Structured;<br>→ More Meaningful.… <a href="https://t.co/O18NI5L8XD">pic.twitter.com/O18NI5L8XD</a></p>&mdash; Deepanshu Sharma (@deepanshusharmx) <a href="https://twitter.com/deepanshusharmx/status/1708118904391053714?ref_src=twsrc%5Etfw">September 30, 2023</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>