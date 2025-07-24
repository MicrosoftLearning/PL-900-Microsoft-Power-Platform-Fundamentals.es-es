---
lab:
  title: 'Laboratorio 3: Creación de un sitio de Power Pages'
  learning path: 'Learning Path: Demonstrate the capabilities of Microsoft Power Pages'
  module: 'Module 2: Create a Microsoft Power Pages site'
---
## Objetivo de aprendizaje

En este ejercicio, los alumnos usarán Copilot para crear un sitio de Power Pages. Una vez creado el sitio, usará Power Pages Design Studio para realizar tareas como agregar y modificar contenido, así como cambiar los temas.

### Escenario

A lo largo del año, Contoso Consulting hospeda muchos tipos diferentes de eventos. Van desde eventos en persona, hasta seminarios web, cursos dirigidos por instructores y mucho más. Buscan usar Microsoft Power Platform para administrar los diferentes eventos que han organizado. Quieren usar Power Pages para crear un sitio de administración de eventos que muestre los distintos eventos que hospedan.

Tras completar correctamente este ejercicio, hará lo siguiente:

-   Usar Copilot para crear un sitio web de Administración de eventos.
-   Agregar contenido nuevo al sitio.
-   Obtener una vista previa del nuevo sitio de Power Pages de diferentes tipos de dispositivos.

**Detalles del laboratorio:**

Antes de comenzar este ejercicio, es necesario que haya completado el siguiente laboratorio:

- **Laboratorio 2: Creación de un modelo de datos**

> **Importante:** Este laboratorio usa IA para crear los componentes. Dado que los resultados de la inteligencia artificial pueden variar, es importante tener en cuenta que los resultados pueden ser diferentes (pero similares) a lo que se define en el laboratorio. Los conceptos básicos descritos en el laboratorio serán los mismos independientemente de lo que se haya creado o de lo que se haya llamado. Si las tablas y columnas no coinciden exactamente, es posible que tenga que ajustarse a lo que se creó automáticamente.

El tiempo estimado para completar este ejercicio es de **30 a 45** minutos.

**Antes de empezar:** Si es la primera vez que accede al portal de Power Pages Maker, es posible que deba finalizar el proceso de configuración.  Si es así, siga las instrucciones siguientes.  De lo contrario, puede continuar con la **Tarea 1.**  

1.  Si es necesario, vaya a [Microsoft Power Pages](https://make.powerpages.microsoft.com).
1.  En la pantalla **Bienvenido a Power Pages**, seleccione el botón **Introducción**.

    ![Captura de pantalla de la pantalla de bienvenida de Power Pages.](media/get-started.png)

1. En la pantalla **Cuéntanos un poco sobre ti mismo**, selecciona el botón **Omitir**.

    ![Captura de pantalla de la pantalla de bienvenida de Power Pages.](media/about-you.png)

## Tarea 1: Use Copilot para crear un sitio de Power Pages.

1.  Si es necesario, vaya a <https://make.powerpages.microsoft.com>
1.  En la página principal de **Power Pages Design Studio**, escriba el texto siguiente: "*Cree un sitio para administrar eventos que hospeda nuestra organización".*
1.  Seleccione el botón **Enviar**.
1.  En la pantalla **Comprobar los detalles básicos del sitio**, configure de la siguiente manera:
    - **Asigne un nombre al sitio:**`Contoso Event Management`
    - **Cree una dirección web:** Aceptar la dirección predeterminada proporcionada
    - **Idioma del sitio:** Inglés

    ![Captura de pantalla que muestra los detalles básicos del sitio](media/9a5bc928349720c1da2f112bf1baf562.png)

1.  Seleccione el botón **Siguiente**.
1.  En la pantalla **Elegir un diseño**, revise el diseño sugerido proporcionado. Si desea sugerencias de diseño adicionales, seleccione **Probar de nuevo** para que **Copilot** sugiera otro diseño.
1.  Una vez que haya identificado la plantilla que desea usar, seleccione **Siguiente.**
1.  En la sección **Agregar páginas comunes**, seleccione las páginas siguientes:
    - Acerca de nosotros
    - Contáctenos
    - Preguntas más frecuentes
    - Seleccione las páginas adicionales, según sea necesario.
1.  Una vez que haya seleccionado las páginas, seleccione **Listo**.

    El nuevo sitio se creará en segundo plano, lo que puede tardar varios minutos.

1.  Una vez creado el sitio, ábralo (si aún no lo ha hecho).

    > **Nota:** A veces, cuando el sitio se carga por primera vez, es posible que vea un mensaje de un objeto Liquid no encontrado. Si esto sucede, actualice (F5) la ventana del explorador para volver a cargar el sitio. Debería aparecer el sitio.

## Tarea 2: Modificar el contenido del sitio

Ahora que se ha creado el sitio inicial, puede usar el estudio de diseño para modificarlo agregando páginas, texto, imágenes, formularios, etc.

1.  **Navegación principal**, seleccione **Inicio** para abrir la página **Principal**.
1.  Mantenga el puntero sobre el texto del **sitio de administración de eventos de Contoso** en el encabezado del sitio y seleccione **Editar encabezado de sitio**.
1.  Cambie el **título del sitio** a **Contoso Consulting**.
1.  Seleccione el botón **Cargar imagen**.
1.  En la pantalla **Agregar una imagen**, seleccione **Cargar imagen**, elija el **logotipo de Contoso** en los archivos de clase y elija **Abrir**.
1.  Con la imagen **logotipo de Contoso** seleccionada, seleccione **Aceptar**.
1.  Cuando haya terminado con los cambios, seleccione la **X** para salir de la pantalla **Editar encabezado del sitio**.
1.  Para cambiar la imagen de fondo del sitio, haga clic en cualquier lugar de la imagen de fondo.
1.  En el menú que aparece, elija **Editar fondo**.
1. Seleccione el botón **Cambiar imagen**.
1. Seleccione **Biblioteca multimedia** y elija **Cargar imagen**.
1. Seleccione la imagen **Site_Background** de los archivos de clase y elija **Abrir**.
1. Con el Site_Background seleccionado, elija **Aceptar**.
1. Seleccione el texto **Bienvenido a Eventos de Contoso** y cambie el texto a **Contoso Consulting**.
1. En la barra de herramientas que aparece, seleccione el botón **Diseño** *(Pincel)*.
1. Seleccione la flecha situada junto a la propiedad **Sombra de texto** y establezca el **H-Offset** en **2**.
1. Seleccione la **X** para cerrar la ventana **Diseño de texto**.
1. Seleccione el texto debajo de Contoso Consulting (*Podría decir algo similar a Su partner en administración de eventos)* y cámbielo a **Su partner para hoy y mañana.**

    Ahora que hemos realizado algunos cambios básicos en la página principal, vamos a actualizar el tema del sitio para que coincida mejor con la personalización de marca de Contoso.

1.  Con el panel de navegación de la izquierda, seleccione el botón **Estilo**.
1.  Seleccione el tema **Azul brillante**.
1.  En los **colores que identifican la marca**, seleccione el círculo de color **gris**.
1.  Cambie el color **hexadecimal****: 101E2B**
1.  Seleccione **Aceptar**.
1.  Seleccione el círculo **Blanco** y cambie el color al código **hexa** **e8e8e8**
1.  Seleccione **Aceptar**
1.  Seleccione el círculo **Negro** y cambie el color a **Blanco**. (ffffff)
1.  Seleccione **Aceptar**.
1. Realice los cambios adicionales de creación de temas que desee. Una vez que haya terminado con el cambio de creación de temas, seleccione el botón **Guardar**.

## Tarea 3: Conexión del sitio a los datos empresariales

Una de las principales ventajas de Power Pages es la capacidad de conectar Power Pages a los datos empresariales que se encuentra en Dataverse. Para poder incorporar los datos, es necesario crear algunos elementos que se usarán.

1.  Con el panel de navegación de la izquierda, seleccione el icono **Datos**.
1.  En el campo **Buscar**, escriba **Evento**.
1.  Seleccione la tabla **Evento**.

    En primer lugar, vamos a crear un formulario que se usará cuando deseemos agregar un nuevo evento.

1.  Seleccione la pestaña **Formularios** y elija **+ Nuevo formulario**.
1.  Establezca el **nombre del formulario** en `Create Event` y, a continuación, seleccione el botón **Crear**.
1.  No vamos a realizar modificaciones en el diseño. Seleccione el botón **Guardar y publicar**.
1.  Presione el **flecha Atrás** para volver al diseñador.

    A continuación, vamos a crear un formulario que se usará para ver y editar eventos existentes.

1.  Seleccione el botón **+ Nuevo formulario**.
1.  Asigne al formulario el nombre **Ver evento** y seleccione el botón **Crear**.
1.  En la **barra de comandos**, seleccione **Agregar componente** y elija **Subcuadrícula**.
1.  Configure la subcuadrícula de la manera siguiente:
    -   **Mostrar registros relacionados:** Sí
    -   **Tabla:** Sesiones de eventos
    -   **Valor predeterminado:** Sesiones activas
1.  Selecciona **Listo.**
1.  Seleccione el botón **Guardar y publicar**.
1.  Seleccione el botón **Atrás** para volver al **Design Studio**.

## Tarea 4: Crear formularios de página web necesarios

Ahora que hemos definido formularios para la tabla Evento, vamos a crear páginas que incluyan esos formularios para que los usuarios del sitio puedan trabajar con registros de eventos. Vamos a crear páginas para ver, crear y editar eventos.

1.  Con el panel de navegación de la izquierda, seleccione el icono **Páginas**.
1.  Seleccione el botón **+ Página**.
1.  En **Copilot**, escriba el texto siguiente: *`Add a new blank page.`* Seleccione el botón **Enviar**.
1.  Seleccione el botón **Mantenerla**.
1.  En la parte superior de la nueva página, seleccione el botón **Agregar una sección**.
1.  Seleccione **1 columna**.
1.  En **Elegir un componente para agregar a esta sección**, seleccione **Formulario**.
1.  Seleccione **+ Formulario nuevo**.
1.  En la pantalla **Agregar un formulario**, configure de la siguiente manera:
    - **Elegir una tabla:** Evento
    - **Seleccione un formulario:** Crear evento
    - **Asigne un nombre a la copia del formulario seleccionado:** Crear evento
1. Seleccione la pestaña **Datos** y compruebe que los **datos de este formulario** están establecidos en **Crear un nuevo registro**.
1. Seleccione la pestaña **Al enviar**. En el campo **Mostrar este mensaje**, escriba *`Your event has been successfully submitted.`*.
1. Seleccione el botón **Aceptar**.

    Vamos a quitar las secciones adicionales de la página, ya que no las necesitamos.

1. Seleccione la **Sección** debajo del **Formulario** que acaba de agregar. En la barra de herramientas que aparece, seleccione Más **(...)** y elija **Eliminar**.
1. Repita el paso anterior para quitar las dos secciones restantes de la página.

    Una vez completado, los únicos elementos que deben permanecer son el formulario que creó y el pie de página en la parte inferior de la página.

1. En **Navegación principal** de la izquierda, seleccione los puntos suspensivos junto a la **página nueva** que creó.
1. En el menú que aparece, seleccione **Configuración de página**.
1. Configure los valores de la página de la manera siguiente:
    - **Nombre**: Nuevo evento
    - **URL parcial:** New-Events
1. Seleccione el botón **Aceptar**.

    A continuación, agregaremos una página adicional que se puede usar para ver un evento individual.

1.  Asegúrese de que aún tiene **Páginas** seleccionadas y haga clic en el botón **+ Página**.
1.  En la pantalla **Describir una página para crearla**, escriba: *`Add a Blank Page named View Event.`* Seleccione el botón **Enviar**.
1.  Seleccione el botón **Mantenerla** para aceptar la nueva página.
1.  En la parte superior de la nueva página, seleccione el botón **Agregar una sección**.
1.  Seleccione **1 columna**.
1.  En **Elegir un componente para agregar a esta sección**, seleccione **Formulario**.
1.  Seleccione **+ Formulario nuevo**.
1.  En la pantalla **Agregar un formulario**, configure de la siguiente manera:
    - **Elegir una tabla:** Evento
    - **Seleccione un formulario:** Ver evento
    - **Asigne un nombre a la copia del formulario seleccionado:** Ver evento
1.  Seleccione la pestaña **Datos** y establezca el campo **Datos de este formulario** en **Es de solo lectura**.
1. Seleccione el botón **Aceptar**.

    Vamos a quitar las secciones adicionales de la página, ya que no las necesitamos.

1. Seleccione la **Sección** debajo del **Formulario** que acaba de agregar. En la barra de herramientas que aparece, seleccione Más **(...)** y elija **Eliminar**.
1. Repita el paso anterior para quitar la sección restante de la página.
1. En **Navegación principal** de la izquierda, seleccione los **puntos suspensivos** junto a la nueva página que creó.
1. En el menú que aparece, seleccione **Configuración de página**.
1. Configure los valores de la página de la manera siguiente:
    - **Nombre**: Ver evento
    - **URL parcial:** Ver eventos
1. Seleccione el botón **Aceptar**.

    Por último, vamos a crear un formulario más de página web que podamos usar para editar un evento.

1.  Asegúrese de que aún tiene **Páginas** seleccionadas y haga clic en el botón **+ Página**.
1.  En la pantalla **Describir una página para crearla**, escriba: *`Add a Blank Page named Edit Event.`* Seleccione el botón **Enviar**.
1.  Seleccione el botón **Mantenerla** para aceptar la nueva página.
1.  En la parte superior de la nueva página, seleccione el botón **Agregar una sección**.
1.  Seleccione **1 columna**.
1.  En **Elegir un componente para agregar a esta sección**, seleccione **Formulario**.
1.  Seleccione **+ Formulario nuevo**.
1.  En la pantalla **Agregar un formulario**, configure de la siguiente manera:
    - **Elegir una tabla:** Evento
    - **Seleccione un formulario:** Crear evento
    - **Asigne un nombre a la copia del formulario seleccionado:** Editar evento
1.  Seleccione la pestaña **Datos** y establezca los **datos de este formulario** en **Actualizaciones de un registro existente**.
1. Seleccione el botón **Aceptar**.

    Vamos a quitar las secciones adicionales de la página, ya que no las necesitamos.

1. Seleccione la **Sección** debajo del **Formulario** que acaba de agregar. En la barra de herramientas que aparece, seleccione Más **(...)** y elija **Eliminar**.
1. Repita el paso anterior para quitar las secciones restantes de la página.
1. Seleccione el botón **Aceptar**.

## Tarea 5: Crear una página que muestre una lista de eventos

Ahora que hemos definido los formularios necesarios que vamos a usar para administrar registros, vamos a crear una vista de página para mostrar esos registros.

1.  Seleccione el botón **+ Página**.

1.  En la pantalla **Describir una página para crearla**, escriba: *`Add a blank page called events.`* Seleccione el botón **Enviar**.
1.  Seleccione **Mantenerla** para aceptar la nueva página.
1.  En la parte superior de la nueva página, seleccione el botón **Agregar una sección**.
1.  Seleccione **1 columna**.
1.  En **Elegir un componente para agregar a esta sección**, seleccione el botón **Más** *(...)*. En el grupo de **datos conectados**, seleccione **Lista**.
1.  En la pantalla **Agregar una lista**, seleccione la pestaña **Configuración** y configure de la siguiente manera:
    - **Elegir una tabla:** Evento
    - **Seleccione las vistas de datos:** Eventos activos, eventos inactivos
    - **Nombre para mostrar:**`Events`
1.  Seleccione la pestaña **Acciones** y configure de la manera siguiente:
    - **Crear un nuevo registro:** Activado
        - **Tipo de destino:** Formulario
        - **Formulario:** Crear evento
        - **Etiqueta para mostrar:**`Create New Event`
    - **Ver detalles:** Activado
        - **Tipo de destino:** Formulario
        - **Formulario:** Ver evento
        - **Etiqueta para mostrar:**`See Event Details`
    - **Editar registro:** Activado
        - **Tipo de destino:** Formulario
        - **Formulario:** Editar evento
        - **Etiqueta para mostrar:**`Edit Event`
1. Selecciona **Listo.**

## Tarea 6: Actualizar permisos

Para asegurarse de que los usuarios solo ven los datos pertinentes, las organizaciones pueden especificar permisos de tabla. En esta tarea vamos a crear permisos muy básicos que proporcionan acceso a cualquier persona.

1.  En **Navegación principal**, seleccione la página **Eventos**.
1.  Seleccione la lista **Eventos** y haga clic en el botón **+ Nuevo permiso**.
1.  Configure el permiso de la manera siguiente:
    -   **Nombre**: Eventos
    -   **Tabla:** Evento
    -   **Tipo de acceso:** Acceso global
1.  Establezca el **permiso** en **lectura**.
1.  Seleccione **Agregar roles** y elija los roles de **Administradores**, **Usuarios anónimos** y **Usuarios autenticados**.
1.  Selecciona el botón **Guardar**.
1.  Una pantalla que indica **Que cualquier usuario puede ver los datos**, seleccione **Guardar**.

    Vamos a repetir ese proceso para las páginas del formulario de eventos. Comenzaremos con la página **Nuevo evento**

1.  En **Navegación principal**, seleccione la página **Nuevo evento**.
1.  Seleccione el botón **Actualizar permiso**.
1.  Configure el permiso de la manera siguiente:
    -   **Nombre**: Creación de eventos
    -   **Tabla:** Evento
    -   **Tipo de acceso:** Acceso global
1.  Establezca el **permiso** en **lectura** y **crear**.
1.  Seleccione **Agregar roles** y elija los roles de **Administradores**, **Usuarios anónimos** y **Usuarios autenticados**.
1.  Seleccione el botón **Guardar** y vuelva a seleccionar **Guardar** en la pantalla emergente.

    A continuación, configuraremos la pantalla **Editar evento**.

1.  En **Navegación principal**, seleccione la página **Editar evento**.
1.  Seleccione el botón **Actualizar permiso**.
1.  Configure el permiso de la manera siguiente:
    -   **Nombre**: Creación de eventos
    -   **Tabla:** Evento
    -   **Tipo de acceso:** Acceso global
1.  Establezca el **Permiso** en **Lectura** y **Actualizar**.
1.  Seleccione **Agregar roles** y elija los roles de **Administradores**, **Usuarios anónimos** y **Usuarios autenticados**.
1.  Seleccione el botón **Guardar** y vuelva a seleccionar **Guardar** en la pantalla emergente.

## Tarea 7: Actualización de la navegación del sitio

Ahora que tenemos nuestras páginas y elementos con el formato que queremos, vamos a ajustar la navegación del sitio en consecuencia.

1.  En **Navegación principal**, seleccione los **puntos suspensivos** situados junto a la página **Evento**.

1.  En el menú que aparece, seleccione **Subir**.
1.  Repita el paso hasta la página **Evento** que se encuentra debajo de la página **Ponerse en contacto con nosotros**.
1.  Asegúrese de que la página **Nuevo evento** se encuentra directamente en la página **Eventos**. *(Si no es así, mueva la página Nuevo evento hasta que sea).*
1.  En la página **Nuevo evento**, seleccione el botón **Puntos suspensivos**.
1.  En el menú que aparece, seleccione **Convertir esta subpágina**.
1.  Seleccione los puntos suspensivos junto a **Ver evento** y seleccione **Mover a otras páginas**.
1.  Seleccione los puntos suspensivos junto a **Editar evento** y seleccione **Mover a otras páginas**.
1.  En la barra **Comando**, seleccione el botón **Sincronizar**.

## Tarea 8: Vista previa y refinación del sitio

Una vez creado el sitio, querrá revisarlo para asegurarse de que satisface sus necesidades y requisitos empresariales para poder determinar los refinamientos necesarios. Los sitios se pueden obtener una vista previa en modo de escritorio y móvil

1.  En el estudio de diseño, seleccione el botón **Página principal**.
1.  Haga clic en **Vista previa** en la barra de comandos.
1.  Seleccione **Escritorio** para obtener una vista previa del sitio en un explorador.
1.  Al ver en **modo de escritorio**, revise los siguientes aspectos del sitio, como:
    -   Diseño y navegación.
    -   Elementos de personalización de marca, como colores, fuentes y logotipos.
1.  Una vez que haya terminado de probar el sitio, cierre la **pestaña Explorador** para volver al editor del sitio.

    A continuación, se previsualizará el sitio tal y como aparecería en los dispositivos móviles.

1.  Vuelva a seleccionar el botón **vista previa**.
1.  Escanee el **código QR** que se muestra con el dispositivo móvil.
1.  El sitio se abrirá en el dispositivo móvil *(nota: es posible que se le pida que inicie sesión, si es así, proporcione sus credenciales de inicio de sesión).*
1.  Como hizo mientras estaba en modo de escritorio, revise los siguientes aspectos de su sitio como:
    - Diseño y navegación.
    - Elementos de personalización de marca, como colores, fuentes y logotipos.
1. Una vez finalizada la prueba, cierre la pestaña del explorador para volver al sitio.
