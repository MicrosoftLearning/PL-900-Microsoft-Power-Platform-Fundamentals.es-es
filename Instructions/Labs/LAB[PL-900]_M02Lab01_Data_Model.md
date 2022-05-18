---
lab:
  title: 'Laboratorio 1: Modelado de datos'
  module: 'Module 2: Introduction to Microsoft Dataverse'
ms.openlocfilehash: c3ea362eebf9156f069a9ab8635859e6186c1626
ms.sourcegitcommit: 0118c25a230425d0ccba16e6c3922053ee07c183
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2022
ms.locfileid: "144810913"
---
# <a name="module-2-introduction-to-microsoft-dataverse"></a>Módulo 2: Introducción a Microsoft Dataverse

# <a name="scenario"></a>Escenario

Bellows College es una institución educativa que tiene un campus con varios edificios. Actualmente se guarda un registro físico de las visitas al campus. La información no se recaba de manera uniforme y no hay forma de recopilar y analizar los datos sobre las visitas de todo el campus.

La administración del campus querría modernizar el sistema de registro de visitantes de los edificios cuyo acceso esté controlado por el personal de seguridad y en los que los anfitriones deban anotar con antelación las visitas y dejar constancia de ellas.

A lo largo de este curso, creará aplicaciones y realizará la automatización para permitir que el personal de administración y seguridad de Bellows College administre y controle el acceso a los edificios en el campus.

En este laboratorio, accederá a su ambiente, creará una base de datos de Microsoft Dataverse y creará una solución para seguir los cambios. También creará un modelo de datos que cumpla con los siguiente requisitos:

-   R1: Hacer un seguimiento de la información de las visitas programadas al campus

-   R2: Registrar información básica para identificar y hacer un seguimiento de los visitantes

-   R3 – Programar, registrar y administrar visitas

Por último, importará los datos de ejemplo en Microsoft Dataverse.

# <a name="high-level-lab-steps"></a>Pasos de alto nivel del laboratorio

Para preparar sus entornos de aprendizaje tendrá que:

* crear una solución y un publicador
* agregar los componentes nuevos y existentes que se necesitan para cumplir con los requisitos de la aplicación. Consulte la descripción de los metadatos (tablas y relaciones) en el [documento del modelo de datos](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus%20Management.png). Puede mantener presionada la tecla CTRL y hacer clic o hacer clic con el botón derecho en el vínculo para abrir el documento del modelo de datos en una nueva ventana.
* crear la tabla Visita.
* importación de datos de visita mediante una hoja de cálculo de Excel

## <a name="prerequisites"></a>Requisitos previos:

-   Finalización del **Módulo 0 Laboratorio 0: Validación del entorno de laboratorio**

## <a name="things-to-consider-before-you-begin"></a>Cuestiones a tener en cuenta antes de comenzar:

-   Convenciones de nomenclatura: escriba los nombres con cuidado.

# <a name="exercise-1-create-new-table"></a>Ejercicio \#1: Creación de una nueva tabla

**Objetivo:** En este ejercicio, creará una nueva tabla personalizada para las visitas. 

## <a name="task--1-create-visit-table-and-columns"></a>Tarea \#1: Crear la tabla y las columnas Visita

La tabla **Visita** contendrá información sobre las visitas al campus, incluidos el visitante, la hora programada y la hora real de cada visita.

Nos gustaría asignar a cada visita un número único que el visitante pueda ingresar e interpretar fácilmente cuando se le solicite durante el proceso de registro de la visita.

>   Utilizamos el comportamiento de **Zona horaria independiente** para registrar información de la fecha y hora, ya que el horario de una visita es siempre local para la ubicación del edificio y no debe cambiar cuando se ve desde una zona horaria diferente.

1.  Haga clic en <https://make.powerapps.com> (si aún no ha iniciado sesión).

2.  Seleccione su ambiente **Práctica [mis iniciales]** en la parte superior derecha, si aún no está seleccionado.

3.  Con el panel de navegación de la izquierda, expanda Dataverse y seleccione Tablas.

4.  Haga clic en **Nueva tabla**.

5.  Escriba **Visita** en **Nombre para mostrar**.

6.  Haga clic en **Crear**. Esto iniciará el aprovisionamiento de la tabla en segundo plano, y podrá comenzar a agregar otras columnas.

7.  Crear la columna Inicio programado

    1.  Debe estar en la página de columnas de la tabla Visita.

    2.  Asegúrese de tener la pestaña **Campos** seleccionada y haga clic en **Agregar columna**.

    3.  Escriba **Inicio programado** para **Nombre para mostrar**.

    4.  Seleccione **Fecha y hora** para **Tipo de datos**.

    5.  En **Obligatorio**, seleccione **Obligatorio**.

    6.  Expanda la sección **Opciones avanzadas**.

    7.  En **Comportamiento**, seleccione **Independiente de la zona horaria**.

    8.  Haga clic en **Done**(Listo).

8.  Crear la columna Fin programado

    1.  Haga clic en **Agregar columna**.

    2.  Escriba **Fin programado** en **Nombre para mostrar**.

    3.  Seleccione **Fecha y hora** para **Tipo de datos**.

    4.  En **Obligatorio**, seleccione **Obligatorio**.

    5.  Expanda la sección **Opciones avanzadas**.

    6.  En **Comportamiento**, seleccione **Independiente de la zona horaria**.

    7.  Haga clic en **Done**(Listo).

9.  Crear la columna Inicio real

    1.  Haga clic en **Agregar columna**.

    2.  Escriba **Inicio real** para el **Nombre para mostrar**.

    3.  Seleccione **Fecha y hora** para **Tipo de datos**.

    4.  En el campo **Necesario**, déjelo como **Opcional**.

    5.  Expanda la sección **Opciones avanzadas**.

    6.  En **Comportamiento**, seleccione **Independiente de la zona horaria**.

    7.  Haga clic en **Done**(Listo).

10. Crear la columna Fin real

    1.  Haga clic en **Agregar columna**.

    2.  Escriba **Fin real** para **Nombre para mostrar**.

    3.  Seleccione **Fecha y hora** para **Tipo de datos**.

    4.  En el campo **Necesario**, déjelo como **Opcional**.

    5.  Expanda la sección **Opciones avanzadas**.

    6.  En **Comportamiento**, seleccione **Independiente de la zona horaria**.

    7.  Haga clic en **Done**(Listo).

11. Crear la columna Código

    1.  Haga clic en **Agregar columna**.

    2.  Escriba **Código** para **Nombre para mostrar**.

    3.  Seleccione **Autonumeración** para **Tipo de datos**.
    
    4.  Seleccione **Número prefijado de fecha** para **Tipo de autonumeración**.

    5.  Haga clic en **Done**(Listo).

12. Crear columna de búsqueda de visitante

    1.  Haga clic en **Agregar columna**.

    2.  Escriba **Visitante** en **Nombre para mostrar**.

    3.  Seleccione **Búsqueda** en **Tipo de datos**.

    4.  Seleccione **Contacto** para la **tabla Relacionados.**

    5.  Expanda la sección **Opciones avanzadas**.
    
    6.  Escriba **visitor_id** en **Nombre de la relación**.
    
    7.  Haga clic en **Done**(Listo).

13. Haga clic en **Guardar tabla**, en la parte inferior derecha.

# <a name="exercise-2-import-data"></a>Ejercicio \#2: Importación de datos

**Objetivo:** En este ejercicio importará datos de ejemplo a la base de datos de Dataverse.

## <a name="task-1-import-the-visitsxls-file"></a>Tarea \#1: Importe el archivo Visits.xls.

En esta tarea, importará los datos de una visita desde un archivo de Excel. 

1.  Debe tener el archivo **Visits.xls** almacenado en su escritorio. Si no es así, descargue el archivo [Visits.xls](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/Visits.xlsx).

2.  Si aún no ha iniciado sesión, inicie sesión en <https://make.powerapps.com>.

3.  Seleccione su ambiente **Práctica [mis iniciales]** en la parte superior derecha, si aún no está seleccionado.

4.  Con el panel de navegación de la izquierda, expanda **Dataverse** y seleccione Tablas.
    >   Es posible que vea esto como Datos \> Tablas en la pantalla. 

5.  Busque y abra la tabla **Visita** que creó en el ejercicio anterior.

6.  Con el menú de la parte superior, seleccione la flecha desplegable situada junto a **Datos**, seleccione la flecha situada junto a **Obtener datos** y, a continuación, seleccione **Obtener datos desde Excel**.

7.  En el menú que aparece, seleccione el botón **Cargar**.

8.  Busque y seleccione el archivo **Visits.xls** que descargó anteriormente. *(Tenga en cuenta que el archivo puede tardar un minuto o dos en cargarse). No se preocupe si recibe un error que le indica que hay errores de asignación, nos encargaremos de eso más adelante).*

9. Seleccione **Asignar columnas**.

10. Asigne las columnas como se indica a continuación:

    | Columnas de bases de datos de visitas | Valores de origen   |
    |------------------|-----------------|
    | Finalización real       | Finalización real      |
    | Inicio real     | Inicio real    |
    | Código             | Código            |
    | Nombre             | Nombre            |
    | Final programado    | Finalización programada   |
    | Scheduled Start  | Inicio programado |

11. Deje todos los demás campos en **Sin establecer**.

12. En la esquina superior derecha de la pantalla, seleccione **Guardar cambios**.

13. En la pantalla **Importar datos**, compruebe que el estado de asignación indica que la asignación se realizó correctamente.

14. Seleccione **Importar** en la esquina superior derecha para completar la importación de los datos.

**Nota:** *Los datos pueden tardar unos minutos en importarse en la tabla. No se preocupe si aparecen algunos errores, es normal, y no afectará al resto del curso.*

## <a name="task-2-verify-data-import"></a>Tarea \#2: Comprobar la importación de datos

1.  Una vez importados los datos, use el menú de navegación a la izquierda de la pantalla para seleccionar de nuevo la tabla **Visita**.

2.  Tenga en cuenta que tiene muchas pestañas para la tabla Visita. Entre ellas, se incluyen Cikynns, Relaciones, Reglas de negocio, Vistas, etc. 

3.  Seleccione la pestaña **Datos** de la tabla Visita. Esto está debajo de **Tablas** \> **Visita**.

3.  Compruebe que hay registros en la tabla. Para cambiar la vista, seleccione el nombre de la vista en la parte superior derecha y cámbielo a **Todas las columnas**. 

Enhorabuena, ha creado una tabla nueva y ha importado datos correctamente.
