---
title: Listas de comprobación de mantenimiento
description: En este tema se describen las listas de comprobación de mantenimiento en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 325ff1fa0811d6aac5189cc69f21483fce6b3e8f
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875888"
---
# <a name="maintenance-checklists"></a>Listas de comprobación de mantenimiento


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Las listas de comprobación de mantenimiento se configuran en tipos de trabajo de mantenimiento y se usan cuando trabaje en una orden de trabajo. Rellenar las listas de comprobación de mantenimiento forma parte de completar una orden de trabajo. Consulte la sección [Categorías del tipo de trabajo de mantenimiento y tipos de trabajo de mantenimiento, variantes del tipo de trabajo de mantenimiento, comercios de trabajo de mantenimiento y listas de comprobación de mantenimiento](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md) para obtener más información sobre cómo configurar listas de comprobación de mantenimiento en tipos de trabajo de mantenimiento en el formulario **Valores predeterminados del tipo de trabajo de mantenimiento**.

Al trabajar con listas de comprobación de mantenimiento en una orden de trabajo, puede rellenar las listas de comprobación de mantenimiento predefinidas que están relacionadas con los tipos de trabajo de mantenimiento. También es posible agregar listas de comprobación de mantenimiento adicionales.

## <a name="fill-out-a-maintenance-checklist"></a>Rellenar una lista de comprobación de mantenimiento

1. Haga clic en **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.

2. Seleccione la orden de trabajo y haga clic en **Lista de comprobación de mantenimiento**.

3. En la **Lista de comprobación de trabajo de mantenimiento de orden de trabajo**, verá las listas de comprobación de mantenimiento para todas las tareas de la orden de trabajo. Si las tareas de la orden de trabajo tienen distintos tipos de trabajo de mantenimiento, las listas de comprobación de mantenimiento pueden ser diferentes en cada tarea de la orden de trabajo. Seleccione una tarea de la orden de trabajo para trabajar con la lista de comprobación de mantenimiento relacionada. Los detalles de una línea de la lista de comprobación de mantenimiento seleccionada se muestran en la ficha desplegable **Detalles de línea**.

4. Complete todas las líneas de la lista de comprobación de mantenimiento, de una en una, en el orden secuencial en que se muestran. A continuación, se utiliza una línea de la lista de comprobación de mantenimiento de tipo "Encabezado" como cabecera para agrupar las líneas de la lista de comprobación de mantenimiento. No es necesario que rellene un encabezado, pero al igual que para todos los tipos de línea de lista de comprobación de mantenimiento, es posible agregar una **Nota** al encabezado.

5. Si las instrucciones están relacionadas con una línea de la lista de comprobación de mantenimiento, se selecciona la casilla **Instrucciones**. Lea las instrucciones para la línea de la lista de comprobación de mantenimiento seleccionada en la ficha desplegable **Detalles de línea** > sección **Instrucciones**.

6. La información necesaria para completar una línea de la lista de comprobación de mantenimiento puede variar según el tipo de lista de comprobación de mantenimiento relacionado. Complete una línea de la lista de comprobación de mantenimiento rellenando los campos en la ficha desplegable **Detalles de línea**. Por ejemplo, en una línea de tipo "Texto", puede agregar una **Nota** que explique cuál fue el resultado de esa línea de la lista de comprobación. En una línea de tipo "Medida", puede agregar el **Valor del contador**, leerlo en el equipo y también agregar una **Nota**, si es necesario.

- Cuando haya completado una línea de la lista de comprobación del mantenimiento, seleccione la casilla **Comprobada** en la línea para marcarla como completada. Si desea descartar una línea de la lista de comprobación de mantenimiento porque no es relevante para la tarea de la orden de trabajo, seleccione la casilla **N/A** en la línea. Si una línea de la lista de comprobación de mantenimiento se marca como **Obligatoria**, debe marcarla como "Comprobada" o "N/A".  
- Solo puede actualizar los registros de la lista de comprobación de mantenimiento si la orden de trabajo está en un estado de ciclo de vida [Activo](../setup-for-work-orders/work-order-lifecycle-states.md).  


## <a name="add-a-maintenance-checklist-line"></a>Agregar una línea de la lista de comprobación de mantenimiento

Las listas de comprobación de mantenimiento se crean a partir de la definición del valor predeterminado del tipo de trabajo de mantenimiento y se transfieren a una tarea de la orden de trabajo. Si es necesario, puede agregar líneas de la lista de comprobación de mantenimiento a una tarea de la orden de trabajo. Las líneas de la lista de comprobación de mantenimiento agregadas manualmente obtienen la referencia "Manual".

1. En la **Lista de comprobación de trabajo de mantenimiento de orden de trabajo**, seleccione la tarea de la orden de trabajo para la que desea agregar una lista de comprobación de mantenimiento.

2. En la ficha desplegable **Líneas de la lista de comprobación de mantenimiento**, seleccione una línea de la lista de comprobación de mantenimiento y presione el botón de flecha abajo en el teclado si desea insertar una nueva línea después de la línea de la lista de comprobación de mantenimiento seleccionada. El siguiente número en la secuencia se inserta automáticamente en el campo **Número de línea**. También puede seleccionar una línea de la lista de comprobación de mantenimiento y hacer clic en el botón **Agregar línea** si desea insertar una nueva línea encima de la línea de la lista de comprobación de mantenimiento seleccionada.

3. Inserte un nombre para la lista de comprobación de mantenimiento en el campo **Nombre**.

4. En el campo **Tipo**, seleccione un tipo para la línea de la lista de comprobación de mantenimiento. Para cada tipo de lista de comprobación de mantenimiento, los campos relacionados se muestran en la ficha desplegable **Detalles de línea**.  
  a. "Texto" se usa para agregar una línea de la lista de comprobación de mantenimiento con una descripción de texto de lo que desea hacer. Este tipo de lista de comprobación de mantenimiento se puede usar si desea que un trabajador compruebe o inspeccione algo, sin esperar un resultado específico (medible). Inserte una descripción de qué hacer en la sección **Instrucciones** en la ficha desplegable **Detalles de línea**. b. "Encabezado" se usa como cabecera para agrupar las líneas de la lista de comprobación de mantenimiento que se muestran en el encabezado. Este resulta útil si tiene varias líneas de la lista de comprobación de mantenimiento que se pueden dividir en áreas específicas. Inserte un nombre descriptivo en el campo **Nombre**.  
  c. "Plantilla" no es aplicable si agrega una línea de la lista de comprobación de mantenimiento manualmente en una tarea de la orden de trabajo.  
  d. "Variable" se usa para definir un posible resultado en un intervalo en una línea de la lista de comprobación de mantenimiento. La configuración de variables de una lista de comprobación de mantenimiento se describe en [Categorías del tipo de trabajo de mantenimiento y tipos de trabajo de mantenimiento, variantes del tipo de trabajo de mantenimiento, comercios de trabajo de mantenimiento y listas de comprobación de mantenimiento](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md). Inserte un nombre para describir la variable en el campo **Nombre**. Seleccione la variable en el campo **Variable**. Inserte una descripción de qué hacer en la sección **Instrucciones** en la ficha desplegable **Detalles de línea**.  
  e. "Medida" se usa para registrar una medida concreta. Inserte un nombre para la medida en el campo **Nombre**. En la ficha desplegable **Detalles de línea**, seleccione **Contador** y **Unidad**. Inserte una descripción de qué hacer en la sección **Instrucciones**.  

5. Cuando termine de agregar manualmente líneas de la lista de comprobación de mantenimiento, rellene las líneas tal como se describe en la sección anterior.

>[!NOTE]
>En **Lista de comprobación de trabajo de mantenimiento de orden de trabajo**, no puede eliminar las líneas de la lista de comprobación de mantenimiento con la referencia "Tipo de trabajo". Solo puede eliminar las líneas de la lista de comprobación de mantenimiento con la referencia "Manual", que usted u otros trabajadores de mantenimiento han creado manualmente.


![Figura 1](media/14-work-orders.png)

