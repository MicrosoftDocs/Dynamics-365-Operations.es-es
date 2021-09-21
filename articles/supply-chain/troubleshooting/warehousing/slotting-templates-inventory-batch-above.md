---
title: Inventario disponible no considerado para los artículos por encima de lotes
description: Algunas plantillas de slotting no consideran el inventario disponible actual para los artículos por encima de lotes. El lote o número de serie debe especificarse en la orden de demanda.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: df5642b32f5e053144230eab3dbcf633f526279a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477524"
---
# <a name="slotting-templates-dont-consider-on-hand-inventory-for-batch-above-items"></a>Las plantillas de slotting no consideran el inventario disponible para los artículos por encima de lotes

## <a name="symptoms"></a>Síntomas

Las plantillas de posicionamiento que tienen el criterio *Considerar espacio disponible* no consideran el inventario disponible actual para los artículos *batch-above*. Solo lo tienen en cuenta si el número de lote se especifica en la línea de orden de venta.

Sin embargo, cuando usa artículos *batch-below*, el inventario disponible actual se considera como esperado.

Para más información, consulte [Slotting de almacén](/dynamics365/supply-chain/warehousing/warehouse-slotting).

## <a name="resolution"></a>Resolución

El encabezado de la plantilla de planificación se puede definir para la estrategia de demanda *Ordenada*, *Reservada*, o *Publicada*. Para la estrategia de demanda *Ordenada*, se aplican los mismos requisitos de jerarquía de reservas que se aplican a los procesos de reserva o liberación a almacén. Por lo tanto, para los artículos que tienen *batch-above* y *serial-below* como jerarquías de reserva, el lote o número de serie debe especificarse en la orden de demanda (venta o transferencia).

Alternativamente, la estrategia de demanda *Reservada* se puede utilizar para seleccionar el lote o el número de serie antes de que se genere la demanda de asignación del almacén.
