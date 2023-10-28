---
lab:
  title: "Laboratorio\_1: Modelado de datos"
  module: 'Module 2: Introduction to Microsoft Dataverse'
---

# Laboratorio 1: Modelado de datos

**Inquilinos de WWL: términos de uso** Si, como parte de la impartición de un curso dirigido por un instructor, se le proporciona un inquilino, tenga en cuenta que el inquilino está disponible para apoyar los laboratorios prácticos en este tipo de cursos. Los inquilinos no deben compartirse ni usarse para otros fines que no sean los de los laboratorios prácticos. El inquilino usado en este curso es un inquilino de prueba y no se puede usar ni tener acceso a él después de que la clase haya terminado y no sea apto para la extensión. Los inquilinos no se deben convertir a suscripciones de pago. Los inquilinos obtenidos como parte de este curso siguen siendo propiedad de Microsoft Corporation y nos reservamos el derecho de acceso y recuperación en cualquier momento. 

## Escenario

Bellows College es una institución educativa que tiene un campus con varios edificios. Actualmente se guarda un registro físico de las visitas al campus. La información no se recaba de manera uniforme y no hay forma de recopilar y analizar los datos sobre las visitas de todo el campus.

La administración del campus querría modernizar el sistema de registro de visitantes de los edificios cuyo acceso esté controlado por el personal de seguridad y en los que los anfitriones deban anotar con antelación las visitas y dejar constancia de ellas.

A lo largo de este curso, creará aplicaciones y realizará la automatización para permitir que el personal de administración y seguridad de Bellows College administre y controle el acceso a los edificios en el campus.

En este laboratorio, creará un modelo de datos que cumpla los siguiente requisitos:

- R1: Hacer un seguimiento de la información de las visitas programadas al campus.

- R2: Registrar información básica para identificar los visitantes y hacer un seguimiento de ellos.

- R3: Programar, registrar y administrar visitas.

Por último, importará los datos de ejemplo en Microsoft Dataverse.

Pasos de alto nivel del laboratorio

Para preparar sus entornos de aprendizaje tendrá que:

- Consulte la descripción de los metadatos (tablas y relaciones) en el [documento del modelo de datos](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus%20Management.png). Puede mantener presionada la tecla Ctrl y hacer clic con el botón izquierdo o con el botón derecho en el vínculo para abrir el documento del modelo de datos en una nueva ventana.
- Crear la tabla Visita
- Importación de datos de visita mediante una hoja de cálculo de Excel


## Prerrequisitos

- Finalización del **Módulo 0 Laboratorio 0: Validación del entorno de laboratorio**

Cuestiones que tener en cuenta antes de comenzar

- Convenciones de nomenclatura: escriba los nombres con cuidado.


# Ejercicio 1: Creación de una nueva tabla

**Objetivo:** En este ejercicio, creará una nueva tabla personalizada para las visitas.

## Tarea 1: Creación de la tabla de visitas y las columnas

La tabla **Visita** contendrá información sobre las visitas al campus, incluidos el visitante, la hora programada y la hora real de cada visita.

Nos gustaría asignar a cada visita un número único que el visitante pueda ingresar e interpretar fácilmente cuando se le solicite durante el proceso de registro de la visita.

1.  Si aún no ha iniciado sesión, inicie sesión en <https://make.powerapps.com>. 

1.  En el menú **Entorno** de la parte superior derecha, asegúrese de que el entorno **Práctica** esté seleccionado. 

1.  En el panel de navegación de la izquierda, seleccione **Tablas**.

1.  Seleccione **+ Nueva tabla** y elija **Establecer propiedades avanzadas**. 

1.  En **Nombre para mostrar**, escriba `Visit`.

1.  Seleccione **Guardar**. 

1.  En la sección **Esquema**, seleccione **Columnas**. 


## Crear la columna Inicio programado

1.  Seleccione **+ Nueva columna**. 

1.  En **Nombre para mostrar**, escriba `Scheduled Start`. 

1.  En **Tipo de datos**, seleccione **Fecha y hora**. 

1.  Cambie **Requerido** a **Requerido por la empresa**. 

1.  Expanda **Opciones avanzadas**. 

1.  En **Ajuste de zona horaria**, seleccione **Independiente de la zona horaria**. 

    > **Nota:** Usamos el comportamiento **Independiente de la zona horaria** para registrar la información de fecha y hora, ya que el horario de una visita es siempre local para la ubicación del edificio y no debe cambiar cuando se ve desde una zona horaria diferente. 

1.  Seleccione **Guardar**. 


## Crear la columna Fin programado

1.  Seleccione **+ Nueva columna**. 

1.  En **Nombre para mostrar**, escriba `Scheduled End`.

1.  En **Tipo de datos**, seleccione **Fecha y hora**.

1.  En **Obligatorio**, seleccione **Empresa requerida**.

1.  Expanda **Opciones avanzadas**.

1.  En **Ajuste de zona horaria**, seleccione **Independiente de la zona horaria**.

1.  Seleccione **Guardar**. 


## Crear la columna Inicio real

1.  Seleccione **+ Nueva columna**. 

1.  En **Nombre para mostrar**, escriba `Actual Start`.

1.  En **Tipo de datos**, seleccione **Fecha y hora**.

1.  En el campo **Necesario**, déjelo como **Opcional**.

1.  Expanda **Opciones avanzadas**.

1.  En **Ajuste de zona horaria**, seleccione **Independiente de la zona horaria**. 

1.  Seleccione **Guardar**. 


## Crear la columna Fin real

1.  Seleccione **+ Nueva columna**.

1.  En **Nombre para mostrar**, escriba `Actual End`.

1.  En **Tipo de datos**, seleccione **Fecha y hora**.

1.  En el campo **Necesario**, déjelo como **Opcional**.

1.  Expanda **Opciones avanzadas**.

1.  En **Ajuste de zona horaria**, seleccione **Independiente de la zona horaria**.

1.  Seleccione **Guardar**.


## Crear la columna Código

1.  Seleccione **+ Nueva columna**.

1.  En **Nombre para mostrar**, escriba `Code`.

1.  Seleccione **Autonumeración** para **Tipo de datos**.

1.  Seleccione **Número prefijado de fecha** para **Tipo de autonumeración**.

1.  Seleccione **Guardar**. 


## Crear columna de búsqueda de visitante

1.  Seleccione **+ Nueva columna**.

1.  En **Nombre para mostrar**, escriba `Visitor`.

1.  Seleccione **Búsqueda** > **Búsqueda** en **Tipo de datos**. 

1.  Seleccione **Contacto** para la **Tabla relacionada**. 

1.  Expanda **Opciones avanzadas**. 

1.  Escriba `visitor_id` en **Nombre de la relación**. 

1.  Seleccione **Guardar**.


# Ejercicio 2: Importación de datos

**Objetivo:** En este ejercicio importará datos de ejemplo a la base de datos de Dataverse.

## Tarea \#1: Carga del archivo de Excel en OneDrive

1.  Debe tener el archivo **Visits.xlsx** almacenado en la máquina virtual en **C:/LabFiles**. Si no es así, descargue el archivo [Visits.xlsx](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/Visits.xlsx).

2.  Si aún no ha iniciado sesión, inicie sesión en [https://make.powerapps.com](https://make.powerapps.com/). 

3.  Seleccione su ambiente **Práctica [mis iniciales]** en la parte superior derecha, si aún no está seleccionado.

4.  Seleccione el botón con forma de gofre de la esquina superior izquierda para cambiar las aplicaciones y elija **OneDrive**. (OneDrive podría tardar un poco en configurarse. Seleccione **Su OneDrive está listo** cuando lo vea en la pantalla.

5.  Seleccione **+Agregar nuevo** en el menú y seleccione **Carga de archivos**.

6.  Busque y seleccione el archivo **Visits.xlsx** y elija **Abrir**.

    > **Nota:** El archivo debe encontrarse en la carpeta **Escritorio** > **Todos los archivos** de la máquina virtual.


## Tarea \#2: Creación de un flujo de datos

1.  Si aún no ha iniciado sesión, inicie sesión en <https://make.powerapps.com>. 

2.  En el menú **Entorno** de la parte superior derecha, asegúrese de que el entorno **Práctica** esté seleccionado. 

3.  En el panel de navegación de la izquierda, seleccione **Tablas**. 

4.  Abra la tabla **Visit** que creó en el ejercicio anterior. 

5.  Con el menú de la parte superior, seleccione **Importar** > **Importar datos**.

6.  En el cuadro de diálogo **Elegir origen de datos**, seleccione **Libro de Excel**.

7.  Seleccione la opción **Vincular a archivo**. Seleccione **Examinar OneDrive**. Cuando se le solicite, inicie sesión con sus credenciales de Microsoft 365. Configure el explorador para permitir siempre elementos emergentes. 

8.  Seleccione el archivo **Visits.xlsx** que se cargó en OneDrive en la tarea anterior. 

9.  Seleccione **Next** (Siguiente). 

10. En la pantalla **Power Query** > **Elegir datos**, active el libro **Visitas** de Excel. 

11. Seleccione **Next** (Siguiente). No se vaya de esta página.

12. Seleccione **Next** (Siguiente). 

13. En la sección **Asignar tablas**, en **Configuración de carga**, seleccione **Cargar en una tabla existente**. 

14. En el menú desplegable **Tabla de destino**, seleccione la tabla **crXXX_Visit** (donde XXX es un conjunto aleatorio de letras y números).

15. En la sección **Asignación de columnas**, asigne las columnas a sus columnas de destino correspondientes:

    | Columnas de destino  | Valores de origen   |
    |:---------------------|:----------------|
    | crxxx_ActualEnd      | fin real      |
    | crxxx_ActualStart    | inicio real    |
    | crxxx_Code           | código            |
    | crxxx_Name           | name            |
    | crxxx_ScheduledEnd   | fin programado   |
    | crxxx_ScheduledStart | inicio programado |

16. Seleccione **Next** (Siguiente). 

17. Seleccione **Actualizar manualmente**. 

18. Seleccione **Publicar**. 

    > **Nota:** Los datos pueden tardar unos minutos en importarse en la tabla. No se preocupe si aparecen algunos errores, es normal, y no afectará al resto del curso.


## Tarea 3: Comprobación de la importación de los datos

1.  Una vez importados los datos, use el menú de navegación a la izquierda de la pantalla para seleccionar **Tablas** y abrir la tabla **Visit**.

2.  Compruebe que ve los datos importados en la sección **Visitar columnas y datos**.

Enhorabuena, ha creado una tabla nueva y ha importado datos correctamente.

