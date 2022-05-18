---
lab:
  title: 'Laboratorio 5: Procedimientos para crear un panel sencillo'
  module: 'Module 5: Get Started with Power BI'
ms.openlocfilehash: 8d104c42de9d4114c668a63a4d8d30cbbcc4b39e
ms.sourcegitcommit: 36c8fda9cdc6f448416d7000e38c1606bea87d2e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2022
ms.locfileid: "144812939"
---
# <a name="module-5-get-started-with-power-bi"></a>Módulo 5: Introducción a Power BI
## <a name="lab-how-to-build-a-simple-dashboard"></a>Laboratorio: Procedimientos para crear un panel sencillo

# <a name="scenario"></a>Escenario

Bellows College es una institución educativa que tiene un campus con varios edificios. Los visitantes del campus están actualmente registrados en revistas en papel. La información no se recaba de manera uniforme y no hay forma de recopilar y analizar los datos sobre las visitas de todo el campus.

La administración del campus querría modernizar el sistema de registro de visitantes de los edificios cuyo acceso esté controlado por el personal de seguridad y en los que los anfitriones deban anotar con antelación las visitas y dejar constancia de ellas.

A lo largo de este curso, creará aplicaciones y realizará la automatización para permitir que el personal de administración y seguridad de Bellows College administre y controle el acceso a los edificios en el campus.

En este laboratorio, creará un panel de control de Power BI que visualiza datos sobre las visitas al campus.

# <a name="high-level-lab-steps"></a>Pasos de alto nivel del laboratorio

Seguiremos los pasos a continuación para diseñar y crear un panel de control de Power BI:

-   Conectarse a Dataverse.

-   Transforme los datos para incluir descripciones fáciles de usar para los registros relacionados (búsquedas)

-   Cree y publique un informe con varias visualizaciones de la información de las visitas al campus.

-   Utilice una consulta de lenguaje natural del usuario para crear visualizaciones adicionales

-   Compile una vista móvil del panel de información de Power BI

## <a name="prerequisites"></a>Prerrequisitos

-   Finalización del **Módulo 0 Laboratorio 0: Validación del entorno de laboratorio**

-   Finalización del **Módulo 2 Laboratorio 1: Introducción a Microsoft Dataverse**

## <a name="things-to-consider-before-you-begin"></a>Cuestiones que tener en cuenta antes de comenzar

-   ¿Quién es la audiencia objetivo del informe?

-   ¿Cómo consumirá el informe la audiencia? ¿Dispositivo típico? ¿Ubicación?

-   ¿Tiene suficientes datos para visualizar?

-   ¿Cuáles son las posibles características que puede usar para analizar datos sobre las visitas?

# <a name="exercise-1-create-power-bi-report"></a>Ejercicio \#1: Cree informes de Power BI

**Objetivo:** En este ejercicio, creará un informe de Power BI basado en los datos de la hoja de cálculo de Excel que hemos aprovechado en un ejercicio anterior.

## <a name="task-1-prepare-power-bi-service"></a>Tarea \#1: Preparar el servicio Power BI

1.  Descargue [visits.pbix](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/visits.pbix) y guárdelo en su equipo.

2.  Vaya a <https://app.powerbi.com/> e inicie sesión si es necesario.

3.  En la esquina inferior izquierda de la pantalla, haga clic en **Obtener datos**.

4.  Seleccione el botón **Obtener** en **Archivos**, en la sección **Crear contenido**.

5.  Seleccione **Archivo Local**.

6.  Busque y seleccione el archivo **visits.pbix** que ha descargado anteriormente.

7.  Una vez completada la carga de datos, seleccione el informe de **visitas** (observe que Tipo esté establecido en **Informe**).

8.  Haga clic en **Editar**. Si el elemento del menú **Editar** no es visible, haga clic en **...** y luego seleccione **Editar**.

Ahora ya configuró el servicio Power BI para usarlo en sus laboratorios. 

## <a name="task-2-create-chart-and-time-visualizations"></a>Tarea \#2: Cree gráficos y visualizaciones de tiempo

1.  Presione el icono de **gráfico circular** en el panel **Visualizaciones** para insertar un gráfico.

2.  Presione la flecha desplegable situada junto a **bc_name** en el panel Campos. Arrastre el campo **Edificio** y colóquelo en el cuadro **Leyenda**.

3.  Presione la flecha desplegable situada junto **a bc_Visit** en el panel Campos. Arrastre el campo **Visita** y colóquelo en el cuadro **Valores**.

4.  Cambie el tamaño del gráfico circular utilizando los tiradores de las esquinas para que todos los componentes del gráfico sean visibles.

5.  Haga clic en el informe fuera del gráfico circular para anular la selección y seleccione el gráfico de columnas apiladas en el panel **Visualizaciones**.

6.  Presione la flecha desplegable situada junto **a bc_Visit** en el panel Campos. Arrastre el campo **Visita** y colóquelo en el cuadro **Valores**.

7.  Arrastre el campo **Comienzo** y colóquelo en el cuadro de destino **Eje**.

8.  En el panel Visualizaciones, haga clic en **X** junto a **Año** y **Trimestre** para dejar solo los totales de **Mes** y **Día** para el eje.

9.  Cambie el tamaño del gráfico como desee con los identificadores de las esquinas.

10. Pruebe la interactividad del informe:

    1.  Haga clic en varios sectores de creación en el gráfico circular y observe los cambios en el informe de tiempo.

    2.  Haga clic en el gráfico de columnas. Presione la flecha hacia abajo para activar el modo **Explorar en profundidad** (o haga clic con el botón derecho en el gráfico y seleccione **Explorar en profundidad**) y, a continuación, haga clic en una columna para explorar en profundidad hasta el siguiente nivel (días). 
    
    3.  Rastree agrupando y desagrupando datos y seleccione varias barras en el gráfico de columnas de tiempo para observar los cambios en el informe circular.

11. Guarde el trabajo en curso presionando **Guardar**.

# <a name="exercise-2-create-power-bi-dashboard"></a>Ejercicio \#2: Crear un panel de información de Power BI

## <a name="task-1-create-power-bi-dashboard"></a>Tarea \#1: Crear un panel de información de Power BI

1.  Debería tener abierto el informe de la tarea anterior.

2.  Seleccione **Anclar a un panel de información** en el menú. Según el diseño, es posible que deba presionar **...** para mostrar los elementos de menú adicionales.

3.  Seleccione **Nuevo tablero** en la confirmación de **Anclar al tablero**.

4.  Introduzca **Administración del campus** como un **Nombre del tablero**, presione **Anclar elemento en vivo**.

5.  Seleccione **Mi área de trabajo** en la parte superior, seleccione el panel de información **[Su apellido] Administración del campus**.

6.  Un elemento emergente le pedirá que tenga el panel creado. Seleccione **Ir al panel**.

7.  Pruebe la interactividad de los gráficos circulares y de barras que se muestran.

## <a name="task-2-add-visualizations-using-natural-language"></a>Tarea \#2: Agregue visualizaciones usando lenguaje natural

1.  En el panel de información **Administración de campus**, seleccione la barra **Pregunte algo sobre sus datos** en la parte superior.

2.  Introduzca **edificios por número de visitas** en el área de preguntas y respuestas. Se mostrará un gráfico de barras.

3.  Seleccione **Anclar visualización**.

4.  Seleccione **Panel existente**, seleccione el panel de **Administración del campus**, presione **Anclar**.

5.  Haga clic en **Salir de Preguntas y respuestas**.

El panel de **Administración del campus** debe mostrarse con tres objetos visuales. Es posible que deba desplazarse hacia abajo para ver el nuevo objeto visual Preguntas y respuestas.

Su panel de información debería tener un aspecto similar al siguiente:

![](media/5-powerbi-result.png)
