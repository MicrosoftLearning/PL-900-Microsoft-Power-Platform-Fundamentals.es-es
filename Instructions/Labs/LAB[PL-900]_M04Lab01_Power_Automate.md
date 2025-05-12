---
lab:
  title: "Laboratorio\_4: Cómo crear una solución automatizada"
  module: 'Module 4: Describe building automation with Microsoft Power Automate'
---

# Laboratorio 4: Cómo crear una solución automatizada

**Inquilinos de WWL: términos de uso** Si, como parte de la impartición de un curso dirigido por un instructor, se te proporciona un inquilino, ten en cuenta que el inquilino está disponible para apoyar los laboratorios prácticos en este tipo de cursos. Los inquilinos no deben compartirse ni usarse para otros fines que no sean los de los laboratorios prácticos. El inquilino empleado en este curso es uno de prueba y no se puede usar ni tener acceso a él después de que la clase haya terminado y tampoco se puede ampliar su uso. Los inquilinos no se deben convertir a suscripciones de pago. Los inquilinos obtenidos como parte de este curso siguen siendo propiedad de Microsoft Corporation y nos reservamos el derecho de acceso y recuperación en cualquier momento. 

## Escenario

Bellows College es una organización educativa con varios campus y programas. Muchos de los instructores y administradores de Bellow Colleges necesitan asistir a eventos y comprar artículos. Históricamente, el seguimiento de estos gastos ha sido un problema. 

La administración del campus desea modernizar su sistema de informes de gastos y así proporcionar a los empleados un método digital de notificar los gastos. 

A lo largo de este curso, creará aplicaciones y realizará la automatización para que los empleados de Bellows College puedan administrar los gastos. 

En este laboratorio, creará un flujo de Power Automate para enviar por correo electrónico una copia del informe de gastos al crear un nuevo informe de gastos.

## Pasos de alto nivel del laboratorio

Se han identificado las siguientes condiciones como requisitos que debe implementar para completar el proyecto:

- Los empleados deben recibir un correo electrónico cuando se envía un informe de gastos. 

### Requisitos previos

- Finalización del **Módulo 1 Laboratorio 0: Validación del entorno de laboratorio**

## Ejercicio 1: Creación de un flujo de notificación de informe de gastos

**Objetivo:** En este ejercicio, creará un flujo de Power Automate que implementa el requisito. 

### Tarea n.° 1: Creación de un flujo

1. Vaya a `https://make.powerapps.com`.

1. Es posible que deba volver a autenticarse: seleccione **Iniciar sesión** y siga las instrucciones si es necesario.

1. Seleccione el entorno **Dev One** en la parte superior derecha si aún no lo ha hecho.

1. En el panel de navegación izquierdo, seleccione **Flujos**.

1. Si se le solicita, seleccione **Comenzar**.

1. Seleccione **+Nuevo flujo** y elija **Flujo de nube automatizado**.

1. Escriba `Expense Notification` en **Nombre de flujo**.

1. En **Elija el desencadenador del flujo**, busque Dataverse.

1. Seleccione el desencadenador **Cuando se agrega, modifica o elimina una fila** y, luego, elija **Crear**.

1. Rellene las condiciones del desencadenador para el flujo:

    1. Seleccione **Agregado** **Cambiar tipo**.
    
    1. Seleccione **Informes de gastos** para **Nombre de tabla**

    1. Seleccione **Organización** para el **ámbito**.

    1. En el paso del desencadenador, haga clic en los puntos suspensivos ( **...** ) y seleccione **Cambiar nombre**. Cambiar el nombre del paso del desencadenador `When an Expense Report is added` 

Esta es una buena manera de que usted y otros editores de flujo puedan comprender el propósito de la etapa sin tener que profundizar en los detalles.

### Tarea n.°2: Creación de un paso para obtener la fila Informe de gastos

1. Seleccione **+ New step**(+ Nuevo paso). Este paso recuperará la información del informe de gastos, incluida la dirección de correo electrónico.

1. Busque Dataverse

1. Seleccione la acción **Obtener una fila por id.** .

1. Seleccione **Usuarios** como **Nombre de tabla**

1. Seleccione el campo **Id. de fila**. Observe que se abre una ventana para seleccionar **Contenido dinámico** o **Expresiones**.

1. En el campo **id. de fila**, seleccione **Propietario (valor)** de la lista de **Contenido dinámico**. En este paso, busca el propietario de la fila Informe de gastos que se creó para desencadenar este flujo. 

1. En la acción **Obtener una fila por identificador**, seleccione los puntos suspensivos ( **...** ) y elija **Cambiar nombre**. Cambia el nombre de la acción `Get the Owner`

Esta es una buena manera de que tú y otros editores de flujo puedan comprender el propósito de la etapa sin tener que profundizar en los detalles.

### Tarea 3: Creación de un paso para enviar un correo electrónico para confirmar el envío de un informe de gastos

1. Selecciona **+ Nuevo paso**. Este es el paso que enviará un correo electrónico a la persona que envió un informe de gastos.

1. Busca el correo y selecciona la acción **Enviar un correo electrónico (V2)** en el conector de **Office 365 Outlook**.

1. Si se te solicita que aceptes los términos y condiciones para usar esta acción, selecciona **Aceptar**.

1. Selecciona el campo **Para** y escribe tu dirección de correo electrónico personal. (Hay muchas maneras de rellenar dinámicamente una dirección de correo electrónico, pero para este ejercicio vamos a asignarla manualmente).  

1. En el campo **Asunto**, escribe `Your expense report was submitted`

1. Escribe el siguiente texto en el **cuerpo del correo electrónico**:

El contenido dinámico debe colocarse donde se nombran los campos entre paréntesis. Se recomienda copiar y pegar todo el texto primero y, luego, agregar contenido dinámico en los lugares correctos.

    Dear {First Name},
    
    Thank you for submitting your expense report for the total amount of {Report Total Amount} with a due date of {Report Due Date}.
    
     
    Best regards,
    Campus Administration
    Bellows College

1. Resalta el texto **{First Name}**. Reemplázalo por el campo **Nombre** del paso **Obtener el propietario**.

1. Resalta el texto **{Report Total Amount}**. Reemplázalo por el campo **Importe total del informe** del paso **Cuando se envía un informe de gastos**.

1. Resalta el texto **{Report Due Date}**. Reemplázalo por el campo **Fecha de vencimiento del informe** del paso **Cuando se envía un informe de gastos**.

1. Selecciona **Guardar**.

Deja esta pestaña de flujo abierta para la siguiente tarea. El flujo debe tener un aspecto similar al siguiente:

![Captura de pantalla del flujo que acaba de crear](media/lab-4-create-an-automated-solution-01.png)

### Tarea 4: Validación y prueba del flujo

1. Abra una pestaña nueva en el explorador y vaya a `https://make.powerapps.com`.

1. Selecciona el entorno **Dev One** en la parte superior derecha si aún no lo has hecho.

1. Selecciona **Aplicaciones** y abre la **aplicación de seguimiento de gastos**.

1. Deja esta pestaña del explorador abierta y vuelve a la pestaña anterior con el flujo.

1. En la barra de comandos, selecciona **Probar**. Selecciona **Manualmente** y, luego, **Probar**.

1. Ve a la pestaña del explorador con la aplicación basada en modelo abierta.

1. Con el panel de navegación del sitio de la izquierda, selecciona **Informe de gastos**.

1. Selecciona el botón **+Nuevo** para agregar un nuevo registro de **Informe de gastos**.

1. Completa el **registro de Informe de gastos** de la manera siguiente:

    - **Nombre del informe**: `Test Report`

    - **Propósito del informe:** Conferencia

    - **Fecha de vencimiento del informe:** Mañana

1. Selecciona el botón **Guardar &amp; cerrar**.

1. Ve a la pestaña del explorador donde se ejecuta la prueba del flujo. Después de un breve retraso, deberías ver el flujo en ejecución. Aquí es donde puedes detectar cualquier problema en el flujo o confirmar que se ha ejecutado correctamente.

Transcurrido un breve intervalo de tiempo, deberías ver un correo electrónico en la bandeja de entrada. 

>**Nota:** podría ir a la carpeta Correo no deseado.
