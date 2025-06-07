..
   Copyright (c) 2025 Allan Avendaño Sudario
   Licensed under Creative Commons Attribution-ShareAlike 4.0 International License
   SPDX-License-Identifier: CC-BY-SA-4.0

====================================
Guía 09: Promesas, Servicios y JSON 
====================================

.. topic:: Objetivo específico
    :class: objetivo

    Implementar funciones en JavaScript que consuman servicios externos utilizando promesas para recuperar datos en formato JSON y mostrarlos dinámicamente en la landing page mejorando así la interactividad y la presentación de contenido relevante para el usuario.

Actividades previas
=====================

Faker API
---------

1. Visite el sitio web de `Faker API <https://fakerapi.it/>`_.
2. Familiarícese con la documentación de la API del recurso **Texts** y los parámetros que puede utilizar para personalizar las respuestas.
3. Utilice un cliente de IAG para explicar el concepto de :term:`API` y cómo se utiliza para interactuar con servicios externos.

JSON
----

1. Visite el sitio web de `ReqBin <https://reqbin.com/>`_.
2. Realice una petición a la API de Faker, p.e.:
   
   - **URL:** `https://fakerapi.it/api/v2/texts?_quantity=10&_characters=120`
   - **Método:** `GET`

3. Explore la :term:`petición HTTP` y la :term:`respuesta HTTP` en formato :term:`JSON` que se muestra en la sección de respuesta.
4. Utilice un cliente de IAG para explicar cómo se estructura la petición y la respuesta de la API; además del formato JSON.

Ambiente de desarrollo
----------------------

1. Acceda a su proyecto *landing* en Codespaces o en su máquina local.
2. Cree y utilice la(s) rama(s) de desarrollo.
3. Instale los paquetes y levante el servidor, con:

   .. code-block:: bash

      npm install
      npm run dev

Actividades en clases
=====================

Archivos y estructura
---------------------

1. Cree el documento javascript *functions.js* dentro de la carpeta *js* de tu proyecto.
2. Utilice un cliente de IAG para generara el contenido del archivo *functions.js* con las siguientes especificaciones:
   
   a) Declare el modo estricto del documento.
   b) Cree y exporte una función llamada `fetchFakerData`. La función recibe el parámetro `url` de tipo string y retorna la `respuesta` de tipo JSON.
   c) Genere un comentario con la documentación de función con JSDoc. 


'use strict';

/**
 * Realiza una solicitud HTTP a la URL dada y retorna los datos en formato JSON.
 *
 * @param {string} url - La URL del recurso desde donde se desea obtener los datos.
 * @returns {Promise<any>} Una promesa que resuelve con los datos en formato JSON.
 *
 * @example
 * fetchFakerData('https://fakestoreapi.com/products')
 *   .then(data => console.log(data))
 *   .catch(error => console.error(error));
 */
export function fetchFakerData(url) {
  return fetch(url)
    .then(response => {
      if (!response.ok) {
        throw new Error(`Error al obtener los datos: ${response.status}`);
      }
      return response.json();
    });
}

2. Modifique el documento *js/file01.js*, con: 
   
   a) Importe la función `fetchFakerData` del documento *functions.js*.

HTML
----

Promesas (Fetch API)
--------------------

1. En su archivo *js/functions.js*, cree una función que consuma la API de Faker utilizando la `Fetch API <https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API>`_.
2. Utilice un cliente de IAG para explicar el concepto de :term:`Promesa` en JavaScript y cómo se utilizan para manejar operaciones asincrónicas.

   .. code-block:: javascript
      :linenos:

      // Función para consumir la API de Faker
      let fetchFakerData = () => {
          return fetch('https://fakerapi.it/api/v2/texts?_quantity=10&_characters=120')
              .then(response => {
                  if (!response.ok) {
                      throw new Error('Network response was not ok');
                  }
                  return response.json();
              })
              .catch(error => {
                  console.error('There has been a problem with your fetch operation:', error);
              });
      }

Versionamiento
--------------

1. Versione local y remotamente la(s) rama(s) de desarrollo en el repositorio *landing*.
2. Genere la(s) solicitud(es) de cambios (pull request) para la rama principal y apruebe los cambios.

Vercel
------

1. Verifique el despliegue continuo (CD) del proyecto en Vercel.

Conclusiones
============

.. topic:: Preguntas de cierre

    * ¿Cómo te ayudó la inteligencia artificial generativa a entender el flujo de ejecución de una promesa en JavaScript?
    
    * ¿Cómo verificaste que el manejo de errores y la estructura de los then, catch y finally respondieran adecuadamente a diferentes escenarios de respuesta del servicio externo?
    
    * ¿Cómo puedes asegurar que el uso de inteligencia artificial para manejar peticiones asincrónicas no sustituya tu razonamiento lógico y tu comprensión del manejo de datos en tiempo real?

Actividades autónomas
=====================

Recursos extras
------------------------------

En redes:

.. raw:: html

    Promesas en JavaScript

    <blockquote class="twitter-tweet"><p lang="en" dir="ltr">⚡️ Promises in JavaScript Explained⚡️<br><br>A 🧵👇 <a href="https://t.co/EbRRaZOSaD">pic.twitter.com/EbRRaZOSaD</a></p>&mdash; Ighmaz (@ighmaz_js) <a href="https://twitter.com/ighmaz_js/status/1596847897425113088?ref_src=twsrc%5Etfw">November 27, 2022</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

    APIs públicas para probar	

    <blockquote class="twitter-tweet"><p lang="en" dir="ltr">Try Public APIs for free<a href="https://t.co/YKUy0OdgTA">https://t.co/YKUy0OdgTA</a></p>&mdash; SwiftUIX (@SwiftUIHome) <a href="https://twitter.com/SwiftUIHome/status/1917132347260211689?ref_src=twsrc%5Etfw">April 29, 2025</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>