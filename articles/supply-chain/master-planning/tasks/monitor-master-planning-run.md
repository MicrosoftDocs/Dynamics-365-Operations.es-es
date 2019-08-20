---
title: Supervisar una ejecución de planificación maestra
description: El planificador de producción desea ver si una ejecución de planificación maestra está en curso.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, InventItemIdLookupSimple, ReqLog, ReqProcessTaskTrace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b923b215528ecceaed9b5057ddb736ec959f1d65
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845123"
---
# <a name="monitor-a-master-planning-run"></a>Supervisar una ejecución de planificación maestra

[!include [task guide banner](../../includes/task-guide-banner.md)]

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

