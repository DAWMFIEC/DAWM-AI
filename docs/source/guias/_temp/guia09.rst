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

HTML
----

1. En el documento *index.html*, cree una sección para mostrar los datos obtenidos de la API de Faker.

   .. dropdown::

      Dropdown content
   
   .. code-block:: html
      :caption: Código HTML para la sección de datos en index.html
      :emphasize-lines: 3-42
   
      <section class="bg-slate-50 dark:bg-gray-900"> ... </section>

      <section class="bg-slate-50 dark:bg-gray-900">
        <div class="max-w-4xl pt-8 pb-3 mx-auto">
            <div id="skeleton-container" class="grid grid-cols-1 md:grid-cols-3 gap-6 p-6">
            
                <!-- Skeleton Card -->
                <div class="animate-pulse space-y-4 bg-white dark:bg-gray-800 p-4 rounded-2xl shadow">
                <div class="w-full h-40 bg-gray-300 dark:bg-gray-700 rounded-lg"></div>
                <div class="h-6 bg-gray-300 dark:bg-gray-700 rounded w-3/4"></div>
                <div class="h-5 bg-gray-300 dark:bg-gray-700 rounded w-1/2"></div>
                <div class="space-y-2">
                    <div class="h-3 bg-gray-300 dark:bg-gray-700 rounded w-full"></div>
                    <div class="h-3 bg-gray-300 dark:bg-gray-700 rounded w-5/6"></div>
                </div>
                </div>

                <!-- Skeleton Card -->
                <div class="animate-pulse space-y-4 bg-white dark:bg-gray-800 p-4 rounded-2xl shadow">
                <div class="w-full h-40 bg-gray-300 dark:bg-gray-700 rounded-lg"></div>
                <div class="h-6 bg-gray-300 dark:bg-gray-700 rounded w-3/4"></div>
                <div class="h-5 bg-gray-300 dark:bg-gray-700 rounded w-1/2"></div>
                <div class="space-y-2">
                    <div class="h-3 bg-gray-300 dark:bg-gray-700 rounded w-full"></div>
                    <div class="h-3 bg-gray-300 dark:bg-gray-700 rounded w-5/6"></div>
                </div>
                </div>

                <!-- Skeleton Card -->
                <div class="animate-pulse space-y-4 bg-white dark:bg-gray-800 p-4 rounded-2xl shadow">
                <div class="w-full h-40 bg-gray-300 dark:bg-gray-700 rounded-lg"></div>
                <div class="h-6 bg-gray-300 dark:bg-gray-700 rounded w-3/4"></div>
                <div class="h-5 bg-gray-300 dark:bg-gray-700 rounded w-1/2"></div>
                <div class="space-y-2">
                    <div class="h-3 bg-gray-300 dark:bg-gray-700 rounded w-full"></div>
                    <div class="h-3 bg-gray-300 dark:bg-gray-700 rounded w-5/6"></div>
                </div>
                </div>

            </div>
        </div>
      </section>

      <div id="toast-interactive" ... > </div>

Archivos y estructura
---------------------

1. Cree el documento javascript *functions.js* dentro de la carpeta *js* de tu proyecto. Declare el modo estricto del documento. Cree y exporte una función flecha `fetchFakerData`. 
   
   .. code-block:: javascript
      :caption: Declaración de la función fetchFakerData en el archivo functions.js
      :emphasize-lines: 1-5

      'use strict';

      let fetchFakerData = (url) => { }

      export { fetchFakerData }

2. En el documento *js/file01.js*, importe la función `fetchFakerData` del documento *functions.js*.

   .. code-block:: javascript
      :caption: Importación de fetchFakerData en file01.js
      :emphasize-lines: 3

      'use strict';

      import { fetchFakerData } from './functions.js';

      ...

Fetch: Promesas + async/await
-----------------------------

.. sidebar:: 

   .. image:: https://lenguajejs.com/asincronia/introduccion/que-es/asincronia-javascript.png
      
   ¿Qué es la Asincronía? de `ManzDev <https://manz.dev/>`_.

1. Utilice un cliente de IAG para explicar cómo se manejan operaciones asincrónicas con async/await, como las peticiones HTTP.

2. Revise el tutorial `JavaScript async/await <https://www.javascripttutorial.net/javascript-async-await/>`_ y utilice un cliente de IAG para generar el código en *js/functions.js*, de acuerdo con las siguientes especificaciones:

   a) Convierta la función flecha `fetchFakerData` en asincrónica (async). 
   b) La función realiza una petición HTTP con el objeto fetch. Espere (await) a que la :term:`Promesa` se resuelva o se rechace. 
   c) La función siempre devuelve un objeto con las claves **success** y **data** o **error**.
      
      (i) La clave **success** tendrá un valor booleano que indica si la petición fue exitosa (true) o si ocurrió un error (false) en el servidor HTTP o durante el procesamiento del cliente. 
      
      (ii) En caso de éxito, el objeto debe incluir **data** con el contenido de la respuesta convertida a JSON. 
      
      (iii) En caso de error, el objeto debe incluir **error** con un mensaje descriptivo del error ocurrido.


.. admonition:: Haga click aquí para ver la solución
    :collapsible: closed
    :class: solution

    .. code-block:: javascript
        :emphasize-lines: 3-38

        'use strict';

        let fetchFakerData = async (url) => {

            try {

                // Realizar la petición HTTP usando fetch
                const response = await fetch(url);
                
                // Verificar si la respuesta fue exitosa (status 200-299)
                if (!response.ok) {

                    return {
                        success: false,
                        error: `Error HTTP: ${response.status} - ${response.statusText}`
                    };

                }
                
                // Convertir la respuesta a JSON
                const data = await response.json();
                
                // Retornar objeto con éxito
                return {
                    success: true,
                    data: data
                };
                
            } catch (error) {

                // Manejar errores de red, JSON parsing, etc.
                return {
                    success: false,
                    error: `Error en la petición: ${error.message}`
                };

            }
        };
        
        export { fetchFakerData }

Fetch: Promesas + cadena de promesas
------------------------------------

.. sidebar:: 

   .. image:: https://www.scaler.com/topics/images/async-await-vs-promises_thumbnail.webp
      
   Difference Between Promise and Async Await in Node.js de `Scaler.com <https://www.scaler.com/topics/async-await-vs-promises/>`_.

1. Utilice un cliente de IAG para explicar cómo se manejan operaciones asincrónicas con cadena de promesas, como las peticiones HTTP.

2. Revise el tutorial `Promise Chaining <https://www.javascripttutorial.net/promise-chaining/>`_ y utilice un cliente de IAG para generar el código en *js/file01.js*, de acuerdo con las siguientes especificaciones:

   a) Agregue la función flecha `loadData`, que:

      (i) Declare una constante `url` con el valor de la URL de la API de Faker `https://fakerapi.it/api/v2/texts?_quantity=10&_characters=120`.
      
      (ii) Llame a la función `fetchFakerData` pasando la constante `url` como argumento.
      
      (iii) Encadene el método `then` para manejar la respuesta de la función `fetchFakerData`. En caso de éxito, muestre los datos en la consola. En caso de error, muestre el mensaje de error en la consola. Encadene el método `catch` para manejar cualquier error que ocurra durante la ejecución de la promesa. Considere las claves **success** y **data** o **error** del objeto devuelto por la función `fetchFakerData`.
      
      (iv) Encadene el método `finally` para mostrar un mensaje en la consola indicando que la petición ha finalizado, independientemente de si fue exitosa o no.

   b) Llame a la función `loadData` en la función de autojecución.

.. admonition:: Haga click aquí para ver la solución
    :collapsible: closed
    :class: solution

    .. code-block:: javascript
        :emphasize-lines: 7-31, 38

        'use strict';

        import { fetchFakerData } from './functions.js';

        ...	

        const loadData = () => {

            const url = "https://fakerapi.it/api/v2/texts?_quantity=10&_characters=120";

            fetchFakerData(url)
                .then((result) => {

                    if (result.success) {
                        console.log("Data:", result.data);
                    } else {
                        console.error("Error:", result.error);
                    }

                })
                .catch((error) => {

                    console.error("Caught error during promise execution:", error);

                })
                .finally(() => {

                    console.log("Request has ended.");

                });
        };

        // Función de autoejecución
        (() => {

            ...
            
            loadData();
        })();

2. Compruebe la vista previa del resultado y la consola del navegador para verificar la ejecución del código.

JSDoc
-----

1. Utilice un cliente de IAG en el documento javascript para generar la documentación JSDoc de las funciones creadas. Asegúrese de que los comentarios JSDoc incluyan descripciones, parámetros y tipos de retorno.
2. Valide su respuesta con `JSDoc: La Guía Definitiva para Documentar tu Código JavaScript <https://dev.to/goaqidev/jsdoc-la-guia-definitiva-para-documentar-tu-codigo-javascript-ik5>`_.

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

    <blockquote class="twitter-tweet"><p lang="en" dir="ltr">JavaScript&#39;s Fetch API: A Beginner’s Guide 🧵 <a href="https://t.co/K3EUdD72F5">pic.twitter.com/K3EUdD72F5</a></p>&mdash; Csaba Kissi (@csaba_kissi) <a href="https://twitter.com/csaba_kissi/status/1904169335121465653?ref_src=twsrc%5Etfw">March 24, 2025</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

    APIs públicas para probar	

    <blockquote class="twitter-tweet"><p lang="en" dir="ltr">Try Public APIs for free<a href="https://t.co/YKUy0OdgTA">https://t.co/YKUy0OdgTA</a></p>&mdash; SwiftUIX (@SwiftUIHome) <a href="https://twitter.com/SwiftUIHome/status/1917132347260211689?ref_src=twsrc%5Etfw">April 29, 2025</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>