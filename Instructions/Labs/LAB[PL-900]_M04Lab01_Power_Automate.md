---
lab:
    title: 'Laboratorio 6: Cómo crear una solución automatizada'
    module: 'Módulo 4: Comenzar con Power Automate'
---

# Módulo 4: Comience con Power Automate
## Laboratorio: Cómo crear una solución automatizada

## Escenario

Bellows College es una institución educativa que tiene un campus con varios edificios. Los visitantes del campus están actualmente registrados en revistas en papel. La información no se recaba de manera uniforme y no hay forma de recopilar y analizar los datos sobre las visitas de todo el campus. 

La administración del campus querría modernizar el sistema de registro de visitantes de los edificios cuyo acceso esté controlado por el personal de seguridad y en los que los anfitriones deban anotar con antelación las visitas y dejar constancia de ellas.

A lo largo de este curso, creará aplicaciones y realizará la automatización para permitir que el personal de administración y seguridad de Bellows College administre y controle el acceso a los edificios en el campus. 

En este laboratorio, creará flujos de Power Automate para automatizar varias partes de la administración del campus. 

# Pasos de alto nivel del laboratorio

Se han identificado las siguientes condiciones como requisitos que debe implementar para completar el proyecto:

* El código único asignado a cada visitante debe estar disponible antes de su visita.
* El personal de seguridad necesita recibir notificaciones de los visitantes que se quedan durante más tiempo que sus intervalos de tiempo programados.

## Requisitos previos

* Finalización del **Módulo 0 Laboratorio 0: Validación del entorno de laboratorio**
* Finalización del **Módulo 2 Laboratorio 1: Introducción a Microsoft Dataverse**
* Aplicación Personal del campus creada en el **Módulo 3 Laboratorio 2: Cómo crear una aplicación de lienzo (Parte 2)** (para pruebas)
* Contacto de Diego Cabrera creado con una dirección de correo electrónico personal en el **Módulo 3 Laboratorio 4: Cómo crear una aplicación basada en modelo** (para pruebas)

## Cuestiones que tener en cuenta antes de comenzar

-   ¿Cuál es el mecanismo de distribución más apropiado para los códigos de visitante?
-   ¿Cómo se pueden medir las estancias prolongadas y aplicar directivas estrictas?

# Ejercicio 1: Crear flujo de notificación de visita

**Objetivo:** En este ejercicio, creará un flujo de Power Automate que implementa el requisito. El visitante debe recibir un correo electrónico que incluya el código único asignado a la visita.

## Tarea 1: Crear flujo

1.  Abra la solución de Administración del campus.

    -   Inicie sesión en <https://make.powerapps.com>

    -   Seleccione su **entorno.**

    -   Seleccione **Soluciones**.

    -   Haga clic para abrir la solución de **Administración del campus**.

2.  Haga clic en **Nuevo** y seleccione **Automatización**, **Flujo de nube** y luego **Automatizado**. Se abrirá el editor de flujo de Power Automate en una nueva ventana.

3. En **Elija el desencadenador del flujo**, busque **Microsoft Dataverse**.

4. Seleccione el desencadenador **Cuando se agrega, modifica o elimina una flecha** y haga clic en **Crear**.

   * Seleccione **Agregado** para **Tipo de cambio**.
   
   * Seleccione **Visitas** para **Nombre de tabla**.
   
   * Seleccione **Organización** para el **ámbito**.
   
   * En la etapa de desencadenamiento, haga clic en los puntos suspensivos (**...**) y en **Cambiar el nombre**. Cambie el nombre de este desencadenador a **"Cuando se agrega una visita"**. Esta es una buena manera de que usted y otros editores de flujo puedan comprender el propósito de la etapa sin tener que profundizar en los detalles.

5. Seleccione **Nuevo paso**. Esta etapa es necesaria para recuperar la información de los visitantes, incluyendo la dirección de correo electrónico.

6. Busque **Microsoft Dataverse**.

7. Seleccione la acción **Obtener una fila por id.**. 

   * Seleccione **Contactos** como **Nombre de tabla**.
   
   * En el campo **id. de fila**, seleccione **Visitante (valor)** de la lista de contenido dinámico.
   
   * En esta acción, haga clic en los puntos suspensivos (**...**) y en **Cambiar nombre**. Cambie el nombre de esta acción a **"Obtener visitante"**. Esta es una buena manera de que usted y otros editores de flujo puedan comprender el propósito de la etapa sin tener que profundizar en los detalles.

8. Haga clic en **Nuevo paso**. Esta es la etapa que creará y enviará un correo electrónico al visitante.

9. Busque el *correo* y seleccione el conector **Office 365 Outlook** y la acción **Enviar un correo electrónico (V2)**.

   * Si se le solicita que acepte los términos y condiciones para usar esta acción, haga clic en **Aceptar**.
   
   * Seleccione el campo **Para** y **Correo electrónico** en la lista de contenido dinámico. Observe que se encuentra debajo del encabezado **Obtener visitante**. Esto significa que está seleccionando el correo electrónico relacionado con el visitante que buscó en la etapa anterior. 

   * Escriba **Su visita programada a Bellows College** en el campo **Asunto**.

   * Escriba el siguiente texto en el **cuerpo del correo electrónico**:  
        
        > El contenido dinámico debe colocarse donde se nombran los campos entre paréntesis. Se recomienda copiar y pegar todo el texto primero y, luego, agregar contenido dinámico en los lugares correctos.
   
        ```
        Dear {First Name},

        You are currently scheduled to visit Bellows Campus from {Scheduled Start} until {Scheduled End}.

        Your security code is {Code}, please do not share it. You will be required to produce this code during your visit.

        Best regards,

        Campus Administration
        Bellows College
        ```
   
10.  Seleccione el nombre del flujo **Sin título** en la parte superior y cámbiele el nombre a `Visit notification`.

11. Pulse **Guardar**.

    Deje esta pestaña de flujo abierta para la siguiente tarea. El flujo debería tener la siguiente apariencia:

![imagen](https://user-images.githubusercontent.com/78555251/118340724-ccb13300-b4d9-11eb-96c2-c7b005bb9ac0.png)

## Tarea 2: Validar y probar el flujo

1.  Abra una nueva pestaña en su explorador y vaya a <https://make.powerapps.com>.

2.  Haga clic en **Aplicaciones** y seleccione la aplicación **Personal del campus** que creó.

3.  Deje esta pestaña abierta y vuelva a la pestaña anterior con el flujo. 

4.  En la barra de comandos, haga clic en **Probar**. Seleccione **Manualmente** y luego **Guardar y probar**.

5.  Deje abierta la pestaña de flujo y vuelva a la pestaña anterior con la aplicación **Personal del campus**.

6.  Presione **+** para añadir un nuevo registro de visita.

7.  Escriba **John Doe** como **Nombre** y elija cualquier **Edificio**.

8.  Elija a **John Doe** como el **Visitante**.

9.  Elija el **Inicio programado** y **Fechas de finalización programadas** para cualquier fecha en el futuro.

10.  Pulse el icono de **marca de verificación** para guardar la nueva visita.

11.  Vuelva a la pestaña anterior con el flujo que se está probando. Observe cómo se ejecuta el flujo. Si hay algún error, vuelva y compare el flujo con el ejemplo anterior. Si el correo electrónico se envía correctamente, lo recibirá en la bandeja de entrada. 

12.  Haga clic en la flecha hacia atrás de la barra de comandos.

13.  En la sección **Detalles**, observe que el **Estado** está **Habilitado**. Esto significa que el flujo se ejecutará siempre que se cree una nueva Visita, hasta que lo desactive. Cada vez que se ejecute el flujo, verá que se agrega a la lista **Historial de ejecución de 28 días**.

14.  Desactive el flujo haciendo clic en **Apagar** en la barra de comandos. Es posible que deba pulsar los puntos suspensivos (**...**) para ver esta opción.

15.  Cierre esta ventana.

# Ejercicio n.° 2: Cree un flujo de barrido de seguridad

**Objetivo:** En este ejercicio, creará un flujo de Power Automate que implementa el requisito. El barrido de seguridad se realiza cada 15 minutos y se notifica a seguridad si alguno de los visitantes ha sobrepasado la hora programada.

## Tarea 1: Crear un flujo para recuperar registros

1. Abra la solución de Administración del campus.

   -   Inicie sesión en <https://make.powerapps.com>

   -   Seleccione su **Entorno**.

   -   Seleccione **Soluciones**.

   -   Haga clic para abrir la solución de **Administración del campus**.

2. Haga clic en **Nuevo** y seleccione **Automatización**, **Flujo de nube** y luego **Programado**. Se abrirá el editor de flujo de Power Automate en una nueva ventana.

3. Establezca el flujo de modo que se repita cada **15** minutos.

4. Haga clic en **Crear**.

5. Haga clic en **Nuevo paso**. Busque *Current* y seleccione el conector de **Microsoft Dataverse**. Seleccione la acción **Filas de lista**.

   * Especifique **Visitas** como **Nombre de tabla**.
   
   * Haga clic en **Mostrar opciones avanzadas**.

   * Escriba la siguiente expresión como **Filtrar filas**:

   ```
     statecode eq 0 and bc_actualstart ne null and bc_actualend eq null and Microsoft.Dynamics.CRM.OlderThanXMinutes(PropertyName='bc_scheduledend',PropertyValue=15)
   ```
   
   * Para desglosarlo:
       * **statecode eq 0** filtra las visitas activas (aquellas cuyo Estado es igual a Activo).
       * **bc_actualstart ne null** restringe la búsqueda a las visitas en las que Inicio real tenga un valor (es decir, se produjo un registro).
       * **bc_actualend eq null** restringe la búsqueda a las visitas en las que no hubo salida (Final real no tiene valor); 
       * **Microsoft.Dynamics.CRM.OlderThanXMinutes(PropertyName='bc_scheduledend',PropertyValue=15)** restringe las visitas que debieron completarse hace más de 15 minutos.

   * En esta acción, haga clic en los puntos suspensivos (**...**) y en **Cambiar nombre**. Cambie el nombre de esta acción a **“Enumerar las visitas activas que finalizaron hace más de 15 minutos”**. Esta es una buena manera de que usted y otros editores de flujo puedan comprender el propósito de la etapa sin tener que profundizar en los detalles.

6.  Haga clic en **Nuevo paso**. Busque *Aplicar*, Seleccione la acción **Aplicar a cada una** 

7.  Seleccione **valor** del contenido dinámico en el campo **Seleccionar una salida de las etapas anteriores**. Observe que está debajo del encabezado gris **Enumerar las visitas activas que finalizaron hace más de 15 minutos**. Esto significa que está seleccionando la lista de visitas que buscó en la etapa anterior. 

8.  Recuperar datos de Edificios para registro relacionado.

    * Haga clic en **Agregar una acción** dentro de Aplicar para cada bucle.
    
    * Seleccione **Microsoft Dataverse**. 
    
    * Seleccione la acción **Obtener una fila por id.**.
    
    * Seleccione **Edificios** como **Nombre de tabla**.
    
    * Seleccione **Edificio (valor)** como **id. de fila** del contenido dinámico.
    
    * Haga clic en **[...]** junto a **Obtener un registro** y seleccione **Cambiar el nombre**. Escriba **Obtener edificio** como nombre del paso.
    
9.  Recuperar datos de visitantes para registros relacionados.

    * Haga clic en **Agregar una acción** dentro de Aplicar para cada bucle.
    
    * Seleccione **Microsoft Dataverse**.
    
    * Seleccione la acción **Obtener una fila por id.**.
    
    * Seleccione **Contactos** como **Nombre de tabla**.
    
    * Seleccione **Visitante (valor)** como **id. de elemento** del contenido dinámico.
    
    * Haga clic en **[...]** junto a **Obtener un registro** y seleccione **Cambiar el nombre**. Escriba **Obtener visitante** como nombre del paso.
    
10.  Enviar una notificación por correo electrónico

     * Haga clic en **Agregar una acción** dentro de Aplicar para cada bucle. Agregue la acción **Enviar un correo electrónico (V2)** desde la conexión **Office 365 Outlook**.

11.  Introduzca su dirección de correo electrónico como **Para**

12.  Escriba lo siguiente en el campo **Asunto**. **Nombre completo** es un contenido dinámico del paso **Obtener visitante**.

   ```
   {Full Name} overstayed their welcome
   ```
   
13.  Escriba lo siguiente en el campo **Cuerpo**. **Nombre** es un contenido dinámico de la etapa **Obtener edificio**. Es posible que tenga que desplazarse hasta el final de la lista.

   ```
   There is an overstay in building {Name}.
         
   Best,
         
   Campus Security
   ```

14.  Seleccione el nombre de flujo **Sin título** en la esquina superior izquierda y cámbiele el nombre a **Barrido de seguridad**.

15.  Pulse **Guardar**.

    El flujo debería ser algo parecido a lo siguiente:

![Parte 1 del flujo programado del barrido de seguridad](media/4-power-automate-security-sweep-flow.png)

## Tarea 2: Valide y pruebe el flujo

Su flujo comenzará a enviarle correos electrónicos (al correo electrónico que especificó al crear anteriormente el contacto de Diego Cabrera) si hay visitas que cumplan con los requisitos establecidos en el flujo.

1. Compruebe que los registros de visitas:

   1. Tengan estado activo
   
   2. Tengan un final programado pasado (más de 15 minutos).
   
   3. El Inicio real tenga un valor.
   
   > **Nota**: Para ver estos datos, vaya hasta make.powerapps.com en una nueva pestaña. Haga clic en Soluciones en el panel izquierdo para localizar la solución. Seleccione la entidad Visita y luego seleccione la pestaña Datos. Haga clic en Visitas activas en la esquina superior derecha para mostrar el selector de vista y, después, seleccione Todos los campos.
   
2. Navegue hasta el flujo **Barrido de seguridad** si aún no está en él.

3. Cuando se abra el flujo, haga clic en **Probar**.

4. Seleccione **Manualmente**.

5. Haga clic en **Probar** y **Ejecutar flujo**.

6. Cuando el flujo se complete, haga clic en **Listo**. 

7. Expanda **Aplicar a cada uno** y luego expanda la etapa **Enviar una notificación por correo electrónico**. Compruebe los valores **Tema**, **Cuerpo del correo electrónico**.

8. Seleccione la flecha Atrás para volver a los detalles del flujo Barrido de seguridad. Seleccione **Desactivar** en la barra de comandos. Esto es para evitar que el flujo se ejecute según una programación en el sistema de prueba.

# Desafíos

* Agregue el Inicio real y el Final programado al cuerpo del correo electrónico.
* ¿Cómo podría garantizar un formato de fecha fácil de usar en el cuerpo del correo electrónico?
* ¿Es posible generar una tabla con información del exceso del tiempo de permanencia y enviar solo un correo electrónico?
* ¿Se puede generar un código de barras para el código de visita? ¿Cuándo será útil?
