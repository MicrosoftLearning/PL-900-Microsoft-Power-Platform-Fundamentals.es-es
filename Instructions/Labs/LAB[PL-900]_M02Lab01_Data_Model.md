---
lab:
    title: 'Laboratorio 1: Modelar datos'
    module: 'Módulo 2: Introducción a Microsoft Dataverse'
---

# Módulo 2: Introducción a Microsoft Dataverse

# Escenario

Bellows College es una institución educativa que tiene un campus con varios edificios. Actualmente se guarda un registro físico de las visitas al campus. La información no se recaba de manera uniforme y no hay forma de recopilar y analizar los datos sobre las visitas de todo el campus. 

La administración del campus querría modernizar el sistema de registro de visitantes de los edificios cuyo acceso esté controlado por el personal de seguridad y en los que los anfitriones deban anotar con antelación las visitas y dejar constancia de ellas.

A lo largo de este curso, creará aplicaciones y realizará la automatización para permitir que el personal de administración y seguridad de Bellows College administre y controle el acceso a los edificios en el campus. 

En este laboratorio, accederá a su ambiente, creará una base de datos de Microsoft Dataverse y creará una solución para seguir los cambios. También creará un modelo de datos que cumpla con los siguiente requisitos:

-   R1: Hacer un seguimiento de las ubicaciones (edificios) del campus en las que se producen las visitas
-   R2: Registrar información básica para identificar y hacer un seguimiento de los visitantes 
-   R3 – Programar, registrar y administrar visitas 

Por último, importará los datos de ejemplo en Microsoft Dataverse.

# Pasos de alto nivel del laboratorio

Para preparar sus entornos de aprendizaje tendrá que:

* crear una solución y un publicador
* añadir los componentes nuevos y existentes que se necesitan para cumplir con los requisitos de la aplicación. Consulte la descripción de los metadatos (tablas y relaciones) en el [documento del modelo de datos](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus%20Management.png). Puede mantener presionada la tecla CTRL y hacer clic o hacer clic con el botón derecho en el vínculo para abrir el documento del modelo de datos en una nueva ventana.

Su solución contendrá varias tablas al completar todas las personalizaciones:

-   Contacto
-   Edificio
-   Visita

## Requisitos previos:

* Finalización del **Módulo 0 Laboratorio 0: Validación del entorno de laboratorio**

## Cuestiones a tener en cuenta antes de comenzar:

* Convención de nomenclatura

* Tipos de datos, restricciones (por ejemplo, la longitud máxima de un nombre)

* Formato de datetime para facilitar la localización

# Ejercicio 1: Creación de la solución

## Tarea 1: Creación de la solución y el publicador

1.  Creación de la solución

    -   Vaya a <https://make.powerapps.com>. Es posible que deba volver a autenticarse: haga clic en **Iniciar sesión** y siga las instrucciones si es necesario.

    -   Seleccione su entorno haciendo clic en **Entorno**, en la esquina superior derecha de la pantalla, y elija su entorno en el menú desplegable.

    -   Seleccione **Soluciones** en el menú de la izquierda y haga clic en **Nueva solución**.

    -   Escriba **[Su apellido] Administración del campus** en **Nombre para mostrar**.

2.  Cree un publicador

    -   En la sección **Editor**, seleccione **+ Editor**

    -   En la ventana emergente, escriba **Bellows College** en **Nombre para mostrar**. 

    -   Escriba **BellowsCollege** en **Nombre**.
    
    -   Escriba **bc** en **Prefijo**.

    -   Haga clic en **Guardar**
    
    -   Haga clic en **Listo** en la ventana emergente.

3.  Complete la creación de la solución.

    -   Luego, haga clic en el menú desplegable **Publicador** y seleccione el publicador **Bellows College**
        que acaba de crear.

    -   Compruebe que la **Versión** está establecida en **1.0.0.0** 
    
    -   Haga clic en **Crear**.

# Ejercicio 2: Crear nuevas tablas y agregar tablas existentes

**Objetivo:** En este ejercicio, agregará la tabla estándar Contacto y creará nuevas tablas personalizadas para Edificios y Visitas en la solución. 

## Tarea 1: Agregar una tabla existente

1.  Haga clic para abrir la solución **Administración del campus** que acaba de crear.

2.  Seleccione **Agregar existente** y luego **Tabla**.

3.  Localice **Contacto** y selecciónelo.

4.  Haga clic en **Siguiente**.

5.  Haga clic en **Seleccionar componentes** debajo de Contacto.

6.  Seleccione la pestaña **Vistas** y elija la vista **Contactos activos**. Haga clic en
    **Añadir**:
    
7.  Haga clic nuevamente en **Seleccionar componentes**.

8.  Seleccione la pestaña **Formulario** y elija el formulario **Contacto**.
    
9.  Haga clic en **Agregar**.

    > Debería tener **1 vista** y **1 formulario** seleccionados. 
    
10.  Vuelva a hacer clic en **Añadir**. Esto agregará la tabla Contacto con la vista y el formulario seleccionados a la solución que acaba de crear.

> Ahora su solución debería tener una tabla: Contacto.
    
## Tarea 2: Crear la tabla Edificio

1.  Debe mantener su explorador abierto en su solución Administración del campus. De lo contrario, abra la solución Administración del campus siguiendo estos pasos:

    * Regístrese en <https://make.powerapps.com> (si aún no lo ha hecho)
    
    * Seleccione **Soluciones** y haga clic para abrir la solución **[su apellido] Administración del campus**
          que acaba de crear.
          
2.  Crear la tabla Edificio

    -   Haga clic en **Nuevo** y seleccione **Tabla**.
    
    -   Escriba **Edificio** en **Nombre para mostrar**. 
    
    -   Haga clic en **Guardar**. Esto iniciará el aprovisionamiento de la tabla en segundo plano, y podrá comenzar a agregar otras tablas y columnas.

## Tarea 3: Crear la tabla y las columnas Visita

La tabla **Visita** contendrá información sobre las visitas al campus, incluidos el edificio, el visitante, la hora programada y la hora real de cada visita. 

Nos gustaría asignar a cada visita un número único que el visitante pueda ingresar e interpretar fácilmente cuando se le solicite durante el proceso de registro de la visita.

> Usamos el comportamiento de **Independiente de la zona horaria** para registrar información de la fecha y hora, ya que el horario de una visita es siempre local para la ubicación del edificio y no debe cambiar cuando se consulta desde una zona horaria diferente. 

1.  Debe mantener su explorador abierto en su solución Administración del campus. De lo contrario, abra la solución Administración del campus siguiendo estos pasos:

    * Regístrese en <https://make.powerapps.com> (si aún no lo ha hecho)
    
    * Seleccione **Soluciones** y haga clic para abrir la solución **[su apellido] Administración del campus**
          que acaba de crear.

2. Crear la tabla Visita

   * Haga clic en **Nuevo** y seleccione **Tabla**.
   
   * Escriba **Visita** en **Nombre para mostrar**. 
   
   * Haga clic en **Guardar**. Esto iniciará el aprovisionamiento de la tabla en segundo plano, y podrá comenzar a agregar otras columnas.

3. Crear la columna Inicio programado

   * Seleccione la tabla **Visitas**.

   * Asegúrese de tener la pestaña **Campos** seleccionada y haga clic en **Agregar columna**.
   
   * Escriba **Inicio programado** para **Nombre para mostrar**.
   
   * Seleccione **Fecha y hora** para **Tipo de datos**.
   
   * En **Obligatorio**, seleccione **Obligatorio**.
   
   * Expanda la sección **Opciones avanzadas**.
   
   * En **Comportamiento**, seleccione **Independiente de la zona horaria**.
   
   * Haga clic en **Listo**.

4.  Crear la columna Fin programado

    * Haga clic en **Agregar columna**.
    
    * Escriba **Fin programado** en **Nombre para mostrar**.
    
    * Seleccione **Fecha y hora** para **Tipo de datos**.
    
    * En **Obligatorio**, seleccione **Obligatorio**.
    
    * Expanda la sección **Opciones avanzadas**.
    
    * En **Comportamiento**, seleccione **Independiente de la zona horaria**.
    
    * Haga clic en **Listo**.
    
5.  Crear la columna Inicio real

    * Haga clic en **Agregar columna**.
    
    * Escriba **Inicio real** para el **Nombre para mostrar**.
    
    * Seleccione **Fecha y hora** para **Tipo de datos**.
    
    * En el campo **Necesario**, déjelo como **Opcional**.
    
    * Expanda la sección **Opciones avanzadas**.
    
    * En **Comportamiento**, seleccione **Independiente de la zona horaria**.
    
    * Haga clic en **Listo**.
    
6.  Crear la columna Fin real

    * Haga clic en **Agregar columna**.
    
    * Escriba **Fin real** para **Nombre para mostrar**.
    
    * Seleccione **Fecha y hora** para **Tipo de datos**.
    
    * En el campo **Necesario**, déjelo como **Opcional**.
    
    * Expanda la sección **Opciones avanzadas**.
    
    * En **Comportamiento**, seleccione **Independiente de la zona horaria**.
    
    * Haga clic en **Listo**.
    
7.  Crear la columna Código

    * Haga clic en **Agregar columna**.
    
    * Escriba **Código** para **Nombre para mostrar**.
    
    * Seleccione **Autonumeración** para **Tipo de datos**.
    
    * Seleccione **Número prefijado de fecha** para **Tipo de autonumeración**.
    
    * Haga clic en **Listo**.
    
8.  Haga clic en **Guardar tabla**.

# Ejercicio 3: Crear relaciones

**Objetivo:** En este ejercicio, agregará relaciones entre las tablas.

## Tarea 1: Crear relaciones

1.  Asegúrese de que todavía está viendo la tabla **Visita** de su solución de **Administración del campus**. De lo contrario, vaya hacia allí.

2.  Crear una relación de visita a contacto

    * Seleccione la pestaña **Relaciones**.
    
    * Haga clic en **Añadir relación** y seleccione **Varios a uno**.
    
    * Seleccione **Contacto** para **Relacionados (uno)**. 
    
    * Escriba **Visitante** para **Nombre para mostrar del campo de búsqueda** 
    
    * Haga clic en **Listo**.
    
3.  Crear relación de visita a edificio

    * Haga clic en **Añadir relación** y seleccione **Varios a uno**.
    
    * Seleccione **Edificio** en **Relacionados (uno)**. 
    
    * Haga clic en **Listo**.
    
4.  Haga clic en **Guardar tabla**.

5.  Seleccione **Volver a soluciones** en la parte superior izquierda.

6.  Seleccione **Publicar todas las personalizaciones**.

# Ejercicio 4: Importar datos

**Objetivo:** En este ejercicio importará datos de ejemplo a la base de datos de Dataverse.

## Tarea 1: Importar solución

En esta tarea, importará una solución que contiene el flujo de Power Automate necesario para completar la importación de datos.

1. Debería tener el archivo **DataImport_managed.zip** almacenado en su escritorio. Si no, descargue la [Solución de importación de datos](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/DataImport_managed.zip?raw=true).

2. Conéctese a <https://make.powerapps.com>.

3. Seleccione su ambiente **Práctica [mis iniciales]** en la parte superior derecha, si aún no está seleccionado.

4. Seleccione **Soluciones** en el panel de navegación izquierdo.

5. Haga clic en **Importar** y luego en **Examinar**. Examine y seleccione **DataImport_managed.zip** desde su escritorio y luego presione **Siguiente**.

>   Puede recibir el siguiente mensaje:
>
>   Faltan dependencias. Instale las siguientes soluciones antes de instalar esta...
>
>   Ese mensaje indica que el modelo de datos no está completo, el
>   prefijo del publicador no es **bc** o los nombres de las tablas **Building** y **Visits**
>   difieren de los nombres enumerados en los pasos anteriores.

6. Presione **Siguiente**. Se le pedirá que restablezca las conexiones. 

7. Expanda el desplegable **Seleccionar una conexión** y seleccione **+Nueva conexión**.

8. Se abre una nueva ventana o pestaña del explorador. Seleccione **Crear** cuando se le pida crear la conexión. Conéctese si es necesario para completar la creación de la conexión.

9. Cierre la pestaña actual para volver a la pestaña **Importar una solución**.

10. Asegúrese de que la conexión que acaba de crear esté seleccionada. Si no ve la conexión, haga clic en **Actualizar** para actualizar la lista de conexiones. 

11. Presione **Importar**.

12. Espere hasta que se complete la importación.

## Tarea 2: Importar datos  

1. Abra la solución **Importar datos**.

2. Compruebe el **Estado** del flujo **Datos de importación**.

3. Si el **Estado** está **Desactivado**, seleccione **[...]** junto a **Importar datos** y, luego, seleccione **Activar**.

   > **Importante:** Si recibe un mensaje de error, compruebe que las tablas y las columnas que creó coincidan con las instrucciones anteriores.

4. Abra el componente **Importar de datos**. Power Automate se abrirá en una nueva pestaña. 

5. Haga clic en **Comenzar** si se muestra en una ventana emergente. 

6. Haga clic en **Ejecutar** luego en **Ejecutar flujo** cuando se le solicite.

7. Haga clic en **Listo**.

8. Espere hasta que la instancia de flujo complete la ejecución. Puede actualizar la tabla **Historial de ejecución de 28 días** para ver cuándo se ha ejecutado el flujo. 

    > El propósito de este flujo era generar datos de ejemplo para los próximos laboratorios. En la siguiente tarea, comprobará que la importación de datos se haya realizado correctamente. 

## Tarea 3: Verificar la importación de datos

1. Vuelva a la pestaña anterior de Power Apps. Haga clic en la ventana emergente **Listo**. 

2. Seleccione **Soluciones** en la barra de navegación izquierda y abra su solución **Administración del campus**.

2. Haga clic para abrir la tabla **Visita**, luego seleccione la pestaña **Datos**.

3. Haga clic en **Visitas activas** en la esquina superior derecha para mostrar el selector de vista, luego seleccione **Todas las columnas**. Esto cambiará la vista que se está utilizando para mostrar los datos de la tabla Visita. 

    > Si no ve **Visitas activas** debido a que la resolución es más pequeña, debería ver un icono con forma de ojo en la misma ubicación.

    > Si la importación se realizó correctamente, debería ver una lista de las filas de visitas.

4. Haga clic en cualquier valor en la columna **Edificio** y confirme que el formulario del edificio se abra en otra ventana. 

5. Cierre la ventana abierta recientemente.

6. Haga clic en cualquier valor en la columna **Visitante** (es posible que deba desplazar la vista hacia la derecha), confirme que el formulario de contacto se abra en una ventana separada.

7. Cierre la ventana abierta recientemente.

# Desafíos

* ¿Consideraría usar la actividad de *cita* como parte de la solución? ¿Qué cambiaría?
* ¿Cómo hacer que el final programado tenga lugar después del inicio programado? 
* ¿Cómo agregar la compatibilidad para múltiples reuniones durante una sola visita?
* ¿Cómo asegurar el acceso al edificio no solo para los contactos externos, sino también para el personal interno?
* ¿Cómo hacer que las visitas a determinados edificios requieran la aprobación de la dirección? ¿Qué cambiaría el proceso de aprobación en el modelo de datos?

