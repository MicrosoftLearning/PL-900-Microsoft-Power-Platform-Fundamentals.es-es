---
lab:
  title: 'Laboratorio 3: Cómo crear una aplicación basada en modelo'
  module: 'Module 3: Get started with Power Apps'
---

# Laboratorio 3: Cómo crear una aplicación basada en modelo

**Inquilinos de WWL: términos de uso** Si, como parte de la impartición de un curso dirigido por un instructor, se le proporciona un inquilino, tenga en cuenta que el inquilino está disponible para apoyar los laboratorios prácticos en este tipo de cursos. Los inquilinos no deben compartirse ni usarse para otros fines que no sean los de los laboratorios prácticos. El inquilino usado en este curso es un inquilino de prueba y no se puede usar ni tener acceso a él después de que la clase haya terminado y no sea apto para la extensión. Los inquilinos no se deben convertir a suscripciones de pago. Los inquilinos obtenidos como parte de este curso siguen siendo propiedad de Microsoft Corporation y nos reservamos el derecho de acceso y recuperación en cualquier momento. 

## Escenario

Bellows College es una institución educativa que tiene un campus con varios edificios. Los visitantes del campus están actualmente registrados en revistas en papel. La información no se recaba de manera uniforme y no hay forma de recopilar y analizar los datos sobre las visitas de todo el campus.

La administración del campus querría modernizar el sistema de registro de visitantes de los edificios cuyo acceso esté controlado por el personal de seguridad y en los que los anfitriones deban anotar con antelación las visitas y dejar constancia de ellas.

A lo largo de este curso, creará aplicaciones y realizará la automatización para permitir que el personal de administración y seguridad de Bellows College administre y controle el acceso a los edificios en el campus.

En este laboratorio, creará una aplicación impulsada por el modelo de Power Apps para permitir que el personal del campus administrativo administre los registros de visitas en todo el campus.

Pasos de alto nivel del laboratorio

Como parte de la creación de la aplicación basada en modelo, completará lo siguiente:

- Cree una nueva aplicación basada en modelo llamada Administración del campus

- Editar la navegación de la aplicación para hacer referencia a las tablas requeridas

- Personalizar los formularios y las vistas de las tablas necesarias para la aplicación

Trabajaremos con los siguientes componentes:

- **Vistas**: Las vistas permiten al usuario mostrar los datos existentes en la tabla del formulario.

- **Formularios**: Aquí es donde el usuario crea/actualiza nuevas filas en las tablas.

Ambos se integrarán a la aplicación basada en modelo para una mejor experiencia de usuario.

Prerrequisitos

- Finalización del **Módulo 0 Laboratorio 0: Validación del entorno de laboratorio**

- Finalización del **Módulo 2 Laboratorio 1: Modelado de datos**

Cuestiones que tener en cuenta antes de comenzar

- ¿Qué cambios debemos hacer para mejorar la experiencia del usuario?

- ¿Qué deberíamos incluir en una aplicación basada en modelo elaborada según el modelo de datos que hemos construido?

- ¿Qué personalizaciones se pueden hacer en el mapa del sitio de una aplicación basada en modelos?

Ejercicio 1: Personalizar las vistas y los formularios

**Objetivo:** En este ejercicio, personalizará las vistas y formularios de las tablas creadas de manera personalizada que se utilizarán en la aplicación basada en modelo.

Tarea n.° 1: Editar el formulario de visita

1.  Haga clic en <https://make.powerapps.com> si no ha iniciado sesión aún.

2.  Seleccione su ambiente **Práctica [mis iniciales]** en la parte superior derecha, si aún no está seleccionado.

3.  Con el panel de navegación izquierdo, seleccione **Tablas** y abra la tabla **Visit**.

    Si no ve la tabla Visita, asegúrese de que se encuentra en el entorno correcto (paso 2).

4.  En la sección **Experiencias de datos**, seleccione **Formularios** y abra el formulario **Información** con el tipo de formulario **Principal**. (**Importante:** Asegúrese de seleccionar el formulario que tiene el tipo de formato **Principal**). 

    **IMPORTANTE:** Dado que, de forma predeterminada, todos los formularios se denominan Información, asegúrese de comprobar que el formulario que selecciona sea del tipo de formulario **Principal** y no cualquier otro. El formulario tiene dos campos de forma predeterminada: Nombre y Propietario.

5.  En el lado derecho de la pantalla, en el panel **Propiedades**, seleccione el campo **Display Name** y cámbielo a `Main Information`.

6.  Seleccione **Columnas de tabla** en el panel de navegación izquierdo y agregue los campos siguientes debajo del campo **Owner**. Para ello, arrastre las columnas hasta el formulario o simplemente haga clic en los nombres de las columnas:

    1. **Visitante**

    2. **Inicio programado**

    3. **Final programado**

    4. **Inicio real**

    5. **Finalización real**

7.  Arrastre la columna **Código** y suéltela en el encabezado del formulario.

    El encabezado está en la parte superior derecha del formulario. Es posible que deba contraer el panel Propiedades en el lado derecho de la pantalla para ver el campo en el formulario.

8.  Con el campo **Código** seleccionado, marque la casilla de verificación **Solo lectura** en el panel Propiedades del lado derecho de la pantalla.

9.  Seleccione el campo **Propietario**. En el panel Propiedades, cambie la **Etiqueta** a `Host`.

10. Seleccione el botón **Guardar y publicar** en la parte superior derecha y espere a que se complete la operación.

11. Si la vista de edición se abre en una nueva pestaña o ventana del explorador, ciérrela. De lo contrario, haga clic en **🡠 Atrás** en la parte superior izquierda de la pantalla. Ahora debería estar de nuevo en los formularios de la tabla **Visit**.

12. Con las rutas de navegación de la parte superior izquierda (**Tablas** > **Visit** > **Forms**), seleccione **Visit** para volver a la pantalla de propiedades de la tabla **Visit**. 


Tarea n.°2: Editar la vista de visitas activas

En esta tarea, modificaremos la vista predeterminada de Visitas activas y crearemos una nueva vista para las visitas de hoy.

1.  En la sección **Experiencias de datos**, seleccione **Vistas** y abra la vista **Visitas activas**.

2.  Agregue los siguientes campos a la vista haciendo clic o arrastrando y soltando los campos:

    1. **Código**

    2. **Visitante**

    3. **Inicio programado**

    4. **Final programado**

3.  Seleccione el menú desplegable de la columna **Se creó el** y elija **Quitar**. El campo **Se creó el** se quitará ahora de la vista.

4.  Cambie el tamaño de los anchos de columna individuales para que los datos quepan.

5.  En **Ordenar por ...** , seleccione la X para quitar la información de **Nombre** y, en su lugar, elija **Inicio programado**.

6.  Seleccione **Inicio programado** para cambiar el criterio de ordenación a **Más reciente a anterior**.

7.  Seleccione el botón **Guardar y publicar** en la parte superior derecha y espere a que se complete la operación.


Tarea n.° 3: Crear una vista nueva para las visitas de hoy

Ahora clonaremos la vista para crear una nueva vista para las visitas de hoy.

IMPORTANTE: Asegúrese de que no cierra la vista Visitas activas, ya que la aprovecharemos para crear la nueva vista de visitas de hoy.

1.  Seleccione **Guardar como**.

2.  Cambie el valor de **Nombre** por `Today’s Visits` y seleccione **Guardar**.

3.  Seleccione **Editar campos** en el panel de propiedades

4.  Seleccione **+Agregar** y elija **Agregar fila**.

5.  Seleccione **Inicio programado** como campo y, luego, cambie **Igual a** por **Hoy** como condición en el menú desplegable.

6.  Seleccione **...** **Más comandos** en la fila **Estado** y seleccione **Eliminar** para eliminar esa condición de filtro.

7.  Seleccione **Aceptar** para guardar la condición. La vista ahora está filtrada para mostrar solo los registros donde la fecha de **Inicio programada** es hoy.

8.  Agregue los campos **Comienzo real** y **Final real** a la vista.

    **Nota:** Como ya no filtramos el estado de la vista, obtendremos todas las visitas de hoy, incluidas las completadas. Estos campos ayudarán a diferenciar visitas completadas y visitas en curso.

9.  Seleccione el botón **Guardar y publicar** en la parte superior derecha y espere a que se complete la operación.


Ejercicio 2: Crear una aplicación basada en modelo

**Objetivo:** En este ejercicio, creará una aplicación basada en modelo, personalizará el mapa del sitio y probará la aplicación.

Por motivos de simplicidad y tiempo, no abordaremos algunas de las columnas de visitas de este laboratorio.

Tarea 1: Creación de la aplicación

1.  Inicie sesión en <https://make.powerapps.com>, si aún no lo ha hecho.

2.  Seleccione su ambiente **Práctica [mis iniciales]** en la parte superior derecha, si aún no está seleccionado.

3.  Seleccione **+Crear** en el panel de navegación izquierdo.

4.  Cree una aplicación basada en modelos:

    1. Seleccione **Aplicación en blanco** en la sección **Iniciar a partir de** de la pantalla **Crear la aplicación**.

    2. En **Aplicación vacía basada en Dataverse**, seleccione **Crear**.

    3. Escriba `Bellows Campus Management` en **Nombre** y seleccione **Crear**.

5.  Una vez que se cargue la nueva aplicación controlada por modelos, seleccione el botón **+ Agregar página**.

6.  En la pantalla **Agregar página**, elija **Tabla de Dataverse** y, luego, seleccione el botón **Siguiente**.

7.  Seleccione las tablas siguientes:

    1. Visite

    2. Contacto

8.  Después de seleccionar las dos tablas, elija **Agregar**.

9.  Con los iconos de navegación del panel izquierdo de la pantalla, seleccione **Navegación**.

10. En el panel de navegación, seleccione **Nuevo grupo** a continuación, donde dice Navegación. Es posible que tenga que expandir el menú de la izquierda.

11. En el lado derecho de la pantalla, en la sección **Opciones de visualización**, cambie la propiedad **Título** a `Security`.

12. Seleccione **Guardar** y espere hasta que se guarden los cambios.

13. Una vez completada la operación **Guardar**, seleccione el botón **Publicar** para publicar los cambios.


Tarea 2: Prueba de la aplicación

Inicio de la aplicación

1. Seleccione el botón **Reproducir**. La aplicación basada en modelo se cargará en una nueva pestaña.

Creación de un contacto

2.  La aplicación debería abrirse en la vista **Mis contactos activos**. Si no es así, seleccione **Contactos** en el panel de navegación izquierdo.

3.  Seleccione **+Nuevo** en la barra de comandos.

4.  En **Nombre**, escriba `John` y, en **Apellido**, escriba `Doe`.

5.  Proporcione su correo electrónico personal como **Correo electrónico**. Esta información se usará en un laboratorio futuro, donde recibirá un correo electrónico.

6.  Seleccione **Guardar y cerrar**.

7.  Ahora, debería ver el contacto creado en la vista **Mis contactos activos**.

Creación de una nueva visita

8.  Seleccione **Visitas** en el panel de navegación izquierdo (también conocido como mapa del sitio).

9.  Seleccione **+ Nuevo**.

10. Rellene los campos como sigue:

    1. **Nombre**: `New test visit`

    2. **Visitante**: seleccione **John Doe**.

    3. **Inicio programado**: seleccione la fecha de mañana y las 02:00 como hora de inicio.

    4. **Final programado**: seleccione la fecha de mañana y las 03:30 como hora de finalización.

11. Seleccione **Guardar y cerrar**. A continuación, se creará la visita, que verá en la vista **Visitas activas**.

12. Cambie la vista a **Visitas de hoy** con la lista desplegable situada junto a **Visitas activas**. Ya no debería ver la nueva visita en la vista, ya que está programada para mañana.

13. Puede agregar más registros de prueba.

Su aplicación basada en modelo en ejecución debería tener este aspecto:

![](media/3-model-driven-app.png)

Felicidades. Ha creado y configurado la primera aplicación basada en modelo.

## Desafíos

- Seleccione vistas y formularios específicos para Contactos.

