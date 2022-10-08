---
lab:
  title: "Laboratorio\_4: Cómo crear una solución automatizada"
  module: 'Module 4: Get Started with Power Automate'
---

# <a name="lab-4-how-to-build-an-automated-solution"></a>Laboratorio 4: Cómo crear una solución automatizada

## <a name="scenario"></a>Escenario

Bellows College is an educational organization with multiple buildings on campus. Campus visitors are currently recorded in paper journals. The information is not captured consistently, and there are no means to collect and analyze data about the visits across the entire campus.

La administración del campus querría modernizar el sistema de registro de visitantes de los edificios cuyo acceso esté controlado por el personal de seguridad y en los que los anfitriones deban anotar con antelación las visitas y dejar constancia de ellas.

A lo largo de este curso, creará aplicaciones y realizará la automatización para permitir que el personal de administración y seguridad de Bellows College administre y controle el acceso a los edificios en el campus.

En este laboratorio, creará un flujo de Power Automate para enviar un correo electrónico a un visitante cuando se programe una visita.

## <a name="high-level-lab-steps"></a>Pasos de alto nivel del laboratorio

Se han identificado las siguientes condiciones como requisitos que debe implementar para completar el proyecto:

- Los contactos deben recibir una notificación por correo electrónico cuando se programe una visita.

## <a name="prerequisites"></a>Prerrequisitos

- Finalización del **Módulo 0 Laboratorio 0: Validación del entorno de laboratorio**
- Finalización del **Módulo 2 Laboratorio 1: Modelado de datos**
- Finalización del **Módulo 2 Laboratorio 3: Cómo crear una aplicación basada en modelo**
- Contacto John Doe creado con una dirección de correo electrónico personal

## <a name="exercise-1-create-visit-notification-flow"></a>Ejercicio 1: Crear flujo de notificación de visita

<bpt id="p1">**</bpt>Objective:<ept id="p1">**</ept> In this exercise, you will create a Power Automate flow that implements the requirement. The visitor should be sent an email that includes the unique code assigned to the visit when a visit is created.

### <a name="task-1-create-a-flow"></a>Tarea \#1: Creación de un flujo

1.  Navigate to <ph id="ph1">&lt;https://make.powerapps.com&gt;</ph>. You may need to reauthenticate - click <bpt id="p1">**</bpt>Sign in<ept id="p1">**</ept> and follow instructions if needed.

2.  Seleccione su ambiente **Práctica [mis iniciales]** en la parte superior derecha, si aún no está seleccionado.

3.  En el panel de navegación izquierdo, seleccione **Flujos**.

4.  Si se le solicita, seleccione **Comenzar**.

5.  Haga clic en **Nuevo flujo** y seleccione **Flujo de nube automatizado**.

6.  Escriba "Notificación de visita" para **Nombre de flujo**.

7.  En **Elija el desencadenador del flujo**, busque **Dataverse**.

8.  Seleccione el desencadenador **Cuando se agrega, modifica o elimina una fila** y, luego, haga clic en **Crear**.

9.  Rellene las condiciones del desencadenador para el flujo:

    1.  Seleccione **Agregado** **Cambiar tipo**.

    2.  Seleccione **Visitas** para **Nombre de tabla**.

    3.  Seleccione **Organización** para el **ámbito**.

    4.  On the trigger step, click the ellipsis (<bpt id="p1">**</bpt>...<ept id="p1">**</ept>) and click <bpt id="p2">**</bpt>Rename<ept id="p2">**</ept>. Rename this trigger <bpt id="p1">**</bpt>"When a visit is added"<ept id="p1">**</ept>. This is a good practice, so you and other flow editors can understand the purpose of the step without having to dive into the details.

### <a name="task-2-create-a-step-to-get-the-visitor-row"></a>Tarea \#2: Crear un paso para obtener la fila del visitante

1.  Bellows College es una institución educativa que tiene un campus con varios edificios.

2.  Busque **Dataverse**.

3.  Seleccione la acción **Obtener una fila por id.** .

4.  Seleccione **Contactos** como **Nombre de tabla**.

5.  Los visitantes del campus están actualmente registrados en revistas en papel.

6.  La información no se recaba de manera uniforme y no hay forma de recopilar y analizar los datos sobre las visitas de todo el campus.

7.  On this action, click the ellipsis (<bpt id="p1">**</bpt>...<ept id="p1">**</ept>) and click <bpt id="p2">**</bpt>Rename<ept id="p2">**</ept>.
        Rename this action <bpt id="p1">**</bpt>"Get the Visitor"<ept id="p1">**</ept>. This is a good practice, so you and other flow editors can understand the purpose of the step without having to dive into the details.

### <a name="task-3-create-a-step-to-send-an-email-to-the-visitor"></a>Tarea \#3: Crear un paso para enviar un correo electrónico al visitante

1.  Click <bpt id="p1">**</bpt>+ New step<ept id="p1">**</ept>. This is the step that will send an email to the visitor.

2.  Busque *correo*, seleccione el conector de **Office 365 Outlook** y la acción **Enviar un correo electrónico (V2)** .

3.  Si se le solicita que acepte los términos y condiciones para usar esta acción, haga clic en **Aceptar**.

4.  Seleccione **Agregar contenido dinámico** en el campo **Para**. 
    
5.  Seleccione **Correo electrónico** en la lista de contenido dinámico.
        > Notice that it is beneath the **Get the visitor** header. This means you
        are selecting the Email that is related to the Visitor that you looked
        up in the previous step.

6.  Escriba **Su visita programada a Bellows College** en el campo **Asunto**.

7.  Escriba el siguiente texto en el **cuerpo del correo electrónico**:

>   Dynamic content needs to be placed where fields are named in brackets. It is recommended to copy &amp; paste all text first and then add dynamic content in the correct places.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
   Dear {First Name},

   You are currently scheduled to visit Bellows Campus from {Scheduled Start} until {Scheduled End}.

   Best regards,

   Campus Administration
   Bellows College
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

8.  Highlight the <bpt id="p1">**</bpt>{First Name}<ept id="p1">**</ept> text. Replace it with the <bpt id="p1">**</bpt>First Name<ept id="p1">**</ept> field from the <bpt id="p2">**</bpt>Get the Visitor<ept id="p2">**</ept> step.

9.  Highlight the <bpt id="p1">**</bpt>{Scheduled Start}<ept id="p1">**</ept> text. Replace it with the <bpt id="p1">**</bpt>Scheduled Start<ept id="p1">**</ept> field <bpt id="p2">**</bpt>When a visit is added<ept id="p2">**</ept> step.

10.  Highlight the <bpt id="p1">**</bpt>{Scheduled End}<ept id="p1">**</ept> text. Replace it with the <bpt id="p1">**</bpt>Scheduled End<ept id="p1">**</ept> field from the <bpt id="p2">**</bpt>When a visit is added<ept id="p2">**</ept> step.

11.  Haga clic en **Save**(Guardar).

Leave this flow tab open for the next task. You flow should look approximately like the following:

![Ejemplo de pasos de flujo.](media/4-Flow.png)

### <a name="task-4-validate-and-test-the-flow"></a>Tarea \#4: Validar y probar el flujo

1.  Abra una pestaña nueva en el explorador y vaya a <https://make.powerapps.com>.

2.  Seleccione su ambiente **Práctica [mis iniciales]** en la parte superior derecha, si aún no está seleccionado.

3.  Haga clic en **Aplicaciones** y seleccione la aplicación basada en el modelo **Administración del campus de Bellows** que creó anteriormente.

3.  Deje esta pestaña del explorador abierta y vuelva a la pestaña anterior con el flujo.

4.  On the command bar, click <bpt id="p1">**</bpt>Test<ept id="p1">**</ept>. Select <bpt id="p1">**</bpt>Manually<ept id="p1">**</ept> and then click <bpt id="p2">**</bpt>Test<ept id="p2">**</ept>.

5.  Vaya a la pestaña del explorador con la aplicación basada en modelo abierta. 

6.  Con el panel de navegación de la izquierda, seleccione **Visitas**.

6. Presione el botón **+ Nuevo** para agregar un nuevo registro de **Visita**.

7. Complete el registro de visita de la siguiente manera:

    -   **Nombre**: Visita de prueba

    -   **Visitante:** John Doe

    -   **Inicio programado:** Mañana a las 8:00 a. m.

    -   **Finalización programada:** Mañana a las 9:00 a. m.

8. Seleccione el botón **Guardar y cerrar**.

9. Navigate to the browser tab with your flow test running. After a short delay, you should see the flow running. This is where you can catch any issues in the flow or confirm that it ran successfully.

After a short delay, you should see an email in your inbox, since you populated John Doe's email as your personal email. Note that it may go to your Junk Email folder.

## <a name="challenges"></a>Desafíos

- Play around with the formatting on the email. How can you make it more professional looking?