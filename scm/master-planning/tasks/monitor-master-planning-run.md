--- 
title: "Supervisar una ejecución de planificación maestra"
description: "El planificador de producción desea ver si una ejecución de planificación maestra está en curso."
author: YuyuScheller
manager: AnnBe
ms.date: 06/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 8eb19ac9ded4dc2a091ff733f2f43cb6cafa1b43
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="monitor-a-master-planning-run"></a>Supervisar una ejecución de planificación maestra

[!include[task guide banner](../../includes/task-guide-banner.md)]

El planificador de producción desea ver si una ejecución de planificación maestra está en curso. Use la empresa de datos de demostración USMF para completar este procedimiento.


## <a name="run-master-planning"></a>Ejecutar planificación maestra
1. Haga clic en Planificación maestra.
    * Encontrará esto en el panel de predeterminado.  
2. En el campo Plan, especifique o seleccione un valor.
    * Ejemplo: StaticPlan  
3. Haga clic en Ejecutar.
4. Seleccione Sí en el campo Realizar seguimiento de tiempo procesamiento.
    * Si el campo ya está seleccionado, omita este paso.  
5. En el campo Número de subprocesos, especifique un número.
6. Expanda la sección Registros que incluir.
7. Haga clic en Filtro.
8. En la lista, marque la fila seleccionada.
    * Marque la fila donde Campo = Número de artículo.  
9. En el campo Criterios, especifique o seleccione un valor.
    * Ejemplo: T0001  
10. Haga clic en Aceptar
11. Haga clic en Aceptar

## <a name="monitor-the-master-planning-run"></a>Supervisar la ejecución de planificación maestra
1. Haga clic en Historial.
2. Haga clic en Consultas.
3. Haga clic en Duración de la tarea de proceso.
4. En la lista, busque y seleccione el registro deseado.
    * Para cada artículo puede obtener una visión general de cuánto tiempo se tardó en completar cada paso de planificación.  


