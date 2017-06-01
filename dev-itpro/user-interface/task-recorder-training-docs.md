---
title: "Crear documentación o formación con las grabaciones de tareas"
description: "Este tema explica qué son el Grabador de tareas y las guías de tareas, cómo crear grabaciones de tareas y cómo personalizar las guías de tareas de Microsoft e incluirlas en la Ayuda."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 8b44dc66cdcd1ede59cb9bb4ed05be27dd465599
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="create-documentation-or-training-using-task-recordings"></a>Crear documentación o formación con las grabaciones de tareas

[!include[banner](../includes/banner.md)]

Este tema explica qué son el Grabador de tareas y las guías de tareas, cómo crear grabaciones de tareas y cómo personalizar las guías de tareas de Microsoft e incluirlas en la Ayuda.

<a name="learn-about-task-recorder"></a>Información sobre el grabador de tareas
-------------------------

El Grabador de tareas es una herramienta de Microsoft Dynamics 365 for Operations que puede usar para grabar las acciones que realiza en la interfaz de usuario (IU) de producto. Al usar el Grabador de tareas, se capturan todos los eventos que realiza en la IU que se ejecutan en relación con el servidor, entre los que se incluyen la adición de valores, el cambio de configuración y la eliminación de datos. Los pasos que grabe se denominan conjuntamente *grabación de tareas*. Las grabaciones de tareas se pueden usar de muchas maneras:

-   **Las grabaciones de tareas se pueden reproducir como guías de tareas.** Las guías de tareas son una parte integral de la experiencia de Dynamics 365 for Operations. Una guía de tareas es una experiencia controlada, dirigida e interactiva a través de los pasos de un proceso empresarial. Al usuario se le indica que complete cada paso mediante un aviso móvil (o "burbuja"), que se animará a través de la IU y señalará al elemento de la IU con el que debe interactuar el usuario. La “burbuja” también proporciona información sobre cómo interactuar con el elemento, como "Haga clic aquí" o "En este campo, escriba un valor". Se ejecuta una guía de tareas con el conjunto de datos actual del usuario y los datos especificados se guardan en el entorno del usuario.
-   **Las registros de tarea se pueden mostrar como pasos de procedimientos en el panel de la Ayuda.** Puede usar el panel de la Ayuda para buscar y mostrar grabaciones de tareas. Puede obtener acceso al panel de la Ayuda haciendo clic en el icono **?** de la barra de navegación superior o puede usar la combinación de teclas de método abreviado, **Ctrl+Mayús+?**. Solo puede leer los pasos de una grabación de tareas en el panel de la Ayuda o puede optar por reproducir la grabación como guía de tareas para que le guíe por la IU.
-   **Los registros de tareas se pueden guardar en BPM.** Puede guardar su grabación de tareas en una línea de una jerarquía en una biblioteca de Modelador de procesos empresariales (BPM) en Lifecycle Services (LCS). Se generará una lista de pasos y un diagrama de flujo de proceso empresarial desde la grabación. Las grabaciones de tareas que se han guardado en una biblioteca de BPM se pueden mostrar en Dynamics 365 for Operations como Ayuda.
-   **Las grabaciones de tareas se pueden guardar como documentos de Word.** Esto le permite producir con facilidad guías de formación imprimibles.

Puede crear sus propias grabaciones de tareas, reproducir grabaciones de tareas proporcionadas por Microsoft o modificar grabaciones de tareas proporcionadas por Microsoft para reflejar su configuración. Para obtener más información sobre el Grabador de tareas, consulte [Grabador de tareas en Dynamics 365 for Operations](task-recorder.md).

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
-   Para cada paso de una grabación de tareas, puede crear anotaciones. Durante la reproducción de una guía de tareas, las anotaciones aparecen en la "burbuja" como notas por encima o por debajo del texto para el paso. Cuando se ve como texto en el panel de la Ayuda, las anotaciones aparecen como texto en línea en el paso. Como con la descripción, es una buena idea escribir y guardar sus anotaciones en un documento independiente. Cuando registre la grabación de tareas, corte y pegue las anotaciones desde ese documento.

**Comprender los diferentes tipos de anotaciones** Todas las anotaciones son opcionales. Agréguelas solo cuando proporcionen información útil al usuario.

-   **Puesto:** una anotación del puesto aparecerá antes del texto del paso que el grabador de tareas genera automáticamente. En la guía de tareas, la anotación del título aparece sobre el texto generado automáticamente. Use este tipo de anotación para explicar por qué el usuario realiza el paso o para dar un contexto adicional.

Este es el panel de edición que ve al agregar una anotación conforme crea su grabación. Especifique una anotación del puesto en el cuadro **Puesto**. 

[![screen1](./media/screen1.png)](./media/screen1.png) 

Así es como se muestra la anotación del puesto en la “burbuja” de la guía de tareas. 

[![screen2](./media/screen2.png)](./media/screen2.png)

-   **Notas:** Una anotación de notas aparecerá después del texto del paso que el grabador de tareas genera automáticamente. En la guía de tareas solo será visible si el usuario hace clic en el vínculo **Muestra más** de la burbuja de la guía de tareas. Use este tipo de anotación para describir cualquier cosa que un usuario tenga que saber para completar el paso.

Este es el panel de edición que ve al agregar una anotación conforme crea su grabación. Especifique una anotación de notas en el cuadro **Notas**. 

[![screen3](./media/screen3.png)](./media/screen3.png) 

Así es como se muestra la anotación del notas en la “burbuja” de la guía de tareas.

[![screen4](./media/screen4.png)](./media/screen4.png)

-   **Paso de la información**: estas anotaciones se crean haciendo clic con el botón secundario en un control o en cualquier lugar de un formulario &lt; **Grabador de tareas** &lt; **Agregar paso de información. **Los pasos de información aparecen como paso numerado en cualquier punto en el que lo inserta, aunque no se haya grabado ninguna acción en la IU. Puede agregar un paso de información de nivel de formulario o un paso de información asociado con un control. Cuando un paso de información está asociado a un formulario, la "burbuja" de la guía de tareas aparecerá en algún lugar del formulario, sin puntero, cuando se reproduzca la guía de tareas. Cuando un paso de información está asociado a un control, la "burbuja" de la guía de tareas señalará al control cuando se reproduzca la guía de tareas. En el panel de la Ayuda, aparecerá una anotación del paso de la información como paso numerado siempre que escriba texto. Use los pasos de información para preparar al usuario para los pasos siguientes, para describir los pasos que se deben dar fuera de Dynamics 365 for Operations, o para hacer referencia a otras grabaciones (aunque no puede crear hipervínculos en anotaciones.).

**Determine el tiempo para realizar la grabación**

-   El usuario generalmente leerá o reproducirá la grabación desde el principio al fin; por tanto, no combine pasos o tareas que se realicen mejor por separado.
-   Intente no grabar un escenario largo que abarque múltiples subprocesos. Por ejemplo, "Dirigir el departamento de servicio de atención al cliente en la tienda" es demasiado amplia; divídala en tareas más breves como "Aceptar devoluciones" y "Agregar a tarjeta regalo".
-   Si una tarea se puede llevar a cabo como parte de varios procesos empresariales, cree una grabación independiente para ella y podrá consultarla en las demás grabaciones.
-   Si el proceso implica varias tareas que la persona probablemente realiza de una vez, puede mantener las tareas en una grabación, por ejemplo, "Configurar y asignar perfiles de funcionalidad".
-   Si es algo que alguien hace una vez (como la configuración) y después otra tarea que puede realizar inmediatamente a continuación pero que pueda realizar repetidamente y, por sí mismo, divídalas en dos grabaciones de tareas.

**Decida en qué lugar de la IU se iniciará una grabación** La página en la que se encuentra al iniciar la grabación de tareas afecta a para qué página se muestra la guía de tareas. Por ejemplo, si desea que su grabación de tareas se muestre en el panel de la Ayuda cuando un usuario hace clic en la Ayuda de la página Parámetros de contabilidad general, debe comenzar la grabación en la página Parámetros de contabilidad general. **Guarde las grabaciones como archivos .axtr** Cuando haya acabado de crear o editar una grabación de tareas, se le presentarán varias opciones para cómo desea descargar o guardar la grabación. Puede descargar el archivo como paquete de grabación de tareas (.axtr), descargarlo como archivo de grabación en bruto (.xml), descargarlo como documento de Word o guardar el archivo en una biblioteca de LCS. Es una buena idea guardar siempre su grabación de tareas como un archivo de paquete de grabación de tareas (.axtr). Esto facilitará el mantenimiento del archivo si los procedimientos o las anotaciones necesitan cambiarse posteriormente. Si desea descargar el archivo como documento de Word, guárdelo también como archivo de paquete de grabación de tareas.

## <a name="create-your-task-recording"></a>Crear la grabación de tareas
Para los pasos detallados de tutorial, consulte [Cómo crear una grabación de tareas](task-recorder.md).

## <a name="copy-and-customize-microsofts-task-recordings"></a>Copiar y personalizar las grabaciones de tareas de Microsoft
Puede descargar y editar las grabaciones de tareas de Microsoft para usarlas para sus propios materiales de formación y documentación de la Ayuda. Para descargar una grabación de tarea de Microsoft, siga estos pasos:

1.  Abra el Grabador de tareas en Microsoft Dynamics 365 for Operations. El Grabador de tareas se encuentra en el menú **Parámetros**.
2.  En el panel Grabador de tareas, haga clic en **Mantener una grabación**.
3.  En **¿Dónde encuentro la grabación?**, haga clic en **Se encuentra en la biblioteca LCS**.
4.  Haga clic en **Seleccionar biblioteca de LCS**.
5.  Seleccione la biblioteca global de Microsoft.
6.  En el árbol, seleccione el nodo de la biblioteca del proceso empresarial con el que está asociado el registro de la tarea.
7.  Haga clic en **Aceptar**.
8.  Haga clic en **Inicio**.
9.  En este momento, pase por la grabación, cambiando los pasos conforme avanza para volver a grabar. **Nota**: si solo tiene que cambiar el texto de una grabación, puede abrir la grabación en el modo **Editar las anotaciones de una grabación** y, a continuación, guardarla.
10. Cuando se haya reproducido la grabación hasta el final, haga clic en **Detener** en el grabador de tareas de la parte superior de la pantalla.
11. Elija cómo desea guardar la grabación de tareas.

## <a name="include-your-task-recordings-in-the-help-pane"></a>Incluir las grabaciones de tareas en el panel de la Ayuda
Para mostrar sus propias grabaciones de tareas personalizadas en el panel de la Ayuda para que se puedan reproducir como guías de tareas o ver como texto, debe guardar sus grabaciones de tareas en su propia biblioteca de BPM y después actualizar los parámetros del sistema de Ayuda para que señalen a la biblioteca de BPM. Para obtener más información, consulte [Conexión del sistema de Ayuda](../get-started/help-connect.md)

<a name="see-also"></a>Consulte también
--------

[Ayuda de Dynamics 365 for Operations](..\get-started\help-overview.md)

[Ayuda sobre Connect](..\get-started\help-connect.md)

[Grabador de tareas de Dynamics 365 for Operations](task-recorder.md)

[Funciones recién agregadas en el Grabador de tareas](\core\get-started\recently-added-editing-features-in-task-recorder)

[Creación de nuevas bibliotecas de formación para Dynamics AX dentro de Lifecycle Services con el Grabador de tareas (vínculo externo)](https://docs.com/mufife/163372c6-f366-4c5a-94fa-93e2c25f878a/creating-new-training-libraries-for-dynamics-ax)

[Crear Rich Help Topics con el Grabador de tareas (vínculo externo)](https://mbspartner.microsoft.com/AX/Videos/970)




