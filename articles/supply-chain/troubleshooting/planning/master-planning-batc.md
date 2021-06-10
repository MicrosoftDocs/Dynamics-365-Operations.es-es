---
title: No puede filtrar elementos de planificación maestra por sus valores de grupo de cobertura relacionados
description: No puede filtrar elementos de planificación maestra por sus valores de grupo de cobertura relacionados.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: fa0b614b6710c65811add8725a0e255ce2c34b88
ms.sourcegitcommit: 3c15a26e9708adc9a75082dc551f0a3a0a7d89f4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049489"
---
# <a name="you-cant-filter-master-planning-items-by-their-related-coverage-group-values"></a>No puede filtrar elementos de planificación maestra por sus valores de grupo de cobertura relacionados

Número de KB: 4612572

## <a name="symptoms"></a>Síntomas

Desea filtrar los artículos que se incluirán en un trabajo por lotes de planificación maestra, según los valores de los registros relacionados de la tabla de cobertura de artículos. (Por ejemplo, desea filtrar elementos por su **Proveedor** y / o valor de **Grupo de cobertura**). La configuración del filtro para el trabajo por lotes le permite crear una combinación desde la tabla **Artículos** a la tabla **Cobertura de artículos** y, a continuación, especifique los valores de campo de la tabla de cobertura de elementos en su consulta. Sin embargo, después de completar esta configuración, el sistema aún crea órdenes planificadas para toda la cobertura de artículos, no solo para los artículos que coinciden con los valores de campo especificados de la tabla de cobertura de artículos.

## <a name="resolution"></a>Resolución

El filtro de trabajo por lotes solo puede filtrar por elementos. Aunque puede agregar una combinación a la tabla **Cobertura de artículos**, la configuración de filtro que realice en esa tabla no afectará el resultado de la consulta. En runtime, el sistema ejecuta la planificación para todos los grupos de cobertura y todas las variaciones que tienen los artículos filtrados. Una vez que un elemento ya está incluido en la ejecución, los grupos de cobertura incluidos en el filtro de elementos a no afectarán el resultado de la planificación.
