..
   Copyright (c) 2025 Allan Avendaño Sudario
   Licensed under Creative Commons Attribution-ShareAlike 4.0 International License
   SPDX-License-Identifier: CC-BY-SA-4.0

========================================================================
Guía 12: React - Introducción y MUI - Librería de componentes para React
========================================================================

.. topic:: Objetivo específico
    :class: objetivo

    Utilizar React para construir la estructura inicial del dashboard e integrar la librería MUI para incorporar componentes visuales modernos que mejoren la usabilidad e interfaz del sistema.
 

Actividades previas
=====================

Diseño del dashboard
----------------------

1. Explore la documentación de la `API de Open-Meteo <https://open-meteo.com/en/docs>`_.
2. Identifique los elementos claves del API que serán útiles para el :term:`dashboard`:

   a) **Parámetros de entrada (Input)**: Determine qué parámetros son necesarios para realizar una solicitud a la API, como ubicación geográfica o zona horaria.
   b) **Datos disponibles (Variables climáticas)**: Explore las variables climáticas que la API puede proporcionar y su frecuencia temporal, como temperatura actual, por día o por hora, etc.
   c) **Formato de respuesta (Response)**: Familiarícese con el formato de respuesta de la API, que generalmente es JSON, y cómo se estructuran los datos.
   d) **Codificación del clima (weathercode)**: Comprenda cómo se codifica el clima en la respuesta de la API, lo que le permitirá interpretar correctamente las condiciones climáticas.
   e) **Errores comunes**: Identifique la respuesta de la API para los errores más comunes, como solicitudes mal formadas o problemas de conexión.
   f) **Casos de uso para el dashboard**: Reflexione sobre cómo estos datos pueden ser utilizados en el dashboard, como mostrar el clima actual, pronósticos extendidos, gráficos de evolución, alertas visuales, etc.
      
      a) Clima actual: temperatura, humedad, estado del cielo
      b) Gráficos de evolución: temperatura por hora, precipitación acumulada
      c) Pronósticos extendidos: próximos 7 días
      e) Alertas visuales: si uv_index_max supera cierto umbral, mostrar advertencia
      f) Íconos adaptativos: usando weathercode

Ambiente de desarrollo
----------------------

1. Cree un repositorio en GitHub con el nombre *dashboard*.

   a) Agregue un archivo README.md con el título de su dashboard y una breve descripción del objetivo de su proyecto.
   b) Agregue un archivo *.gitignore* con la plantilla de *Node*.
   
2. Acceda a su proyecto *dashboard* en Codespaces o en su máquina local.
3. Cree y utilice la(s) rama(s) de desarrollo.

Actividades en clases
=====================

React
------

1. Explore la documentación de `React <https://react.dev/>`_ para comprender los conceptos básicos de esta biblioteca.
2. Cree un proyecto de React utilizando `Vite <https://vitejs.dev/guide/#scaffolding-your-first-vite-project>`_.

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
