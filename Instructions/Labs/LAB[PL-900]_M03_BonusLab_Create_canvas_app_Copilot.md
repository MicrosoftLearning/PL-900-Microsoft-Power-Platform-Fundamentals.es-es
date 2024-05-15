---
lab:
  title: 'Laboratorio de bonificación: Compilación de una aplicación de lienzo mediante Copilot'
  module: 'Module 3: Get started with Power Apps'
---

# Laboratorio de bonificación: Compilación de una aplicación de lienzo mediante Copilot

**Inquilinos de WWL: términos de uso** Si, como parte de la impartición de un curso dirigido por un instructor, se le proporciona un inquilino, tenga en cuenta que el inquilino está disponible para apoyar los laboratorios prácticos en este tipo de cursos. Los inquilinos no deben compartirse ni usarse para otros fines que no sean los de los laboratorios prácticos. El inquilino empleado en este curso es uno de prueba y no se puede usar ni tener acceso a él después de que la clase haya terminado y tampoco se puede ampliar su uso. Los inquilinos no se deben convertir a suscripciones de pago. Los inquilinos obtenidos como parte de este curso siguen siendo propiedad de Microsoft Corporation y nos reservamos el derecho de acceso y recuperación en cualquier momento. 

## Escenario

Bellows College es una institución educativa que tiene un campus con varios edificios. Los visitantes del campus están actualmente registrados en revistas en papel. La información no se recaba de manera uniforme y no hay forma de recopilar y analizar los datos sobre las visitas de todo el campus.

La administración del campus querría modernizar el sistema de registro de visitantes de los edificios cuyo acceso esté controlado por el personal de seguridad y en los que los anfitriones deban anotar con antelación las visitas y dejar constancia de ellas.

En este laboratorio, usará Copilot para crear una aplicación de lienzo para registrar visitas. 

## Pasos de alto nivel del laboratorio

Seguiremos el siguiente esquema para diseñar la aplicación de lienzo:

- Descripción de la aplicación que quiere compilar

- Uso de Copilot para modificar la estructura de la tabla auxiliar

 ## Requisitos previos

- Finalización del **Módulo 1 Laboratorio 0: Validación del entorno de laboratorio**

## Ejercicio 1: Use Copilot para crear una aplicación de visitas a la universidad.

**Objetivo:** En este ejercicio, creará una aplicación de lienzo mediante la conexión a una tabla de visitas de Campus.

### Tarea \#1: Creación de la aplicación inicial

1. Vaya a https://make.powerapps.com.

2. Es posible que deba volver a autenticarse: seleccione **Iniciar sesión** y siga las instrucciones si es necesario.

3. Seleccione el entorno **Dev One** en la parte superior derecha si aún no está seleccionado.

4. En el cuadro **Describir la aplicación que quiere crear**, escriba el texto siguiente. Cree una aplicación que registre las visitas a un campus universitario. 

5. Seleccione el botón **Ir**.

Copilot comenzará a crear una estructura de tabla para admitir la aplicación. 

> **IMPORTANTE:** Al usar la Inteligencia artificial generativa, no siempre obtendrá los mismos resultados exactos. Es posible que la tabla no coincida exactamente con la tabla creada para otro alumno. 

6. En el cuadro **Describir qué cambiar**, escriba el texto: Agregue dos columnas, Hora de entrada y Hora de salida. Las dos deben ser campos de fecha y hora.  

7. Seleccione el botón **Ir** o presione **Entrar**. 

8. Desplácese hasta el lado de la tabla y compruebe que se han creado las columnas **Hora de entrada** y **Hora de salida**. 

Como se van a registrar las horas de entrada y salida de los visitantes, ya no se necesita ningún otro campo de fecha de visita. 

9. Busque el campo **Fecha de visita** (u otro equivalente) y, en el cuadro **Describir qué cambiar**, escriba el texto Quitar el campo Fecha de visita. 

10. Seleccione el botón **Ir**. 

11. Quite los campos de fecha adicionales que puedan estar presentes que no sean **Hora de entrada** ni **Hora de salida**. 

Inicialmente, se ha agregado un campo como **Propósito** con formato de tipo de datos de texto. Hará que Copilot lo cambie a un menú desplegable (Opción). 

12. En el cuadro **Describir qué cambiar**, escriba el texto siguiente: Cambie el campo Propósito a un menú de opciones con las siguientes opciones: Paseo por el campus, Feria profesional, Reunión con el profesor, Asesoramiento para estudiantes, Otros. 

13. Seleccione el botón **Ir**. 

14. Como también se quiere capturar el número de edificio, en el cuadro **Describir qué cambiar**, escriba lo siguiente: Agregar una columna de edificio. 

15. Seleccione el botón **Ir**. 

16. Cuando esté satisfecho con la tabla, seleccione el botón **Crear aplicación**. 

17. Si es necesario, en la pantalla de **bienvenida a Power Apps Studio**, active la casilla **No volver a mostrar** y, luego, seleccione el botón **Omitir**. 

![Captura de pantalla de la aplicación recién creada](media/bonus-lab-copilot-01.png)

Enhorabuena, ha usado Copilot para crear una aplicación. 
