---
title: Análisis de aptitud de la optimización de la planificación
description: Este tema explica cómo comprobar la configuración actual y los datos frente a las prestaciones de la funcionalidad de optimización de la planificación.
author: ChristianRytt
manager: AnnBe
ms.date: 10/30/2019
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
ms.openlocfilehash: a61529da63bc20fdd591afc94db960b05c284bb9
ms.sourcegitcommit: b806f0c94d703bec39680fead827733361d47045
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "2935884"
---
[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

# <a name="planning-optimization-fit-analysis"></a>Análisis de aptitud de la optimización de la planificación

Para ver el grado de compatibilidad de su configuración actual y los datos con la funcionalidad de optimización de la planificación, vaya **Planificación maestra** \> **Configuración** \> **Análisis de aptitud de la optimización de la planificación** y después seleccione **Ejecutar análisis**. Si el análisis detecta incoherencias, se enumeran en la misma página. (El análisis puede tardar algunos minutos en ejecutarse).

> [!NOTE]
> Si se encuentran incoherencias, puede usar la optimización de la planificación. Los resultados del análisis de aptitud solo muestran las ubicaciones en las que el servicio de planificación no coincide con la configuración actual. Es decir, muestran las ubicaciones en las que algunos procesos se pueden omitir o no están admitidos.

## <a name="analysis-results-example-1"></a>Resultados de análisis: ejemplo 1

- **Característica:** producción
- **Problema:** artículos con L.MAT mayor que cero: 56
- **Explicación:** el análisis de aptitud encontró 56 artículos con una lista de materiales (L.MAT) configurada para producción. Dado que la versión actual de la optimización de la planificación no admite la producción, la optimización de la planificación generará pedidos de compra planificados en lugar de pedidos de producción planificados. También mostrará una advertencia que enumere los artículos afectados.

### <a name="analysis-results-example-2"></a>Resultados de análisis: ejemplo 2

- **Característica:** acciones
- **Problema:** grupos de cobertura con el cálculo de las acciones habilitado: 6
- **Explicación:** el análisis de aptitud detectó seis grupos de cobertura donde el cálculo de la acción está activado. Dado que la versión actual de la optimización de la planificación no admite acciones, no se generarán acciones durante la planificación maestra.

## <a name="related-resources"></a>Recursos relacionados

[Visión general de la optimización de la planificación](planning-optimization-overview.md)

[Introducción a la optimización de planificación](get-started.md)

[Ver el historial del plan y los registros de planificación](plan-history-logs.md)

[Aplicar filtros a un plan](plan-filters.md)

[Cancelar un trabajo de planificación](cancel-planning-job.md)
