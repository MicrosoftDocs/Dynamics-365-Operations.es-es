---
title: Ver el historial del plan y los registros de planificación
description: Este tema explica cómo ver el historial de los trabajos de planificación desencadenados por la funcionalidad de optimización de la planificación.
author: ChristianRytt
ms.date: 10/30/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MPSPlanRegenerationJobList, MPSPlanRegenerationJobLogs
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: d7bba084b03f8698c8bf31d171d5e4e486ed06ad
ms.sourcegitcommit: a7649b361ec54b49c0e9ee1c1c63a8815f320225
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187256"
---
# <a name="view-plan-history-and-planning-logs"></a>Ver el historial del plan y los registros de planificación

[!include [banner](../../includes/banner.md)]

Este tema explica cómo ver el historial de los trabajos de planificación desencadenados por la funcionalidad de optimización de la planificación en Microsoft Dynamics 365 Supply Chain Management.

Para ver el historial de un plan, abra el plan; para ello, vaya a **Planificación maestra** \> **Configuración** \> **Planes** \> **Planes maestros** y seleccionando **Historial**. El historial contiene todos los trabajos para el plan seleccionado. La lista incluye los trabajos completados y trabajos.

El historial de trabajos para las ejecuciones de planificación maestra de Planning Optimization mantiene solo hasta 60 registros por plan maestro. Siempre que ejecuta un nuevo cálculo de planificación maestra, se elimina el registro histórico más antiguo de ese plan.

Además de ver la hora de inicio y el estado de los trabajos, puede ver el registro para un trabajo específico. El registro incluye información adicional y advertencias. No todos los trabajos tienen un registro. Para ver el registro de un trabajo, seleccione **Registro**. Las entradas del registro solo se almacenan durante 30 días después de la fecha en que finalizó el trabajo, después de eso se eliminan automáticamente.

## <a name="related-resources"></a>Recursos relacionados

- [Información general de la optimización de la planificación](planning-optimization-overview.md)
- [Introducción a la optimización de la planificación](get-started.md)
- [Análisis de aptitud de la optimización de la planificación](planning-optimization-fit-analysis.md)
- [Aplicar filtros a un plan](plan-filters.md)
- [Cancelar un trabajo de planificación](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]