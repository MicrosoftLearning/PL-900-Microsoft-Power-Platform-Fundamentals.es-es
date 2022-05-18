---
lab:
  title: 'Laboratorio 3: Cómo crear una aplicación basada en modelo'
  module: 'Module 3: Get started with Power Apps'
ms.openlocfilehash: 56a807c49479c245f95e3af9566450651bcc3ebb
ms.sourcegitcommit: 99acd470de1164d438d7c4794faa28d6489c39db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2022
ms.locfileid: "144812453"
---
# <a name="module-3-get-started-with-power-apps"></a>Módulo 3: Introducción a Power Apps
## <a name="lab-how-to-build-a-model-driven-app"></a>Laboratorio: Cómo crear una aplicación basada en modelo

# <a name="scenario"></a>Escenario

Bellows College es una institución educativa que tiene un campus con varios edificios. Los visitantes del campus están actualmente registrados en revistas en papel. La información no se recaba de manera uniforme y no hay forma de recopilar y analizar los datos sobre las visitas de todo el campus.

La administración del campus querría modernizar el sistema de registro de visitantes de los edificios cuyo acceso esté controlado por el personal de seguridad y en los que los anfitriones deban anotar con antelación las visitas y dejar constancia de ellas.

A lo largo de este curso, creará aplicaciones y realizará la automatización para permitir que el personal de administración y seguridad de Bellows College administre y controle el acceso a los edificios en el campus.

En este laboratorio, creará una aplicación impulsada por el modelo de Power Apps para permitir que el personal del campus administrativo administre los registros de visitas en todo el campus.

# <a name="high-level-lab-steps"></a>Pasos de alto nivel del laboratorio

Como parte de la creación de la aplicación basada en modelo, completará lo siguiente:

-   Cree una nueva aplicación basada en modelo llamada Administración del campus

-   Editar la navegación de la aplicación para hacer referencia a las tablas requeridas

-   Personalizar los formularios y las vistas de las tablas necesarias para la aplicación

Trabajaremos con los siguientes componentes:

-   **Vistas**: Las vistas permiten al usuario mostrar los datos existentes en la tabla del formulario.

-   **Formularios**: Aquí es donde el usuario crea/actualiza nuevas filas en las tablas.

Ambos se integrarán a la aplicación basada en modelo para una mejor experiencia de usuario.

## <a name="prerequisites"></a>Prerrequisitos

-   Haber realizado el **módulo 0, laboratorio: Validación del entorno de laboratorio**

-   Haber realizado el **módulo 2, laboratorio: Modelado de datos**

-   Haber realizado el **módulo 3, laboratorio: Cómo crear una aplicación de lienzo**

## <a name="things-to-consider-before-you-begin"></a>Cuestiones que tener en cuenta antes de comenzar

-   ¿Qué cambios debemos hacer para mejorar la experiencia del usuario?

-   ¿Qué deberíamos incluir en una aplicación basada en modelo elaborada según el modelo de datos que hemos construido?

-   ¿Qué personalizaciones se pueden hacer en el mapa del sitio de una aplicación basada en modelos?

# <a name="exercise-1-customize-views-and-forms"></a>Ejercicio \#1: Personalizar las vistas y formularios

**Objetivo:** En este ejercicio, personalizará las vistas y formularios de las tablas creadas de manera personalizada que se utilizarán en la aplicación basada en modelo.

## <a name="task-1-edit-visit-form"></a>Tarea \#1: Editar el formulario de visita

1.  Haga clic en <https://make.powerapps.com> si no ha iniciado sesión aún.

2.  Seleccione su ambiente **Práctica [mis iniciales]** en la parte superior derecha, si aún no está seleccionado.

3.  Con el panel de navegación de la izquierda, expanda **Dataverse**, seleccione **Tablas** y haga clic para abrir la tabla **Visitas**.
>   Si no ve la tabla Visita, asegúrese de que se encuentra en el entorno correcto (paso 2).

4.  Seleccione la pestaña **Formularios** y haga clic para abrir el formulario Información con el tipo de formulario **Principal**.
>   **IMPORTANTE:** *Dado que, de forma predeterminada, todos los formularios se denominan Información, asegúrese de comprobar que el formulario que selecciona sea del tipo de formulario*  **Principal**  *y no cualquier otro.*
Por defecto, el formulario tiene dos campos: Nombre (campo principal) y Propietario.

5.  En el lado derecho de la pantalla, en el panel Propiedades, seleccione el campo **Nombre para mostrar** y cámbielo a **Información principal**.

6.  Con el menú de la parte superior de la pantalla, seleccione el **campo + Formulario** y agregue los siguientes campos debajo del campo **Propietario**. Para ello, arrastre las columnas hasta el formulario o simplemente haga doble clic en los nombres de las columnas:

    1.  **Visitante**

    2.  **Inicio programado**

    3.  **Final programado**

    4.  **Inicio real**

    5.  **Finalización real**

7.  Arrastre la columna **Código** y suéltela en el encabezado del formulario.

    >   El encabezado está en la parte superior derecha del formulario. Es posible que deba contraer el panel Propiedades en el lado derecho de la pantalla para ver el campo en el formulario.

8.  Con el campo **Código** seleccionado, marque la casilla de verificación **Solo lectura** en el panel Propiedades del lado derecho de la pantalla.

9.  Seleccione el campo **Propietario**. En el panel Propiedades, cambie la **Etiqueta** a **Host**.

10.  Haga clic en **Guardar** en la parte superior derecha y espere a que se termine de guardar.

11.  Haga clic en **Publicar** en la parte superior derecha y espere hasta que se complete la publicación.

12.  Si la vista de edición se abre en una nueva pestaña o ventana del explorador, ciérrela. De lo contrario, haga clic en **Atrás** en la parte superior izquierda de la pantalla. Ahora debe estar de nuevo en la pestaña Formularios de la tabla Visita.

## <a name="task-2-edit-active-visits-view"></a>Tarea \#2: Editar la vista de visitas activas

En esta tarea, modificaremos la vista predeterminada de Visitas activas y crearemos una nueva vista para las visitas de hoy.

1.  Seleccione la pestaña **Vistas** y haga clic para abrir la vista **Visitas activas**.

2.  Agregue los siguientes campos a la vista haciendo clic o arrastrando y soltando los campos:

    1.  **Código**

    2.  **Visitante**

    3.  **Inicio programado**

    4.  **Final programado**

3.  Haga clic en la columna **Creado en** y seleccione **Quitar**. El campo **Creado en** ahora se eliminará de la vista.

4.  Cambie el tamaño de los anchos de las columnas individuales para que los datos entren.

5.  Haga clic en **Guardar** y espere hasta que se guarden los cambios.

6.  Haga clic en **Publicar** y espere a que se complete la publicación.

## <a name="task-3-create-new-view-for-todays-visits"></a>Tarea \#3: Crear una vista nueva para las visitas de hoy

Ahora clonaremos la vista para crear una nueva vista para las visitas de hoy.

1.  Haga clic en la **flecha desplegable** situada junto al botón Guardar (tenga cuidado de no presionar el botón) y seleccione **Guardar como**.

2.  Cambie el nombre a **Visitas de hoy** y presione **Guardar**.

3.  Haga clic en el vínculo **Editar filtros** en el panel Propiedades.

2.  Haga clic en **Agregar**, seleccione **Agregar fila**.

3.  Seleccione **Inicio programado** como campo y, luego, **Hoy** como condición en el menú desplegable.

4.  Haga clic en **...** en la fila **Estado** y haga clic en **Eliminar** para eliminar esa condición de filtro.

5.  Presione **Aceptar** para guardar la condición. La vista ahora está filtrada para mostrar solo los registros donde la fecha de inicio programada es hoy.

6.  Agregue los campos **Comienzo real** y **Final real** a la vista.

> **Nota:** Como ya no filtramos el estado de la vista, obtendremos todas las visitas de hoy, incluidas las completadas. Estos campos ayudarán a diferenciar visitas completadas y visitas en curso.

7.  Haga clic en **Save**(Guardar).

8.  Haga clic en **Publicar** y espere a que se complete la publicación.

# <a name="exercise-2-create-model-driven-application"></a>Ejercicio \#2: Crear una aplicación basada en modelos

**Objetivo:** En este ejercicio, creará la aplicación basada en modelos, personalizará el mapa del sitio y probará la aplicación.

>   Por motivos de simplicidad y tiempo, no abordaremos algunas de las columnas de visitas de este laboratorio. 

## <a name="task-1-create-application"></a>Tarea \#1: Crear una aplicación

1.  Haga clic en <https://make.powerapps.com> (si aún no ha iniciado sesión).

2.  Seleccione su ambiente **Práctica [mis iniciales]** en la parte superior derecha, si aún no está seleccionado.

3.  Cree una aplicación basada en modelos:

    1.  Seleccione **Aplicación vacía** en la sección **Iniciar desde** de la pantalla de inicio.

    2.  En **Aplicación vacía basada en Dataverse**, seleccione **Crear**.

    3.  Seleccione la experiencia **Diseñador de aplicaciones modernas**.
    
    4.  Seleccione **Crear**.
    
    5.  Escriba **Administración del campus de Bellows** en Nombre y seleccione **Crear**.

4.  Una vez que se cargue la nueva aplicación controlada por modelos, seleccione el botón **+ Agregar página**.

5.  En la pantalla Agregar página, elija **Vista y formulario basados en tablas** y, a continuación, seleccione el botón **Siguiente**.

6.  Agregue las tablas siguientes:

    1.  Visite

    2.  Contacto

7.  Después de seleccionar las 2 tablas, seleccione **Agregar**.

8.  Con los iconos de navegación del panel izquierdo de la pantalla, seleccione **Navegación**.

9.  En el panel de navegación, seleccione el **Grupo 1** debajo de Barra de navegación.

10.  En el lado derecho de la pantalla, en la sección **Opciones de presentación**, cambie la propiedad **Título** a **Seguridad**.

## <a name="task-2-edit-your-app"></a>Tarea \#2: Editar la aplicación
Ahora que tenemos todos los componentes necesarios agregados a la aplicación controlada por modelos, organizaremos los elementos.

1.  En el panel de navegación, en el grupo de seguridad, seleccione **SubArea1**.

2.  Seleccione la **Elipsis** y, en el menú que aparece, seleccione eliminar **SubArea1**.

3.  Con la navegación del panel izquierdo de la pantalla, seleccione **Páginas**.

4.  Busque y expanda **Visita** en el panel Páginas.

5.  Seleccione **Formulario de visita**.

6.  En la parte derecha de la pantalla, seleccione **Administrar formularios**.

7.  Seleccione el formulario **Información principal** y, a continuación, haga clic en **Guardar**.

8.  En **Visita** en el panel Páginas, seleccione **Vista de visita**.

9.  En la parte derecha de la pantalla, seleccione **Administrar vistas**.

10. Seleccione los formularios **Visitas de hoy** y **Visitas activas** y, a continuación, seleccione **Guardar**.

11. Seleccione **Guardar**.

12. Una vez completada la operación **Guardar**, seleccione el botón **Publicar** para publicar los cambios.

## <a name="task-3-test-application"></a>Tarea \#3: Probar la aplicación

1.  Inicio de la aplicación

    1.  Seleccione **Reproducir** para abrir la aplicación en una ventana nueva.

2.  Crear un nuevo contacto

    1.  La aplicación debería abrirse en la vista **Mis contactos activos**. Si no es así, seleccione Visitas a la izquierda. 

    2.  Haga clic en **Nuevo** en el menú superior.

    3.  Proporcione el **Nombre de pila** como `John` y **Apellido** como `Doe`.

    4.  Proporcione su correo electrónico personal como **Correo electrónico**. Esto se usará en un laboratorio futuro donde recibirá un correo electrónico. 

    5.  Haga clic en **Guardar y cerrar**.

    6.  Ahora debería ver el contacto creado en la vista **Contactos activos**.

4.  Crear una nueva visita

    1.  Seleccione **Visitas** del mapa del sitio.

    2.  Haga clic en **Nueva**.

    3.  Especifique los campos de la siguiente forma

        1.  **Nombre**: `New test visit`

        2.  **Visitante**: seleccione John Doe

        3.  **Inicio programado**: seleccione la fecha de mañana y las 02:00 como hora de inicio.

        4.  **Final programado**: seleccione la fecha de mañana y las 03:30 como hora de finalización.

    4.  Haga clic en **Guardar y cerrar**. Esto creará el registro de la visita y debería poder verlo en la vista Visitas activas.

    5.  Cambie la vista a **Visitas de hoy**. Ya no debería ver la nueva visita en la vista, ya que está programada para mañana.

5.  Puede agregar más registros de prueba.

    Su aplicación en ejecución debería verse aproximadamente como la siguiente:

![](media/3-model-driven-app.png)

Felicidades. Ha creado y configurado la primera aplicación basada en modelo.

# <a name="challenges"></a>Desafíos

-   Seleccione vistas y formularios específicos para Contactos
