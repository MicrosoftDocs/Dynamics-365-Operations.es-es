---
title: Cancelar un trabajo de planificación
description: Este tema explica cómo cancelar un trabajo activo de planificación que utilice la función de ajuste de planificación.
author: ChristianRytt
manager: tfehr
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 7cee11e6d9e8bc2fe83f5369554ae9ff9ee2b741
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5008225"
---
# <a name="cancel-a-planning-job"></a>Cancelar un trabajo de planificación

[!include [banner](../../includes/banner.md)]

En Microsoft Dynamics 365 Supply Chain Management puede cancelar un trabajo activo de planificación que utilice la función de ajuste de planificación. Cuando seleccionas **Cancelar** en el cuadro de diálogo cuando un trabajo de optimización de Planificación se activa directamente desde la interfaz de usuario (no en segundo plano), esto no cancelará el trabajo de optimización de Planificación. Incluso si recibe una advertencia como "Operación cancelada", deberá seguir los siguientes pasos para cancelar un trabajo de planificación con la optimización de planificación.


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

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de la optimización de la planificación](planning-optimization-overview.md)

[Introducción a la optimización de la planificación](get-started.md)

[Análisis de aptitud de la optimización de la planificación](planning-optimization-fit-analysis.md)

[Ver el historial del plan y los registros de planificación](plan-history-logs.md)

[Aplicar filtros a un plan](plan-filters.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]