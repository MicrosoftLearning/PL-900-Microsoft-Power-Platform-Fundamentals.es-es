---
lab:
  title: 'Laboratorio 3: Cómo crear una aplicación basada en modelo'
  module: 'Module 3: Describe how to build applications with Microsoft Power Apps'
---

# Laboratorio 3: Cómo crear una aplicación basada en modelo

**Inquilinos de WWL: términos de uso** Si, como parte de la impartición de un curso dirigido por un instructor, se te proporciona un inquilino, ten en cuenta que el inquilino está disponible para apoyar los laboratorios prácticos en este tipo de cursos. Los inquilinos no deben compartirse ni usarse para otros fines que no sean los de los laboratorios prácticos. El inquilino empleado en este curso es uno de prueba y no se puede usar ni tener acceso a él después de que la clase haya terminado y tampoco se puede ampliar su uso. Los inquilinos no se deben convertir a suscripciones de pago. Los inquilinos obtenidos como parte de este curso siguen siendo propiedad de Microsoft Corporation y nos reservamos el derecho de acceso y recuperación en cualquier momento. 

## Escenario

Bellows College es una organización educativa con varios campus y programas. Muchos de los instructores y administradores de Bellow Colleges necesitan asistir a eventos y comprar artículos. Históricamente, el seguimiento de estos gastos ha sido un problema.

La administración del campus desea modernizar su sistema de informes de gastos y así proporcionar a los empleados un método digital de notificar los gastos.

A lo largo de este curso, crearás aplicaciones y realizarás la automatización para que los empleados de Bellows College puedan administrar los gastos.

## Pasos de alto nivel del laboratorio

Como parte de la creación de la aplicación basada en modelo, completarás lo siguiente:

- Crear una nueva aplicación basada en modelo llamada "Gestión de gastos de empleados".

- Editar la navegación de la aplicación para hacer referencia a las tablas requeridas

- Personalizar los formularios y las vistas de las tablas necesarias para la aplicación

Trabajaremos con los siguientes componentes:

- **Vistas**: las vistas permiten al usuario mostrar los datos existentes en la tabla del formulario.

- **Formularios**: aquí es donde el usuario crea/actualiza nuevas filas en las tablas.

Ambos se integrarán a la aplicación basada en modelo para una mejor experiencia de usuario.

### Requisitos previos

- Finalización del **Módulo 1 Laboratorio 0: Validación del entorno de laboratorio**

**Cuestiones que tener en cuenta antes de comenzar**

- ¿Qué cambios debemos hacer para mejorar la experiencia del usuario?

- ¿Qué deberíamos incluir en una aplicación basada en modelo elaborada según el modelo de datos que hemos construido?

- ¿Qué personalizaciones se pueden hacer en el mapa del sitio de una aplicación basada en modelos?

## Ejercicio 1: Personalización de las vistas y los formularios

**Objetivo:** en este ejercicio, personalizarás las vistas y formularios de las tablas creadas de manera personalizada que se utilizarán en la aplicación basada en modelo.

### Tarea 1: Edición del formulario de informe de gastos

1. Si aún no lo estás, inicia sesión en https://make.powerapps.com

1. Selecciona el entorno **Dev One** en la parte superior derecha si aún no lo has hecho.

1. Con el panel de navegación izquierdo, selecciona **Tablas** y abre la tabla **Informe de gastos**.

    >Si no ves la tabla Informe de gastos, asegúrate de que te encuentra en el entorno correcto (paso 2).

1. En la sección **Experiencias de datos**, selecciona **Formularios** y abre el formulario **Información** con el tipo de formulario **Principal**. (**Importante:** asegúrate de seleccionar el formulario que tiene el tipo de formato **Principal**).

    >**IMPORTANTE:** dado que, de forma predeterminada, todos los formularios se denominan Información, asegúrate de comprobar que el formulario que seleccionas sea del tipo de formulario **Principal** y no cualquier otro. El formulario tiene dos campos de forma predeterminada: Nombre y Propietario.

1. En el lado derecho de la pantalla, en el panel **Propiedades**, selecciona el campo **Nombre para mostrar** y cámbialo a `Report Information`.

1. Selecciona **Columnas de tabla** en el panel de navegación izquierdo y agrega los campos siguientes debajo del campo **Owner**. Para ello, arrastra las columnas hasta el formulario o simplemente haz clic en los nombres de las columnas:

    - **Descripción**

    - **Propósito del informe**

    - **Fecha de vencimiento del informe**

    - **Importe total del informe**

1. Arrastra la columna **Razón para el estado** y suéltala en el encabezado del formulario.

    >El encabezado está en la parte superior derecha del formulario. Es posible que debas contraer el panel Propiedades en el lado derecho de la pantalla para ver el campo en el formulario.

1. Selecciona el campo **Propietario**. En el panel Propiedades, cambia la **etiqueta** por `Requestor`.

1. Selecciona el botón **Guardar y publicar** en la parte superior derecha y espera a que se complete la operación.

1. Si la vista de edición se abre en una nueva pestaña o ventana del explorador, ciérrala. De lo contrario, haz clic en **🡠 Atrás** en la parte superior izquierda de la pantalla. Ahora deberías estar de nuevo en los formularios de la tabla **Informe de gastos**.

1. Con las rutas de navegación de la parte superior izquierda (**Tablas** > **Informe de gastos** > **Formularios**). Selecciona **Informe de gastos** para volver a la pantalla de propiedades de la tabla **Informe de gastos**.

## Tarea 2: Edición de la vista Informes de gastos activos

En esta tarea, modificaremos la vista predeterminada de Informes de gastos activos y crearemos una nueva vista para los informes de gastos que vencen hoy.

1. En la sección **Experiencias de datos**, selecciona **Vistas** y abre la vista **Informes de gastos activos**.

1. Agrega los siguientes campos a la vista haciendo clic o arrastrando y soltando los campos:

    - **Propósito del informe**

    - **Fecha de vencimiento del informe**

    - **Importe total del informe**

1. Selecciona el menú desplegable de la columna **Se creó el** y elige **Quitar**. El campo **Se creó el** se quitará ahora de la vista.

1. Cambia el tamaño de los anchos de columna individuales para que los datos quepan.

1. En **Ordenar por ...** , Selecciona la X para quitar **Nombre de informe** y, en su lugar, elige **Importe total del informe**.

1. Selecciona **Importe total del informe** para cambiar el criterio de ordenación a **De mayor a menor**.

1. Selecciona el botón **Guardar y publicar** en la parte superior derecha y espera a que se complete la operación.

### Tarea 3: Creación de una nueva vista para Informes que venza hoy

Ahora clonaremos la vista para crear otra para las visitas de hoy.

>    **IMPORTANTE:** asegúrate de que no cierras la vista Informes de gastos activos, ya que la aprovecharemos para crear la nueva vista de informes que vencen hoy.

1. Selecciona **Guardar como**.

1. Cambie el valor de **Nombre** por `Expense Reports Due Today` y seleccione **Guardar**.

1. Seleccione **Editar campos** en el panel de propiedades

1. Selecciona **+Agregar** y elige **Agregar fila**.

1. Selecciona **Fecha de vencimiento del informe** como campo y, luego, cambia **Igual a** por **Hoy** como condición en el menú desplegable.

1. Selecciona **...** **Más comandos** en la fila **Estado** y selecciona **Eliminar** para eliminar esa condición de filtro.

1. Selecciona **Aceptar** para guardar la condición. La vista ahora está filtrada para mostrar solo los registros donde la **fecha de vencimiento del informe** sea hoy.

1. Agrega el campo **Importe del reembolso** a la vista.

1. Selecciona el botón **Guardar y publicar** en la parte superior derecha y espera a que se complete la operación.

## Ejercicio 2: Creación de una aplicación basada en modelo

**Objetivo:** en este ejercicio, crearás una aplicación basada en modelo, personalizarás el mapa del sitio y probarás la aplicación.

Por motivos de simplicidad y tiempo, no abordaremos algunas de las columnas de Informe de gastos de este laboratorio.

### Tarea 1: Creación de la aplicación

1. Si aún no lo estás, inicia sesión en https://make.powerapps.com

1. Selecciona el entorno **Dev One** en la parte superior derecha si aún no está seleccionado.

1. Seleccione **Soluciones** en el panel de navegación izquierdo.

1. Abre la solución **Gestión de gastos**.

1. Selecciona **+ Nuevo** y, después, seleccione **APP** y selecciona **Aplicación basada en modelo**.

1. Escribe `Employee Expense Management` en **Nombre** y selecciona **Crear**.

1. Una vez que se cargue la nueva aplicación basada en modelo, selecciona el botón **+ Agregar página**.

1. En la pantalla **Agregar página**, elige **Tabla de Dataverse**.

1. Selecciona las tablas siguientes:

    - Informe de gastos

    - Contacto

1. Después de seleccionar las dos tablas, elige **Agregar**.

1. Con los iconos de navegación del panel izquierdo de la pantalla, selecciona **Navegación**.

1. En el panel de navegación, selecciona **Nuevo grupo** a continuación, donde dice Navegación. Es posible que tengas que expandir el menú de la izquierda.

1. En el lado derecho de la pantalla, en la sección **Opciones de visualización**, cambia la propiedad **Título** a `Reports`.

1. Selecciona **Guardar** y espera hasta que se guarden los cambios.

1. Una vez completada la operación **Guardar**, selecciona el botón **Publicar** para publicar los cambios. Espera a que se complete la publicación.

## Tarea 2: Prueba de la aplicación

**Inicio de la aplicación**

1. Selecciona el botón **Reproducir**. La aplicación basada en modelo se cargará en una nueva pestaña.

**Creación de un contacto**

1. La aplicación debería abrirse en la vista **Mis contactos activos**. Si no es así, selecciona **Contactos** en el panel de navegación izquierdo.

1. Selecciona **+Nuevo** en la barra de comandos.

1. En **Nombre**, escribe `John` y, en **Apellido**, escribe `Doe`.

1. Proporciona tu correo electrónico personal como **Correo electrónico**. Esta información se usará en un laboratorio futuro, donde recibirá un correo electrónico.

1. Selecciona **Guardar &amp; cerrar**.

1. Ahora, deberías ver el contacto creado en la vista **Mis contactos activos**.

**Creación de un informe de gastos**

1. Selecciona **Informes de gastos** en el panel de navegación izquierdo (también conocido como mapa del sitio).

1. Selecciona **+ Nuevo**.

1. Especifica los campos de la siguiente manera:

    - **Nombre del informe**: `New Test Report`

    - En **Propósito del informe**, selecciona **Conferencia**.

    - **Fecha de vencimiento del informe**: selecciona la fecha de hoy.

1. Selecciona **Guardar &amp; cerrar**. Esto creará el nuevo informe de prueba y deberías poder verlo en la vista **Informes de gastos activos**.

1. Cambia la vista a **Informes de gastos que vencen hoy** con la lista desplegable situada junto a **Informes de gastos activos**. 

1. Puedes agregar más registros de prueba.

Tu aplicación basada en modelo en ejecución debería tener este aspecto:

![Captura de pantalla de la aplicación controlada por modelos recién creada.](media/lab-3-create-a-model-app-01.png)

Felicidades. Has creado y configurado la primera aplicación basada en modelo.
