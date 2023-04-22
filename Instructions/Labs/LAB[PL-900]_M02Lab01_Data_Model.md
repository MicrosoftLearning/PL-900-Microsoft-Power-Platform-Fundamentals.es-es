---
lab:
  title: "Laboratorio\_1: Modelado de datos"
  module: 'Module 2: Introduction to Microsoft Dataverse'
---

# Laboratorio 1: Modelado de datos

## Escenario

Bellows College es una institución educativa que tiene un campus con varios edificios. Actualmente se guarda un registro físico de las visitas al campus. La información no se recaba de manera uniforme y no hay forma de recopilar y analizar los datos sobre las visitas de todo el campus.

La administración del campus querría modernizar el sistema de registro de visitantes de los edificios cuyo acceso esté controlado por el personal de seguridad y en los que los anfitriones deban anotar con antelación las visitas y dejar constancia de ellas.

A lo largo de este curso, creará aplicaciones y realizará la automatización para permitir que el personal de administración y seguridad de Bellows College administre y controle el acceso a los edificios en el campus.

En este laboratorio, accederá a su entorno y creará una base de datos de. Microsoft Dataverse. También creará un modelo de datos que cumpla con los siguiente requisitos:

- R1: Hacer un seguimiento de la información de las visitas programadas al campus

- R2: Registrar información básica para identificar y hacer un seguimiento de los visitantes

- R3 – Programar, registrar y administrar visitas

Por último, importará los datos de ejemplo en Microsoft Dataverse.


## Pasos de alto nivel del laboratorio

Para preparar sus entornos de aprendizaje tendrá que:

- Consulte la descripción de los metadatos (tablas y relaciones) en el [documento del modelo de datos](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus%20Management.png). Puede mantener presionada la tecla CTRL y hacer clic o hacer clic con el botón derecho en el vínculo para abrir el documento del modelo de datos en una nueva ventana.
- Crear la tabla Visita
- Importación de datos de visita mediante una hoja de cálculo de Excel

## Prerrequisitos

- Finalización del **Módulo 0 Laboratorio 0: Validación del entorno de laboratorio**

## Cuestiones que tener en cuenta antes de comenzar

- Convenciones de nomenclatura: escriba los nombres con cuidado.


## Ejercicio 1: Creación de una nueva tabla

**Objetivo:** En este ejercicio, creará una nueva tabla personalizada para las visitas.


### Tarea \#1: Crear la tabla y las columnas Visita

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

## Ejercicio 2: Importación de datos

**Objetivo:** En este ejercicio importará datos de ejemplo a la base de datos de Dataverse.

### Tarea 1.1: Carga del archivo de Excel en OneDrive

1. Debe tener el archivo **Visits.xlsx** almacenado en la máquina virtual en **C:/LabFiles**. Si no es así, descargue el archivo [Visits.xlsx](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/Visits.xlsx).

2. Si aún no ha iniciado sesión, inicie sesión en [https://make.powerapps.com](https://make.powerapps.com/).

3. Seleccione su ambiente **Práctica [mis iniciales]** en la parte superior derecha, si aún no está seleccionado.

4. Haga clic en el botón con forma de gofre de la esquina superior izquierda para cambiar las aplicaciones y seleccione **OneDrive**. (OneDrive podría tardar un poco en configurarse. Haga clic en **El OneDrive está listo** cuando lo vea en la pantalla.

5. Haga clic en **Cargar** en el menú superior y seleccione **Archivos**.

6. Busque y seleccione el archivo **Visits.xlsx** y haga clic en **Abrir**.

 **Nota**: Este archivo se encuentra en la carpeta **Todos los archivos** de la máquina.
 
### Tarea 1.2: Creación de un flujo de datos

1. Si aún no ha iniciado sesión, inicie sesión en [https://make.powerapps.com](https://make.powerapps.com/).

2. Seleccione su ambiente **Práctica [mis iniciales]** en la parte superior derecha, si aún no está seleccionado.

3. Con el panel de navegación de la izquierda, expanda **Dataverse** y seleccione **Tablas**.

4. Busque y abra la tabla **Visita** que creó en el ejercicio anterior.

5. En el menú de la parte superior, seleccione la flecha desplegable al lado de **Importar** y seleccione **Importar datos**.

6. En el cuadro de diálogo **Elegir origen de datos**, seleccione **Libro de Excel**.

7. Seleccione la opción **Vincular a archivo**. Haga clic en **Browse OneDrive** (Examinar OneDrive). Cuando se le solicite, inicie sesión con sus credenciales de Microsoft 365.

8. Seleccione el archivo **Visits.xlsx** que se ha cargado en OneDrive y haga clic en **Seleccionar**.

9. Haga clic en **Next**.

10. En **Elegir datos**, active la casilla situada junto al libro de Excel denominado **Visits**.

11. Haga clic en **Next**. No se vaya de esta página.

12. Haga clic en **Next**.

13. En la sección **Map tables** (Asignar tablas), seleccione **Load to existing table** (Cargar en la tabla existente) en la **configuración de carga**.

14. En el menú desplegable **Tabla de destino**, seleccione el nombre de la tabla que comienza por **crXXX_visit** (donde XXX es un conjunto aleatorio de letras y números).

15. En **Asignación de columnas**, asigne las columnas a sus columnas de destino correspondientes.

| Columnas de destino  | Valores de origen   |
|:---------------------|:----------------|
| crxxx_ActualEnd      | fin real      |
| crxxx_ActualStart    | inicio real    |
| crxxx_Code           | código            |
| crxxx_Name           | name            |
| crxxx_ScheduledEnd   | fin programado   |
| crxxx_ScheduledStart | inicio programado |

16. Haga clic en **Next**.

17. Seleccione **Actualizar manualmente**.

18. Haga clic en **Publicar**.

**Nota:** Los datos pueden tardar unos minutos en importarse en la tabla. No se preocupe si aparecen algunos errores, es normal, y no afectará al resto del curso.

### Tarea 3: Comprobación de la importación de los datos

1. Una vez importados los datos, use el menú de navegación a la izquierda de la pantalla para seleccionar de nuevo la tabla **Visita**.

2. Compruebe que ve los datos importados en la sección **Visitar columnas y datos**.

Enhorabuena, ha creado una tabla nueva y ha importado datos correctamente.
