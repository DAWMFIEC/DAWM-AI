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
        :emphasize-lines: 3-20

        section { ... }
        
        nav > ul {

            /* Activa el modelo de diseño Flexbox*/
            display: flex; 

            /* Distribuye los elementos con espacio igual entre ellos */
            justify-content: space-between;

            /* Organiza los elementos en una fila horizontal de izquierda a derecha */ 
            flex-direction: row;

            /* Centra verticalmente los elementos dentro del contenedor */
            align-items: center; 

            /* Establece un espacio uniforme de 1rem entre cada elemento */
            gap: 1rem; 

        }

2. Compruebe la vista previa del resultado en el navegador.

   .. note::

        Revisa los conceptos básicos de flexbox en `Basic concepts of flexbox <https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Basic_concepts_of_flexbox>`_ y la guía de CSS flexbox en `CSS Flexbox Layout Guide <https://css-tricks.com/snippets/css/a-guide-to-flexbox/>`_.

Grid
----

.. sidebar:: 

    Con :term:`grid` los elementos dentro de un contenedor pueden alinearse en filas y columnas, lo que permite crear diseños más complejos y estructurados.

    .. image:: https://tutorial.techaltum.com/images/css-grids.jpg

1. Compruebe en el archivo *index.html*:

   a) Todos los controles del formulario deben estar al mismo nivel, es decir, no deben estar anidados dentro de etiquetas `<div>` o `<span>`. 

   .. code-block:: html
       :caption: Controles del formulario sin etiquetas contenedoras.
       :linenos:

       <form>
            <label> ... </label>
            <input ... >
            
            <label> ... </label>
            <select ... > ... </select>
            
            <fieldset> ... <fieldset>
            
            <button> ... </button>
       </form>

2. Utilice un cliente de IAG para generar las reglas CSS en el documento *stylesheets/style.css*:

   a) Con el selector para la etiqueta hija `<form>` dentro de la etiqueta `<section>`, utilice la propiedad `display` con el valor `grid` para activar el modelo de diseño grid.

   b) Para el selector anterior, define una estructura de una sola columna en un contenedor con diseño de cuadrícula (grid), asignándole una fracción proporcional del espacio disponible, de modo que ocupe todo el ancho del área del contenedor.
   
   c) Para el selector anterior, establece un espacio uniforme de 1 unidad relativa al tamaño de la fuente raíz (1rem) entre cada par de elementos hijos por fila y por columna, por separado.

.. admonition:: Haga click aquí para ver la solución
    :collapsible: closed
    :class: solution

    .. code-block:: text
        :emphasize-lines: 3-17

        nav > ul { ... }
        
        section > form {
            
            /* Activa el modelo de diseño basado en cuadrícula */
            display: grid;

            /* Define una sola columna que ocupa todo el ancho disponible del contenedor */
            grid-template-columns: 1fr;

            /* Establece un espacio vertical uniforme de 1rem entre filas */
            row-gap: 1rem;

            /* Establece un espacio horizontal uniforme de 1rem entre columnas */
            column-gap: 1rem;

        }


3. Compruebe la vista previa del resultado en el navegador.

   .. note::

        Revisa los conceptos básicos de grid en `Basic concepts of grid layout <https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Basic_concepts_of_grid_layout>`_ y la guía de CSS grid en `CSS Grid Layout Guide <https://css-tricks.com/snippets/css/complete-guide-grid/>`_.

Flex vs Grid
-------------------------------------

1. Compruebe en el archivo *index.html*:

   a) En la sección de referencias, organice los elementos de la siguiente manera:

      (i) El subtítulo es una etiqueta `<h2>`.
      (ii) Las tres artículos son etiquetas `<article>`, y se encuentran al mismo nivel que el subtítulo.

   .. code-block:: html
       :caption: Estructura de la sección referencias.
       :linenos:

       <section>
           <h2>Referencias</h2>
           <article> ... </article>
           <article> ... </article>
           <article> ... </article>
       </section>
        
2. Utilice un cliente de IAG para generar las reglas CSS en el documento *stylesheets/style.css*:

   a) Para organizar la sección referencias para Grid y Flex, independientemente. El subtitulo ocupa todo el ancho y los tres artículos ocupen el espacio equitativamente. El espacio de separación entre filas y columnas es 1rem. No agregue otras etiquetas, ni atributos. 


.. admonition:: Haga click aquí para ver la solución
    :collapsible: closed
    :class: solution

    .. tabs::

        .. tab:: Flex

           .. code-block:: text
               :emphasize-lines: 3-14,16-21,23-28

               section > form { ... }

               #referencias {

                    /* Activa el modelo Flexbox */
                    display: flex;

                    /* Permite que los hijos pasen a la siguiente línea si no caben */
                    flex-wrap: wrap;

                    /* Espaciado uniforme entre filas y columnas */
                    gap: 1rem;
            
               }

               #referencias > h2 {
            
                    /* Hace que el subtítulo ocupe el 100% del ancho del contenedor */
                    flex: 0 0 100%;
                
               }

               #referencias > article {
                
                    /* Distribuye equitativamente los artículos en tres columnas */
                    flex: 1 1 calc(33.333% - 1rem);
                
               }            

        .. tab:: Grid
        
           .. code-block:: text
               :emphasize-lines: 3-14,16-21

               section > form { ... }

               #referencias {

                    /* Activa el modelo Grid */
                    display: grid;

                    /* Define tres columnas iguales */
                    grid-template-columns: repeat(3, 1fr);

                    /* Espacio entre filas y columnas */
                    row-gap: 1rem;
                    column-gap: 1rem;

               }
                    
               #referencias > h2 {

                    /* El subtítulo ocupa las tres columnas */
                    grid-column: 1 / -1;

               }
        

3. Compruebe la vista previa del resultado en el navegador.

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

    <blockquote style="width:px; max-width:100%; max-height:500px; height:px;" class="twitter-tweet" data-dnt="true" align="center"><a class="twitter-timeline" href="https://x.com/cristiank170319/status/1710508125567000742">Loading...</a></blockquote><script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script><div style="position: absolute;width: 77%;bottom: 3px;left: 0;right: 0;margin-left: auto;margin-right: auto;color: #000;text-align: center;"><small style="line-height: 1.3;font-size: 0px;background: #fff;"> <a href="https://twitembed.com/">Twitter embed code generator</a> </small><script type="text/javascript" src="https://twitembed.com/tw.js"></script></div><style>.twit2{height:221px;width:211px;} #fav img{max-height:none!important;max-width:none!important;background:none!important} #twit twit{max-height:none!important;max-width:none!important;background:none!important}</style></div>