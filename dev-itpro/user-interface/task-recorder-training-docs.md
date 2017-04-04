---
title: "Crear documentación o formación con las grabaciones de tareas"
description: "Este tema explica qué son Grabador de tareas y guías de la tarea, cómo crear registros de la tarea, y cómo personalizar las guías de la tarea de Microsoft y incluirlas en la Ayuda."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SysHelpSetup
audience: Application User, IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 25391
ms.assetid: 59bf39f8-1464-441e-8b23-9a856c73471b
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: b21fd97426b331726c12ea29f89817a46dd445c3
ms.openlocfilehash: 38bce4a843f0db575c8d1ba08b7dc2ece8366663
ms.lasthandoff: 03/31/2017


---

# <a name="create-documentation-or-training-using-task-recordings"></a>Crear documentación o formación con las grabaciones de tareas
Este tema explica qué son Grabador de tareas y guías de la tarea, cómo crear registros de la tarea, y cómo personalizar las guías de la tarea de Microsoft y incluirlas en la Ayuda.

<a name="learn-about-task-recorder"></a>Información sobre el grabador de tareas
-------------------------

El Grabador de tareas es un Microsoft Dynamics 365 para la herramienta de las operaciones que puede usar para registrar acciones que se admite la interfaz de usuario (UI) del producto. Al usar el Grabador de tareas, se capturan todos los eventos que realiza en la IU que se ejecutan en relación con el servidor, entre los que se incluyen la adición de valores, el cambio de configuración y la eliminación de datos. Los pasos que grabe se denominan conjuntamente *grabación de tareas*. Las grabaciones de tareas se pueden usar de muchas maneras:

-   **Las grabaciones de tareas se pueden reproducir como guías de tareas.** Le orienta acerca de la tarea son un residuo entero de Dynamics 365 para la experiencia de la Ayuda de las operaciones. Guía de la tarea es una experiencia controla, dirigida, interactiva a través de los pasos del proceso empresarial. Al usuario se le indica que complete cada paso mediante un aviso móvil (o "burbuja"), que se animará a través de la IU y señalará al elemento de la IU con el que debe interactuar el usuario. La “burbuja” también proporciona información sobre cómo interactuar con el artículo, por ejemplo “haga clic aquí” o “en este campo, escriba un valor.” Guía de la tarea se ejecuta con el conjunto de datos actual del usuario y los datos se especifica que se guarda en el entorno de usuario.
-   ** Los registros de la tarea se pueden aparecer como pasos del procedimiento en el panel de la Ayuda. ** Puede usar los registros de la tarea del panel de la Ayuda para buscar y de la pantalla. ¿Puede tener acceso al panel de la Ayuda haciendo clic en **? ** ¿el icono de la barra de navegación superior o bien puede usar la combinación de teclas de método abreviado, ** Ctrl+Shift+? **. Puede leer los pasos de una tarea que registra en el panel de la Ayuda, o puede optar por jugar el registro como una guía de la tarea se le guiará tan con la interfaz de usuario.
-   **Los registros de tareas se pueden guardar en BPM.** Puede guardar su grabación de tareas en una línea de una jerarquía en una biblioteca de Modelador de procesos empresariales (BPM) en Lifecycle Services (LCS). Se generará una lista de pasos y un diagrama de flujo de proceso empresarial desde la grabación. Tareas a registros que se han guardado a una biblioteca de BPM se pueden mostrar en Dynamics 365 para las operaciones como ayuda.
-   **Las grabaciones de tareas se pueden guardar como documentos de Word.** Esto le permite producir con facilidad guías de formación imprimibles.

Puede crear sus propias registros de la tarea, registros de la tarea del juego proporcionados por Microsoft, o modificar Microsoft- proporcionó registros de la tarea para reflejar la configuración. Para obtener más información acerca del Grabador de tareas, consulte [Grabador de tareas en Dynamics 365 para las operaciones task-recorder.md] ().

## <a name="plan-your-task-recording"></a>Planear su grabación de tareas
Si está creando una nueva grabación de tareas o basando su grabación en una grabación de tareas de Microsoft, tenga en cuenta la siguiente información.

-   Planee su grabación como planearía un vídeo. Tome todas sus decisiones con antelación.
-   Recorra el proceso empresarial una o dos veces sin grabarlo para comprender los pasos.
-   Cuando recorra el proceso antes de grabar, observe dónde usa teclas de método abreviado o la tecla **Entrar**, para que pueda evitar usarlas durante la grabación real.
-   Identifique lo siguiente:
    -   ¿Desea agrupar los pasos juntos en subtareas? Las subtareas separan visualmente secciones de un proceso. Por ejemplo, si crea una grabación para "Crear y liberar un producto", puede que desee agrupar de manera conjunta los pasos necesarios para crear un producto y, a continuación, agrupar de manera conjunta los pasos que se requieren para liberarlo. Las subtareas también hacen que los procesos más largos sean más sencillos de leer.
    -   ¿Desea agregar anotaciones y, de ser así, dónde? Vea "Comprender los diferentes tipos de anotaciones" a continuación para obtener más información.
    -   ¿Qué valores agregará en los distintos campos conforme completa los pasos del proceso empresarial? Resulta buena idea saber qué seleccionará o especificará conforme continúa para no realizar un seguimiento hacia atrás o corregir errores conforme graba.

**Escriba la descripción y las anotaciones por adelantado**

-   Al comienzo de cada grabación de tareas, hay un campo de descripción que le permite especificar una introducción para el registro. Es una buena idea escribir y guardar la descripción por adelantado en un documento independiente para poder copiarlo y pegarlo en la grabación de tareas cuando graba. De esa manera, puede pasar tiempo restringiendo el texto cuando no se encuentra en el proceso de grabación. Cortar y pegar el texto hace que el proceso de grabación sea más rápido y funcione mejor.
-   Para cada paso de una grabación de tareas, puede crear anotaciones. Durante la reproducción de una guía de tareas, las anotaciones aparecen en la "burbuja" como notas por encima o por debajo del texto para el paso. Cuando se vistas como texto en el panel de la Ayuda, las anotaciones aparecen como texto escrito en el paso. Como con la descripción, es una buena idea escribir y guardar sus anotaciones en un documento independiente. Cuando registre la grabación de tareas, corte y pegue las anotaciones desde ese documento.

**Comprender los diferentes tipos de anotaciones** Todas las anotaciones son opcionales. Agréguelas solo cuando proporcionen información útil al usuario.

-   ** Puesto **: Una anotación del puesto aparecerá antes de que el texto del paso que el Grabador de tareas genera automáticamente. En la guía de la tarea, la anotación del título aparece sobre el texto generado automáticamente. Use este tipo de anotación para explicar por qué el usuario realiza el paso o para dar un contexto adicional.

Este es el panel de edición que ve al agregar una anotación conforme crea su grabación. Especifique una anotación del puesto en el cuadro **Puesto**. 

![screen1 [] (. /media/screen1.png])(. /media/screen1.png) 

Así es como se muestra la anotación del puesto en la “burbuja” de la guía de tareas. 

![screen2 [] (. /media/screen2.png])(. /media/screen2.png)

-   **Notas:** Una anotación de notas aparecerá después del texto del paso que el grabador de tareas genera automáticamente. En la guía de tareas solo será visible si el usuario hace clic en el vínculo **Muestra más** de la burbuja de la guía de tareas. Use este tipo de anotación para describir cualquier cosa que un usuario tenga que saber para completar el paso.

Este es el panel de edición que ve al agregar una anotación conforme crea su grabación. Especifique una anotación de notas en el cuadro **Notas**. 

![screen3 [] (. /media/screen3.png])(. /media/screen3.png) 

Esto es el que los ser de la anotación de las notas de la “burbuja” en la guía de la tarea.

![screen4 [] (. /media/screen4.png])(. /media/screen4.png)

-   ** Paso de la información: ** Estas anotaciones se crean por la derecha que hace clic en un control o en cualquier lugar en un formulario &lt; ** Grabador de tareas ** &lt; ** agregar el paso de la información. ** Los pasos de la información aparecen como un paso de numeración en los puntos lo introduce automáticamente, aunque no se registró ninguna acción en la interfaz de usuario. Puede agregar un paso de información de nivel de formulario o un paso de información asociado con un control. Cuando un paso de información está asociado a un formulario, la "burbuja" de la guía de tareas aparecerá en algún lugar del formulario, sin puntero, cuando se reproduzca la guía de tareas. Cuando un paso de la información está asociado con un control, la guía “burbuja” de la tarea va a notificar a control cuando se tiene la guía de la tarea. En el panel de la Ayuda, una anotación del paso de la información aparecerá como un paso de numeración con el texto que ha especificado. La información de uso Pasos preparar el usuario para los pasos siguientes, para describir los pasos que se deban exterior terminado de Dynamics 365 para las operaciones, o para hacer referencia a otras registros (aunque no puede crear hyperinks en anotaciones.).

**Determine el tiempo para realizar la grabación**

-   El usuario generalmente leerá o reproducirá la grabación desde el principio al fin; por tanto, no combine pasos o tareas que se realicen mejor por separado.
-   Intente no grabar un escenario largo que abarque múltiples subprocesos. Por ejemplo, "Dirigir el departamento de servicio de atención al cliente en la tienda" es demasiado amplia; divídala en tareas más breves como "Aceptar devoluciones" y "Agregar a tarjeta regalo".
-   Si una tarea se puede llevar a cabo como parte de varios procesos empresariales, cree una grabación independiente para ella y podrá consultarla en las demás grabaciones.
-   Si el proceso implica varias tareas que la persona probablemente realiza de una vez, puede mantener las tareas en una grabación, por ejemplo, "Configurar y asignar perfiles de funcionalidad".
-   Si es algo que alguien hace una vez (como la configuración) y después otra tarea que puede realizar inmediatamente a continuación pero que pueda realizar repetidamente y, por sí mismo, divídalas en dos grabaciones de tareas.

** Decida en la que, en la interfaz de usuario, para iniciar el registro ** la página que se encuentra en al iniciar registrar una tarea que registra los efectos que paginan la guía de tarea se muestra para. Por ejemplo, si desea que la tarea que registra para que ésta aparezca en el panel de la Ayuda cuando un usuario hace clic en Ayuda en los parámetros de contabilidad general página, debe comenzar su registro en la página de parámetros de contabilidad general. **Guarde las grabaciones como archivos .axtr** Cuando haya acabado de crear o editar una grabación de tareas, se le presentarán varias opciones para cómo desea descargar o guardar la grabación. Puede descargar el archivo como paquete de grabación de tareas (.axtr), descargarlo como archivo de grabación en bruto (.xml), descargarlo como documento de Word o guardar el archivo en una biblioteca de LCS. Es una buena idea guardar siempre su grabación de tareas como un archivo de paquete de grabación de tareas (.axtr). Esto facilitará el mantenimiento del archivo si los procedimientos o las anotaciones necesitan cambiarse posteriormente. Si desea descargar el archivo como documento de Word, guárdelo también como archivo de paquete de grabación de tareas.

## <a name="create-your-task-recording"></a>Crear la grabación de tareas
Para los pasos detallados de recorrido, consulte [de cómo crear una tarea que registra task-recorder.md] ().

## <a name="copy-and-customize-microsofts-task-recordings"></a>Copiar y personalizar las grabaciones de tareas de Microsoft
Puede descargar y editar los registros de la tarea de Microsoft para utilizarlas para su propio material de la documentación de ayuda o de formación. Para descargar una grabación de tarea de Microsoft, siga estos pasos:

1.  En Dynamics 365 para las operaciones, abra el Grabador de tareas. El Grabador de tareas se encuentra en el menú **Parámetros**.
2.  En el panel Grabador de tareas, haga clic en **Mantener una grabación**.
3.  En **¿Dónde encuentro la grabación?**, haga clic en **Se encuentra en la biblioteca LCS**.
4.  Haga clic en **Seleccionar biblioteca de LCS**.
5.  Seleccione la biblioteca global de Microsoft.
6.  En el árbol, seleccione el nodo de la biblioteca del proceso empresarial con el que está asociado el registro de la tarea.
7.  Haga clic en **Aceptar**.
8.  Haga clic en **Inicio**.
9.  En este punto, paso a través del registro, cambie cualquier pasos como va a volverla a registrar. ** ** Nota: Si sólo necesita modificar el texto de un registro, puede abrir el registro en ** editar las anotaciones de un registro ** manera, la y guardarla.
10. Cuando se haya reproducido la grabación hasta el final, haga clic en **Detener** en el grabador de tareas de la parte superior de la pantalla.
11. Elija cómo desea guardar la grabación de tareas.

## <a name="include-your-task-recordings-in-the-help-pane"></a>Incluir sus registros de la tarea en el panel de la Ayuda
Para mostrar sus propias registros de la tarea personalizada en el panel de la Ayuda de modo que puedan van a jugada como guías de la tarea o vista como texto, es necesario guardar los registros de la tarea a su propia biblioteca de BPM y, a continuación actualizar los parámetros del sistema de ayuda para señalar el biblioteca de BPM. Para obtener más información, consulte [conectar el sistema de ayuda.] (. /get-started/help-connect.md)

<a name="see-also"></a>Consulte también
--------

[365 Dinámica para la Ayuda de las operaciones.] (. \ \ obtener- comenzado help-overview.md)

Ayuda [] (conectar. \ \ obtener- comenzado help-connect.md)

[Grabador de tareas en Dynamics 365 para las operaciones (task-recorder.md])

[Funciones recién agregadas Grabador de tareas (] base \ \ \ obtener- comenzado reciente-agregar-edición-característica-en-tarea- grabadora)

[Creando nuevas bibliotecas de formación para Dynamics AX dentro de servicios del ciclo de vida utilizando el Grabador de tareas (vínculo externo)](https://docs.com/mufife/163372c6-f366-4c5a-94fa-93e2c25f878a/creating-new-training-libraries-for-dynamics-ax)

[Crear Rich Help Topics con el Grabador de tareas (el vínculo externo)](https://mbspartner.microsoft.com/AX/Videos/970)


