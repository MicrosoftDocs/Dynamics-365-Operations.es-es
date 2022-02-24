---
title: Listas de comprobación de mantenimiento
description: En este tema se describen las listas de comprobación de mantenimiento en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderChecklist, EntAssetMobileWorkOrderLineChecklistDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b2ec7130fbe8c397c30cdc2a76f34ecfdfdc0737
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "5017927"
---
# <a name="maintenance-checklists"></a>Listas de comprobación de mantenimiento

[!include [banner](../../includes/banner.md)]



Las listas de comprobación de mantenimiento se configuran en tipos de trabajo de mantenimiento. Se rellenan las listas de comprobación de mantenimiento como parte del proceso de completar una orden de trabajo. Para obtener más información sobre cómo configurar listas de comprobación de mantenimiento en tipos de trabajo de mantenimiento en la página **Valores predeterminados del tipo de trabajo de mantenimiento**, consulte [Categorías del tipo de trabajo de mantenimiento y tipos de trabajo de mantenimiento, variantes del tipo de trabajo de mantenimiento, comercios de trabajo de mantenimiento y listas de comprobación de mantenimiento](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).

Al trabajar con listas de comprobación de mantenimiento en una orden de trabajo, puede rellenar las listas de comprobación de mantenimiento predefinidas que están relacionadas con los tipos de trabajo de mantenimiento. También puede agregar más listas de comprobación mantenimiento.


## <a name="fill-in-a-maintenance-checklist"></a>Rellenar una lista de comprobación de mantenimiento

1. Haga clic en **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.

2. Seleccione la orden de trabajo y, a continuación, en el panel de acciones, en la pestaña **Orden de trabajo**, en el grupo **Líneas**, seleccione **Lista de comprobación de mantenimiento**.

3. La **Lista de comprobación de trabajo de mantenimiento de orden de trabajo** muestra listas de comprobación de todos los trabajos de la orden de trabajo. Si las tareas de la orden de trabajo tienen distintos tipos de trabajo de mantenimiento, las listas de comprobación de mantenimiento pueden ser diferentes en cada tarea de la orden de trabajo. Seleccione una tarea de la orden de trabajo para trabajar con la lista de comprobación de mantenimiento relacionada. Los detalles de la línea de la lista de comprobación de mantenimiento seleccionada se muestran en la ficha desplegable **Detalles de línea**.

4. Complete todas las líneas de la lista de comprobación de mantenimiento, de una en una, en el orden en que se muestran. Complete una línea de la lista de comprobación de mantenimiento rellenando los campos en la ficha desplegable **Detalles de línea**. La información necesaria para completar una línea puede variar, en función del tipo de línea. Por ejemplo, en una línea de tipo **Texto** puede agregar una nota que explique cuál fue el resultado de la comprobación. En una línea de tipo **Medida**, puede agregar el valor del contador, leerlo en el equipo y también agregar una nota, si es necesario. A continuación, se utiliza una línea de la lista de comprobación de mantenimiento de tipo **Encabezado** como cabecera para agrupar las líneas de la lista de comprobación de mantenimiento que aparecen debajo. No es necesario rellenar un encabezado. Con respecto al resto de los tipos de líneas de la lista de comprobación del mantenimiento, puede agregar una nota a una línea del tipo **Encabezado**.

5. Si las instrucciones están relacionadas con una línea de la lista de comprobación de mantenimiento, se selecciona la casilla **Instrucciones**. Lea las instrucciones para la línea de la lista de comprobación de mantenimiento seleccionada en el campo **Instrucciones** de la ficha desplegable **Detalles de línea**.

6. Cuando haya completado una línea de la lista de comprobación del mantenimiento, seleccione la casilla **Comprobada** en la línea para marcarla como completada. Para descartar una línea de la lista de comprobación de mantenimiento porque no es relevante para la tarea de la orden de trabajo, seleccione la casilla **N/A** en la línea. Si la casilla de verificación **Obligatorio** se selecciona en una línea de la lista de comprobación de mantenimiento, debe seleccionar la casilla de verificación **Comprobado** o la casilla de verificación **N/D**.

>[!NOTE]
>Solo puede actualizar los registros de la lista de comprobación de mantenimiento si la orden de trabajo está en un estado de ciclo de vida [Activo](../setup-for-work-orders/work-order-lifecycle-states.md).  


## <a name="add-a-maintenance-checklist-line"></a>Agregar una línea de la lista de comprobación de mantenimiento

Las listas de comprobación de mantenimiento se crean a partir de la definición del valor predeterminado del tipo de trabajo de mantenimiento y se transfieren a una tarea de la orden de trabajo. Si es necesario, puede agregar líneas de la lista de comprobación de mantenimiento a una tarea de la orden de trabajo. Las líneas de la lista de comprobación de mantenimiento agregadas manualmente obtienen la referencia **Manual**.

1. En la página **Lista de comprobación de trabajo de mantenimiento de orden de trabajo**, seleccione la tarea de la orden de trabajo para la que desea agregar una lista de comprobación de mantenimiento.

2. En la ficha desplegable **Líneas de comprobación de mantenimiento** , seleccione una línea de lista de comprobación de mantenimiento. A continuación, para insertar una nueva línea después de la línea seleccionada, presione la tecla **Flecha abajo**. El siguiente número en la secuencia se inserta automáticamente en el campo **Número de línea**. Para insertar una nueva línea antes de la línea seleccionada, seleccione **Agregar línea**. 

3. Inserte un nombre para la lista de comprobación de mantenimiento en el campo **Nombre**.

4. En el campo **Tipo**, seleccione un tipo para la línea de la lista de comprobación de mantenimiento. Para cada tipo de lista de comprobación de mantenimiento, la ficha desplegable **Detalles de línea** muestra los campos relacionados.
    - **Texto**: use este tipo para agregar una línea de la lista de comprobación de mantenimiento que tenga texto que describa lo que debe hacer. Por ejemplo, puede utilizar este tipo si quiere que un trabajador compruebe o inspeccione algo, pero sin esperar resultados específicos (medibles). Tras seleccionar este tipo, en la ficha desplegable **Detalles de líneas**, en el campo **Instrucciones**, escriba el texto que describe lo que debe hacer.
    - **Encabezado**: se utiliza una línea de la lista de comprobación de mantenimiento de este tipo como cabecera para agrupar las líneas de la lista de comprobación de mantenimiento que aparecen debajo. Este tipo es útil si tiene varias líneas de la lista de comprobación de mantenimiento que se pueden dividir en áreas específicas. Tras seleccionar este tipo, especifique un nombre descriptivo en el campo **Nombre**.
    - **Plantilla**: este tipo no es aplicable si agrega una línea de la lista de comprobación de mantenimiento manualmente en una tarea de la orden de trabajo.  
    - **Variable**: se usa este tipo para definir un posible resultado en un intervalo en una línea de la lista de comprobación de mantenimiento. Para obtener información sobre la configuración de la lista de comprobación de mantenimiento, consulte [Categorías del tipo de trabajo de mantenimiento y tipos de trabajo de mantenimiento, variantes del tipo de trabajo de mantenimiento, comercios de trabajo de mantenimiento y listas de comprobación de mantenimiento](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md). Tras seleccionar este tipo, especifique un nombre descriptivo para la variable en el campo **Nombre**. En la ficha desplegable **Detalles de línea**, en el campo **Variable**, seleccione la variable. En el campo **Instrucciones**, escriba un texto que describa qué se debe hacer.
    - **medida**: use este tipo para registrar una medida específica de la línea de la lista de comprobación mantenimiento. Tras seleccionar este tipo, especifique un nombre para la medida en el campo **Nombre**. En la ficha desplegable **Detalles de línea**, en el **Contador** y los campos **Unidad**, seleccione valores adecuados. En el campo **Instrucciones**, escriba un texto que describa qué se debe hacer.

5. Cuando haya terminado de agregar manualmente las líneas de la lista de comprobación de mantenimiento, complete las líneas como se describe en la sección **Rellenar una lista de comprobación de mantenimiento** arriba.

>[!NOTE]
>En la página **Lista de comprobación de trabajo de mantenimiento de orden de trabajo**, no puede eliminar las líneas de la lista de comprobación de mantenimiento con la referencia **Tipo de trabajo**. Solo puede eliminar las líneas de la lista de comprobación de mantenimiento con la referencia **Manual**, que usted u otros trabajadores de mantenimiento han creado manualmente.

En la ilustración siguiente se muestra un ejemplo de lista de comprobación de mantenimiento.

![Figura 1](media/14-work-orders.png)

