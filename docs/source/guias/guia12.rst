..
   Copyright (c) 2025 Allan Avendaño Sudario
   Licensed under Creative Commons Attribution-ShareAlike 4.0 International License
   SPDX-License-Identifier: CC-BY-SA-4.0

===================================
Guía 12: React y MUI - Introducción
===================================

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
      
      (i) Clima actual: temperatura, humedad, estado del cielo
      (ii) Gráficos de evolución: temperatura por hora, precipitación acumulada
      (iii) Pronósticos extendidos: próximos 7 días
      (iv) Alertas visuales: si uv_index_max supera cierto umbral, mostrar advertencia
      (v) Íconos adaptativos: usando weathercode

Ambiente de desarrollo
----------------------

1. Cree un repositorio en GitHub con el nombre *dashboard*.

   a) Agregue un archivo README.md con el título de su dashboard y una breve descripción del objetivo de su proyecto.
   b) Agregue un archivo *.gitignore* con la plantilla de *Node*.
   
2. Acceda a su proyecto *dashboard* en Codespaces o en su máquina local.
3. Cree y utilice la(s) rama(s) de desarrollo.

Actividades en clases
=====================

React: Inicialización del proyecto
----------------------------------

1. Explore la documentación de `React <https://react.dev/>`_ para comprender los conceptos básicos de esta biblioteca.
2. Cree un proyecto de React utilizando `Vite <https://vitejs.dev/guide/#scaffolding-your-first-vite-project>`_.

   a) Dentro de la carpeta de su proyecto, abra la terminal y cree un nuevo proyecto de Vite con el siguiente comando:

   .. code-block:: bash

      npm create vite@latest . 
   
   b) Seleccione el framework como :term:`React` y la variante como `TypeScript`.
   c) Instale las dependencias del proyecto e inicie el servidor de desarrollo con los siguientes comandos:

   .. code-block:: bash

      npm install
      npm run dev

3. Compruebe la vista previa del resultado en el navegador.
4. Con un cliente de IAG, explique la estructura del proyecto en React, específicamente por el propósito de los archivos `index.html`, `main.tsx` y `App.tsx`.

React: App.tsx
--------------

1. Modifique el archivo `App.tsx` para mostrar un mensaje de bienvenida, por ejemplo:

   .. code-block:: tsx
      :emphasize-lines: 5-7

      import React from 'react';

      function App() {
          return (
              <div>
                  <h1>Bienvenido al Dashboard</h1>
              </div>
          );
      }

      export default App;

2. Compruebe la vista previa del resultado en el navegador.
3. Utilice un cliente de IAG, para explicar cómo se renderiza el componente principal de la aplicación y :term:`JSX`.

MUI: Inicialización del proyecto y componente Grid
--------------------------------------------------

1. Explore la documentación de `MUI <https://mui.com/material-ui/getting-started/overview/>`_ para comprender cómo integrar esta biblioteca en su proyecto de React.
2. Instale MUI y sus dependencias en su proyecto de React con el siguiente comando:

   .. code-block:: bash

      npm install @mui/material @emotion/react @emotion/styled

3. Importe el componente `Grid` de MUI en su archivo `App.tsx` y utilícelo para crear una estructura básica de cuadrícula para su dashboard:

   .. dropdown:: Ver el código 
    :color: primary

    .. code-block:: tsx
        :emphasize-lines: 2, 6-29

         import React from 'react';
         import { Grid } from '@mui/material';

         function App() {
            return (
               <Grid>

                  {/* Encabezado */}
                  <Grid>Elemento: Encabezado</Grid>

                  {/* Alertas */}
                  <Grid>Elemento: Alertas</Grid>

                  {/* Selector */}
                  <Grid>Elemento: Selector</Grid>

                  {/* Indicadores */}
                  <Grid>Elemento: Indicadores</Grid>

                  {/* Gráfico */}
                  <Grid>Elemento: Gráfico</Grid>

                  {/* Tabla */}
                  <Grid>Elemento: Tabla</Grid>

                  {/* Información adicional */}
                  <Grid>Elemento: Información adicional</Grid>

               </Grid>
            );
         }

         export default App;

4. Compruebe la vista previa del resultado en el navegador. 
5. Con un cliente de IAG, explique cómo se utiliza el componente `Grid` de MUI para crear una estructura de cuadrícula y cómo se pueden agregar elementos dentro de esta cuadrícula.

MUI: Ubicación de elementos y Responsividad
-------------------------------------------

1. Modifique el componente `Grid` su archivo `App.tsx`:

   a) Para que sea un contenedor principal utilizando el :term:`prop` `container <https://mui.com/material-ui/react-container/>`_.
   b) Ajuste el espaciado de 5 unidades entre los elementos utilizando la propiedad `spacing <https://mui.com/material-ui/react-container/>`_. 
   c) Alinee los elementos en el centro utilizando la propiedad `sx <https://mui.com/material-ui/react-container/>`_ para los estilos  `justifyContent` y `alignItems`.
   d) Compruebe la vista previa del resultado en el navegador.
   
   .. code-block:: tsx
       :emphasize-lines: 5

       ...

       function App() {
         return (
            <Grid container spacing={5} sx={{ justifyContent: "center", alignItems: "center" }}>
               ...
            </Grid>
       }

2. Utilice su cliente de IAG para definir el prop `size <https://mui.com/material-ui/react-grid/#multiple-breakpoints>`_, para aplicar el estilo en los múltiples puntos de interrupción:

   a) Pantallas extra pequeñas `xs`, todos los elementos se apilen verticalmente. 
   b) Pantallas medianas `md`, en adelante:
   
      (i) El encabezado ocupe todo el ancho (12 columnas), 
      (ii) Las alertas ocupan 12 columnas.
      (iii) El selector ocupa 3 columnas y los indicadores ocupan 9 columnas.
      (iv) El gráfico ocupa 6 columnas y la tabla ocupa 6 columnas.
      (v) El elemento de información adicional ocupan 12 columnas.

   c) Compruebe la vista previa del resultado en el navegador.

   .. dropdown:: Ver el código 
    :color: primary

    .. code-block:: tsx
        :emphasize-lines: 8, 13, 16

         ...

         function App() {
            return (
               <Grid ... >

                  {/* Encabezado */}
                  <Grid size={{ xs: 12, md: 12 }}>Elemento: Encabezado</Grid>

                  ...

                  {/* Selector */}
                  <Grid size={{ xs: 12, md: 3  }}>Elemento: Selector</Grid>

                  {/* Indicadores */}
                  <Grid size={{ xs: 12, md: 9 }}>Elemento: Indicadores</Grid>

                  ...


               </Grid>
            );
         }

         export default App;

3. Con un cliente de IAG, genere el código para modificar los elementos del Grid:

   a) La gráfica y la tabla tienen la propiedad `sx <https://mui.com/material-ui/customization/how-to-customize/#the-sx-prop>`_ para ocultar los elementos en pantallas extra pequeñas y mostrar como bloque en pantallas medianas.
   b) Compruebe la vista previa del resultado en el navegador para diferentes tamaños.

   .. dropdown:: Ver el código 
    :color: primary

    .. code-block:: tsx
        :emphasize-lines: 11, 19

         ...

         function App() {
            return (
               <Grid ... >

                  ...

                  {/* Gráfico */}
                  <Grid ... 
                     sx={{ display: { xs: "none", md: "block"} }} >
                     Elemento: Gráfico
                  </Grid>

                  ...

                  {/* Tabla */}
                  <Grid ... 
                     sx={{ display: { xs: "none", md: "block" } }}>
                     Elemento: Tabla
                  </Grid>

                  ...


               </Grid>
            );
         }

         export default App;

4. Consulte su cliente de IAG para explicar la utilidad de los props en los componentes.

MUI: Componentes adicionales
----------------------------

1. Explore la documentación de MUI para estilizar los siguientes componentes en su archivo `App.tsx`:

   a) `Typography <https://mui.com/material-ui/react-typography/>`_ para mostrar títulos y descripciones de manera estilizada.
   b) `Alert <https://mui.com/material-ui/react-alert/>`_ para crear alertas visuales que resalten información importante, como advertencias o errores.
   c) Compruebe la vista previa del resultado en el navegador.

   .. dropdown:: Ver el código 
    :color: primary

    .. code-block:: tsx
        :emphasize-lines: 2, 10, 15

         import React from 'react';
         import { Grid, Typography } from '@mui/material';

         function App() {
            return (
               <Grid ... >

                  {/* Encabezado */}
                  <Grid ... >
                     <Typography variant="h1">Dashboard</Typography>
                  </Grid>

                  {/* Alertas */}
                  <Grid>
                     <Alert severity="warning">Alerta: lluvias durante la noche</Alert>
                  </Grid>

                  ...

               </Grid>
            );
         }

         export default App;

2. Con un cliente de IAG, explique cómo se utilizan los componentes de MUI para mejorar la usabilidad y la apariencia del dashboard.

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
