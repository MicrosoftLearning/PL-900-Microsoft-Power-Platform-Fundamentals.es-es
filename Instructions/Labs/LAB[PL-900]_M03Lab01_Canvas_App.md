---
lab:
  title: "Laboratorio\_2: Cómo crear una aplicación de lienzo"
  module: 'Module 3: Get started with Power Apps'
---

# <a name="lab-2-how-to-build-a-canvas-app"></a>Laboratorio 2: Cómo crear una aplicación de lienzo

## <a name="scenario"></a>Escenario

Bellows College is an educational organization with multiple buildings on campus. Campus visits are currently recorded in paper journals. The information is not captured consistently, and there are no means to collect and analyze data about the visits across the entire campus.

Currently, campus administration is leveraging an Excel spreadsheet to track visitor registration. They would like to modernize their visitor registration system where access to the buildings is controlled by security personnel and all visits are required to be pre-registered and recorded by their hosts.

A lo largo de este curso, creará aplicaciones y realizará la automatización para permitir que el personal de administración y seguridad de Bellows College administre y controle el acceso a los edificios en el campus.

## <a name="high-level-lab-steps"></a>Pasos de alto nivel del laboratorio

Seguiremos el siguiente esquema para diseñar la aplicación de lienzo:

- Creación de una aplicación de lienzo a partir de datos en la tabla Visita

- Configurar cómo se muestran las visitas en la pantalla de exploración

- Realizar algunos cambios básicos en la aplicación

- Probar la funcionalidad de la aplicación

## <a name="prerequisites"></a>Prerrequisitos

- Finalización del **Módulo 0 Laboratorio 0: Validación del entorno de laboratorio**
- Finalización del **Módulo 2 Laboratorio 1: Modelado de datos**

## <a name="exercise-1-create-visits-canvas-app"></a>Ejercicio 1: Crear una aplicación de lienzo Visitas

**Objetivo:** En este ejercicio, creará una aplicación de lienzo mediante la conexión de la tabla Visitas que creó anteriormente.

### <a name="task-1-create-the-visits-app"></a>Tarea \#1: Crear la aplicación Visitas

1.  Navigate to <ph id="ph1">&lt;https://make.powerapps.com&gt;</ph>. You may need to reauthenticate - click <bpt id="p1">**</bpt>Sign in<ept id="p1">**</ept> and follow instructions if needed.

2.  Seleccione su ambiente **Práctica [mis iniciales]** en la parte superior derecha, si aún no está seleccionado.

3.  If necessary, click the <bpt id="p1">**</bpt>Home<ept id="p1">**</ept> icon on the left side of the screen. Under the <bpt id="p1">**</bpt>Start from<ept id="p1">**</ept> section, select <bpt id="p2">**</bpt>Dataverse<ept id="p2">**</ept>.

4.  Seleccione la conexión de Dataverse.

    > **NOTA:** *Si no existe ninguna conexión de Dataverse:*
    > - Seleccione **Nueva conexión**
    > - Busque **Microsoft Dataverse**
    > - Haga clic en **Crear**

5.  Busque y seleccione la tabla **Visitas** que creó en el laboratorio anterior.

6.  Seleccione el botón **Conectar** en la esquina inferior derecha.

7.  Una vez creada la aplicación, en la pantalla Bienvenido a Power Apps Studio, active la casilla **No volver a mostrar** y, a continuación, seleccione **Omitir**.

8.  Una vez creada, debería ser similar a la de la imagen siguiente.

![Aplicación de lienzo creada a partir de los datos de visitas.](media/2-canvas-app-from-data.png)

9. Bellows College es una institución educativa que tiene un campus con varios edificios.

10. Cierre la vista previa de la aplicación seleccionando la **X** de la esquina superior derecha de la pantalla.

Actualmente se guarda un registro físico de las visitas al campus.

### <a name="task-2-modify-and-theme-the-newly-created-app"></a>Tarea \#2: Modificar y aplicar un tema a la nueva aplicación

En esta tarea, personalizará el texto del encabezado en cada una de las tres pantallas de la aplicación (Examinar, Detalles y Editar) y cambiará el tema de la aplicación.

1.  La información no se recaba de manera uniforme y no hay forma de recopilar y analizar los datos sobre las visitas de todo el campus.

1.  En el lado derecho de la pantalla, en la pestaña Propiedades, actualice la propiedad de control **Texto** a **"Visitas a Bellows College".**

1. En las propiedades, cambie el **tamaño de la fuente** a **24**.

1.  Haga clic en el fondo en blanco de la pantalla para ver el texto actualizado en la pantalla de exploración.

1.  Mediante la vista de árbol del panel de navegación izquierdo, seleccione **DetailScreen1**.

1.  Seleccione la etiqueta **Visitas** en la pantalla.

1.  En el lado derecho de la pantalla, en la pestaña Propiedades, actualice la propiedad de control **Texto** a **"Detalles de la visita"** .

1.  Haga clic en el fondo en blanco de la pantalla para ver el texto actualizado en la pantalla de detalles.

1.  Mediante la vista de árbol en el panel de navegación izquierdo, seleccione **EditScreen1** (es posible que tenga que desplazarse hacia abajo para verlo en esa vista).

1.  Seleccione la etiqueta **Visitas** en la pantalla.

1.  En el lado derecho de la pantalla, en la pestaña Propiedades, reemplace el texto Table1 en la propiedad de control **Texto** por **"Editar detalles"** .

1.  Haga clic en el fondo en blanco de la pantalla para ver el texto actualizado en la pantalla de edición.

1. Mediante la vista de árbol del panel de navegación izquierdo, seleccione **BrowseScreen1**.

1. En la barra de herramientas de comandos, seleccione el botón **Tema** y, en la lista que aparece, seleccione el color **rojo** para el tema.

### <a name="task-3-test-your-visits-app"></a>Tarea \#3: Probar la aplicación de visitas

En esta tarea, probará la nueva aplicación.

1.  Con la aplicación abierta en el Diseñador de aplicaciones, seleccione **Archivo**, actualice el nombre de la aplicación a **Aplicación de visitas** y seleccione **Guardar**.

2.  Seleccione la flecha **Atrás** para volver a la aplicación.

3.  En el panel de navegación izquierdo, seleccione **BrowseScreen1**.

4.  In the app designer, select the <bpt id="p1">**</bpt>preview the app<ept id="p1">**</ept> button (Play icon) on the command bar. <bpt id="p1">*</bpt>(You can also preview the app by pressing F5 on your keyboard.)<ept id="p1">*</ept>

4.  Una vez que se abra la aplicación, en el campo **Buscar elementos**, escriba el texto **Maria**
     *(observe cómo se filtran los elementos de la galería en función de lo que se escribe en el campo de búsqueda).*

5.  Actualmente, la administración del campus utiliza una hoja de cálculo de Excel para realizar un seguimiento del registro de visitantes.

6.  Para editar el registro, seleccione el **icono de lápiz** en la esquina superior derecha de la aplicación.

7.  Aquí puede editar el nombre de la visita y hacer clic en el icono de marca de verificación de la parte superior derecha para guardar el cambio.

8.  En la parte superior derecha de la pantalla, haga clic en el icono **X** para volver al editor de aplicaciones de lienzo.

Le gustaría modernizar el sistema de registro de visitantes de los edificios cuyo acceso esté controlado por el personal de seguridad y en los que los anfitriones deban anotar con antelación las visitas y dejar constancia de ellas.

## <a name="challenges"></a>Desafíos

- Agregue las siguientes columnas a los formularios en DetailScreen1 y EditScreen1: Inicio real, Finalización real, Código, Inicio programado y Finalización programada