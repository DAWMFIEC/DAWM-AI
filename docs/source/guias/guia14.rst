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

1. Cree el componente funcional `SelectorUI`.
2. Utilice su cliente de IAG, para modificar el componente `AlertUI` con el siguiente código:

   a) Importe los componentes `FormControl`, `InputLabel`, `Select` y `MenuItem` desde la librería `@mui/material`.
   b) Exporte el componente funcional predeterminado `SelectorUI`
   c) Retorne el código:

   .. code-block:: tsx
       :emphasize-lines: 1-11

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
                <MenuItem value=""><em>Seleccione una ciudad</em></MenuItem>
                <MenuItem value={"guayaquil"}>Guayaquil</MenuItem>
                <MenuItem value={"quito"}>Quito</MenuItem>
                <MenuItem value={"manta"}>Manta</MenuItem>
             </Select>

          </FormControl>
          )
       }

5. Con un cliente de IAG, compare el uso del DOM versus el uso del DOM Virtual de React.

Evento: onChange
^^^^^^^^^^^^^^^^

Hooks: useState
^^^^^^^^^^^^^^^^

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
