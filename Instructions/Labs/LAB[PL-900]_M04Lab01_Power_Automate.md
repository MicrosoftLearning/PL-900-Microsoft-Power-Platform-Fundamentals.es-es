---
lab:
  title: "Laboratorio\_4: Cómo crear una solución automatizada"
  module: 'Module 4: Get Started with Power Automate'
---

# Laboratorio 4: Cómo crear una solución automatizada

**Inquilinos de WWL: términos de uso** Si, como parte de la impartición de un curso dirigido por un instructor, se le proporciona un inquilino, tenga en cuenta que el inquilino está disponible para apoyar los laboratorios prácticos en este tipo de cursos. Los inquilinos no deben compartirse ni usarse para otros fines que no sean los de los laboratorios prácticos. El inquilino usado en este curso es un inquilino de prueba y no se puede usar ni tener acceso a él después de que la clase haya terminado y no sea apto para la extensión. Los inquilinos no se deben convertir a suscripciones de pago. Los inquilinos obtenidos como parte de este curso siguen siendo propiedad de Microsoft Corporation y nos reservamos el derecho de acceso y recuperación en cualquier momento. 

## Escenario

Bellows College es una institución educativa que tiene un campus con varios edificios. Los visitantes del campus están actualmente registrados en revistas en papel. La información no se recaba de manera uniforme y no hay forma de recopilar y analizar los datos sobre las visitas de todo el campus.

La administración del campus querría modernizar el sistema de registro de visitantes de los edificios cuyo acceso esté controlado por el personal de seguridad y en los que los anfitriones deban anotar con antelación las visitas y dejar constancia de ellas.

A lo largo de este curso, creará aplicaciones y realizará la automatización para permitir que el personal de administración y seguridad de Bellows College administre y controle el acceso a los edificios en el campus.

En este laboratorio, creará un flujo de Power Automate para enviar un correo electrónico a un visitante cuando se programe una visita.

## Pasos de alto nivel del laboratorio

Se han identificado las siguientes condiciones como requisitos que debe implementar para completar el proyecto:

- Los contactos deben recibir una notificación por correo electrónico cuando se programe una visita.

## Prerrequisitos

- Finalización del **Módulo 0 Laboratorio 0: Validación del entorno de laboratorio**
- Finalización del **Módulo 2 Laboratorio 1: Modelado de datos**
- Finalización del **Módulo 2 Laboratorio 3: Cómo crear una aplicación basada en modelo**
- Contacto John Doe creado con una dirección de correo electrónico personal.

## Ejercicio 1: Crear flujo de notificación de visita

**Objetivo:** En este ejercicio, creará un flujo de Power Automate que implementa el requisito. Cuando se crea una visita, el visitante debe recibir un correo electrónico que incluya el código único asignado a la visita.

### Tarea \#1: Creación de un flujo

1.  Vaya a <https://make.powerapps.com>. Es posible que deba volver a autenticarse: seleccione **Iniciar sesión** y siga las instrucciones si es necesario.

2.  Seleccione su ambiente **Práctica [mis iniciales]** en la parte superior derecha, si aún no está seleccionado.

3.  En el panel de navegación izquierdo, seleccione **Flujos**.

4.  Si se le solicita, seleccione **Comenzar**.

5.  Seleccione **+Nuevo flujo** y elija **Flujo de nube automatizado**.

6.  Escriba `Visit Notification` en **Nombre de flujo**.

7.  En **Elija el desencadenador del flujo**, busque `Dataverse`.

8.  Seleccione el desencadenador **Cuando se agrega, modifica o elimina una fila** y, luego, elija **Crear**.

9.  Rellene las condiciones del desencadenador para el flujo:

    1.  Seleccione **Agregado** **Cambiar tipo**.

    2.  Seleccione **Visitas** para **Nombre de tabla**.

    3.  Seleccione **Organización** para el **ámbito**.

    4.  En el paso del desencadenador, haga clic en los puntos suspensivos ( **...** ) y seleccione **Cambiar nombre**. Cambiar el nombre del paso del desencadenador `When a Visit is added` 

        Esta es una buena manera de que usted y otros editores de flujo puedan comprender el propósito de la etapa sin tener que profundizar en los detalles.


### Tarea \#2: Crear un paso para obtener la fila del visitante

1.  Seleccione **+ New step**(+ Nuevo paso). Este paso recuperará la información de los visitantes, incluida la dirección de correo electrónico.

2.  Busque `Dataverse`.

3.  Seleccione la acción **Obtener una fila por id.** .

4.  Seleccione **Contactos** como **Nombre de tabla**.

5.  Seleccione el campo **Id. de fila**. Observe que se abre una ventana para seleccionar **Contenido dinámico** o **Expresiones**.

6.  En el campo **Id. de fila**, seleccione **Visitante (valor)** en la lista **Contenido dinámico**. En este paso, busca el contacto para la fila de visita que se creó para desencadenar este flujo. Puesto que la dirección de correo electrónico forma parte de la tabla Contacto, necesitará esta información para enviar el correo electrónico al visitante.

7.  En la acción **Obtener una fila por identificador**, seleccione los puntos suspensivos ( **...** ) y elija **Cambiar nombre**. Cambiar el nombre de la acción `Get the Visitor`
 
    Esta es una buena manera de que usted y otros editores de flujo puedan comprender el propósito de la etapa sin tener que profundizar en los detalles.


### Tarea \#3: Crear un paso para enviar un correo electrónico al visitante

1.  Seleccione **+ Nuevo paso**. Este es el paso que enviará un correo electrónico al visitante.

2.  Busque `mail` y seleccione la acción **Enviar correo electrónico (V2)** en el conector **Office 365 Outlook**.

3.  Si se le solicita que acepte los términos y condiciones para usar esta acción, seleccione **Aceptar**.

4.  Seleccione **Agregar contenido dinámico** en el campo **Para**. 
    
5.  Seleccione **Correo electrónico** en la lista de contenido dinámico.

    > Observa que está debajo del encabezado **Obtener visitante**. Esto significa que vas a seleccionar el correo electrónico relacionado con el visitante que has buscado en el paso anterior.

7.  En el campo **Asunto**, escriba `Your scheduled visit to Bellows College`

8.  Escriba el siguiente texto en el **cuerpo del correo electrónico**:

    > El contenido dinámico debe colocarse donde se nombran los campos entre paréntesis. Se recomienda copiar y pegar todo el texto primero y, luego, agregar contenido dinámico en los lugares correctos.

    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    Dear {First Name},

    You are currently scheduled to visit Bellows Campus from {Scheduled Start} until {Scheduled End}.

    Best regards,

    Campus Administration
    Bellows College
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

8.  Resalte el texto **{First Name}** . Reemplácelo por el campo **Nombre** del paso **Obtener el visitante**.

9.  Resalte el texto **{Scheduled Start}** . Reemplácelo por el campo **Inicio programado** del paso **Cuando se agrega una visita**.

10.  Resalte el texto **{Scheduled End}** . Reemplácelo por el campo **Fin programado** del paso **Cuando se agrega una visita**.

11.  Seleccione **Guardar**.

Deje esta pestaña de flujo abierta para la siguiente tarea. El flujo debería tener la siguiente apariencia:

![Ejemplo de pasos de flujo.](media/4-Flow.png)


### Tarea \#4: Validar y probar el flujo

1.  Abra una pestaña nueva en el explorador y vaya a <https://make.powerapps.com>.

2.  Seleccione su ambiente **Práctica [mis iniciales]** en la parte superior derecha, si aún no está seleccionado.

3.  Seleccione **Aplicaciones** y abra la aplicación basada en el modelo **Bellows Campus Management** que creó anteriormente.

3.  Deje esta pestaña del explorador abierta y vuelva a la pestaña anterior con el flujo.

4.  En la barra de comandos, seleccione **Probar**. Seleccione **Manualmente** y, luego, **Probar**.

5.  Vaya a la pestaña del explorador con la aplicación basada en modelo abierta. 

6.  Con el panel de navegación del sitio de la izquierda, seleccione **Visitas**.

6.  Seleccione el botón **+Nuevo** para agregar un nuevo registro de **Visita**.

7.  Complete el registro de visita de la siguiente manera:

    -   **Nombre**: `Test Visit`

    -   **Visitante:** John Doe

    -   **Inicio programado:** Mañana a las 8:00 a. m.

    -   **Finalización programada:** Mañana a las 9:00 a. m.

8.  Seleccione el botón **Guardar y cerrar**.

9.  Vaya a la pestaña del explorador donde se ejecuta la prueba del flujo. Después de un breve retraso, debería ver el flujo en ejecución. Aquí es donde puede detectar cualquier problema en el flujo o confirmar que se ha ejecutado correctamente.

    Después de una pausa breve, debería ver un correo electrónico en la bandeja de entrada, ya que ha rellenado el correo electrónico de John Doe como su correo electrónico personal. Tenga en cuenta que puede ir a la carpeta Correo no deseado.


## Desafío

- Experimente con el formato en el correo electrónico. ¿Cómo darle un aspecto más profesional?


