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

1. Utilice un cliente de IAG para generar las :term:`reglas CSS` en el documento *stylesheets/style.css*:

   a) Con el :term:`selector CSS` para todo el documento, aplique la :term:`propiedad CSS` **font-family** con el :term:`valor CSS` **'Segoe UI', Tahoma, Geneva, Verdana, sans-serif**.

      .. admonition:: Prompt sugerido

            Agrega el selector CSS para todo el documento que aplique la propiedad CSS font-family con el valor CSS “Segoe UI”, Tahoma, Geneva, Verdana, sans-serif.
    
   b) Con el selector para el título principal, aplique la propiedad CSS para alinear el texto al centro y en negritas.

.. admonition:: Haga click aquí para ver la solución
    :collapsible: closed
    :class: solution

    .. code-block:: text
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

1. Compruebe la vista previa del resultado en el navegador.

Reglas CSS - II
---------------

1. Modifique el archivo *index.html*:

   a) A la etiqueta `<img>`, agregue el atributo **id** con el valor **photo**.
   b) A las etiquetas `<h2>`, agregue el atributo **class** con el valor **subtitle**.

2. Utilice un cliente de IAG para generar las reglas CSS en el documento *stylesheets/style.css*:

   a) Con el selector por id con el valor **photo** cuyo ancho es `25vw` y el alto es `automático`.
   b) Con el selector por clase con el valor **subtitle** cuyo color del texto es `rgb(151 156 165 / 0.89);` y el texto en mayúsculas.


.. admonition:: Haga click aquí para ver la solución
    :collapsible: closed
    :class: solution

    .. code-block:: text
        :emphasize-lines: 5-12,14-21

        * { ... } 

        h1 { ... }

        #photo {

            /* Ancho del elemento */
            width: 25vw; 

            /* Alto del elemento */
            height: auto; 
        }

        .subtitle {

            /* Color del texto en rgba */
            color: rgb(151 156 165 / 0.89);

            /* Transformación del texto a mayúsculas */ 
            text-transform: uppercase; 
        }

3. Compruebe la vista previa del resultado en el navegador.

Modelo de caja
--------------

1. Utilice un cliente de IAG para generar las reglas CSS en el documento *stylesheets/style.css*:

   a)  Con el selector por elemento para las etiquetas <section> con el borde tiene un grosor de 0.2 puntos, es sólido (sin trazos o estilos especiales) y su color es un tono gris azulado claro (#cedddd).
   b) Para la regla CSS anterior, entre el borde y el contenido agrega una separación vertical de 1.5% y una separación horizonal 0.8%; 
   c) Para la regla CSS anterior, agrega un margen de 4 píxeles en la parte superior, 2 píxeles en los lados derecho e izquierdo, y 8 píxeles en la parte inferior.

.. admonition:: Haga click aquí para ver la solución
    :collapsible: closed
    :class: solution

    .. code-block:: text
        :emphasize-lines: 5-23

        ...

        .subtitle { ... }

        section {

            /* borde de grosor 0.2 en puntos, estilo sólido y color hexadecimal #cedddd  */
            border: 0.2pt solid #cedddd; 

            /* relleno (espacio interno) de 
            1.5% en la parte superior e inferior y 
            0.8% a los lados derecho e izquierdo. */

            padding: 1.5% 0.8%; 

            /* margen (espacio externo) superior, derecho, abajo e izquierda */
            margin: 4px 2px 8px 2px; 

        }

2. Compruebe la vista previa del resultado en el navegador.


Efectos CSS
-----------

1. Utilice el servicio de `Border Radius <https://border-radius.com/>`_ para generar un borde redondeado de 5 píxeles para el borde de la etiqueta `<section>`.
2. Utilice el servicio de `Box Shadows <https://box-shadow.dev/>`_ para crear una sombra con desplazamiento de 3 píxeles en ambas direcciones, un desenfoque de 1 píxel y sin expansión, utilizando un color gris claro (235, 234, 234) semitransparente (0.6).

.. admonition:: Haga click aquí para ver la solución
    :collapsible: closed
    :class: solution

    .. code-block:: text
        :emphasize-lines: 7-10,12-15

        ...

        section { 
            
           ... 

           /* borde redondeado con un radio de 5 píxeles */
           -webkit-border-radius: 5px;
           -moz-border-radius: 5px;
           border-radius: 5px;

           /* sombra a un elemento */
           -webkit-box-shadow: 3px 3px 1px 0px rgba(235, 234, 234, 0.60);
           -moz-box-shadow: 3px 3px 1px 0px rgba(235, 234, 234, 0.60);
           box-shadow: 3px 3px 1px 0px rgba(235, 234, 234, 0.60);
        }

3. Compruebe la vista previa del resultado en el navegador.

.. note :: 
   
   Las propiedades `-webkit-border-` y `-moz-box-` son prefijos específicos de navegadores que se utilizaban en versiones antiguas de navegadores para implementar características experimentales o no estandarizadas de CSS. 
   
   Pueden aparecer en :term:`código legado` o para garantizar compatibilidad con navegadores muy antiguos.

Despliegue con GitHub Pages
---------------------------

1. Versione local y remotamente el repositorio *curriculum*.
2. Compruebe el resultado en el navegador.

Conclusiones
============

.. topic:: Preguntas de cierre

    ¿Cómo justificarías el impacto visual y funcional de utilizar bordes, márgenes, relleno y sombras en la presentación de las secciones de tu documento HTML frente a otros estilos posibles?


Actividades autónomas
=====================

Estándar CSS
------------------------------

* Revisa la documentación de `CSS - MDN <https://developer.mozilla.org/es/docs/Web/CSS>`_.
* En **W3Schools** revisa las opciones de `Selectores CSS <https://www.w3schools.com/cssref/css_selectors.php>`_ y las `Propiedades y Valores CSS <https://www.w3schools.com/cssref/index.php>`_.

Recursos extras
------------------------------

En redes:

.. raw:: html

    Animaciones CSS

    <blockquote class="twitter-tweet"><p lang="en" dir="ltr">🔵 CSS Animation Overview 🔵 <br><br>CSS Animations make animating web UI elements simple. You can achieve many animations without needing any JS or external packages and can be done straight away with vanilla CSS.<br><br>Let&#39;s break down CSS animations. 👇 🧵 1/14 <a href="https://t.co/bzCqU3SXm5">pic.twitter.com/bzCqU3SXm5</a></p>&mdash; Coner Murphy (@MrConerMurphy) <a href="https://twitter.com/MrConerMurphy/status/1387832309848625153?ref_src=twsrc%5Etfw">April 29, 2021</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

    Transiciones CSS

    <blockquote class="twitter-tweet"><p lang="en" dir="ltr">🌟 8 Practical examples of CSS transitions 🌟 <a href="https://t.co/pv679jfGPe">pic.twitter.com/pv679jfGPe</a></p>&mdash; George Moller (@_georgemoller) <a href="https://twitter.com/_georgemoller/status/1522250968741654531?ref_src=twsrc%5Etfw">May 5, 2022</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>