---
title: Planificación con cantidades negativas disponibles
description: Este tema explica cómo se maneja la disponibilidad negativa cuando utiliza la optimización de planificación.
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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 72367927a11879adffe68d7242d88f5cfab73e22
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436824"
---
# <a name="planning-with-negative-on-hand-quantities"></a>Planificación con cantidades negativas disponibles

[!include [banner](../../includes/banner.md)]

Si el sistema muestra una cantidad agregada negativa disponible, el motor de planificación trata la cantidad como 0 (cero) para ayudar a evitar el exceso de oferta. Así es como funciona esta funcionalidad:

1. La función de optimización de planificación agrega cantidades disponibles en el nivel más bajo de dimensiones de cobertura. (Por ejemplo, si *ubicación* no es una dimensión de cobertura, la optimización de planificación agrega cantidades disponibles en el nivel *almacén*).
1. Si la cantidad disponible en el nivel más bajo de las dimensiones de cobertura es negativa, el sistema supone que la cantidad disponible es realmente 0 (cero).

> [!IMPORTANT]
> El sistema de planificación solo puede ser tan preciso como los datos de entrada. Si los datos de entrada son inexactos, los registros negativos disponibles indicarán que la información de inventario en Microsoft Dynamics 365 Supply Chain Management no está sincronizada con el mundo real. Por lo tanto, el resultado de la planificación será defectuoso. Para obtener un resultado de planificación preciso, debe minimizar la cantidad de registros que muestran una cantidad disponible negativa.

## <a name="example-1"></a>Ejemplo 1

El almacén 13 se configura de la siguiente manera:

- **Código de cobertura:** Mín./Máx.
- **Mínimo:** 15 unidades (uds.)
- **Máximo:** 25 uds.

El nivel más bajo de dimensiones de cobertura es *almacén*, y las siguientes cantidades disponibles se registran en el nivel *ubicación*:

- **Sitio 1, almacén 13, ubicación 1:** 20 uds.
- **Sitio 1 almacén 13, ubicación 2:** &minus;8 uds.

Por lo tanto, la cantidad total disponible para el almacén 13 es de 12 unidades. (= 20 uds. &minus; 8 uds.).

En este caso, el motor de planificación utiliza una cantidad total disponible de 12 unidades. para almacén 13.

El resultado es un pedido planificado de 13 uds. (= 25 uds. &minus; 12 uds.) para rellenar el almacén 13 desde 12 uds. a 25 unidades.

## <a name="example-2"></a>Ejemplo 2

El almacén 13 se configura de la siguiente manera:

- **Código de cobertura:** Mín./Máx.
- **Mínimo:** 15 uds.
- **Máximo:** 25 uds.

El nivel más bajo de dimensiones de cobertura es *almacén*, y las siguientes cantidades disponibles se registran en el nivel *ubicación*:

- **Sitio 1, almacén 13, ubicación 1:** 4 uds.
- **Sitio 1 almacén 13, ubicación 2:** &minus;8 uds.

Por lo tanto, la cantidad total disponible para el almacén 13 es de &minus;4 unidades. (= 4 uds. &minus; 8 uds.). En otras palabras, es menor de 0 (cero).

En este caso, el motor de planificación supone que la cantidad disponible para el almacén 13 es 0 unidades. en lugar de &minus;4 uds.

El resultado es un pedido planificado de 25 uds. (= 25 uds. &minus; 0 uds.) para rellenar el almacén 13 desde 0 uds. a 25 unidades.

## <a name="related-resources"></a>Recursos relacionados

[Visión general de la optimización de la planificación](planning-optimization-overview.md)

[Introducción a la optimización de la planificación](get-started.md)

[Análisis de aptitud de la optimización de la planificación](planning-optimization-fit-analysis.md)

[Ver el historial del plan y los registros de planificación](plan-history-logs.md)

[Cancelar un trabajo de planificación](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]