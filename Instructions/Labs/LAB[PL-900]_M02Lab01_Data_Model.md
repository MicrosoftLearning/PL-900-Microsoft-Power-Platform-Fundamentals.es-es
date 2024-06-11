---
lab:
  title: "Laboratorio\_1: Modelado de datos"
  module: 'Module 2: Identify foundational components of Microsoft Power Platform'
---

# Laboratorio 1: Modelado de datos

**Inquilinos de WWL: términos de uso** Si, como parte de la impartición de un curso dirigido por un instructor, se le proporciona un inquilino, tenga en cuenta que el inquilino está disponible para apoyar los laboratorios prácticos en este tipo de cursos. Los inquilinos no deben compartirse ni usarse para otros fines que no sean los de los laboratorios prácticos. El inquilino empleado en este curso es uno de prueba y no se puede usar ni tener acceso a él después de que la clase haya terminado y tampoco se puede ampliar su uso. Los inquilinos no se deben convertir a suscripciones de pago. Los inquilinos obtenidos como parte de este curso siguen siendo propiedad de Microsoft Corporation y nos reservamos el derecho de acceso y recuperación en cualquier momento. 

## Escenario

Bellows College es una organización educativa con varios campus y programas. Muchos de los instructores y administradores de Bellow Colleges necesitan asistir a eventos y comprar artículos. Históricamente, el seguimiento de estos gastos ha sido un problema. 

La administración del campus desea modernizar su sistema de informes de gastos y así proporcionar a los empleados un método digital de notificar los gastos. 

A lo largo de este curso, creará aplicaciones y realizará la automatización para que los empleados de Bellows College puedan administrar los gastos.

Por último, importará los datos de ejemplo en Microsoft Dataverse.

## Pasos de alto nivel del laboratorio

Para preparar sus entornos de aprendizaje tendrá que:

- Consulte la descripción de los metadatos (tablas y relaciones) en el [documento del modelo de datos](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus Management.png). Puede mantener presionada la tecla Ctrl y hacer clic con el botón izquierdo o con el botón derecho en el vínculo para abrir el documento del modelo de datos en una nueva ventana.

- Creación de una tabla de gastos

- Agregue algunos datos de ejemplo. 

### Requisitos previos

- Finalización del **Módulo 1 Laboratorio 0: Validación del entorno de laboratorio**

Cuestiones que tener en cuenta antes de comenzar

- Convenciones de nomenclatura: escriba los nombres con cuidado.

## Ejercicio 1: Creación de una nueva tabla

**Objetivo:** En este ejercicio, creará una nueva tabla personalizada para gastos.

### Tarea n.° 1: Creación de una tabla de gastos y sus columnas

La tabla **Gastos** contendrá información sobre los gastos que cada empleado puede enviar, como el motivo, el tipo, la fecha y el importe.

1. Si aún no ha iniciado sesión, inicie sesión en https://make.powerapps.com.

1. En el menú **Entorno** de la parte superior derecha, asegúrese de que el entorno **Dev One** esté seleccionado.

1. En el panel de navegación de la izquierda, seleccione **Tablas**.

1. Seleccione **+ Nueva tabla** y elija **Establecer propiedades avanzadas**.

1. En **Nombre para mostrar**, escriba ”Gastos”.

1. Seleccione **Guardar**.

1. En la sección **Esquema**, seleccione **Columnas**.

### Creación de la columna Fecha del gasto

1. Seleccione **+ Nueva columna**.

1. En **Nombre para mostrar**, escriba ”Fecha del gasto”.

1. En **Tipo de datos**, seleccione **Solo fecha**.

1. Cambie **Requerido** a **Requerido por la empresa**.

1. Expanda **Opciones avanzadas**.

1. En **Ajuste de zona horaria**, seleccione **Solo fecha**.

    >**Nota:** Usamos el comportamiento **Solo fecha** para registrar la información de la fecha, porque la fecha de los gastos no debe cambiar cuando se ven desde una zona horaria diferente.

1. Seleccione **Guardar**.

### Creación de la columna ”Tipo de gasto”

1. Seleccione **+ Nueva columna**.

1. En **Nombre para mostrar**, escriba ”Tipo de gasto”.

1. En **Tipo de datos**, seleccione **Opción**.

1. En **Obligatorio**, seleccione **Opcional**.

1. Establezca **Sincronizar con opción global** en **Sí (recomendado)**.

1. En el campo **Sincronizar esta opción con**, seleccione **Tipo de gasto**.

1. Establezca el campo **Opción predeterminada** en **Ninguno**.

1. Seleccione **Guardar**.

### Creación de la columna ”Propósito del gasto”

1. Seleccione **+ Nueva columna**.

1. En **Nombre para mostrar**, escriba ”Propósito del gasto”.

1. En **Tipo de datos**, seleccione **Opción**.

1. En **Obligatorio**, seleccione **Opcional**.

1. Establezca **Sincronizar con opción global** en **Sí (recomendado)**.

1. En el campo **Sincronizar esta opción con**, seleccione **Propósito del gasto**.

1. Establezca el campo **Predeterminado** en **Ninguno**.

1. Seleccione **Guardar**.

### Creación de la columna ”Descripción del artículo”

1. Seleccione **+ Nueva columna**.

1. En **Nombre para mostrar**, escriba ”Descripción del artículo”.

1. En **Tipo de datos**, seleccione **Varias líneas de texto&gt; Texto sin formato**.

1. Seleccione **Guardar**.

### Creación de la columna ”Importe del gasto”

1. Seleccione **+ Nueva columna**.

1. En **Nombre para mostrar**, escriba ”Importe del gasto”.

1. En **Tipo de datos**, seleccione **Moneda**.

1. Seleccione **Guardar**.

 
## Ejercicio 2: Especificar datos

**Objetivo:** En este ejercicio, escribirá manualmente algunos datos de ejemplo en la nueva tabla. 

### Tarea n.° 1: Modificación de las columnas mostradas

1. Si aún no ha iniciado sesión, inicie sesión en https://make.powerapps.com

1. Seleccione el entorno **Dev One** en la parte superior derecha si aún no lo ha hecho.

1. En el panel de navegación de la izquierda, seleccione **Tablas**.

1. Abra la tabla **Gastos** que creó en el ejercicio anterior.

1. Junto a la columna **Nombre**, seleccione **+26 más**.

1. En el menú que aparece, seleccione las columnas siguientes.

    1. Fecha del gasto

    2. Propósito del gasto 

    3. Tipo de gasto

    4. Importe del gasto

    5. Descripción del elemento

1. Seleccione el botón **Guardar**.

## Tarea n.°2: Adición de un registro de ejemplo

1. Seleccione la **flecha** situada junto a **Editar**. En el menú que aparece, seleccione **Editar en la nueva pestaña**.

1. En la columna **Nombre**, escriba **John Doe**.

1. En la columna **Fecha del gasto**, escriba **xxx**.

1. En **Propósito del gasto**, escriba **Conferencia**.

1. En la columna **Tipo de gasto**, seleccione **Viajes**.

1. En la columna **Importe del gasto**, escriba **750,00**.

1. En **Descripción del artículo**, escriba una breve descripción.

1. Presione el botón de tabulación para avanzar a la siguiente fila y **guardar** el registro.

Enhorabuena, ha creado una nueva tabla y ha agregado datos correctamente.


