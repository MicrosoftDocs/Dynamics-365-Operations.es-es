---
title: Cancelar un trabajo de planificación
description: Este tema explica cómo cancelar un trabajo activo de planificación que utilice la función de ajuste de planificación.
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: a2d90f04985fdd66ca83582ee676100fffb26981
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2774048"
---
[!include [banner](../../includes/banner.md)]
[!include [banner](../../includes/preview-banner.md)]

# <a name="cancel-a-planning-job"></a>Cancelar un trabajo de planificación

En Microsoft Dynamics 365 Supply Chain Management puede cancelar un trabajo activo de planificación que utilice la función de ajuste de planificación.

Para cancelar un trabajo activo de planificación, siga estos pasos.

> [!NOTE]
> Sólo puede cancelar trabajos activos.

1. Vaya a **Planificación maestra \> Configuración \> Planes**.
2. Seleccione un plan apropiado para la ejecución de planificación.
3. Seleccione **Historial**.
4. Seleccione el trabajo de planificación que se desea cancelar.
5. Seleccione **Cancelar**.

El estado del trabajo será **Cancelando** hasta que el servicio de optimización de la planificación confirme que el trabajo se ha cancelado. El estado se cambiará a **Cancelado**.

> [!NOTE]
> Para ver cambios de estado, debe actualizar la página seleccionando el botón **Actualizar**.

## <a name="related-resources"></a>Recursos relacionados

[Visión general de la optimización de planificación](planning-optimization-overview.md)

[Introducción a la optimización de planificación](get-started.md)

[Análisis de aptitud de la optimización de la planificación](planning-optimization-fit-analysis.md)

[Ver el historial del plan y los registros de planificación](plan-history-logs.md)

[Aplicar filtros a un plan](plan-filters.md)
