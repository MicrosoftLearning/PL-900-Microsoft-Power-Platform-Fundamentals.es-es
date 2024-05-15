---
lab:
  title: 'Laboratorio 3: Cómo crear una aplicación basada en modelo'
  module: 'Module 3: Get started with Power Apps'
---

# Laboratorio 3: Cómo crear una aplicación basada en modelo

**Inquilinos de WWL: términos de uso** Si, como parte de la impartición de un curso dirigido por un instructor, se le proporciona un inquilino, tenga en cuenta que el inquilino está disponible para apoyar los laboratorios prácticos en este tipo de cursos. Los inquilinos no deben compartirse ni usarse para otros fines que no sean los de los laboratorios prácticos. El inquilino empleado en este curso es uno de prueba y no se puede usar ni tener acceso a él después de que la clase haya terminado y tampoco se puede ampliar su uso. Los inquilinos no se deben convertir a suscripciones de pago. Los inquilinos obtenidos como parte de este curso siguen siendo propiedad de Microsoft Corporation y nos reservamos el derecho de acceso y recuperación en cualquier momento. 

## Escenario

Bellows College es una organización educativa con varios campus y programas. Muchos de los instructores y administradores de Bellow Colleges necesitan asistir a eventos y comprar artículos. Históricamente, el seguimiento de estos gastos ha sido un problema.

La administración del campus desea modernizar su sistema de informes de gastos y así proporcionar a los empleados un método digital de notificar los gastos.

A lo largo de este curso, creará aplicaciones y realizará la automatización para que los empleados de Bellows College puedan administrar los gastos.

## Pasos de alto nivel del laboratorio

Como parte de la creación de la aplicación basada en modelo, completará lo siguiente:

- Cree una nueva aplicación basada en modelo llamada "Gestión de gastos de fuelles".

- Editar la navegación de la aplicación para hacer referencia a las tablas requeridas

- Personalizar los formularios y las vistas de las tablas necesarias para la aplicación

Trabajaremos con los siguientes componentes:

- **Vistas**: Las vistas permiten al usuario mostrar los datos existentes en la tabla del formulario.

- **Formularios**: Aquí es donde el usuario crea/actualiza nuevas filas en las tablas.

Ambos se integrarán a la aplicación basada en modelo para una mejor experiencia de usuario.

### Requisitos previos

- Finalización del **Módulo 1 Laboratorio 0: Validación del entorno de laboratorio**

**Cuestiones que tener en cuenta antes de comenzar**

- ¿Qué cambios debemos hacer para mejorar la experiencia del usuario?

- ¿Qué deberíamos incluir en una aplicación basada en modelo elaborada según el modelo de datos que hemos construido?

- ¿Qué personalizaciones se pueden hacer en el mapa del sitio de una aplicación basada en modelos?

## Ejercicio 1: Personalizar las vistas y los formularios

**Objetivo:** En este ejercicio, personalizará las vistas y formularios de las tablas creadas de manera personalizada que se utilizarán en la aplicación basada en modelo.

### Tarea n.° 1: Editar formulario de informe de gastos

1. Si aún no lo está, inicie sesión en https://make.powerapps.com

1. Seleccione el entorno **Dev One** en la parte superior derecha si aún no lo ha hecho.

1. Con el panel de navegación izquierdo, seleccione **Tablas** y abra la tabla **Informe de gastos**.

Si no ve la tabla Informe de gastos, asegúrese de que se encuentra en el entorno correcto (paso 2).

1. En la sección **Experiencias de datos**, seleccione **Formularios** y abra el formulario **Información** con el tipo de formulario **Principal**. (**Importante:** Asegúrese de seleccionar el formulario que tiene el tipo de formato **Principal**).

    >**IMPORTANTE:** Dado que, de forma predeterminada, todos los formularios se denominan Información, asegúrese de comprobar que el formulario que selecciona sea del tipo de formulario **Principal** y no cualquier otro. El formulario tiene dos campos de forma predeterminada: Nombre y Propietario.

1. En el lado derecho de la pantalla, en el panel **Propiedades**, seleccione el campo ** Nombre para mostrar** y cámbielo a Información del informe.

1. Seleccione **Columnas de tabla** en el panel de navegación izquierdo y agregue los campos siguientes debajo del campo **Owner**. Para ello, arrastre las columnas hasta el formulario o simplemente haga clic en los nombres de las columnas:

    - **Descripción**

    - **Propósito del informe**

    - **Fecha de vencimiento del informe**

    - **Importe total del informe**

1. Arrastre la columna **Razón para el estado** y suéltela en el encabezado del formulario.

El encabezado está en la parte superior derecha del formulario. Es posible que deba contraer el panel Propiedades en el lado derecho de la pantalla para ver el campo en el formulario.

1. Seleccione el campo **Propietario**. En el panel Propiedades, cambie **Etiqueta** a Solicitante.

1. Seleccione el botón **Guardar y publicar** en la parte superior derecha y espere a que se complete la operación.

1. Si la vista de edición se abre en una nueva pestaña o ventana del explorador, ciérrela. De lo contrario, haga clic en **🡠 Atrás** en la parte superior izquierda de la pantalla. Ahora debería estar de nuevo en los formularios de la tabla **Informe de gastos**.

1. Con las rutas de navegación de la parte superior izquierda (**Tablas** > **Informe de gastos** > **Formularios**). Seleccione **Informe de gastos** para volver a la pantalla de propiedades de la tabla **Informe de gastos**.

## Tarea n.°2: Editar la vista Informes de gastos activos

En esta tarea, modificaremos la vista predeterminada de Informes de gastos activos y crearemos una nueva vista para los informes de gastos que vencen hoy.

1. En la sección **Experiencias de datos**, seleccione **Vistas** y abra la vista **Informes de gastos activos**.

1. Agregue los siguientes campos a la vista haciendo clic o arrastrando y soltando los campos:

    - **Propósito del informe**

    - **Fecha de vencimiento del informe**

    - **Total del informe**

1. Seleccione el menú desplegable de la columna **Se creó el** y elija **Quitar**. El campo **Se creó el** se quitará ahora de la vista.

1. Cambie el tamaño de los anchos de columna individuales para que los datos quepan.

1. En **Ordenar por ...** , Seleccione la X para quitar **Nombre** y, en su lugar, elija **Cantidad total del informe**.

1. Seleccione **Cantidad total del informe** para cambiar el criterio de ordenación a **De mayor a menor**.

1. Seleccione el botón **Guardar y publicar** en la parte superior derecha y espere a que se complete la operación.

### Tarea n.° 3: Creación de una nueva vista para Informes que venza hoy

Ahora clonaremos la vista para crear otra para las visitas de hoy.

>    **IMPORTANTE:** Asegúrese de que no cierra la vista Informes de gastos activos, ya que la aprovecharemos para crear la nueva vista de informes que vence hoy.

1. Seleccione **Guardar como**.

1. Cambie el **Nombre** a Informes de gastos que vencen hoy y seleccione **Guardar**.

1. Seleccione **Editar campos** en el panel de propiedades

1. Seleccione **+Agregar** y elija **Agregar fila**.

1. Seleccione **Fecha de vencimiento del informe** como campo y, luego, cambie **Igual a** por **Hoy** como condición en el menú desplegable.

1. Seleccione **...** **Más comandos** en la fila **Estado** y seleccione **Eliminar** para eliminar esa condición de filtro.

1. Seleccione **Aceptar** para guardar la condición. La vista ahora está filtrada para mostrar solo los registros donde la **fecha de vencimiento del informe** sea hoy.

1. Agregue el campo **Importe del reembolso** a la vista.

1. Seleccione el botón **Guardar y publicar** en la parte superior derecha y espere a que se complete la operación.

## Ejercicio 2: Crear una aplicación basada en modelo

**Objetivo:** En este ejercicio, creará una aplicación basada en modelo, personalizará el mapa del sitio y probará la aplicación.

Por motivos de simplicidad y tiempo, no abordaremos algunas de las columnas de Informe de gastos de este laboratorio.

### Tarea 1: Creación de la aplicación

1. Si aún no lo está, inicie sesión en https://make.powerapps.com

1. Seleccione el entorno **Dev One** en la parte superior derecha si aún no está seleccionado.

1. Seleccione **+Crear** en el panel de navegación izquierdo.

1. Cree una aplicación basada en modelos:

    - Seleccione **Aplicación en blanco** en la sección **Iniciar a partir de** de la pantalla **Crear la aplicación**.

    - En **Aplicación vacía basada en Dataverse**, seleccione **Crear**.

    - Escriba "Administración de gastos de los empleados" en **Nombre** y seleccione **Crear**.

1. Una vez que se cargue la nueva aplicación controlada por modelos, seleccione el botón **+ Agregar página**.

1. En la pantalla **Agregar página**, elija **Tabla de Dataverse** y, luego, seleccione el botón **Siguiente**.

1. Seleccione las tablas siguientes:

    - Informe de gastos

    - Contacto

1. Después de seleccionar las dos tablas, elija **Agregar**.

1. Con los iconos de navegación del panel izquierdo de la pantalla, seleccione **Navegación**.

1. En el panel de navegación, seleccione **Nuevo grupo** a continuación, donde dice Navegación. Es posible que tenga que expandir el menú de la izquierda.

1. En el lado derecho de la pantalla, en la sección **Opciones de presentación**, cambie la propiedad **Título** a Informes.

1. Seleccione **Guardar** y espere hasta que se guarden los cambios.

1. Una vez completada la operación **Guardar**, seleccione el botón **Publicar** para publicar los cambios. Espere a que se complete la publicación.

## Tarea 2: Prueba de la aplicación

**Inicio de la aplicación**

1. Seleccione el botón **Reproducir**. La aplicación basada en modelo se cargará en una nueva pestaña.

**Creación de un contacto**

1. La aplicación debería abrirse en la vista **Mis contactos activos**. Si no es así, seleccione **Contactos** en el panel de navegación izquierdo.

1. Seleccione **+Nuevo** en la barra de comandos.

1. Escriba "John" en **Nombre** y "Doe" en **Apellido**

1. Proporcione su correo electrónico personal como **Correo electrónico**. Esta información se usará en un laboratorio futuro, donde recibirá un correo electrónico.

1. Seleccione **Guardar y cerrar**.

1. Ahora, debería ver el contacto creado en la vista **Mis contactos activos**.

**Creación de un informe de gastos**

1. Seleccione **Informes de gastos** en el panel de navegación izquierdo (también conocido como mapa del sitio).

1. Seleccione **+ Nuevo**.

1. Especifique los campos de la siguiente manera:

    - **Nombre de informe**: nuevo informe de prueba

    - En **Propósito del informe**, seleccione **Conferencia**.

    - **Fecha de vencimiento del informe**: Seleccione la fecha de hoy.

1. Seleccione **Guardar y cerrar**. Esto creará el nuevo informe de prueba y debería poder verlo en la vista **Informes de gastos activos**.

1. Cambie la vista a **Informes de gastos que vencen hoy** con la lista desplegable situada junto a **Informes de gastos activos**. 

1. Puede agregar más registros de prueba.

Su aplicación basada en modelo en ejecución debería tener este aspecto:

![Captura de pantalla de la aplicación controlada por modelos recién creada.](media/lab-3-create-a-model-app-01.png)

Felicidades. Ha creado y configurado la primera aplicación basada en modelo.
