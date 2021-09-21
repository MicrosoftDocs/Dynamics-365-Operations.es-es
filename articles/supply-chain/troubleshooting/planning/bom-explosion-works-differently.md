---
title: La explosión de la lista de materiales se comporta de manera diferente para órdenes de producción firmes y estimadas
description: La explosión de la lista de materiales se comporta de manera diferente para las órdenes de producción firmes y para las órdenes de producción estimadas para el trabajo creado manualmente
author: ChristianRytt
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 94d4b00ea30396923a61b2748cf1aaeedc0af8af
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477521"
---
# <a name="bom-explosion-behaves-differently-for-firmed-and-estimated-production-orders"></a>La explosión de la lista de materiales se comporta de manera diferente para órdenes de producción firmes y estimadas

## <a name="symptoms"></a>Síntomas

Cuando se confirma una orden de producción, los artículos no se desglosan cuando se desglosa la lista de materiales (BOM). Sin embargo, cuando crea manualmente una orden de trabajo y luego estima la orden de producción, los artículos se desglosan.

### <a name="resolution"></a>Resolución

La explosión que se produce cuando se confirma la orden de producción apuntará a la orden planificada, pero no parece que la orden planificada esté actualmente firme en este caso. Sin embargo, si se ha estimado la orden de producción, la explosión se desencadena desde la orden de producción liberada donde no existe una orden previsional.
