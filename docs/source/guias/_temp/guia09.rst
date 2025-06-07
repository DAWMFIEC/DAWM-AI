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

Fetch: async/await
------------------

1. En su archivo *js/functions.js*, modifique la función `fetchFakerData` que consuma el API de Faker utilizando la `Fetch API <https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API>`_.
2. Utilice un cliente de IAG para generar el contenido del archivo *functions.js* con las siguientes especificaciones:

   a) Modifique la función flecha `fetchFakerData` como asincrónica (utilice async/await). 
   b) Esta función debe realizar una petición HTTP mediante una :term:`Promesa`, utilizando fetch. La función siempre devuelve un objeto con las claves **success** y **data** o **error**.
   c) La clave **success** tendrá un valor booleano que indica si la petición fue exitosa (true) o si ocurrió un error (false) en el servidor HTTP o durante el procesamiento del cliente. 
   d) En caso de éxito, el objeto debe incluir **data** con el contenido de la respuesta convertida a JSON. 
   e) En caso de error, el objeto debe incluir **error** con un mensaje descriptivo del error ocurrido.


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

JSDoc
-----

1. Utilice un cliente de IAG en el documento javascript para generar la documentación JSDoc de las funciones creadas en el archivo *functions.js*. Asegúrese de que los comentarios JSDoc incluyan descripciones, parámetros y tipos de retorno.
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