---
lab:
  title: 'Laboratorio 3: Crear una aplicación de lienzo'
  learning path: 'Learning Path: Demonstrate the capabilities of Microsoft Power Apps'
  module: 'Module 2: Build a canvas app'
---
## Objetivo de aprendizaje

En este ejercicio, usará Copilot para crear una aplicación de lienzo que los empleados puedan usar para solicitar y administrar las solicitudes de restauración de tiempo de espera y equipos. Una vez creada la aplicación, usará Copilot y el diseñador de Power Apps para modificar la aplicación.

Al completar este laboratorio, harás lo siguiente:

- Use Copilot para ayudarle a crear un modelo de datos para admitir la aplicación.
- Modifique una aplicación de lienzo.

### Escenario

Contoso Consulting es una organización de servicios profesionales especializada en servicios de consultoría de TI e IA. Buscan crear una aplicación de tiempo libre que los empleados pueden usar para solicitar el tiempo de espera.

### Detalles del laboratorio

Antes de comenzar este ejercicio, es necesario que haya completado el siguiente laboratorio:

- **Laboratorio 2: Creación de un modelo de datos**

> **Importante** Este laboratorio usa IA para construir los componentes. Dado que los resultados de la inteligencia artificial pueden variar, es importante tener en cuenta que los resultados pueden ser diferentes (pero similares) a lo que se define en el laboratorio. Los conceptos básicos descritos en el laboratorio serán los mismos independientemente de lo que se haya creado o de lo que se haya llamado. Si las tablas y columnas no coinciden exactamente, es posible que tenga que ajustarse a lo que se creó automáticamente.

El tiempo estimado para completar este ejercicio es de **60 a 75** minutos.

## Tarea 1: Inicie sesión en Power Apps y explore la interfaz

1.  Abra un explorador web y vaya al portal de [Power Apps](https://make.powerapps.com/) Maker Portal.
1.  Con la navegación del lado izquierdo, seleccione **Crear**.
1.  En **Crear las aplicaciones**, elija **Empezar con Copilot**.
1.  En la pantalla **Describir las tablas que desea que construya Copilot**, escriba: *` I want to store time off requests sent by employees. The table should identify the start and end times of the request.`*
1.  Seleccione el botón **Opciones de tabla**. En el menú que aparece, seleccione **Una Tabla**.

    ![Recorte de pantalla de introducción a Copilot](media/60a2ec72988f48c91df7c370532cb331.png)

1.  Selecciona el botón **Generar**.

    Copilot debería haber creado una tabla **Solicitud de tiempo libre**. A continuación, agregaremos más columnas a la tabla.

    **Nota**: Si es necesario, agregue el nombre de la tabla al mensaje.

1.  En el panel **Copilot**, escriba: *`Add a choice column called Time Off Reason.`*
1.  En el panel **Copilot**, agregue individualmente los siguientes avisos.
    - *`Add a choice column named Time off Type.`*
    - *`Add a Date column called Submission Date.`*
    - *`Add a choice column to the Time Off request table called Approval Status.`*
    - *`Add a multi-line text column called Request Details.`*

    La tabla de tiempo libre debe ser similar a la imagen:

    ![Recorte de pantalla de la tabla de Solicitud de tiempo libre completada ](media/2ac256daafe1853e5367852467690c76.png)

    A continuación, vamos a agregar la tabla de usuarios al modelo de datos para poder asociar solicitudes de tiempo de espera a usuarios específicos.

1.  En la barra **Comando**, seleccione **+ Tabla existente**.
1.  Cambie de **Recomendado** a **Todas las Tablas**.
1.  En el campo **Buscar**, introduzca **Usuario**.
1.  Seleccione la tabla **Usuario** y haga clic en el botón **Agregar seleccionados**.
1.  En la barra Comandos, seleccione **Crear relaciones**.
1.  Configure la relación como sigue:

    -   **Uno:** Usuario
    -   **Varios:** Solicitud de indisponibilidad
    -   **Nombre para mostrar**: `Requesting Employee`
  
1.  Selecciona **Listo.**

    El modelo de datos completado debe ser similar a la imagen:

    ![Recorte de pantalla del modelo de datos completado ](media/daa74d51e2ceada8e1e8b004cae9942a.png)

1.  Selecciona el botón **Guardar y abrir aplicación**.

> [!NOTE]
> La nueva aplicación puede tardar varios minutos en crearse.

## Tarea 2: Personalización de la nueva aplicación

Ahora que se ha creado la nueva aplicación, vamos a realizar algunas modificaciones para adaptarla mejor a nuestras necesidades. Comenzaremos realizando algunas modificaciones en la pantalla de bienvenida.

1.  Con la nueva aplicación abierta, seleccione el marcador de posición **Imagen** situado encima del texto **Solicitudes de tiempo libre**.
1.  En el menú que aparece, seleccione **Editar** \> **Cargar**.
1.  Seleccione la imagen **Tiempo libre** de la carpeta de archivos de clase y, a continuación, seleccione **Abrir**.
1.  A continuación, seleccione el marcador de posición **Imagen** situado encima de **Usuarios**.
1.  En el menú que aparece, seleccione **Editar** \> **Cargar**.
1.  Seleccione la imagen **Empleado** de la carpeta de archivos de clase y, a continuación, seleccione **Abrir**.

    A continuación, vamos a ajustar el tamaño de las imágenes para que sean más fáciles de leer para los usuarios. Además, vamos a ajustar el texto que se muestra para cada elemento.

1.  En la **Barra de comandos**, seleccione el botón **Propiedades**. (*Situado justo a la derecha del botón Edición.*)
1.  Seleccione la imagen **Time libre** que ha añadido anteriormente.
1.  En el panel **Propiedades**, configure la imagen como se indica a continuación:
    
    -   **Posición de la imagen:** Llenar
    -   **Ancho:** 300
    -   **Alto:** 300
      
1.  Repita el paso anterior para ajustar **Altura** y **Anchura** de la imagen **Empleado** a **300** x **300**.
1.  Seleccione el texto que aparece debajo de **Solicitudes de tiempo libre**.
1.  En el panel **Propiedades**, seleccione el campo **Texto** y cambie el texto a: *`Create, View, and Manage you time off requests.`*
1.  Seleccione el texto **Pantalla de bienvenida** en el **Título**.
1.  En el panel **Propiedades** de la derecha, seleccione el campo **Logo**.
1.  En el menú que aparece, seleccione **Cargar**.
1. Seleccione el **Logotipo de Contoso** de sus archivos de clase y seleccione **Abrir**.
1. En el panel **Propiedades** del grupo **Estilo** y tema, seleccione el icono **Relleno** de color.
1. Seleccione la pestaña **Personalizado**.
1. Cambia el color **Hex** a: `101E2B`
1. Asegúrese de que aún tiene seleccionado el **Encabezado**, y cambie el **Título** a `Contoso Employee Hub`.
1. En la barra **Comando**, seleccione el botón **Guardar** para guardar la aplicación.
1. En la pantalla **Guardar**, establezca el **Nombre** en `Contoso Employee Hub` y seleccione **Guardar.**

    La aplicación será similar a la imagen.

    ![Recorte de pantalla de la pantalla de bienvenida de la aplicación Canvas.](media/533c80cc861941b6a353b56bfc0dbc0f.png)

## Tarea 3: Agregue una nueva pantalla a la aplicación.

Mientras está creando la aplicación, uno de sus gerentes se pone en contacto con usted y le pregunta si los empleados también podrían utilizar esta aplicación para restaurar los equipos. Contoso ya almacena la información de restauración de los equipos en Dataverse, por lo que solo es cuestión de hacer que la información esté disponible en la aplicación.

1.  Con la aplicación aún abierta, amplíe el panel **Copilot** (si es necesario). En Copilot, escriba lo siguiente: *`Add a new screen called Equipment Checkout.`*
1.  Selecciona **Enviar**.
1.  Seleccione el botón **Mantener** para aceptar la pantalla.
1.  Se agrega una nueva pantalla denominada **Restauración de equipos** a la aplicación.
1.  Estando en la pantalla **Restauración de equipos**, haga clic en **Con diseño** y seleccione el diseño **Barra lateral**.
1.  Expanda los distintos contenedores hasta que **SideBarContainer** esté visible.

    ![Recorte de pantalla de la vista de árbol ](media/cde6257402b7a8786e679ab64ee0f882.png)

1.  Haga clic con el botón derecho en **SidebarContainer** y cambie el nombre a **EquipContainer1**.
1.  Con el contenedor **EquipContainer1** seleccionado, haga clic en el botón **Abrir menú Insertar**.
1.  En la ventana **Buscar**, introduzca **Galería** y seleccione **Galería vertical**.
1.  Cuando se le pida que proporcione un origen de datos en el campo **Buscar** que aparece, escriba **Equipos**, y seleccione la tabla **Equipos**.
1. En **Vista de árbol** en la parte izquierda de la pantalla, seleccione el control **Galería1** que acaba de añadir.
1. Haga clic con el botón derecho en el nombre de la Galería, seleccione **Cambiar nombre** y cambie el nombre a `Equipment List`.
1. Pase el ratón por encima de la galería **Lista de equipos**, en la barra de herramientas que aparece sobre la galería, seleccione **Diseño**.
1. Seleccione la opción **Disposición de títulos y subtítulos**.
1. Con la galería **Lista de equipos** seleccionada, en el panel **Propiedades**, configure como se indica a continuación:

    -   **Width**: `360`
    -   **Altura flexible:** Activado
    -   **Altura mínima:** `287`

    A continuación, vamos a añadir un contenedor adicional al contenedor **EquipmentContiner1** para almacenar un control de búsqueda que utilizaremos para filtrar el contenido de la galería **Lista de equipos**.

1.  En la vista **Árbol**, seleccione **EquipContainer1**.
1.  Coloque el ratón sobre el contenedor y seleccione el icono de **Copilot**.
1.  Escriba el siguiente texto: *`Insert a Horizontal container.`*

    ![Recorte de pantalla de la inserción de una galería en un contenedor.](media/b9b784ea5625469c8785650b977f32d1.png)

1.  Seleccione el botón **Mantenerla**.
1.  Se agregará un nuevo contenedor a la parte inferior del contenedor de **EquipContainer1**.
1.  En la **Vista de árbol**, haga clic, mantenga pulsado y arrastre el nuevo contenedor, y colóquelo encima de la galería **Lista de equipos**.
1.  Cambie el nombre del contenedor a `EquipSearchContainer`.
1.  Con **EquipSearchContainer** seleccionado, en el panel **Propiedades**, configure como se indica a continuación:
    
    -   **Ancho mínimo:** `0`
    -   **Altura flexible:** Desactivado
    -   **Height**: `44`
    
1.  Con **EquipSearchContainer** seleccionado, seleccione el botón **Abrir menú Insertar**.
1. En el campo **Buscar**, escriba **Texto** y seleccione **Entrada de texto**.
1. Cambie el nombre del campo **Entrada de texto** a `EquipSearchInput`.
1. Con **EquipSearchInput** seleccionado, en el panel **Propiedades**, configure como se indica a continuación:

    -   **Valor predeterminado:** En blanco (nada)
    -   **Sugerencia:** Buscar
    -   **Fuente:** Open Sans
    -   **Tamaño de fuente:** 14
    -   **Relleno** (Es posible que los valores siguientes ya estén ahí.)
        -   **Superior:** 5
        -   **Inferior:** 5
        -   **Izquierda:** 12
        -   **Derecha:** 5
    -   **Alto:** 44
    -   **Ancho flexible:** Activado
    -   **Ancho mínimo:** 0

        ![Recorte de pantalla de las propiedades de entrada de búsqueda.](media/b0e092b4795edf58dad1153209639051.png)

1. En **Vista en árbol**, seleccione el **EquipSearchContainer.**
1. Pase el ratón por encima del contenedor, seleccione el icono **Copilot** y escriba *`Add a Search Icon.`*
1. Selecciona **Conservar**.

    > **Nota:** Si Copilot ha agregado el icono incorrecto, quítelo e inserte la lupa manualmente.

1. Con el icono **Buscar** seleccionado, en el panel **Propiedades**, configure el control como se indica a continuación:

    -   **Relleno**
        -   **Superior:** 10
        -   **Inferior:** 10
        -   **Izquierda:** 10
        -   **Derecha:** 10
    -   **Alto:** 44
    -   **Ancho:** 44

    ![Recorte de pantalla de las propiedades del icono de búsqueda](media/cb3305731a09bca0bbf166d55d9822a4.png)

1. Utilizando la **Vista de árbol** de la izquierda, seleccione el **EquipSearchContainer.**

    Por último, vamos a configurar la galería **Lista de equipos** para que rellene sus datos en función del texto introducido en el campo de control de búsqueda.

1.  Seleccione la galería **Lista de equipos** que hemos creado anteriormente.
1.  En la propiedad **Elementos**, escriba la siguiente fórmula: `Search([@'Equipments'], EquipSearchInput.Text, 'Equipment Name',Category)`

    ![Captura de pantalla de los elementos PowerFx Formula.](media/powerfx-formula.png)

1. En la barra **Comando**, seleccione el botón **Guardar** para guardar la aplicación.

> **Importante:** Si ha copiado y pegado la fórmula en la barra de fórmulas, es posible que las " sean incorrectas para Equipo y Nombre de equipo. Si recibe un error de fórmula, intente quitarlos y volver a ajustarlos.

## Tarea 4: Cree un contenedor para mostrar las operaciones de registro.

Cuando un usuario selecciona un registro en la lista Equipos, queremos abrir el registro en otro contenedor para permitirle editar el registro seleccionado.

1.  Seleccione **MainContainer** y cámbiele el nombre a `DetailsContainer`.
1.  En el **DetailsContainer**, seleccione el botón **Insertar**.
1.  En el campo **Buscar**, introduzca **Contenedor** y seleccione **Contenedor vertical**.
1.  Haga clic con el botón derecho y **Cambie el nombre** del contenedor a `RecordDetails`.
1.  En el contenedor **RecordDetails**, seleccione el botón **Insertar**.
1.  En el menú **Insertar**, seleccione **Editar formulario**.
1.  En la pantalla de selección de fuente de datos, seleccione **Equipos**. *(Los datos pueden tardar hasta 30 segundos en rellenarse.)*
1.  Haga clic con el botón derecho en el formulario que acaba de agregar y **Cambie el nombre** a `EquipmentForm`.
1.  En el panel **Propiedades**, seleccione la pestaña **Avanzadas** y establezca la propiedad **Elemento** en: `'Equipment List'.Selected` *(Esto rellenará el formulario con el registro actualmente seleccionado).*
1. Seleccione la pestaña **Pantalla** y configure el formulario como se indica a continuación:

    -   **Columnas:** 2
    -   **Modo predeterminado**: Editar

    Ahora vamos a agregar otro contenedor que se usará para controlar las operaciones en el formulario.

1.  Asegúrese de que tiene **DetailsContainer** seleccionada.
1.  Seleccione el icono **Copilot** que aparece. Escriba lo siguiente: *`Insert a horizontal container.`*
1.  Selecciona **Conservar**.
1.  Haga clic con el botón derecho en el contenedor y **Cambie el nombre** a `SelectedRecord1`
1.  Con la vista **Árbol**, mueva el contenedor **SelectedRecord1** por encima del contenedor **RecordDetails**.
1.  Configure el contenedor **SelectedRecord1** como se indica a continuación:
    
    -   **Ancho mínimo:** 250
    -   **Altura flexible:** Desactivado
    -   **Height**: 50
    
1.  Con el contenedor **SelectedRecord1** seleccionado, seleccione el botón **Insertar**.
1.  Seleccione **Etiqueta de texto.**
1.  Cambie el nombre de la etiqueta a `SelectedRecordTitle`.
1. Configure **SelectedRecordTitle** como se indica a continuación:

    1.  **Relleno**
        1.  **Superior:** 5
        2.  **Inferior:** 5
        3.  **Izquierda:** 30
        4.  **Derecha:** 5
    2.  **Ancho flexible:** Activado
    3.  **Ancho mínimo:** 150
    4.  **Alto:** 40
       
1. Seleccione el contenedor **SecondRecord1**, Seleccione el botón **Insertar**.
1. En el campo **Buscar**, introduzca **Guardar** y seleccione el icono **Guardar**.
1. Configure el botón **Guardar** del siguiente modo:

    -   **Alto:** 40
    -   **Width**: 40
      
1. Seleccione la propiedad **OnSelect** y escriba la siguiente fórmula: `SubmitForm(EquipmentForm)`

    ![Recorte de pantalla de la fórmula OnSelect PowerFx.](media/e5b22c91a437e6918269d65e2616afc8.png)

## Tarea 5: Modificar el encabezado de la página

El último paso en la creación de esta pantalla es rellenar el contenedor del lector con datos.

1.  Seleccione **HeaderContainer** en la parte superior de la aplicación.
1.  Seleccione el botón **Insertar**.
1.  Seleccione **Etiqueta de texto**.
1.  Configure el control **Etiqueta de texto** como se indica a continuación:
   
    -   **Text**: `Equipment Checkout`
    -   **Fuente:** Open Sans
    -   **Tamaño de fuente:** 16
    -   **Espesor de la fuente:** Seminegrita
    -  **Relleno**
        -   **Superior:** 16
        -   **Inferior:** 16
        -   **Izquierda:** 16
        -   **Derecha:** 16
    -   **Alto:** 40
    -   **Ancho flexible:** Activado

        ![Recorte de pantalla de las propiedades de la etiqueta de texto.](media/088cafeec651b099fa49ac1f151cd228.png)

1.  Seleccione el **HeaderContainer**, seleccione **Insertar** y seleccione el **Icono de inicio**.
1.  Establezca la propiedad **OnSelect** del botón de inicio en: `Back()`

    ![Recorte de pantalla del comando de navegación Atrás.](media/38d0e5367ee41da58ac9902f8056b1af.png)

## Tarea 6: Finalizar la configuración de la pantalla de bienvenida

Tras la revisión, hemos decidido que no necesitamos tener la capacidad de crear usuarios en esta aplicación, por lo que vamos a cambiar la pantalla de bienvenida para que pueda acceder a la desprotección de equipos.

1.  Utilizando **Vista de árbol**, seleccione la **Pantalla de bienvenida**.
1.  Seleccione **Imagen** encima de **Usuarios**.
1.  En el menú que aparece, seleccione **Editar**, y seleccione **Cargar**.
1.  Localice la imagen **Equipo** en su carpeta de estudiante y seleccione **Abrir**.
1.  Establece la propiedad **OnSelect** de la imagen en: `Navigate('Equipment Checkout')`
1.  Seleccione el texto **Usuarios** y establezca la propiedad **Text** en `Equipment`.
1.  Seleccione el **Texto** situado debajo de **Equipos** y cambie la propiedad **Text** a: `Check out equipment and edit reservations`.

    ![Un recorte de pantalla de un contenido generado por ordenador con IA puede ser incorrecto.](media/561d1e8cd023541761b6523138c2fde8.png)

1. Seleccione el botón **Guardar** para guardar la aplicación.

## Tarea 7: Prueba de la aplicación

1.  En la **Barra de comandos**, seleccione el botón **Reproducir**.
1.  Seleccione la imagen **Equipos**.
1.  En el campo **Buscar**, introduzca **Electrónica**. (*Observe cómo filtra la lista*)
1.  Seleccione el registro **Portátil**.
1.  Cambia la **Categoría** a **Muebles**.
1.  Selecciona el botón **Guardar**.
1.  Observe cómo la categoría de **Portátil** cambia a **Muebles**.
1.  Seleccione el botón **Inicio**.
1.  Seleccione **Purple X** para salir del modo **VIsta previa**.

## Tarea 8: Guarde y publique la aplicación.

**Objetivo**: Guarde y publique la aplicación para que sea accesible en exploradores web, dispositivos móviles o plataformas insertadas como SharePoint o Teams.

1.  En Power Apps Studio, seleccione el botón **Guardar**.
1.  Seleccione el botón **Publicar**.
1.  Seleccione **Publicar esta versión.**

