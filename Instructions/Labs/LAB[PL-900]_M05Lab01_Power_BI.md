---
lab:
  title: "Laboratorio\_5: Procedimientos para crear un panel sencillo"
  module: 'Module 5: Get Started with Power BI'
---

## <a name="lab-5-how-to-build-a-simple-dashboard"></a>Laboratorio 5: Procedimientos para crear un panel sencillo

## <a name="scenario"></a>Escenario

Bellows College is an educational organization with multiple buildings on campus. Campus visitors are currently recorded in paper journals. The information is not captured consistently, and there are no means to collect and analyze data about the visits across the entire campus.

La administración del campus querría modernizar el sistema de registro de visitantes de los edificios cuyo acceso esté controlado por el personal de seguridad y en los que los anfitriones deban anotar con antelación las visitas y dejar constancia de ellas.

A lo largo de este curso, creará aplicaciones y realizará la automatización para permitir que el personal de administración y seguridad de Bellows College administre y controle el acceso a los edificios en el campus.

En este laboratorio, creará un panel y un informe de Power BI que visualiza datos sobre las visitas al campus.

## <a name="high-level-lab-steps"></a>Pasos de alto nivel del laboratorio

Seguiremos los pasos a continuación para diseñar y crear un panel de control de Power BI:

-   Crear un informe con varias visualizaciones de la información de las visitas al campus

-   Utilice una consulta de lenguaje natural del usuario para crear visualizaciones adicionales

## <a name="prerequisites"></a>Prerrequisitos

- Finalización del **Módulo 0 Laboratorio 0: Validación del entorno de laboratorio**
- Finalización del **Módulo 2 Laboratorio 1: Modelado de datos**

## <a name="things-to-consider-before-you-begin"></a>Cuestiones que tener en cuenta antes de comenzar

-   ¿Quién es la audiencia objetivo del informe?
-   How will the audience consume the report? Typical device? Location?
-   ¿Tiene suficientes datos para visualizar?
-   ¿Cuáles son las posibles características que puede usar para analizar datos sobre las visitas?

## <a name="exercise-1-create-power-bi-report"></a>Ejercicio 1: Cree informes de Power BI

**Objetivo:** En este ejercicio, creará un informe de Power BI basado en los datos de la hoja de cálculo de Excel que hemos aprovechado en un ejercicio anterior.

### <a name="task-1-prepare-power-bi-service"></a>Tarea \#1: Preparar el servicio Power BI

1.  Descargue [visits.pbix](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/visits.pbix) y guárdelo en su equipo.

2.  Vaya a <https://app.powerbi.com/> e inicie sesión si es necesario.

3.  En la esquina inferior izquierda de la pantalla, haga clic en **Obtener datos**.

4.  Seleccione el botón **Obtener** en **Archivos**, en la sección **Crear contenido**.

5.  Seleccione **Archivo Local**.

6.  Busque y seleccione el archivo **visits.pbix** que ha descargado anteriormente.

7.  Una vez completada la carga de datos, expanda **Mi área de trabajo** y seleccione el informe de **visitas** (observe que el Tipo está establecido en **Informe**).

8.  Click <bpt id="p1">**</bpt>Edit<ept id="p1">**</ept>. If <bpt id="p1">**</bpt>Edit<ept id="p1">**</ept> menu item is not visible click <bpt id="p2">**</bpt>...<ept id="p2">**</ept> and then select <bpt id="p3">**</bpt>Edit<ept id="p3">**</ept>.

Ahora ya configuró el servicio Power BI para usarlo en sus laboratorios.

### <a name="task-2-create-chart-and-time-visualizations"></a>Tarea \#2: Cree gráficos y visualizaciones de tiempo

1.  Presione el icono de **gráfico circular** en el panel **Visualizaciones** para insertar un gráfico.

2.  Press the drop-down arrow beside <bpt id="p1">**</bpt>bc_building<ept id="p1">**</ept> in the Fields pane. Drag the <bpt id="p1">**</bpt>Building<ept id="p1">**</ept> field and drop it into <bpt id="p2">**</bpt>Legend<ept id="p2">**</ept> box.

3.  Bellows College es una institución educativa que tiene un campus con varios edificios.

4.  Cambie el tamaño del gráfico circular utilizando los tiradores de las esquinas para que todos los componentes del gráfico sean visibles.

5.  Haga clic en el informe fuera del gráfico circular para anular la selección y seleccione el gráfico de columnas apiladas en el panel **Visualizaciones**.

6.  Los visitantes del campus están actualmente registrados en revistas en papel.

7.  Arrastre el campo **Comienzo** y colóquelo en el cuadro de destino **Eje X**.

8.  En el panel Visualizaciones, haga clic en **X** junto a **Año** y **Trimestre** para dejar solo los totales de **Mes** y **Día** para el eje.

9.  Cambie el tamaño del gráfico como desee con los identificadores de las esquinas.

10. Pruebe la interactividad del informe:

    1.  Haga clic en varios sectores de creación en el gráfico circular y observe los cambios en el informe de tiempo.

    2.  La información no se recaba de manera uniforme y no hay forma de recopilar y analizar los datos sobre las visitas de todo el campus.

    3.  Rastree agrupando y desagrupando datos y seleccione varias barras en el gráfico de columnas de tiempo para observar los cambios en el informe circular.

11. Guarde el trabajo en curso presionando **Guardar**.

## <a name="exercise-2-create-power-bi-dashboard"></a>Ejercicio 2: Crear un panel de información de Power BI

### <a name="task-1-create-power-bi-dashboard"></a>Tarea \#1: Crear un panel de información de Power BI

1.  Debería tener abierto el informe de la tarea anterior.

2.  Select <bpt id="p1">**</bpt>Pin to a dashboard<ept id="p1">**</ept> on the menu. Depending on the layout you may need to press <bpt id="p1">**</bpt>...<ept id="p1">**</ept> to show additional menu items.

3.  Seleccione **Nuevo tablero** en la confirmación de **Anclar al tablero**.

4.  Introduzca **Administración del campus** como un **Nombre del tablero**, presione **Anclar elemento en vivo**.

5.  A pop-up will prompt you that the dashboard has been created. Select <bpt id="p1">**</bpt>Go to dashboard<ept id="p1">**</ept>.

6.  Pruebe la interactividad de los gráficos circulares y de barras que se muestran.

### <a name="task-2-add-visualizations-using-natural-language"></a>Tarea \#2: Agregue visualizaciones usando lenguaje natural

1.  En el panel de información **Administración de campus**, seleccione la barra **Pregunte algo sobre sus datos** en la parte superior.

2.  Enter <bpt id="p1">**</bpt>buildings by number of visits<ept id="p1">**</ept> in Q&amp;A area. A bar chart will be displayed.

3.  Seleccione **Anclar visualización**.

4.  Seleccione **Panel existente**, seleccione el panel de **Administración del campus**, presione **Anclar**.

5.  Haga clic en **Salir de Preguntas y respuestas**.

Your <bpt id="p1">**</bpt>Campus Management<ept id="p1">**</ept> dashboard should be displayed with three visuals on it. You may have to scroll down to see the new Q&amp;A visual.

Su panel de información debería tener un aspecto similar al siguiente:

![](media/5-powerbi-result.png)