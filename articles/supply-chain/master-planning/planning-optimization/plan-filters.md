---
title: Aplicar filtros a un plan
description: Este artículo explica cómo usar filtros en un plan cuando se utiliza la funcionalidad optimización de la planificación.
author: t-benebo
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: c2df379be0876225bc7b0301d21f4e6660b04eb6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875315"
---
# <a name="apply-filters-to-a-plan"></a>Aplicar filtros a un plan

[!include [banner](../../includes/banner.md)]

Cuando se usa la funcionalidad optimización de la planificación, puede aplicar un filtro a un plan. El **Filtro de plan** se aplicará siempre durante la ejecución de una planificación maestra. Un **Filtros de plan** es útil cuando se desea restringir un plan a un determinado grupo de artículos y asegurarse de que no se incluyan otros artículos como parte de la planificación maestra resultante.

Si se aplica un **Filtro de plan** y también se aplica un filtro de tiempo de ejecución durante la ejecución de la planificación maestra, solo se incluirá la intersección de los dos filtros en la ejecución de la planificación.

Se puede acceder al **Filtro de plan** desde **Planes maestros** cuando se utiliza la Optimización de planificación.

## <a name="example-scenario"></a>Supuesto de ejemplo

Se configura un filtro de planes que incluye los artículos A, B, y C. Después se ejecutan las planificaciones maestras para el mismo plan, pero se aplican diferentes filtros de tiempo de ejecución:

- **Filtro de tiempo de ejecución que incluye el artículo D:** no hay artículos planificados, porque no hay intersección entre el filtro del plan y el filtro del tiempo de ejecución.
- **Filtro de tiempo de ejecución que incluye los artículos A y D:** solo se incluye el artículo A en la ejecución de la planificación, porque el artículo D no es parte del filtro del plan.
- **Filtro de tiempo de ejecución que incluye el artículo B:** solo se incluye el artículo B en la ejecución de la planificación, y el resultado de la planificación anterior para el artículo A se conserva.
- **Filtro de tiempo de ejecución que incluye todos los artículos (filtro en blanco):** los artículos A, B, y C se incluye en la ejecución de la planificación y el resultado de la planificación anterior para los artículos A y B se anula.

> [!NOTE]
> Si establece un filtro de plan en el plan que se selecciona como **Plan maestro dinámico actual** en la página **Parámetros de planificación maestra**, la funcionalidad del plan maestro dinámico se limitará a los elementos filtrados. Por ejemplo, si los requisitos netos se actualizan para un elemento que no sea parte del filtro del plan, no se generará ningún resultado.

## <a name="related-resources"></a>Recursos relacionados

[Visión general de la optimización de la planificación](planning-optimization-overview.md)

[Introducción a la optimización de planificación](get-started.md)

[Análisis de aptitud de la optimización de la planificación](planning-optimization-fit-analysis.md)

[Ver el historial del plan y los registros de planificación](plan-history-logs.md)

[Cancelar un trabajo de planificación](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
