..
   Copyright (c) 2025 Allan Avendaño Sudario
   Licensed under Creative Commons Attribution-ShareAlike 4.0 International License
   SPDX-License-Identifier: CC-BY-SA-4.0

==========================================
Guía 10: Firebase: Realtime Database y SDK
==========================================

.. topic:: Objetivo específico
    :class: objetivo

    Integrar Firebase Realtime Database utilizando su SDK para almacenar y recuperar datos en tiempo real desde una landing page desarrollada con JavaScript y TailwindCSS, permitiendo una experiencia de usuario dinámica e interactiva.

Actividades previas
=====================

Firebase
--------

Proyecto
^^^^^^^^

1. Acceda a `Firebase <https://firebase.google.com/>`_ con su cuenta personal de Google.
2. Cree un proyecto en `Firebase Console <https://console.firebase.google.com/>`_. No es necesario configurar Google Analytics para este proyecto.
3. Utilice un cliente de IAG para explicar los servicios, y sus casos prácticos de uso, que ofrece Firebase.

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

Firebase
--------

App - web
^^^^^^^^^

1. En su proyecto de Firebase:
   
   a) Junto a **Project Overview**, despliegue el menú de configuración del proyecto y escoja **Project settings**.
   b) En la pestaña **General**, desplácese hasta la sección **Your apps**.
   c) Haga clic en el ícono de elemento HTML para crear una **web app**.

2. En **Add Firebase to your web app** 
    
   a) Ingrese un nombre para su aplicación web y haga clic en **Register app**.
   b) En **Add Firebase SDK***, seleccione la opción **Use a <script> tag** y copie la configuración para establecer la conexión con Firebase.

   
   .. code-block:: html

       const firebaseConfig = {
         apiKey: "API_KEY",
         authDomain: "PROJECT_ID.firebaseapp.com",
         projectId: "PROJECT_ID",
         // The value of `storageBucket` depends on when you provisioned your default bucket (learn more)
         storageBucket: "PROJECT_ID.firebasestorage.app",
         messagingSenderId: "SENDER_ID",
         appId: "APP_ID",
       };

3. Con un cliente de IAG, explique cómo se utiliza el objeto de configuración de Firebase en la inicialización de la aplicación web y en la conexión con los servicios con Vanilla Javascript.

.env
^^^^

1. En la raíz de su proyecto, cree un archivo llamado **.env**.
2. En este archivo, agregue las siguiente variables de entorno y pegue los valores correspondientes de la configuración de Firebase que copió anteriormente:
    
   .. code-block:: env

       VITE_FIREBASE_API_KEY=API_KEY
       VITE_FIREBASE_AUTH_DOMAIN=PROJECT_ID.firebaseapp.com
       VITE_FIREBASE_PROJECT_ID=PROJECT_ID
       VITE_FIREBASE_STORAGE_BUCKET=PROJECT_ID.firebasestorage.app
       VITE_FIREBASE_MESSAGING_SENDER_ID=SENDER_ID
       VITE_FIREBASE_APP_ID=APP_ID

3. Asegúrese de que el archivo **.env** esté incluido en su archivo **.gitignore** para evitar subirlo al repositorio.
4. Con un cliente de IAG, explique la importancia de las variables de entorno para mantener la seguridad de las credenciales de Firebase y cómo se utilizan en el código en Vite.

Realtime Database
^^^^^^^^^^^^^^^^^

1. Dentro de su proyecto en Firebase, acceda a la sección **Build*** y en la opción **Realtime Database**.
2. Cree una base de datos en tiempo real seleccionando **Create Database**.
   
   a) Seleccione la ubicación de la base de datos, preferiblemente la más cercana a su usuario final.
   b) En **Security rules**, elija **Start in Test Mode** para permitir el acceso sin restricciones durante el desarrollo inicial. Esto es útil para pruebas, pero asegúrese de cambiar a un modo más seguro antes de desplegar su aplicación en producción.

3. Utilice una cliente de IAG para explicar cómo se estructura la base de datos en tiempo real de Firebase y cómo se pueden realizar operaciones CRUD (Crear, Leer, Actualizar, Eliminar) en ella con el Firebase SDK.

Javascript: procesamiento de datos
----------------------------------


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

    * ¿Qué desafíos conceptuales encontraste al interpretar el código generado por IA para integrar Firebase en tu landing page?

    * ¿Qué modificaciones realizaste al código sugerido por la IA para adaptarlo a los requerimientos específicos de tu landing page?

    * ¿Cómo aseguras que el uso de IA en la implementación de Firebase no sustituya tu comprensión del flujo de datos ni tu responsabilidad en el manejo seguro de la información del usuario?

Actividades autónomas
=====================

Recursos extras
------------------------------

En redes:

.. raw:: html

    <blockquote class="twitter-tweet"><p lang="es" dir="ltr">🔥 <a href="https://twitter.com/hashtag/Firebase?src=hash&amp;ref_src=twsrc%5Etfw">#Firebase</a> está preparando un nuevo SDK para JavaScript que hará la librería más ligera y traerá cambios importantes que nos harán refactorizar nuestras apps si queremos aprovechas sus ventajas.<br><br>🧵 Te las cuento en el hilo 👇 <a href="https://t.co/oJHLopDw1J">pic.twitter.com/oJHLopDw1J</a></p>&mdash; Carlos Azaustre 💻 (@carlosazaustre) <a href="https://twitter.com/carlosazaustre/status/1421036271242252288?ref_src=twsrc%5Etfw">July 30, 2021</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>