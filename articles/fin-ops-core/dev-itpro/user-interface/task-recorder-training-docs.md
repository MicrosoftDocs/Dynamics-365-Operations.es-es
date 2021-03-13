---
title: Crear documentación o formación con Grabador de tareas
description: Este tema explica qué son el Grabador de tareas y las guías de tareas, cómo crear grabaciones, y cómo personalizar las guías de tareas de Microsoft e incluirlas en la Ayuda.
author: josaw1
manager: AnnBe
ms.date: 03/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: SysHelpSetup
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: 25391
ms.assetid: 59bf39f8-1464-441e-8b23-9a856c73471b
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1bc634a324e3cc12855a1b36b9a58a9cb38eb5d2
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092878"
---
# <a name="create-documentation-or-training-with-task-recorder"></a>Crear documentación o formación con Grabador de tareas

[!include [banner](../includes/banner.md)]

Este tema explica qué son el Grabador de tareas y las guías de tareas, cómo crear grabaciones de tareas y cómo personalizar las guías de tareas de Microsoft e incluirlas en la Ayuda.

> [!IMPORTANT]
> Puede registrar sus propias guías de tareas para Dynamics 365 Human Resources, pero no podrá salvarlas en una biblioteca del modelador de procesos empresariales (BPM) o abrirlas desde el panel de Ayuda en este momento. Puede salvarlas localmente o en una ubicación de red y, a continuación, abrirlas y volver a verlas utilizando el Grabador de tareas. 

<a name="learn-about-task-recorder"></a>Información sobre el grabador de tareas
-------------------------

El Grabador de tareas es una herramienta que puede usar para grabar las acciones que realice en la interfaz de usuario (IU) del producto. Al usar el Grabador de tareas, se capturan todos los eventos que realiza en la IU que se ejecutan en relación con el servidor, entre los que se incluyen la adición de valores, el cambio de configuración y la eliminación de datos. Los pasos que grabe se denominan conjuntamente *grabación de tareas*. Las grabaciones de tareas se pueden usar de muchas maneras:

-   **Las grabaciones de tareas se pueden reproducir como guías de tareas.** Las guías de tareas son una parte integral de la experiencia de la Ayuda. Una guía de tareas es una experiencia controlada, dirigida e interactiva a través de los pasos de un proceso empresarial. Al usuario se le indica que complete cada paso mediante un aviso móvil (o "burbuja"), que se animará a través de la IU y señalará al elemento de la IU con el que debe interactuar el usuario. La “burbuja” también proporciona información sobre cómo interactuar con el elemento, como "Haga clic aquí" o "En este campo, escriba un valor". Se ejecuta una guía de tareas con el conjunto de datos actual del usuario y los datos especificados se guardan en el entorno del usuario.
-   **Las grabaciones de tareas se pueden guardar como documentos de Word.** Esto le permite producir con facilidad guías de formación imprimibles.

Puede crear sus propias grabaciones de tareas, reproducir grabaciones de tareas proporcionadas por Microsoft o modificar grabaciones de tareas proporcionadas por Microsoft para reflejar su configuración. Para obtener más información sobre el Grabador de tareas, consulte [Grabador de tareas](task-recorder.md).

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
-   Para cada paso de una grabación de tareas, puede crear anotaciones. Durante la reproducción de una guía de tareas, las anotaciones aparecen en la "burbuja" como notas por encima o por debajo del texto para el paso. Cuando se ve como texto en el panel de la Ayuda, las anotaciones aparecen como texto en línea en el paso. Como con la descripción, es una buena idea escribir y guardar sus anotaciones en un documento independiente. Cuando registre la grabación de tareas, corte y pegue las anotaciones desde ese documento.

**Comprender los diferentes tipos de anotaciones** Todas las anotaciones son opcionales. Agréguelas solo cuando proporcionen información útil al usuario.

-   **Puesto:** una anotación del puesto aparecerá antes del texto del paso que el grabador de tareas genera automáticamente. En la guía de tareas, la anotación del título aparece sobre el texto generado automáticamente. Use este tipo de anotación para explicar por qué el usuario realiza el paso o para dar un contexto adicional.

Este es el panel de edición que ve al agregar una anotación conforme crea su grabación. Especifique una anotación del puesto en el cuadro **Puesto**. 

[![Panel de edición con la anotación del puesto](./media/screen1.png)](./media/screen1.png) 

Así es como se muestra la anotación del puesto en la “burbuja” de la guía de tareas. 

[![Apariencia de la anotación del puesto en guía de tareas](./media/screen2.png)](./media/screen2.png)

-   **Notas:** Una anotación de notas aparecerá después del texto del paso que el grabador de tareas genera automáticamente. En la guía de tareas solo será visible si el usuario hace clic en el vínculo **Muestra más** de la burbuja de la guía de tareas. Use este tipo de anotación para describir cualquier cosa que un usuario tenga que saber para completar el paso.

Este es el panel de edición que ve al agregar una anotación conforme crea su grabación. Especifique una anotación de notas en el cuadro **Notas**. 

[![Panel de edición con anotación en cuadro Notas](./media/screen3.png)](./media/screen3.png) 

Así es como se muestra la anotación del notas en la “burbuja” de la guía de tareas.

[![Apariencia de la anotación de las notas en guía de tareas](./media/screen4.png)](./media/screen4.png)

-   **Paso de la información**: estas anotaciones se crean haciendo clic con el botón secundario en un control o en cualquier lugar de un formulario &lt; **Grabador de tareas** &lt; **Agregar paso de información**. Los pasos de información aparecen como paso numerado en cualquier punto en el que lo inserta, aunque no se haya grabado ninguna acción en la IU. Puede agregar un paso de información de nivel de formulario o un paso de información asociado con un control. Cuando un paso de información está asociado a un formulario, la "burbuja" de la guía de tareas aparecerá en algún lugar del formulario, sin puntero, cuando se reproduzca la guía de tareas. Cuando un paso de información está asociado a un control, la "burbuja" de la guía de tareas señalará al control cuando se reproduzca la guía de tareas. En el panel de la Ayuda, aparecerá una anotación del paso de la información como paso numerado siempre que escriba texto. Uso los pasos de información para preparar al usuario para los pasos siguientes, para describir los pasos que se deben dar fuera de la aplicación, o para hacer referencia a otras grabaciones (aunque no puede crear hipervínculos en anotaciones).

**Determine el tiempo para realizar la grabación**

-   El usuario generalmente leerá o reproducirá la grabación desde el principio al fin; por tanto, no combine pasos o tareas que se realicen mejor por separado.
-   Intente no grabar un escenario largo que abarque múltiples subprocesos. Por ejemplo, "Dirigir el departamento de servicio de atención al cliente en la tienda" es demasiado amplia; divídala en tareas más breves como "Aceptar devoluciones" y "Agregar a tarjeta regalo".
-   Si una tarea se puede llevar a cabo como parte de varios procesos empresariales, cree una grabación independiente para ella y podrá consultarla en las demás grabaciones.
-   Si el proceso implica varias tareas que la persona probablemente realiza de una vez, puede mantener las tareas en una grabación, por ejemplo, "Configurar y asignar perfiles de funcionalidad".
-   Si es algo que alguien hace una vez (como la configuración) y después otra tarea que puede realizar inmediatamente a continuación pero que pueda realizar repetidamente y, por sí mismo, divídalas en dos grabaciones de tareas.

**Decida en qué lugar de la IU se iniciará una grabación** La página en la que se encuentra al iniciar la grabación de tareas afecta a para qué página se muestra la guía de tareas. Por ejemplo, si desea que su grabación de tareas se muestre en el panel de la Ayuda cuando un usuario hace clic en la Ayuda de la página Parámetros de contabilidad general, debe comenzar la grabación en la página Parámetros de contabilidad general. **Guarde las grabaciones como archivos .axtr** Cuando haya acabado de crear o editar una grabación de tareas, se le presentarán varias opciones para cómo desea descargar o guardar la grabación. Puede descargar el archivo como paquete de grabación de tareas (.axtr), descargarlo como archivo de grabación en bruto (.xml), descargarlo como documento de Word o guardar el archivo en una biblioteca de LCS. Es una buena idea guardar siempre su grabación de tareas como un archivo de paquete de grabación de tareas (.axtr). Esto facilitará el mantenimiento del archivo si los procedimientos o las anotaciones necesitan cambiarse posteriormente. Si desea descargar el archivo como documento de Word, guárdelo también como archivo de paquete de grabación de tareas.

## <a name="create-your-task-recording"></a>Crear la grabación de tareas
Para los pasos detallados de tutorial, consulte [Recursos del Grabador de tareas](task-recorder.md).

## <a name="copy-and-customize-microsofts-task-recordings"></a>Copiar y personalizar las grabaciones de tareas de Microsoft
Puede descargar y editar las grabaciones de tareas de Microsoft para usarlas para sus propios materiales de formación y documentación de la Ayuda. Para descargar una grabación de tarea de Microsoft, siga estos pasos:

1.  Abra el Grabador de tareas. El Grabador de tareas se encuentra en el menú **Parámetros**.
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



<a name="additional-resources"></a>Recursos adicionales
--------

[Sistema de ayuda](../../fin-ops/get-started/help-overview.md)

[Conectar el sistema de ayuda](../../fin-ops/get-started/help-connect.md)

[Grabador de tareas](task-recorder.md)

[Crear Rich Help Topics con el Grabador de tareas (vínculo externo)](https://mbspartner.microsoft.com/AX/Videos/970)
