..
   Copyright (c) 2025 Allan Avendaño Sudario
   Licensed under Creative Commons Attribution-ShareAlike 4.0 International License
   SPDX-License-Identifier: CC-BY-SA-4.0

========================================================
Guía 04: CSS - Reglas CSS y Modelo de caja
========================================================

.. topic:: Objetivo específico
    :class: objetivo

    Aplicar reglas CSS en la personalización de efectos visuales mediante el desarrollo de un currículum vitae digital para la presentación de información profesional de manera organizada y accesible en línea.

Actividades previas
=====================

Diseño
------

1. Escoge las tipografías con `Google Fonts <https://fonts.google.com/>`_ y combínalas con `Fontjoy <https://fontjoy.com/>`_ de acuerdo a tu gusto para el título de pricipal, para los títulos en las secciones y para todo el documento.
2. Seleciona a tu gusto una combinación de colores de acuerdo con la guía de `Happy Hues <https://www.happyhues.co/>`_, `Huemint <https://huemint.com/website-2/>`_, `Coolors <https://coolors.co/>`_ o `ColorMagic <https://colormagic.app/>`_.

Github
------

1. Clone localmente tu repositorio *curriculum*.

Actividades en clases
=====================

Archivos y estructura
----------------------

1. Cree la carpeta *stylesheets* dentro del directorio de tu proyecto.
2. Cree el documento :term:`CSS` *style.css* dentro de la carpeta *stylesheets* de tu proyecto.
3. Referencie el documento *style.css* en el documento *index.html* dentro de la etiqueta `<head>`. Valide su respuesta con la guía para :download:`referenciar una hoja de estilo externa <./pdfs/guia04-referenciacss.pdf>`.


Reglas CSS - I
--------------

1. Utilice un cliente de IAG para generar las :term:`reglas CSS` en el documento *stylesheets/style.css*, con:

   a) Con el :term:`selector CSS` para todo el documento, aplique la :term:`propiedad CSS` **font-family** con el :term:`valor CSS` **'Segoe UI', Tahoma, Geneva, Verdana, sans-serif**.

   b) Con el selector para el título principal, aplique la propiedad CSS para alinear el texto al centro y en negritas.

.. admonition:: Haga click aquí para ver la solución
    :collapsible: closed
    :class: solution

    .. code-block:: css
        :emphasize-lines: 1-6,8-16

        * {

            /* Familia de fuentes */
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;

        }

        h1 {

            /* Alineación del texto */
            text-align: center;

            /* Grosor de la fuente negrita */ 
            font-weight: bold; 

        }

Despliegue con GitHub Pages
---------------------------

1. Versione local y remotamente el repositorio *curriculum*.
2. Compruebe el resultado en el navegador.

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

    <blockquote class="twitter-tweet"><p lang="en" dir="ltr"><a href="https://twitter.com/deepanshusharmx/status/1708118904391053714">Tweet from @deepanshusharmx</a>
    <img alt="" src="https://pbs.twimg.com/ext_tw_video_thumb/1708115269187710976/pu/img/316z8sA74Czf1nR6.jpg" width="65%" height="auto" class="align-center"><source type="video/mp4" src="blob:https://x.com/e7c71b7e-0d51-4f41-8e56-28a08cc675fa"></p>
    </blockquote>