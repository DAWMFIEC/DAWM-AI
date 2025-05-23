..
   Copyright (c) 2025 Allan Avendaño Sudario
   Licensed under Creative Commons Attribution-ShareAlike 4.0 International License
   SPDX-License-Identifier: CC-BY-SA-4.0

========================================================
Guía 05: CSS - Diseño
========================================================

.. topic:: Objetivo específico
    :class: objetivo

    Utlizar reglas CSS en la organización visual del contenido mediante el desarrollo de un currículum vitae digital para la presentación de información profesional de manera organizada y accesible en línea.

Actividades previas
=====================

Ambiente de desarrollo
----------------------

1. Acceda a su proyecto *curriculum* en Codespaces o en su máquina local.
2. Haga clic en el ícono de `Live Preview` en la barra de estado de VSCode para iniciar el servidor local.

Actividades en clases
=====================

Flex
----

.. sidebar:: 

    Con :term:`flex`, o flexbox, los elementos dentro de un contenedor pueden crecer, encogerse y alinearse de manera flexible.

    .. image:: https://img.uxcel.com/practices/flexbox-1665382286109/a-1665382286109-2x.jpg


1. Utilice un cliente de IAG para generar las reglas CSS en el documento *stylesheets/style.css*:

   a) Con el selector para la etiqueta hija `<ul>` dentro de la etiqueta `<nav>`, utilice la propiedad `display` con el valor `flex` para activar el modelo de diseño flexbox.
   
   b) Para el selector anterior, distribuya el espacio equitativamente entre los elementos de la lista.
   
   c) Para el selector anterior, establece que los elementos hijos de un contenedor flexible se organicen en una fila horizontal, de izquierda a derecha, siguiendo la dirección principal del eje horizontal.

   d) Para el selector anterior, establece que los elementos hijos de un contenedor flexible se alineen verticalmente en el centro del eje transversal, ubicándolos equidistantes respecto a los bordes superior e inferior del contenedor.

   e) Para el selector anterior, establece un espacio uniforme de 1 :term:`unidad relativa al tamaño de la fuente raíz` (1rem) entre cada par de elementos hijos.

.. admonition:: Haga click aquí para ver la solución
    :collapsible: closed
    :class: solution

    .. code-block:: text
        :emphasize-lines: 3-9

        section { ... }
        
        nav > ul {
            display: flex;
            justify-content: space-between;
            flex-direction: row;
            align-items: center;
            gap: 1rem;
        }

2. Compruebe la vista previa del resultado en el navegador.

    .. note::

         Revisa la guía de CSS flexbox en `CSS Flexbox Layout Guide <https://css-tricks.com/snippets/css/a-guide-to-flexbox/>`_.

Grid
----

.. sidebar:: 

    Con :term:`grid` los elementos dentro de un contenedor pueden alinearse en filas y columnas, lo que permite crear diseños más complejos y estructurados.

1. Utilice un cliente de IAG para generar las reglas CSS en el documento *stylesheets/style.css*:

2. Compruebe la vista previa del resultado en el navegador.

Criterios de evaluación: Flex vs Grid
-------------------------------------


Despliegue con GitHub Pages
---------------------------

1. Versione local y remotamente el repositorio *curriculum*.
2. Compruebe el resultado en el navegador.

Conclusiones
============

.. topic:: Preguntas de cierre

    * ¿Qué diferencias conceptuales encontraste entre el uso de Flexbox y Grid para organizar visualmente el contenido del currículum vitae?

    * ¿Qué modificaciones realizaste sobre el código generado por la IA al momento de implementar el diseño con Flexbox o Grid?

    * ¿Cómo puedes garantizar que el uso de inteligencia artificial en la implementación de Flexbox o Grid no reemplace tu capacidad de toma de decisiones como futuro desarrollador web?


Actividades autónomas
=====================

Recursos extras
------------------------------

En redes:

.. raw:: html

    Flexbox vs Grid mediante juegos interactivos.

    <blockquote class="twitter-tweet"><p lang="es" dir="ltr">Descubre <a href="https://twitter.com/hashtag/CSSGrid?src=hash&amp;ref_src=twsrc%5Etfw">#CSSGrid</a> y <a href="https://twitter.com/hashtag/Flexbox?src=hash&amp;ref_src=twsrc%5Etfw">#Flexbox</a> de manera divertida con Grid Garden y Flexbox Froggy. 🎮🌐 Aprende jugando . 💻🚀 <br>Jardín Grid: <a href="https://t.co/SLubvps9gb">https://t.co/SLubvps9gb</a><br>Flexbox Froggy: <a href="https://t.co/e17lQydbXT">https://t.co/e17lQydbXT</a><br>¡CSS nunca fue tan divertido! 🌈✨<a href="https://twitter.com/hashtag/WebDev?src=hash&amp;ref_src=twsrc%5Etfw">#WebDev</a> <a href="https://twitter.com/hashtag/CodingFun?src=hash&amp;ref_src=twsrc%5Etfw">#CodingFun</a> <a href="https://t.co/OPd5eAouGd">pic.twitter.com/OPd5eAouGd</a></p>&mdash; Cristian Omar Guzman (@cristiank170319) <a href="https://twitter.com/cristiank170319/status/1710508125567000742?ref_src=twsrc%5Etfw">October 7, 2023</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>