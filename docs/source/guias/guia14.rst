..
   Copyright (c) 2025 Allan Avendaño Sudario
   Licensed under Creative Commons Attribution-ShareAlike 4.0 International License
   SPDX-License-Identifier: CC-BY-SA-4.0

===========================================
Guía 14: React - Eventos y Hooks (useState)
===========================================

.. topic:: Objetivo específico
    :class: objetivo

    Gestionar la interactividad del dashboard mediante eventos del usuario y el uso de hooks como useState y useRef, permitiendo actualizar el estado de la interfaz de forma reactiva y eficiente. 

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

React: Eventos y Hooks
----------------------

.. note::

    Considere la explicación del uso de hooks en `React Hooks - Tutorial <https://adictosaltrabajo.com/2020/02/06/react-hooks-tutorial/>`_ y del manejo de eventos en `Tutorial React: Eventos en React <https://certidevs.com/tutorial-react-eventos-y-manejo-de-eventos>`_.

Selector
^^^^^^^^

1. Utilice la documentación del componente `Select <https://mui.com/material-ui/react-select/>`_ para crear el componente funcional `SelectorUI`, con el siguiente código:

   .. code-block:: tsx
       :emphasize-lines: 1-25

       import FormControl from '@mui/material/FormControl';
       import InputLabel from '@mui/material/InputLabel';
       import Select from '@mui/material/Select';
       import MenuItem from '@mui/material/MenuItem';

       export default function SelectorUI() {
    
       return (
          <FormControl fullWidth>
             <InputLabel id="city-select-label">Ciudad</InputLabel>
             <Select
                labelId="city-select-label"
                id="city-simple-select"
                label="Ciudad">
                <MenuItem disabled><em>Seleccione una ciudad</em></MenuItem>
                <MenuItem value={"guayaquil"}>Guayaquil</MenuItem>
                <MenuItem value={"quito"}>Quito</MenuItem>
                <MenuItem value={"manta"}>Manta</MenuItem>
                <MenuItem value={"cuenca"}>Cuenca</MenuItem>
             </Select>

          </FormControl>
          )
       }

2. Compruebe la vista previa del resultado en el navegador.
3. Con un cliente de IAG, compare el uso del DOM versus el uso del DOM Virtual de React.

Evento: onChange
^^^^^^^^^^^^^^^^



Hooks: useState
^^^^^^^^^^^^^^^^


Versionamiento
--------------

1. Versione local y remotamente la(s) rama(s) de desarrollo en el repositorio *dashboard*.
2. Genere la(s) solicitud(es) de cambios (pull request) para la rama principal y apruebe los cambios.

Despliegue
----------

1. Desde la línea de comandos, ejecute el comando de transpilación y despliegue del sitio web, con:

   .. code-block:: bash

      npm run deploy

   a) De ser necesario, elimine, corrija o comente las secciones de código identificadas por el transpilador.
   b) Vuelva a ejecutar el comando de transpilación y despliegue del sitio web.

2. Compruebe el resultado en el navegador, con la URL: `https://<username>.github.io/dashboard`

Conclusiones
============

.. topic:: Preguntas de cierre

    * ¿Cómo te ayudó la inteligencia artificial generativa a entender la relación entre los eventos onChange y el hook useState al capturar y actualizar datos en tiempo real dentro de un componente?

    * ¿Qué ajustes tuviste que realizar al código propuesto por la IA para lograr que el evento onChange actualizara correctamente el estado mediante useState en tu dashboard?

    * ¿Cómo puedes demostrar que comprendes y eres responsable del código que usas, incluso si fue generado por IA, particularmente cuando se trata de funcionalidades interactivas como la gestión de estado?

Actividades autónomas
=====================

Recursos extras
------------------------------

En redes:
