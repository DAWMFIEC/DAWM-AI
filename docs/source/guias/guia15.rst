..
   Copyright (c) 2025 Allan Avendaño Sudario
   Licensed under Creative Commons Attribution-ShareAlike 4.0 International License
   SPDX-License-Identifier: CC-BY-SA-4.0

==================================
Guía 15: React - Hooks (useEffect)
==================================

.. topic:: Objetivo específico
    :class: objetivo

    Implementar la gestión efectos secundarios y la actualización dinámica de la interfaz según los cambios de ubicación o preferencias del usuario en el dashboard. 

Actividades previas
=====================

Open-Meteo
----------

1. Consulte la documentación de la API de Open-Meteo en `Open-Meteo API <https://open-meteo.com/en/docs>`_.
2. Seleccione la ubicación que desea utilizar para las consultas, con coordenadas geográficas.
3. Marque los indicadores que desea mostrar el dashboard, como temperatura, humedad, viento, etc, en la sección de `Current Weather <https://open-meteo.com/en/docs#current_weather>`_ de la documentación.
4. Seleccione la configuración de las unidades de medida de la API, como temperatura, velocidad del viento, unidades de precipitación, etc.  
5. Obtenga la URL de la API con los parámetros seleccionados.
6. Compruebe la estructura del JSON de salida en su navegador.

Ambiente de desarrollo
----------------------

1. Acceda a su proyecto *dashboard* en Codespaces o en su máquina local.
2. Cree y utilice la(s) rama(s) de desarrollo.
3. Instale los paquetes y levante el servidor, con:

   .. code-block:: bash

      npm install
      npm run dev

Actividades en clases
=====================

Interfaces
----------

1. Genere el tipo de datos TypeScript para el JSON de salida de la API de Open-Meteo, con:

   a) Utilice `Transform JSON to TypeScript <https://transform.tools/json-to-typescript>`_. 
   b) Coloque el JSON de salida de la API de Open-Meteo en el campo de entrada.
   c) Genere el código TypeScript de las interfaces y cópielo en su proyecto en el archivo `src/types/WeatherTypes.tsx`.
   d) Modifique el nombre de la interfaz `Root` por `OpenMeteoResponse`.

2. Utilice su cliente de IAG para justificar el uso de las interfaces y el tipo de datos que representan.

React - Hook: useEffect
-----------------------

React - Hook: useState
-----------------------

Conclusiones
============

.. topic:: Preguntas de cierre

    * ¿Qué?

    * ¿Qué?

    * ¿Cómo?

Actividades autónomas
=====================

Recursos extras
------------------------------

En redes:

.. raw:: html

    <blockquote class="twitter-tweet"><p lang="en" dir="ltr">⚛️ useEffect cheatsheet ↓<br><br>❌ Thinking of useEffect as a lifecycle method.<br><br>✅ Thinking of useEffect as a mechanism to sync data (state/props) with systems that aren’t controlled by React. <a href="https://t.co/v8BK5CLsSn">pic.twitter.com/v8BK5CLsSn</a></p>&mdash; George Moller (@_georgemoller) <a href="https://twitter.com/_georgemoller/status/1714250976947794418?ref_src=twsrc%5Etfw">October 17, 2023</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>