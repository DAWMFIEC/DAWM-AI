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

1. Cree el archivo `src/components/Header.tsx`.
2. Utilice su cliente de IAG, para generar el siguiente código:

   a) Importe el componente `Typography <https://mui.com/joy-ui/react-typography/>`_ desde la librería `@mui/material/Typography`
   b) Exporte por defecto el :term:`componente funcional` (función) **Header**.
   c) Dentro del componente `Header`, retorna un elemento `Typography` que muestre el texto "Dashboard", con las siguientes características:
      
      (i) Utilice el estilo tipográfico (variant) de un encabezado de nivel 2 (h2),
      (ii) Se renderiza (component) como un encabezado de nivel 1 (h1), y
      (iii) El estilo en línea (sx) para que el texto se muestre en negrita (fontWeight: 'bold').

   .. dropdown:: Ver el código 
        :color: primary

        .. code-block:: tsx
            :emphasize-lines: 1-9

            import Typography from '@mui/material/Typography';

            export default function Header() {
                return (
                    <Typography 
                        variant="h2" 
                        component="h1" 
                        sx={{fontWeight: 'bold'}}>
                        Dashboard
                    </Typography>
                )
            }

3. Modifique el archivo `src/App.tsx` para importar y usar el componente `Header`:

   .. code-block:: tsx
       :emphasize-lines: 2,10

       ...
       import Header from './components/Header';

       function App() {
            
            return (
                <Grid ... >

                {/* Encabezado */}
                <Grid .. >
                    <Header/>
                </Grid>

                ...
            )
        }

4. Compruebe la vista previa del resultado en el navegador.
5. Con un cliente de IAG, explique la renderización del componente `src/components/Header.tsx` dentro del componente `src/App.tsx`.

Alertas
^^^^^^^

Selector e Indicador
^^^^^^^^^^^^^^^^^^^^

Tablas y Gráficos
^^^^^^^^^^^^^^^^^

Configuración para el despliegue
--------------------------------

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