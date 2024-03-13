---
lab:
  title: "Laboratorio\_5: Procedimientos para crear un panel sencillo"
  module: 'Module 5: Get Started with Power BI'
---

## Laboratorio 5: Procedimientos para crear un panel sencillo

**Inquilinos de WWL: términos de uso** Si, como parte de la impartición de un curso dirigido por un instructor, se le proporciona un inquilino, tenga en cuenta que el inquilino está disponible para apoyar los laboratorios prácticos en este tipo de cursos. Los inquilinos no deben compartirse ni usarse para otros fines que no sean los de los laboratorios prácticos. El inquilino empleado en este curso es uno de prueba y no se puede usar ni tener acceso a él después de que la clase haya terminado y tampoco se puede ampliar su uso. Los inquilinos no se deben convertir a suscripciones de pago. Los inquilinos obtenidos como parte de este curso siguen siendo propiedad de Microsoft Corporation y nos reservamos el derecho de acceso y recuperación en cualquier momento. 

## Escenario

Bellows College es una institución educativa que tiene un campus con varios edificios. Los visitantes del campus están actualmente registrados en revistas en papel. La información no se recaba de manera uniforme y no hay forma de recopilar y analizar los datos sobre las visitas de todo el campus.

La administración del campus querría modernizar el sistema de registro de visitantes de los edificios cuyo acceso esté controlado por el personal de seguridad y en los que los anfitriones deban anotar con antelación las visitas y dejar constancia de ellas.

En este laboratorio, creará un panel y un informe de Power BI que visualiza datos sobre las visitas al campus.

**Pasos de alto nivel del laboratorio**

Seguiremos los pasos a continuación para diseñar y crear un panel de control de Power BI:

- Crear un informe con varias visualizaciones de la información de las visitas al campus

- Utilice una consulta de lenguaje natural del usuario para crear visualizaciones adicionales

### Requisitos previos

- Finalización del **Módulo 1 Laboratorio 0: Validación del entorno de laboratorio**

**Cuestiones que tener en cuenta antes de comenzar**

- ¿Quién es la audiencia objetivo del informe?

- ¿Cómo consumirá el informe la audiencia? ¿Dispositivo típico? ¿Ubicación?

- ¿Tiene suficientes datos para visualizar?

- ¿Cuáles son las posibles características que puede usar para analizar datos sobre las visitas?

## Ejercicio n.º 1: Cree informes de Power BI

**Objetivo:** En este ejercicio, creará un informe de Power BI basado en los datos de la hoja de cálculo de Excel que hemos aprovechado en un ejercicio anterior.

### Tarea n.º 1: Preparar el servicio Power BI

1. Debe tener un archivo visits.pbix almacenado en la máquina virtual en la carpeta AllFiles del escritorio. Descargue [visits.pbix](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/visits.pbix) y guárdelo en el equipo, si aún no está allí.

1. Abra una nueva pestaña y vaya a https://app.powerbi.com e inicie sesión si es necesario.

1. Seleccione **Mi área de trabajo** en el panel de navegación izquierdo.

1. Seleccione **Cargar** y, a continuación, **Examinar**.

1. Busque y seleccione el archivo **visits.pbix** que ha descargado anteriormente.

1. Una vez completada la carga de datos, seleccione el informe **visitas**.

    >**Nota:** El tipo está establecido en **Informe**; no seleccione el conjunto de datos.

1. Seleccione **Editar**.

Si el elemento de menú **Editar** no es visible, seleccione los puntos suspensivos en **...** y, a continuación, seleccione **Editar**.

Ahora ya configuró el servicio Power BI para usarlo en sus laboratorios.

### Tarea n.º 2: Crear visualizaciones de tiempo y gráficos

1. Seleccione el icono de **gráfico circular** en el panel **Visualizaciones** para insertar un gráfico.

1. Expanda **bc_Visit** en el panel **Campos**. Arrastre el campo **Building** y colóquelo en el cuadro **Leyenda**.

1. Arrastre el campo **Visit** y colóquelo en el cuadro **Valores**.

1. Cambie el tamaño del gráfico circular utilizando los tiradores de las esquinas para que todos los componentes del gráfico sean visibles.

1. Haga clic en el informe fuera del gráfico circular para anular la selección y seleccione el icono de **gráfico de columnas apiladas** en el panel **Visualizaciones**.

1. Expanda **bc_Visit** en el panel **Campos** si aún no está expandido. Arrastre el campo **Visit** y colóquelo en el cuadro **Eje Y**.

1. Arrastre el campo **Start** y colóquelo en el cuadro **Eje X**.

1. En el panel **Visualizaciones**, seleccione la **x** junto a **Año** y **Trimestre** para dejar solo los totales de **Mes** y **Día** para el eje X.

1. Cambie el tamaño del gráfico como desee con los identificadores de las esquinas.

1. Pruebe la interactividad del informe:

    - Seleccione varios sectores de creación en el gráfico circular y observe los cambios en el gráfico de columnas apiladas.

    - Seleccione el gráfico de columnas apiladas. Seleccione la flecha arriba para **Explorar en profundidad**. Seleccione la flecha abajo para activar el modo **Explorar en profundidad** y, luego, elija una columna para explorar en profundidad hasta el siguiente nivel (días).

    - Rastree agrupando y desagrupando datos y seleccione varias barras en el gráfico de columnas apiladas para observar los cambios en el informe circular.

1. Para guardar el trabajo en curso, seleccione **Guardar este informe**.

## Ejercicio 2: Crear un panel de información de Power BI

### Tarea 1: Crear un panel de información de Power BI

1. Debería tener abierto el informe de la tarea anterior.

1. Seleccione **Anclar a un panel de información** en el menú. Según el diseño, es posible que deba seleccionar el menú de puntos suspensivos **...** para mostrar más opciones.

1. Seleccione **Nuevo tablero** en la confirmación de **Anclar al tablero**.

1. Escriba Campus Management como **Nombre del panel** y seleccione **Anclar en vivo**.

1. Un elemento emergente le pedirá que tenga el panel creado. Seleccione **Ir al panel**.

1. Pruebe la interactividad de los gráficos circulares y de barras que se muestran.

### Tarea n.º 2: Agregar visualizaciones usando lenguaje natural

1. En el panel de información **Administración de campus**, seleccione la barra **Pregunte algo sobre sus datos** en la parte superior.

1. Introduzca edificios por número de visitas en el área de preguntas y respuestas. Se mostrará un gráfico de barras.

1. Seleccione **Anclar visualización**.

1. Seleccione **Panel existente**, elija el panel **Campus Management** y seleccione **Anclar**.

1. Seleccione **Salir de Preguntas y respuestas**.

El panel de **Administración del campus** debe mostrarse con tres objetos visuales. Es posible que deba desplazarse hacia abajo para ver el nuevo objeto visual Preguntas y respuestas.

Su panel de información debería tener un aspecto similar al siguiente:

[![Captura de pantalla del panel que acaba de crear](media/lab-5-power-bi-01.png)](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Instructions/Labs/media/5-powerbi-result.png)

 
