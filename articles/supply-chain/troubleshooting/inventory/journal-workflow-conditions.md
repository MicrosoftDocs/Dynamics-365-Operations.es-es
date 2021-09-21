---
title: Las condiciones del flujo de trabajo del diario de inventario se aplican en el nivel de diario, no a nivel de línea
description: Las condiciones del flujo de trabajo del diario de inventario solo se aplican a nivel de diario, no a nivel de línea.
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 46bdde7f09c639fbefd46162431762b056d521ae
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477523"
---
# <a name="inventory-journal-workflow-conditions-apply-at-the-journal-level-not-line-level"></a>Las condiciones del flujo de trabajo del diario de inventario se aplican en el nivel de diario, no a nivel de línea

## <a name="symptoms"></a>Síntomas

Puede experimentar este problema si, por ejemplo, intenta configurar una condición de flujo de trabajo de diario de inventario en el importe del coste. Configura la condición para que el paso 1 se ejecute únicamente cuando el importe del coste sea menor que 100. A continuación, configura otra condición para que el paso 2 se ejecute únicamente cuando el importe del coste sea mayor o igual que 100. Luego, cuando se ejecuta el flujo de trabajo, el historial de flujo de trabajo muestra solo una línea y la primera condición siempre se evalúa como *verdadero*, independientemente del valor que se envíe.

## <a name="workaround"></a>Solución alternativa

En la versión actual, las condiciones del flujo de trabajo de inventario solo se aplican a nivel de diario, no a nivel de línea. Este comportamiento se debe al diseño. Le recomendamos que establezca sus criterios de condiciones solo en los atributos de nivel de diario.
