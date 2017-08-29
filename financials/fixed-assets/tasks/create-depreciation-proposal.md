--- 
title: "Crear una propuesta de depreciación"
description: "En este procedimiento se describe cómo funcionan las propuestas de lote de depreciación y se explica cómo proponer la depreciación para los activos fijos."
author: saraschi2
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: ffc358fa7db0ae40fb39d3acdfee7783949f0e1f
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-depreciation-proposal"></a>Crear una propuesta de depreciación

[!include[task guide banner](../../includes/task-guide-banner.md)]

En este procedimiento se describe cómo funcionan las propuestas de lote de depreciación y se explica cómo proponer la depreciación para los activos fijos. Esta tarea usa la empresa de prueba USMF y el rol de contable.


## <a name="create-depreciation-proposal"></a>Crear propuesta de depreciación
1. Vaya a Activos fijos > Movimientos de diario > Crear propuesta de depreciación.
2. En el campo Nombre de diario, haga clic en el botón desplegable para abrir la búsqueda.
3. En la lista, haga clic en el vínculo de la fila seleccionada.
4. Especifique una fecha en el campo Fecha final.
    * Active la opción Resumir depreciación para resumir las depreciaciones mensuales en una línea de diario.  
    * Por ejemplo, si el valor de fecha es el 31 de marzo de 2015, se genera la siguiente descripción: “Depreciación desde el 31 de enero de 2015”. El campo Fecha de las líneas de diario propuestas se establece entonces en 31 de marzo de 2015.  
    * La propuesta de depreciación se puede filtrar por activo, grupo de activos u otros criterios mediante la opción Filtro.  
    * Cuando usa el formulario Crear propuestas de adquisición o depreciación para activos fijos, puede proponer la depreciación en lotes. Esto se recomienda para propuestas más grandes que usarán más recursos del sistema. Si selecciona la opción de lote, puede completar otras tareas durante ese tiempo. Cuando se propone la depreciación de esta manera, la depreciación se calcula para los modelos de valor de activos fijos.  
5. Haga clic en Crear diario.

## <a name="review-depreciation-entries"></a>Revisar los movimientos de amortización
1. Vaya a Activos fijos > Movimientos de diario > Diario de activos fijos.
2. En la lista, busque y seleccione el registro deseado.
3. Haga clic en Líneas.
4. Haga clic en Registrar.


