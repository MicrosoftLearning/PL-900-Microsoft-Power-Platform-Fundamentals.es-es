---
lab:
  title: 'Laboratorio 7: Procedimientos para crear un panel sencillo'
  module: 'Module 5: Get Started with Power BI'
ms.openlocfilehash: 5381acb81a59a46f6eb6aca9f2bde18de9846473
ms.sourcegitcommit: ef58c858463b890e923ef808b1d43405423943fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2022
ms.locfileid: "137899057"
---
# <a name="module-5-get-started-with-power-bi"></a>Módulo 5: Introducción a Power BI
## <a name="lab-how-to-build-a-simple-dashboard"></a>Laboratorio: Procedimientos para crear un panel sencillo

# <a name="scenario"></a>Escenario

Bellows College es una institución educativa que tiene un campus con varios edificios. Los visitantes del campus están actualmente registrados en revistas en papel. La información no se recaba de manera uniforme y no hay forma de recopilar y analizar los datos sobre las visitas de todo el campus. 

La administración del campus querría modernizar el sistema de registro de visitantes de los edificios cuyo acceso esté controlado por el personal de seguridad y en los que los anfitriones deban anotar con antelación las visitas y dejar constancia de ellas.

A lo largo de este curso, creará aplicaciones y realizará la automatización para permitir que el personal de administración y seguridad de Bellows College administre y controle el acceso a los edificios en el campus. 

En este laboratorio, creará un panel de control de Power BI que visualiza datos sobre las visitas al campus.

# <a name="high-level-lab-steps"></a>Pasos de alto nivel del laboratorio

Seguiremos los pasos a continuación para diseñar y crear el panel de control de Power BI:

-   Conectarse a Dataverse.
-   Transforme los datos para incluir descripciones fáciles de usar para los registros relacionados (búsquedas)
-   Cree y publique un informe con varias visualizaciones de la información de las visitas al campus.
-   Utilice una consulta de lenguaje natural del usuario para crear visualizaciones adicionales
-   Compile una vista móvil del panel de información de Power BI


## <a name="prerequisites"></a>Prerrequisitos

* Finalización del **Módulo 0 Laboratorio 0: Validación del entorno de laboratorio**
* Finalización del **Módulo 2 Laboratorio 1: Introducción a Microsoft Dataverse**

## <a name="things-to-consider-before-you-begin"></a>Cuestiones que tener en cuenta antes de comenzar

-   ¿Quién es la audiencia objetivo del informe?
-   ¿Cómo consumirá el informe la audiencia? ¿Dispositivo típico? ¿Ubicación?
-   ¿Tiene suficientes datos para visualizar?
-   ¿Cuáles son las posibles características que puede usar para analizar datos sobre las visitas?

# <a name="exercise-1-create-power-bi-report"></a>Ejercicio \#1: Cree informes de Power BI 

**Objetivo:** En este ejercicio, creará un informe de Power BI con los datos de la base de datos de Dataverse.

## <a name="task-1-install-power-bi-desktop--prepare-power-bi-service"></a>Tarea \#1: Instale Power BI Desktop/Prepare el servicio Power BI

1. Siga las siguientes instrucciones para configurar Power BI: 

    - Si Power BI Desktop **ya** está instalado, pase a la [Tarea \#2](#task-2-prepare-data).
    
    - Si no tiene Power BI Desktop instalado, complete el **Paso 2**.
    
    - Si no tiene los permisos necesarios o tiene problemas con la ejecución de Power BI Desktop, continúe con el **Paso 4**.

2. Vaya a [https://aka.ms/pbidesktopstore](https://aka.ms/pbidesktopstore) para descargar e instalar Power BI Desktop.

    > [!IMPORTANT]
    > Si tiene problemas para instalar Power BI Desktop con Microsoft Store, pruebe con el instalador independiente que se puede descargar desde [https://aka.ms/pbiSingleInstaller](https://aka.ms/pbiSingleInstaller).

3. Si instaló Power BI Desktop correctamente, ya puede pasar a la [Tarea \#2](#task-2-prepare-data). De lo contrario, continúe con el siguiente paso.

    > Si no tiene los permisos necesarios para instalar aplicaciones de escritorio o tiene dificultades para ejecutar o configurar Power BI Desktop, complete los pasos de la siguiente tarea.

4. Descargue [visits.pbix](../../Allfiles/visits.pbix) y guárdelo en su equipo.

5. Vaya a [https://app.powerbi.com/](https://app.powerbi.com/) y haga clic en **Iniciar sesión**. 

6. Haga clic en **Mi área de trabajo**. 

7. Cuando se presente la página **Obtener datos**, haga clic en **Omitir**. 

8. Expanda **+Nuevo** y seleccione **Cargar un archivo**.

    > [!IMPORTANT]
    > Si no ve **+Nuevo**, es posible que deba activar el nuevo aspecto de Power BI. Asegúrese de que **Nuevo aspecto** aparezca como **Activado** en la parte superior de la pantalla.

9. Seleccione **Archivo Local**.

10. Busque y seleccione el archivo **visits.pbix** que ha descargado anteriormente.

11. Una vez completada la carga de datos, seleccione el informe de **visitas** (observe que Tipo esté establecido en **Informe**).

12. Haga clic en **Editar**. Si el elemento del menú **Editar** no es visible, haga clic en **...** y luego seleccione **Editar**.

13. Ahora ya configuró el servicio Power BI para usarlo en sus laboratorios. Continúe con la [Tarea \#3](#task-3-create-chart-and-time-visualizations), pero use el servicio Power BI en línea en [https://app.powerbi.com](https://app.powerbi.com) en lugar de Power BI Desktop durante el resto del laboratorio.

## <a name="task-2-prepare-data"></a>Tarea \#2: Preparación de los datos

1.  Encuentre la URL de su organización

    * En la nueva pestaña, vaya al Centro de administración de Power Platform en <https://admin.powerplatform.com>.
    
    * En la página de navegación izquierda, seleccione Entornos y, a continuación, abra su entorno de práctica.
    
    * Haga clic con el botón derecho del mouse en la **URL de entorno** del panel **Detalles**, luego seleccione **Copiar dirección de vínculo**.
    
2. Abra Power BI Desktop e inicie sesión con las credenciales que le han proporcionado si se le solicita.

3. Seleccione **Obtener datos** y, después, **Más...** .

4. Seleccione **Power Platform** a la izquierda, luego seleccione **Common Data Service (heredado)** y presione **Conectar**. Si se le solicita, inicie sesión con las credenciales proporcionadas y haga clic en **Conectar**.

5. Pegue la URL del entorno que copió anteriormente en el campo **URL del servidor**, presione **Aceptar**.

6. Expanda el nodo **Entidades**, seleccione las entidades **bc_Building** y **bc_Visit**, haga clic en **Cargar**.

7. Haga clic en el icono **Modelo** de la barra de herramientas vertical izquierda.

8. Arrastre la columna **bc_buildingid** desde la tabla **bc_Building** y suéltela en la columna **bc_building** de la tabla **bc_Visit**. Eso creará una relación entre las dos tablas que Power BI podrá usar para mostrar datos relacionados.

9. Seleccione el icono **Informe** en la barra de herramientas izquierda.

10. Expanda el nodo **bc_Visit** en el panel **Campos**.

11. Haga clic en **...** junto a **bc_Visit** y seleccione **Nueva columna**.

12. Complete la fórmula del siguiente modo:

    ```
    Column = RELATED(bc_Building[bc_name])
    ```

    y presione Entrar. Eso agregará un nuevo campo con el nombre del edificio en los datos de las visitas.

13. Haga clic en **...** junto al campo **Columna** que acaba de crear y seleccione **Cambiar nombre**. Escriba **Edificio** como nombre del campo.

14. Haga clic en **...** al lado del campo **bc_visitid** y seleccione **Cambiar nombre**. Escriba **Visita** como nombre del campo.

15. Haga clic en **...** al lado del campo **bc_scheduledstart** y seleccione **Cambiar nombre**. Escriba **Inicio** como nombre del campo.

16. Para guardar el trabajo en curso, presione **Archivo \| Guardar** e introduzca un nombre de archivo de su elección.

## <a name="task-3-create-chart-and-time-visualizations"></a>Tarea n.° 3: Cree gráficos y visualizaciones de tiempo

1. Presione el icono de gráfico circular en el panel **Visualizaciones** para insertar un gráfico.

2. Arrastre el campo **Edificio** y colóquelo en el cuadro **Leyenda**.

3. Arrastre el campo **Visita** y colóquelo en el cuadro de destino **Valores**.

4. Cambie el tamaño del gráfico circular utilizando los tiradores de las esquinas para que todos los componentes del gráfico sean visibles.

5. Haga clic en el informe fuera del gráfico circular para anular la selección y seleccione el gráfico de columnas apiladas en el panel **Visualizaciones**. 

6. Arrastre el campo **Visita** y colóquelo en el cuadro de destino **Valores**.

7. Arrastre el campo **Comienzo** y colóquelo en el cuadro de destino **Eje**.

8. En el panel Visualizaciones, haga clic en **X** junto a **Día** y **Trimestre** para dejar solo los totales de **Año** y **Mes** para el eje.

9. Cambie el tamaño del gráfico como desee con los identificadores de las esquinas.

10. Pruebe la interactividad del informe:

    * Seleccione varios sectores de creación en el gráfico circular y observe los cambios en el informe de tiempos.
    
    * Haga clic en el gráfico de columnas. Presione la flecha hacia abajo para activar el modo **Explorar en profundidad** y luego presione la columna para explorar en profundidad hasta el siguiente nivel (meses). Otra manera de hacerlo es hacer clic en **Datos y detalles\| Expandir al siguiente nivel** de la cinta de opciones.
    
    * Rastree agrupando y desagrupando datos y seleccione varias barras en el gráfico de columnas de tiempo para observar los cambios en el informe circular.
    
11. Para guardar el trabajo en curso presione **Archivo \| Guardar**.

# <a name="exercise-2-create-power-bi-dashboard"></a>Ejercicio 2: Crear un panel de información de Power BI

## <a name="task-1-publish-power-bi-report"></a>Tarea n.° 1: Publicar informe de Power BI

1. Presione el botón **Publicar** en la pestaña Inicio de la cinta.

2. Seleccione **Mi espacio de trabajo** como destino, luego presione **Seleccionar**.

3. Espere hasta que se complete la publicación y haga clic en **Abrir \<name of your report\>.pbix en Power BI**.

## <a name="task-2-create-power-bi-dashboard"></a>Tarea n.°2: Crear un panel de información de Power BI

1. Debería tener abierto el informe de la tarea anterior.

2. Seleccione **Anclar a un panel de información** en el menú. Según el diseño, es posible que deba presionar **...** para mostrar los elementos de menú adicionales.

3. Seleccione **Nuevo tablero** en la confirmación de **Anclar al tablero**.

4. Escriba **[Su apellido] Administración del campus** como **Nombre de panel de información** y pulse **Anclar elemento activo**.

5. Seleccione **Mi área de trabajo** en la parte superior, seleccione el panel de información **[Su apellido] Administración del campus**.

6. Pruebe la interactividad de los gráficos circulares y de barras que se muestran.

## <a name="task-3-add-visualizations-using-natural-language"></a>Tarea n.° 3: Agregue visualizaciones usando lenguaje natural

1. En el panel de información **Administración de campus**, seleccione la barra **Pregunte algo sobre sus datos** en la parte superior.

2. Introduzca **edificios por número de visitas** en el área de preguntas y respuestas. Se mostrará el gráfico de barras.

3. Seleccione **Anclar visualización**.

4. Seleccione **Panel existente** y el panel **[Su apellido] Administración del campus** y pulse **Anclar**.

5. Haga clic en **Salir de Preguntas y respuestas**.

Se debería mostrar el panel de información **[Su apellido] Administración del campus**. Es posible que deba desplazarse hacia abajo para ver el nuevo objeto visual Preguntas y respuestas. 

Su panel de información debería tener un aspecto similar al siguiente:

![Panel de Power BI](media/5-powerbi-result.png)

## <a name="task-4-build-mobile-phone-view-and-share-a-report-with-a-qr-code"></a>Tarea 4: Cree una vista de teléfono móvil y comparta un informe con un código QR

1. En el panel, seleccione **Editar \| Diseño para móviles**.

2. Reorganice los iconos como desee.

3. Haga clic en **Diseño para móvil** en la parte superior derecha y cambie la vista a **Diseño web**.

4. Seleccione **Mi área de trabajo** en la parte superior y seleccione su **Informe**.

5. Seleccione **Editar** y luego seleccione **... \| Generar un código QR**.

6. *Opcional*: Si tiene un dispositivo móvil, escanee el código utilizando una aplicación de escáner de QR disponible en plataformas iOS y Android o en la aplicación de la cámara, si su teléfono la admite. Inicie sesión en su cuenta si se le pide. Navegue y explore el informe en un dispositivo móvil.

# <a name="challenges"></a>Desafíos

* Paneles de información e informes para incluir los planos del edificio y el campus
* Informe y analice patrones y tendencias de visitas
* Visualización sobrepasada
* Streaming de Power BI para un procesamiento casi en tiempo real para un campus grande 
