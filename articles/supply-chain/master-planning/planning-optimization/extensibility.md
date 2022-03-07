---
title: Extensibilidad de Optimización de planificación
description: Este tema describe los escenarios de extensibilidad que se admiten en Planning Optimization.
author: ChristianRytt
ms.date: 08/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-07-07
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: e18801a02ae9e904eb5bc597f9f61ed42c537ab9
ms.sourcegitcommit: 614d79cba238e466d445767a7d0a012e785a9861
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/19/2021
ms.locfileid: "7652079"
---
# <a name="planning-optimization-extensibility"></a>Extensibilidad de Optimización de planificación

[!include [banner](../../includes/banner.md)]

Este tema describe los escenarios de extensibilidad relacionados con la planificación mastra y que se admiten en Planning Optimization. Estas capacidades de búsqueda basadas en la nube están disponibles a partir de Microsoft Dynamics 365 Supply Chain Management versión 10.0.13.

## <a name="custom-processing-when-master-planning-is-completed"></a>Procesamiento personalizado cuando se completa la planificación maestra

En el escenario de extensibilidad más común en Planning Optimization, el procesamiento personalizado se realiza después de que se haya actualizado el plan. Por ejemplo, puede agregar una columna a la tabla de pedidos planificados (`ReqPO`), o quizás desee obtener información estadística del plan generado. El principal punto de extensibilidad que habilita estos escenarios es el método `jobCompletedSuccessfully` de la clase `MpsMasterPlanningEvents`.

```X++
public static void jobCompletedSuccessfully(MpsMasterPlanningJobCompletedSuccessfullyEventArgs _args)
```

A continuación, se muestra un ejemplo de una extensión que establece un campo `CstmOrderPriority` en la orden planificada.

```X++
[ExtensionOf(classStr(MpsMasterPlanningEvents))]
public static final class MpsMasterPlanningEvents_Cstm_Extension
{
    public static void jobCompletedSuccessfully(MpsMasterPlanningJobCompletedSuccessfullyEventArgs _args)
    {
        ttsbegin;

        var affectedPlannedOrdersQuery = _args.parmPostProcessingQueryBuilder().buildAffectedPlannedOrdersQuery();
        var affectedPlannedOrdersQueryRun = new QueryRun(affectedPlannedOrdersQuery);

        while (affectedPlannedOrdersQueryRun.next())
        {
            ReqPO reqPO = affectedPlannedOrdersQueryRun.get(tableNum(ReqPO));
            reqPO.selectForUpdate(true);
            reqPO.CstmOrderPriority = reqPO.ReqDate - systemDateGet() < 7 ? CstmPlannedOrderPriority::Urgent : CstmPlannedOrderPriority::Regular;
            reqPO.doUpdate();
        }

        ttscommit;

        next jobCompletedSuccessfully(_args);
    }

}
```

Cuando agregue lógica personalizada, tenga en cuenta las siguientes restricciones y mejores prácticas:

- El método `jobCompletedSuccessfully` se llama al método fuera del alcance de la transacción. Por lo tanto, el plan ya está visible para el usuario cuando comienza a ejecutarse la lógica personalizada. Si su personalización establece campos adicionales en los pedidos planificados, es importante que informe a los usuarios que los valores de esos campos eventualmente serán consistentes (en otras palabras, podrían estar desactualizados inmediatamente después de que se complete un trabajo de planificación).
- Otro trabajo de planificación maestra puede comenzar cuando se llama al método `jobCompletedSuccessfully`. El nuevo trabajo puede afectar el plan completo o parte del plan. El nuevo trabajo puede actualizar o eliminar los mismos pedidos planificados o transacciones de requisitos que se crearon o actualizaron como parte del trabajo de planificación que se manejó en `jobCompletedSuccessfully`. Las excepciones de conflictos de actualización deben manejarse cuando se extiende este evento.
- Evite utilizar el alcance de una sola transacción cuando amplíe este método. Una sola ejecución de planificación maestra puede producir millones de transacciones de requisitos y cientos de miles de pedidos planificados. Si todas estas transacciones y órdenes planificadas se procesan en el ámbito de una sola transacción, se producirán muchos bloqueos SQL y bloquearán otros procesos de planificación. Además, si la transacción se mantiene durante mucho tiempo, se crearán "registros fantasma" en la base de datos SQL. Los registros fantasma afectarán negativamente a todos los procesos del sistema.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]