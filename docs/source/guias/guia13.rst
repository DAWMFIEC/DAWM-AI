..
   Copyright (c) 2025 Allan Avendaño Sudario
   Licensed under Creative Commons Attribution-ShareAlike 4.0 International License
   SPDX-License-Identifier: CC-BY-SA-4.0

===============================================
Guía 13: React: Componentes, Interfaces y Props 
===============================================

.. topic:: Objetivo específico
    :class: objetivo

    Desarrollar componentes funcionales reutilizables en React que se comuniquen mediante props, tipadas con interfaces en TypeScript, asegurando una arquitectura modular y mantenible del dashboard.

Actividades previas
=====================

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

React y MUI: Componentes y Props
---------------------------------

1. Revise la documentación oficial, para:

   a) `Definir un componente <https://es.react.dev/learn/your-first-component>`_ para React.
   b) Componentes de UI en `Material UI components <https://mui.com/material-ui/all-components/>`_

Cabeceras, Tipografía y Alertas
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. Cree el archivo `src/components/HeaderUI.tsx`.
2. Utilice su cliente de IAG, para generar el siguiente código:

   a) Importe el componente `Typography <https://mui.com/material-ui/react-typography/>`_ desde la librería `@mui/material/Typography`
   b) Exporte por defecto el :term:`componente funcional` (función) **HeaderUI**.
   c) Dentro del componente `HeaderUI`, retorna un elemento `Typography` que muestre el texto "Dashboard", con las siguientes características:
      
      (i) Utilice el estilo tipográfico (variant) de un encabezado de nivel 2 (h2),
      (ii) Se renderiza (component) como un encabezado de nivel 1 (h1), y
      (iii) El estilo en línea (sx) para que el texto se muestre en negrita (fontWeight: 'bold').

   .. dropdown:: Ver el código 
        :color: primary

        .. code-block:: tsx
            :emphasize-lines: 1-12

            import Typography from '@mui/material/Typography';

            export default function HeaderUI() {
                return (
                    <Typography 
                        variant="h2" 
                        component="h1" 
                        sx={{fontWeight: 'bold'}}>
                        Dashboard
                    </Typography>
                )
            }

3. Modifique el archivo `src/App.tsx`, con: 

   a) Importe y use el componente `HeaderUI`.

   .. code-block:: tsx
       :emphasize-lines: 2,11

       ...
       import HeaderUI from './components/HeaderUI';

       function App() {
            
            return (
                <Grid ... >

                {/* Encabezado */}
                <Grid ... >
                    <HeaderUI/>
                </Grid>

                ...
            )
        }

4. Compruebe la vista previa del resultado en el navegador.
5. Con un cliente de IAG, explique la renderización de un componente dentro de otro componente, mediante el DOM Virtual de React.

Alertas
^^^^^^^

1. Cree el componente funcional `AlertUI`, con:
    
   a) Importe el componente `Alert <https://mui.com/material-ui/react-alert/>`_.
   b) Retorne el component `Alert`, con el tipo de alerta de éxito (severity="success") y el estilo visual del componente es contorneado (variant="outlined").

2. Modifique el archivo `src/App.tsx`, con:

   a) Importe y use el componente `AlertUI`
   b) Convierta el elemento `Grid` en un contenedor 

   .. code-block:: tsx
       :emphasize-lines: 2,11,12

       ...
       import AlertUI from './components/AlertUI';

       function App() {
            
            return (
                <Grid ... >

                {/* Alertas */}
                <Grid ...
                    container justifyContent="right" alignItems="center">
                    <AlertUI/>
                </Grid>

                ...
            )
        }


3. Compruebe la vista previa del resultado en el navegador.
4. Con un cliente de IAG, compare el uso del DOM versus el uso del DOM Virtual de React.

Selector e Indicador
^^^^^^^^^^^^^^^^^^^^

Configuración para el despliegue
--------------------------------

1. Desde la línea de comandos:

   a) Instale el paquete `gh-pages`

   .. code-block:: 

        npm install gh-pages --save-dev
   
2. Modifique el archivo `package.json`, con:

   a) La entrada **homepage**. Reemplace `<username>` por su nombre de usuario.
   b) Los comandos **predeploy** y **deploy** a la entrada **scripts**.

   .. code-block:: 
       :emphasize-lines: 3,7,8

       {
            ...
            "homepage": "https://<username>.github.io/dashboard",
            ...
            "scripts": { 
                ...
                "predeploy": "npm run build",
                "deploy": "gh-pages -d dist",
                ...
            }
       }

3. Modifique el archivo `vite.config.js`, con la ruta al repositorio remoto:

   .. code-block:: 
       :emphasize-lines: 2

       export default defineConfig({
            base: "/dashboard",
            plugins: ... ,
       })

4. Desde la línea de comandos, ejecute el comando de transpilación y despliegue del sitio web, con:

   .. code-block:: bash

      npm run deploy

   a) De ser necesario, elimine, corrija o comente las secciones de código identificadas por el transpilador.
   b) Vuelva a ejecutar el comando de transpilación y despliegue del sitio web.

5. Compruebe el resultado en el navegador, con la URL: `https://<username>.github.io/dashboard`

Versionamiento
--------------

1. Versione local y remotamente la(s) rama(s) de desarrollo en el repositorio *dashboard*.
2. Genere la(s) solicitud(es) de cambios (pull request) para la rama principal y apruebe los cambios.

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
    
    <blockquote class="twitter-tweet"><p lang="en" dir="ltr">I draw my mental schema of a <a href="https://twitter.com/reactjs?ref_src=twsrc%5Etfw">@reactjs</a> component. Here&#39;s what it looks like! Let&#39;s dig in!<br><br>🧵 Thread: Anatomy of a React Component (1/5) <a href="https://t.co/jeeKGXXu0G">pic.twitter.com/jeeKGXXu0G</a></p>&mdash; Baptiste Adrien (@baptadn) <a href="https://twitter.com/baptadn/status/1808149818763616748?ref_src=twsrc%5Etfw">July 2, 2024</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>