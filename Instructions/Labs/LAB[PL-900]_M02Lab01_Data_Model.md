---
lab:
  title: "Laboratorio\_1: Modelado de datos"
  module: 'Module 2: Introduction to Microsoft Dataverse'
---

# <a name="lab-1-data-modeling"></a>Laboratorio 1: Modelado de datos

## <a name="scenario"></a>Escenario

Bellows College is an educational organization with multiple buildings on campus. Campus visits are currently recorded in paper journals. The information is not captured consistently, and there are no means to collect and analyze data about the visits across the entire campus.

La administración del campus querría modernizar el sistema de registro de visitantes de los edificios cuyo acceso esté controlado por el personal de seguridad y en los que los anfitriones deban anotar con antelación las visitas y dejar constancia de ellas.

A lo largo de este curso, creará aplicaciones y realizará la automatización para permitir que el personal de administración y seguridad de Bellows College administre y controle el acceso a los edificios en el campus.

In this lab you will access your environment, create a Microsoft Dataverse database, and create a solution to track your changes. You will also create a data model to support the following requirements:

- R1: Hacer un seguimiento de la información de las visitas programadas al campus

- R2: Registrar información básica para identificar y hacer un seguimiento de los visitantes

- R3 – Programar, registrar y administrar visitas

Por último, importará los datos de ejemplo en Microsoft Dataverse.

## <a name="high-level-lab-steps"></a>Pasos de alto nivel del laboratorio

Para preparar sus entornos de aprendizaje tendrá que:

- Refer to the <bpt id="p1">[</bpt>data model document<ept id="p1">](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus%20Management.png)</ept> for the metadata description (tables and relationships). You can hold CTRL+click or right click the link to open the data model document in a new window.
- crear la tabla Visita.
- importación de datos de visita mediante una hoja de cálculo de Excel

## <a name="prerequisites"></a>Prerrequisitos

- Finalización del **Módulo 0 Laboratorio 0: Validación del entorno de laboratorio**

## <a name="things-to-consider-before-you-begin"></a>Cuestiones que tener en cuenta antes de comenzar

- Convenciones de nomenclatura: escriba los nombres con cuidado.

## <a name="exercise-1-create-new-table"></a>Ejercicio 1: Creación de una nueva tabla

**Objetivo:** En este ejercicio, creará una nueva tabla personalizada para las visitas.

### <a name="task-1-create-visit-table-and-columns"></a>Tarea \#1: Crear la tabla y las columnas Visita

La tabla **Visita** contendrá información sobre las visitas al campus, incluidos el visitante, la hora programada y la hora real de cada visita.

Nos gustaría asignar a cada visita un número único que el visitante pueda ingresar e interpretar fácilmente cuando se le solicite durante el proceso de registro de la visita.

> Utilizamos el comportamiento **Independiente de la zona horaria** para registrar la información de fecha y hora, ya que el horario de una visita es siempre local para la ubicación del edificio y no debe cambiar cuando se ve desde una zona horaria diferente.

1. Haga clic en [https://make.powerapps.com](https://make.powerapps.com/) (si aún no ha iniciado sesión).

1. Seleccione su ambiente **Práctica [mis iniciales]** en la parte superior derecha, si aún no está seleccionado.

1. Con el panel de navegación de la izquierda, expanda **Dataverse** y seleccione **Tablas**.

1. Haga clic en **+ Nueva tabla**.

1. Escriba **Visita** en **Nombre para mostrar**.

1. Haga clic en **Save**(Guardar).

1. En la sección **Esquema**, seleccione **Columnas**.

1. Creación de la columna Inicio programado

    - Seleccione **+ Nueva columna**.

    - Escriba **Inicio programado** para **Nombre para mostrar**.

    - Seleccione **Fecha y hora** para **Tipo de datos**.

    - En **Obligatorio**, seleccione **Empresa requerida**.

    - Expanda **Opciones avanzadas**.

    - En **Ajuste de zona horaria**, seleccione **Independiente de la zona horaria**.

    - Haga clic en **Guardar**.

1. Crear la columna Fin programado

    - Haga clic en **+ Nueva columna**.

    - Escriba **Fin programado** en **Nombre para mostrar**.

    - Seleccione **Fecha y hora** para **Tipo de datos**.

    - En **Obligatorio**, seleccione **Empresa requerida**.

    - Expanda **Opciones avanzadas**.

    - En **Ajuste de zona horaria**, seleccione **Independiente de la zona horaria**.

    - Haga clic en **Guardar**.

1. Crear la columna Inicio real

    - Haga clic en **+ Nueva columna**.

    - Escriba **Inicio real** para el **Nombre para mostrar**.

    - Seleccione **Fecha y hora** para **Tipo de datos**.

    - En el campo **Obligatorio**, déjelo como **Opcional**.

    - Expanda **Opciones avanzadas**.

    - En **Ajuste de zona horaria**, seleccione **Independiente de la zona horaria**.

    - Haga clic en **Save**(Guardar).

1. Crear la columna Fin real

    - Haga clic en **+ Nueva columna**.

    - Escriba **Fin real** para **Nombre para mostrar**.

    - Seleccione **Fecha y hora** para **Tipo de datos**.

    - En el campo **Necesario**, déjelo como **Opcional**.

    - Expanda **Opciones avanzadas**.

    - En **Ajuste de zona horaria**, seleccione **Independiente de la zona horaria**.

    - Haga clic en **Guardar**.

1. Crear la columna Código

    - Haga clic en **+ Nueva columna**.

    - Escriba **Código** para **Nombre para mostrar**.

    - Seleccione **Autonumeración** para **Tipo de datos**.

    - Seleccione **Número prefijado de fecha** para **Tipo de autonumeración**.

    - Haga clic en **Guardar**.

1. Crear columna de búsqueda de visitante

    - Haga clic en **+ Nueva columna**.

    - Escriba **Visitante** en **Nombre para mostrar**.

    - Seleccione **Búsqueda** en **Tipo de datos**.

    - Seleccione **Contacto** para la **Tabla relacionada**.

    - Expanda **Opciones avanzadas**.

    - Escriba **visitor_id** en **Nombre de la relación**.

    - Haga clic en **Guardar**.

## <a name="exercise-2-import-data"></a>Ejercicio 2: Importación de datos

**Objetivo:** En este ejercicio importará datos de ejemplo a la base de datos de Dataverse.

### <a name="task-1-import-the-visitsxlsx-file"></a>Tarea \#1: Importar el archivo Visits.xlsx

En esta tarea, importará los datos de una visita desde un archivo de Excel.

1. You should have the <bpt id="p1">**</bpt>Visits.xlsx<ept id="p1">**</ept> file stored on your Desktop. Download <bpt id="p1">[</bpt>Visits.xlsx<ept id="p1">](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/Visits.xlsx)</ept> if you do not.

2. Si aún no ha iniciado sesión, inicie sesión en [https://make.powerapps.com](https://make.powerapps.com/).

3. Seleccione su ambiente **Práctica [mis iniciales]** en la parte superior derecha, si aún no está seleccionado.

4. Con el panel de navegación de la izquierda, expanda **Dataverse** y seleccione **Tablas**.

5. Busque y abra la tabla **Visita** que creó en el ejercicio anterior.

6. En el menú de la parte superior, seleccione la flecha desplegable al lado de **Importar**, y seleccione **Importar datos desde Excel**.

7. En el menú que aparece, seleccione el botón **Cargar**.

8. Bellows College es una institución educativa que tiene un campus con varios edificios.

9. Haga clic en **Asignar columnas** (tenga en cuenta que es posible que sea necesario desplazarse a la derecha para ver esta opción).

10. Asigne las columnas como se indica a continuación:

| Columnas de visitas| Valores de origen |
| - | - |
| Finalización real| fin real |
| Inicio real| inicio real |
| Código| código |
| Nombre| name |
| Final programado| fin programado |
| Scheduled Start| inicio programado |

11. Deje todos los demás campos en **Sin establecer**.

12. En la esquina superior derecha de la pantalla, haga clic en **Guardar cambios**.

13. En la pantalla **Importar datos**, compruebe que el estado de asignación indica que la asignación se realizó correctamente.

14. Haga clic en **Importar** en la esquina superior derecha para completar la importación de los datos.

Actualmente se guarda un registro físico de las visitas al campus.

15. Haga clic en **X** para cerrar el panel de importación de datos.

### <a name="task-2-verify-data-import"></a>Tarea \#2: Comprobar la importación de datos

1. Una vez importados los datos, use el menú de navegación a la izquierda de la pantalla para seleccionar de nuevo la tabla **Visita**.

2. Compruebe que ve los datos importados en la sección **Visitar columnas y datos**.

Enhorabuena, ha creado una tabla nueva y ha importado datos correctamente.