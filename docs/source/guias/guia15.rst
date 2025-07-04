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
3. Marque los indicadores que desea mostrar el dashboard en la sección de `Current Weather <https://open-meteo.com/en/docs#current_weather>`_ de la documentación, como temperatura (`Temperature (2 m)`), humedad relativa (`Relative Humidity (2 m)`), temperatura aparente (`Apparent Temperature`),  velocidad del viento (`Wind Speed (10 m)`), etc.
4. Seleccione la configuración de las unidades de medida de la API, como temperatura (`Celsius °C`), velocidad del viento (`km/h`), unidades de precipitación (`Millimeter`), etc.  
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

Interfaces y tipos de datos
---------------------------

1. Genere el tipo de datos TypeScript para el JSON de salida de la API de Open-Meteo, con:

   a) Utilice `Transform JSON to TypeScript <https://transform.tools/json-to-typescript>`_. 
   b) Coloque el JSON de salida de la API de Open-Meteo en el campo de entrada.
   c) Genere el código TypeScript de las interfaces y cópielo en su proyecto en el archivo `src/types/DashboardTypes.tsx`.
   d) Modifique el nombre de la interfaz `Root` por `OpenMeteoResponse`.

2. Utilice su cliente de IAG para justificar el uso de las interfaces y el tipo de datos que representan.

Indicador
---------

1. Cree el componente funcional `IndicatorUI` en el archivo `src/components/IndicatorUI.tsx`, con el siguiente código:
  
   a) Importe los componentes `Paper`, `Typography` y `Box` de la librería `@mui/material`.
    b) Exporte por defecto el :term:`componente funcional` (función) **IndicatorUI**.
    c

   .. code-block:: tsx
       :emphasize-lines: 1-20

       import Paper from '@mui/material/Paper';
       import Typography from '@mui/material/Typography';
       import Box from '@mui/material/Box';

       export default function IndicatorUI() {
        return (
            <Paper>
                <Box sx={{ padding: 2 }}>
                    <Typography variant="h6" component="div">
                    Indicador
                    </Typography>
                    <Typography variant="body2" color="text.secondary">
                    Aquí va la información del indicador.
                    </Typography>
                </Box>    
            </Paper>
        );
       }

2. Importe y use el componente `IndicatorUI` en el archivo `src/App.tsx`, en la sección marcada como Indicadores.

   .. code-block:: tsx
       :emphasize-lines: 2,13,15-17

       ...
       import IndicatorUI from './components/IndicatorUI';
       ...

       function App() {

            ...
            return (
                <Grid ... >

                    {/* Indicadores */}
                    <Grid size={{ xs: 12, md: 9 }} 
                          container spacing={5} justifyContent="space-around" alignItems="flex-start">

                        <IndicatorUI/>
                        <IndicatorUI/>
                        <IndicatorUI/>

                    </Grid>

                </Grid>
            )
       }


3. Compruebe la vista previa del resultado en el navegador.
4. Con un cliente de IAG, explique el uso del hook `useEffect` y la configuración del arreglo de dependencias.


React - Hook: useEffect
-----------------------

.. note::

    Considere la explicación del uso del hook `useEffect <https://es.react.dev/reference/react/useEffect>`_.

DataFetcher
^^^^^^^^^^^

1. Cree el componente funcional `DataFetcher` en el archivo `src/hooks/DataFetcher.tsx`, con:

   a) Importe los hooks `useState` y `useEffect` de React.
   b) Importe la interfaz `OpenMeteoResponse` desde el archivo `../types/DashboardTypes.tsx`.
   c) Dentro de `DataFetcher`:
      
      (i) Agregue el hook `useState` para almacenar los datos obtenidos de la API (`data`, valor predeterminado **null**), un estado de carga (`loading`, valor predeterminado **true**) y el mensaje de error (`error`, valor predeterminado **null**).
      (ii) Agregue el hook `useEffect` para que reaccione **únicamente** después del primer renderizado del DOM.
   
   d) Dentro del hook **useEffect**:
   
      (i) Defina la constante `url` con la URL de la API de Open-Meteo que obtuvo en las actividades previas.
      (ii) Defina la función asíncrona `fetchData` que realizará la petición asíncrona a la API de Open-Meteo. 
      (iii) Valide si la respuesta no es exitosa, lance un error. Caso contrario, si la respuesta es exitosa (código de estado HTTP 200), convierta la respuesta a JSON y almacene el resultado en el estado `data` con `setData`. 
      (iv) En caso de error, almacene el mensaje de error en el estado `error` con `setError`
      (v) Ya sea por éxito o por error, cambie el estado `loading` a `false` una vez que se haya completado la petición.
      (vi) Llame a la función `fetchData` dentro del hook `useEffect`.

   e) El componente `DataFetcher` retorna un objeto con los objetos `data`, `loading` y `error` como propiedades.

   .. dropdown:: Ver la solución 
        :color: success
        
        .. code-block:: tsx
            :emphasize-lines: 1-53

            import { useEffect, useState } from 'react';
            import { type OpenMeteoResponse } from '../types/DashboardTypes';

            interface DataFetcherOutput {
                data: OpenMeteoResponse | null;
                loading: boolean;
                error: string | null;
            }

            export default function DataFetcher() : DataFetcherOutput {

                const [data, setData] = useState<OpenMeteoResponse | null>(null);
                const [loading, setLoading] = useState(true);
                const [error, setError] = useState<string | null>(null);

                useEffect(() => {

                    // Reemplace con su URL de la API de Open-Meteo obtenida en actividades previas
                    const url = `https://api.open-meteo.com/v1/forecast?latitude=-2.1962&longitude=-79.8862&hourly=temperature_2m&current=temperature_2m,wind_speed_10m,relative_humidity_2m,apparent_temperature&timezone=America%2FChicago`

                    const fetchData = async () => {

                        try {
                            
                            const response = await fetch(url);

                            if (!response.ok) {
                                throw new Error(`Error HTTP: ${response.status} - ${response.statusText}`);
                            }

                            const result: OpenMeteoResponse = await response.json();
                            setData(result);

                        } catch (err: any) {

                            if (err instanceof Error) {
                                setError(err.message);
                            } else {
                                setError("Ocurrió un error desconocido al obtener los datos.");
                            }

                        } finally {
                            setLoading(false);
                        }
                    };

                    fetchData();

                }, []); // El array vacío asegura que el efecto se ejecute solo una vez después del primer renderizado

                return { data, loading, error };

            }
            
2. Importe y almacene su salida en una constante `dataFetcherOutput` en el archivo `src/App.tsx`.

   .. code-block:: tsx
       :emphasize-lines: 2,8

       ...
       import DataFetcher from './hooks/DataFetcher';
       ...

       function App() {

            ...
            const dataFetcherOutput = DataFetcher();
            ...
       
            return ( ... )
       }

3. Compruebe la vista previa del resultado en el navegador.
4. Con un cliente de IAG, explique el uso del hook `useEffect` y la configuración del arreglo de dependencias.

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