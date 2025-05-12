---
lab:
  title: 'Laboratorio de bonificación: Compilación de una aplicación de lienzo mediante Copilot'
  module: 'Module 3: Describe how to build applications with Microsoft Power Apps'
---

# Laboratorio de bonificación: Compilación de una aplicación de lienzo mediante Copilot

**Inquilinos de WWL: términos de uso** Si, como parte de la impartición de un curso dirigido por un instructor, se te proporciona un inquilino, ten en cuenta que el inquilino está disponible para apoyar los laboratorios prácticos en este tipo de cursos. Los inquilinos no deben compartirse ni usarse para otros fines que no sean los de los laboratorios prácticos. El inquilino empleado en este curso es uno de prueba y no se puede usar ni tener acceso a él después de que la clase haya terminado y tampoco se puede ampliar su uso. Los inquilinos no se deben convertir a suscripciones de pago. Los inquilinos obtenidos como parte de este curso siguen siendo propiedad de Microsoft Corporation y nos reservamos el derecho de acceso y recuperación en cualquier momento. 

## Escenario

Bellows College es una institución educativa que tiene un campus con varios edificios. Los visitantes del campus están actualmente registrados en revistas en papel. La información no se recaba de manera uniforme y no hay forma de recopilar y analizar los datos sobre las visitas de todo el campus.

La administración del campus querría modernizar el sistema de registro de visitantes de los edificios cuyo acceso esté controlado por el personal de seguridad y en los que los anfitriones deban anotar con antelación las visitas y dejar constancia de ellas.

En este laboratorio, usarás Copilot para crear una aplicación de lienzo para registrar visitas. 

## Pasos de alto nivel del laboratorio

Seguiremos el siguiente esquema para diseñar la aplicación de lienzo:

- Descripción de la aplicación que quiere compilar

- Uso de Copilot para modificar la estructura de la tabla auxiliar

 ## Requisitos previos

- Finalización del **Módulo 1 Laboratorio 0: Validación del entorno de laboratorio**

## Ejercicio 1: Uso de Copilot para crear una aplicación de visitas a la universidad.

**Objetivo:** en este ejercicio, crearás una aplicación de lienzo mediante la conexión a una tabla de visitas de Campus.

### Tarea \#1: Creación de la aplicación inicial

1. Vaya a `https://make.powerapps.com`.

2. Es posible que debas volver a autenticarte: selecciona **Iniciar sesión** y sigue las instrucciones si es necesario.

3. Selecciona el entorno **Dev One** en la parte superior derecha si aún no está seleccionado.

4. Selecciona **+Crear** en el panel de navegación izquierdo de la pantalla. En la sección **Crear las aplicaciones**, selecciona **Iniciar con Copilot**.

5. En el cuadro **Introducción a Copilot**, escribe el texto siguiente. `Create an application that logs visits to a college campus`. 

6. Selecciona el botón **Generar**.

Copilot comenzará a crear una estructura de tabla para admitir la aplicación. 

> **IMPORTANTE:** al usar la Inteligencia artificial generativa, no siempre obtendrás los mismos resultados exactos. Es posible que la tabla no coincida exactamente con la tabla creada para otro alumno. 

7. En el lado derecho, selecciona la estructura de tabla en la ventana de Copilot y, a continuación, selecciona **Opciones de tabla**.

8. Selecciona la opción **Una tabla** y, a continuación, selecciona **Aplicar**.
 
    ![Captura de pantalla de la estructura de tabla recién creada](media/bonus-lab-tablestr.png)


> Para ver la estructura de la tabla, selecciona la tabla y haz clic en el botón **Ver datos** 

9. En el cuadro **¿Qué deseas hacer a continuación?**, escribe el texto: Agrega dos columnas, Hora de entrada y Hora de salida en la tabla. Ambas deben ser campos de fecha y hora. 

10. Selecciona el botón **Ir** o presiona **Entrar**. 

11. Desplázate hasta el lado de la tabla y comprueba que se han creado las columnas **Hora de entrada** y **Hora de salida**. 

Como se van a registrar las horas de entrada y salida de los visitantes, ya no se necesita ningún otro campo de fecha de visita. 

12. Busca el campo **Fecha de visita** (u otro equivalente) y, en el cuadro **Describir qué cambiar**, escribe el texto: Quita el campo Fecha de visita (u otro equivalente). 

>Si es necesario, actualiza el nombre del campo que se va a quitar del nombre de tabla pertinente.

13. Selecciona el botón **Ir**. 

14. Quita los campos de fecha adicionales que puedan estar presentes que no sean **Hora de entrada** ni **Hora de salida**. 

Inicialmente, se ha agregado un campo como **Propósito** con formato de tipo de datos de texto. Haremos que Copilot lo cambie a un menú desplegable (Opción). 

15. En el cuadro **¿Qué deseas hacer a continuación**, escribe el texto siguiente: Cambia el campo Propósito a un menú de opciones con las siguientes opciones: Paseo por el campus, Feria profesional, Reunión con el profesor, Asesoramiento para estudiantes, Otros. 

16. Selecciona el botón **Ir**. 

17. Como también se quiere capturar el número de edificio, en el cuadro **¿Qué deseas hacer a continuación?**, escribe lo siguiente: Agrega una columna de edificio. 

18. Selecciona el botón **Ir**. 

19. Cuando estés satisfecho con la tabla, selecciona el botón **Guardar y abrir aplicación**. 

20. Si es necesario, en la pantalla **¿Has terminado de trabajar?**, selecciona **No volver a preguntarme** y, después, selecciona el botón **Guardar y abrir aplicación**. 

![Captura de pantalla de la aplicación recién creada](media/bonus-lab-copilot-02.png)

Enhorabuena, ha usado Copilot para crear una aplicación. 
