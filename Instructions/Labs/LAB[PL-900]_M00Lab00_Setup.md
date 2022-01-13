---
lab:
    title: 'Laboratorio: Validar el entorno de laboratorio'
    module: 'Módulo 0: Introducción al curso'
---

Módulo 0: Introducción al curso
=================================

Escenario
--------

Bellows College es una institución educativa que tiene un campus con varios edificios. Los visitantes del campus están actualmente registrados en revistas en papel. La información no se recaba de manera uniforme y no hay forma de recopilar y analizar los datos sobre las visitas de todo el campus.

La administración del campus querría modernizar el sistema de registro de visitantes de los edificios cuyo acceso esté controlado por el personal de seguridad y en los que los anfitriones deban anotar con antelación las visitas y dejar constancia de ellas.

A lo largo de este curso, creará aplicaciones y realizará la automatización para permitir que el personal de administración y seguridad de Bellows College administre y controle el acceso a los edificios en el campus.

En este laboratorio del Módulo 0, adquirirá un inquilino de prueba de Power Platform y accederá al centro de administración de Power Platform. En el Centro de administración creará el entorno de **práctica** en el que realizará la mayor parte del trabajo de laboratorio.

## Ejercicio 1: Configuración

### Tarea 1: Adquirir su inquilino de prueba de Microsoft Power Platform

1. Copie sus **Credenciales de Microsoft 365** del proveedor de servicios de hosting del laboratorio autorizado.

2. Navegue hasta <https://powerapps.microsoft.com> y haga clic en **Empezar gratis**.

3. Debajo de **Comenzar**, escriba la dirección de correo electrónico de sus credenciales de Microsoft 365 en el cuadro de texto **Escriba su dirección de correo electrónico del trabajo.**

4. Verá un mensaje que le indica que ya tiene una cuenta con Microsoft. Seleccione **Conectarse**.

5. Escriba la contraseña proporcionada por el proveedor de servicios de hosting del laboratorio autorizado. 

6. Seleccione **Sí** para permanecer conectado.

7. Completa la información de su cuenta y selecciona **Comenzar** para registrarse y obtener su prueba de Microsoft Power Platform.  

### Tarea 2: Crear un entorno

1. Acceda a <https://admin.powerplatform.microsoft.com> y inicie sesión con sus credenciales de Microsoft 365 si se le solicita de nuevo.

2. Seleccione **Entornos** y haga clic en **+Nuevo**.

    - En **Nombre**, escriba **Práctica [mis iniciales]**. (Ejemplo: Práctica AJ).
    
    - En **Tipo**, seleccione **Prueba** (no seleccione la opción de prueba basada en suscripción).
    
    - Cambie el botón de alternancia en **¿Crear una base de datos para este entorno?** a **Sí**.
    
    - Deje todas las demás selecciones como predeterminadas y haga clic en **Siguiente**.
    
    - En la siguiente pestaña, deje todas las selecciones predeterminadas y haga clic en **Guardar**.

3. Su entorno de **práctica** debería mostrarse en la lista de entornos. 

    > El aprovisionamiento del entorno podría tardar unos minutos. Actualice la página si es necesario.

# Ejercicio 2: Aprovisionar un portal de Power Apps

**Objetivo:** El aprovisionamiento de un portal de Power Apps puede llevar algún tiempo. En este ejercicio, creará su portal de Power Apps en su entorno para que se pueda iniciar el proceso de aprovisionamiento. Usará este portal en un laboratorio posterior.

## Tarea 1: Crear un portal de Power Apps

1.  Inicie sesión en <https://make.powerapps.com>

2.  Si el **Ambiente** que se muestra en la parte superior derecha no es su ambiente de práctica, seleccione su ambiente.

3.  En la página Inicio, haga clic en el panel **Portal desde cero**, debajo de **Cree su propia aplicación**.

    > Si no ve esta opción, intente alejar la imagen.

4.  Proporcione nuevos detalles del portal.

    -   Escriba **```Bellows College Visitors```** como **Nombre** del portal.

    -   Proporcione una URL única: **algo**.powerappsportals.com (si el nombre ya está en uso, elija uno diferente).

    -   Seleccione un **Idioma** base para el portal.

    -   Haga clic en **Crear**.

    > El proceso de aprovisionamiento del portal se ejecutará entre 30 y 45 minutos. No tiene que esperar, ya que esto continuará mientras pasa al siguiente módulo.
