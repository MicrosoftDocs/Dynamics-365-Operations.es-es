---
title: La ubicación de la dimensión no puede estar en blanco si se establece el número de serie
description: Si recibe este error al confirmar un envío después de crear una orden de transferencia para un artículo en serie, el campo Ubicación de recepción predeterminada está en blanco.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6f58c72438d5d1d93e59e46525debd65d44d9a76
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477560"
---
# <a name="error-when-confirming-shipment-after-creating-a-transfer-order-for-a-serial-item"></a>Error al confirmar el envío después de crear un pedido de transferencia para un artículo en serie

## <a name="symptoms"></a>Síntomas

Si crea una orden de transferencia para un elemento en serie utilizando un almacén que está habilitado para la administración avanzada de almacenes (WMS) y, luego, una vez completado el trabajo, intenta confirmar el envío, recibe el siguiente mensaje de error:

> La ubicación de la dimensión no puede estar en blanco si se establece el número de serie de la dimensión.

## <a name="cause"></a>Causa

Esto sucede porque el campo **Ubicación de recibo predeterminada** está en blanco para un almacén de tránsito del almacén "desde".

## <a name="resolution"></a>Resolución

Para solucionar este problema, especifique una ubicación de recepción predeterminada en el almacén de tránsito. Asegúrese de que esta ubicación esté controlada por matrículas.
