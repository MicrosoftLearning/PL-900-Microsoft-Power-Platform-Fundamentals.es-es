---
lab:
  title: "Laboratorio\_1: Modelado de datos"
  module: 'Module 2: Identify foundational components of Microsoft Power Platform'
---

# Laboratorio 1: Modelado de datos

**Inquilinos de WWL: términos de uso** Si, como parte de la impartición de un curso dirigido por un instructor, se te proporciona un inquilino, ten en cuenta que el inquilino está disponible para apoyar los laboratorios prácticos en este tipo de cursos. Los inquilinos no deben compartirse ni usarse para otros fines que no sean los de los laboratorios prácticos. El inquilino empleado en este curso es uno de prueba y no se puede usar ni tener acceso a él después de que la clase haya terminado y tampoco se puede ampliar su uso. Los inquilinos no se deben convertir a suscripciones de pago. Los inquilinos obtenidos como parte de este curso siguen siendo propiedad de Microsoft Corporation y nos reservamos el derecho de acceso y recuperación en cualquier momento. 

## Escenario

Bellows College es una organización educativa con varios campus y programas. Muchos de los instructores y administradores de Bellow Colleges necesitan asistir a eventos y comprar artículos. Históricamente, el seguimiento de estos gastos ha sido un problema. 

La administración del campus desea modernizar su sistema de informes de gastos y así proporcionar a los empleados un método digital de notificar los gastos. 

A lo largo de este curso, crearás aplicaciones y realizarás la automatización para que los empleados de Bellows College puedan administrar los gastos.

Por último, importarás los datos de ejemplo en Microsoft Dataverse.

## Pasos de alto nivel del laboratorio

Para preparar tus entornos de aprendizaje tendrás que:

- Crear una tabla de gastos

- Agregar algunos datos de ejemplo. 

### Requisitos previos

- Finalización del **Módulo 1 Laboratorio 0: Validación del entorno de laboratorio**

Cuestiones que tener en cuenta antes de comenzar

- Convenciones de nomenclatura: escriba los nombres con cuidado.

## Ejercicio 1: Creación de una nueva tabla

**Objetivo:** en este ejercicio, crearás una nueva tabla personalizada para gastos.

### Tarea 1: Creación de una tabla de gastos y sus columnas

La tabla **Gastos** contendrá información sobre los gastos que cada empleado puede enviar, como el motivo, el tipo, la fecha y el importe.

1. Si aún no has iniciado sesión, inicia sesión en https://make.powerapps.com.

1. En el menú **Entorno** de la parte superior derecha, asegúrate de que el entorno **Dev One** esté seleccionado.

1. En el panel de navegación de la izquierda, selecciona **Tablas**.

1. Selecciona **+ Nueva tabla** y selecciona **Tabla (propiedades avanzadas)** en el menú desplegable.

1. En **Nombre para mostrar**, escribe `Expense`.

1. Selecciona **Guardar**.

1. En la sección **Esquema**, selecciona **Columnas**.

### Creación de la columna Fecha del gasto

1. Selecciona **+ Nueva columna**.

1. En **Nombre para mostrar**, escribe `Expense Date`.

1. En **Tipo de datos**, selecciona **Solo fecha**.

1. Cambia **Requerido** a **Requerido por la empresa**.

1. Expande **Opciones avanzadas**.

1. En **Ajuste de zona horaria**, selecciona **Solo fecha**.

    >**Nota:** usamos el comportamiento **Solo fecha** para registrar la información de la fecha, porque la fecha de los gastos no debe cambiar cuando se ven desde una zona horaria diferente.

1. Selecciona **Guardar**.

### Creación de la columna ”Tipo de gasto”

1. Selecciona **+ Nueva columna**.

1. En **Nombre para mostrar**, escribe `Expense Type`.

1. En **Tipo de datos**, selecciona **Opción**.

1. En **Obligatorio**, selecciona **Opcional**.

1. Establece **Sincronizar con opción global** en **Sí (recomendado)**.

1. En el campo **Sincronizar esta opción con**, selecciona **Tipo de gasto**.

1. Establece el campo **Opción predeterminada** en **Ninguno**.

1. Selecciona **Guardar**.

### Creación de la columna ”Propósito del gasto”

1. Selecciona **+ Nueva columna**.

1. En **Nombre para mostrar**, escribe `Expense Purpose`.

1. En **Tipo de datos**, selecciona **Opción**.

1. En **Obligatorio**, selecciona **Opcional**.

1. Establece **Sincronizar con opción global** en **Sí (recomendado)**.

1. En el campo **Sincronizar esta opción con**, selecciona **Propósito del gasto**.

1. Establezca el campo **Opción predeterminada** en **Ninguno**.

1. Selecciona **Guardar**.

### Creación de la columna ”Descripción del artículo”

1. Selecciona **+ Nueva columna**.

1. En **Nombre para mostrar**, escriba `Item Description`.

1. En **Tipo de datos**, seleccione **Varias líneas de texto&gt; Texto sin formato**.

1. Selecciona **Guardar**.

### Creación de la columna ”Importe del gasto”

1. Selecciona **+ Nueva columna**.

1. En **Nombre para mostrar**, escribe `Expense Amount`.

1. En **Tipo de datos**, selecciona **Moneda**.

1. Selecciona **Guardar**.

 
## Ejercicio 2: Especificación de datos

**Objetivo:** en este ejercicio, escribirás manualmente algunos datos de ejemplo en la nueva tabla. 

### Tarea 1: Modificación de las columnas mostradas

1. Si aún no has iniciado sesión, inicia sesión en https://make.powerapps.com

1. Selecciona el entorno **Dev One** en la parte superior derecha si aún no lo has hecho.

1. En el panel de navegación de la izquierda, selecciona **Tablas**.

1. Abre la tabla **Gastos** que creaste en el ejercicio anterior.

1. Junto a la columna **Nombre**, selecciona **+26 más**.

1. En el menú que aparece, selecciona las columnas siguientes.

    1. Fecha del gasto

    2. Propósito del gasto 

    3. Tipo de gasto

    4. Importe del gasto

    5. Descripción del elemento

1. Selecciona el botón **Guardar**.

## Tarea 2: Adición de un registro de ejemplo

1. Selecciona la **flecha** situada junto a **Editar**. En el menú que aparece, selecciona **Editar en la nueva pestaña**.

1. En la columna **Nombre**, escribe `John Doe`.

1. En la columna **Fecha del gasto**, escribe **xxx**.

1. En **Propósito del gasto**, escribe **Conferencia**.

1. En la columna **Tipo de gasto**, selecciona **Viajes**.

1. En la columna **Importe del gasto**, escribe `750.00`.

1. En **Descripción del artículo**, escribe una breve descripción.

1. Presiona el botón de tabulación para avanzar a la siguiente fila y **guardar** el registro.

Enhorabuena, has creado una nueva tabla y has agregado datos correctamente.


