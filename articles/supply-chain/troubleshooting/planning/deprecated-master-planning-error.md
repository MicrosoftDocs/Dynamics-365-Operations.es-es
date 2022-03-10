---
title: Recibe un error al ejecutar el motor de planificación maestra integrado
description: Cuando ejecuta el motor de planificación maestra integrado en desuso, recibe un mensaje de error.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: Dialog_ReqCalcScheduleItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 7c0c674818a21d3ad422661fc427b0b9c4aad52b8d44d08791d2d703be528fe3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6751730"
---
# <a name="you-receive-an-error-when-running-the-built-in-master-planning-engine"></a>Recibe un error al ejecutar el motor de planificación maestra integrado

Código de error: ReqCalcScheduleItemTablePlanningOptimizationFitError

## <a name="symptoms"></a>Síntomas

Cuando ejecuta la planificación maestra con el motor de planificación maestra integrado en desuso, recibe el siguiente mensaje de error:

> Recibe este mensaje de error porque el motor de planificación maestro integrado se utilizó para escenarios compatibles con Optimización de la planificación. Debe migrar a Optimización de la planificación ahora, ya que la planificación maestra incorporada actual quedará obsoleta. Tenga en cuenta que esta ejecución de planificación maestra se completó correctamente. En caso de que su migración tenga una fuerte dependencia de las características pendientes, se puede solicitar una excepción al uso continuo del motor de planificación maestro integrado. Complete el siguiente cuestionario para comenzar y, si es relevante, solicite una excepción de la migración a Optimización de la planificación. [Cuestionario de excepción y migración de Planning Optimization](https://go.microsoft.com/fwlink/?linkid=2144962)

## <a name="cause"></a>Causa

Si ejecuta la planificación y no usa las funciones de control de producción, debería considerar migrar a Planning Optimization. El motor de planificación maestro integrado está en desuso. Por lo tanto, si desea continuar usándolo sin recibir el mensaje de error, debe solicitar una excepción de Microsoft.

## <a name="resolution"></a>Resolución

Para obtener más información sobre cómo migrar a Planning Optimization, o cómo solicitar una excepción para poder seguir utilizando el motor de planificación integrado en desuso, consulte [Migración a la optimización de la planificación para la planificación maestra](/dynamics365/supply-chain/master-planning/new-master-planning-engine).
