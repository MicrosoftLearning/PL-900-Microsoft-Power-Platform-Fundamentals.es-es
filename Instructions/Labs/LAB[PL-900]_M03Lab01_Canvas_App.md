---
lab:
  title: "Laboratorio\_2: Cómo crear una aplicación de lienzo"
  module: 'Module 3: Get started with Power Apps'
---

# Laboratorio 2: Cómo crear una aplicación de lienzo

**Inquilinos de WWL: términos de uso** Si, como parte de la impartición de un curso dirigido por un instructor, se le proporciona un inquilino, tenga en cuenta que el inquilino está disponible para apoyar los laboratorios prácticos en este tipo de cursos. Los inquilinos no deben compartirse ni usarse para otros fines que no sean los de los laboratorios prácticos. El inquilino empleado en este curso es uno de prueba y no se puede usar ni tener acceso a él después de que la clase haya terminado y tampoco se puede ampliar su uso. Los inquilinos no se deben convertir a suscripciones de pago. Los inquilinos obtenidos como parte de este curso siguen siendo propiedad de Microsoft Corporation y nos reservamos el derecho de acceso y recuperación en cualquier momento. 

## Escenario

Bellows College es una organización educativa con varios campus y programas. Muchos de los instructores y administradores de Bellow Colleges necesitan asistir a eventos y comprar artículos. Históricamente, el seguimiento de estos gastos ha sido un problema. 

La administración del campus desea modernizar su sistema de informes de gastos y así proporcionar a los empleados un método digital de notificar los gastos. 

A lo largo de este curso, creará aplicaciones y realizará la automatización para que los empleados de Bellows College puedan administrar los gastos. 


## Pasos de alto nivel del laboratorio

Seguiremos el siguiente esquema para diseñar la aplicación de lienzo:

- Creación de una aplicación de lienzo de informes de gastos 

- Configuración de cómo se muestran los informes de gastos en la pantalla de exploración

- Realizar algunos cambios básicos en la aplicación

- Probar la funcionalidad de la aplicación

## Requisitos previos

- Finalización del **Módulo 1 Laboratorio 0: Validación del entorno de laboratorio**

## Ejercicio 1: Creación de una aplicación de lienzo de informes de gastos

### Objetivo: En este ejercicio, creará una aplicación de lienzo mediante la conexión a una tabla de informes de gastos.

### Tarea n.° 1: Creación de la aplicación de informes de gastos

1. Vaya a https://make.powerapps.com.

1. Es posible que deba volver a autenticarse: seleccione **Iniciar sesión** y siga las instrucciones si es necesario.

1. Seleccione el entorno **Dev One** en la parte superior derecha si aún no está seleccionado.

1. Seleccione **+Crear** en el panel de navegación izquierdo de la pantalla. En la sección **Iniciar desde**, seleccione **Dataverse**.

1. Seleccione la conexión de Dataverse.

    >**Nota**: Si no existe ninguna conexión de Dataverse:

    >   - Selección de **+Nueva conexión**

    >   - Busque **Microsoft Dataverse**

    >   - Seleccione **Crear**

    >   - **Inicie sesión** y seleccione **Permitir acceso**.

1. Busque y seleccione la tabla **Informes de gastos**.

1. Seleccione el botón **Conectar** en la esquina inferior derecha.

1. Una vez creada la aplicación, en la pantalla de bienvenida a Power Apps Studio, active la casilla **No volver a mostrar** y, luego, seleccione **Omitir**.

1. En el diseñador de aplicaciones, seleccione el botón **Vista previa de la aplicación** (icono de reproducción) en la barra de comandos. (También puede obtener una vista previa de la aplicación pulsando F5). Eche un vistazo y compruebe el aspecto de su aplicación.

1. Cierre la vista previa de la aplicación seleccionando la **X** de la esquina superior derecha de la pantalla.

Enhorabuena, ha creado correctamente una instancia de Power App a partir de una tabla de Dataverse. El siguiente paso del proceso es adaptar la aplicación para que coincida con la personalización de marca de la organización. La siguiente serie de pasos le guiará por el proceso de personalizar un poco más la aplicación.

### Tarea n.º 2: Modificar y aplicar un tema a la nueva aplicación

En esta tarea, personalizará el texto del encabezado en cada una de las tres pantallas de la aplicación (Examinar, Detalles y Editar) y cambiará el tema de la aplicación.

1. Está en la pantalla Examinar. Seleccione la etiqueta **Informes de gastos** en la pantalla.

1. En el lado derecho de la pantalla, en la pestaña ”Propiedades”, actualice la propiedad de control **Texto** a ”Mis informes de gastos”.

1. En **Propiedades**, cambie el **tamaño de la fuente** a **24**.

1. Seleccione el fondo en blanco de la pantalla para ver el texto actualizado en la pantalla de exploración.

1. Mediante la **vista de árbol** del panel de navegación izquierdo, seleccione **DetailScreen1**.

1. Seleccione la etiqueta **Informes de gastos** en la pantalla.

1. En el lado derecho de la pantalla, en la pestaña **Propiedades**, actualice la propiedad de control **Texto** a "Detalles del informe".

1. Haga clic en el fondo en blanco de la pantalla para ver el texto actualizado en la pantalla de detalles.

1. Mediante la **vista de árbol** del panel de navegación izquierdo, seleccione **EditScreen1** (es posible que tenga que desplazarse hacia abajo para verlo en esa vista).

1. Seleccione la etiqueta **Informes de gastos** en la pantalla.

1. En el lado derecho de la pantalla, en la pestaña **Propiedades**, reemplace el texto de la propiedad de control **Texto** por ”Editar detalles”.

1. Haga clic en el fondo en blanco de la pantalla para ver el texto actualizado en la pantalla de edición.

1. Mediante la **vista de árbol** del panel de navegación izquierdo, seleccione **BrowseScreen1**.

1. En la barra de herramientas de comandos, seleccione el botón **Tema** y, en la lista que aparece, elija el color **Rojo** para el tema.

### Tarea n.° 3: Prueba de la aplicación de informes de gastos

En esta tarea, probará la nueva aplicación.

1. Con la aplicación abierta en el Diseñador de aplicaciones, seleccione **Configuración** (es posible que tenga que seleccionar el botón ... para que aparezca el icono de configuración), en la sección **General**, actualice el nombre de la aplicación a Aplicación de informe de gastos y seleccione la **X** para cerrar la pantalla de configuración. A continuación, seleccione **Guardar**.

1. En el panel de navegación izquierdo, seleccione **BrowseScreen1**.

1. En el diseñador de aplicaciones, seleccione el botón **Vista previa de la aplicación** (icono de reproducción) en la barra de comandos. (También puede obtener una vista previa de la aplicación presionando F5).

1. Cuando se abra la aplicación, en el campo **Buscar artículos**, escriba el texto ”Viaje” (observe cómo se filtran los artículos de la galería en función de lo que se escribe en el campo de búsqueda).

1. Cuando se muestre el registro **Viaje a la conferencia de Power Platform**, seleccione una fila a la que desplazarse y abra la pantalla ”Detalles” de ese gasto.
 
    >**Nota**: Si se muestra más de un registro ”Viaje a la conferencia de Power Platform”, seleccione uno cualquiera.

1. Para editar el registro, seleccione el **icono de lápiz** en la esquina superior derecha de la aplicación.

1. Aquí puede editar el **nombre del informe** y seleccionar el icono de **marca de verificación** de la parte superior derecha para guardar el cambio.

1. En la parte superior derecha de la pantalla, seleccione el icono de la **X** para cerrar el modo de vista previa y volver al editor de aplicaciones de lienzo.

Felicidades. Ha creado y configurado su primera aplicación de lienzo.

 
