---
title: No se puede cancelar un albarán después de que se haya registrado desde un pedido
description: Cuando los procesos de recolección y envío están habilitados para WMS, no puede cancelar un albarán después de que se haya publicado desde un pedido de cliente. Esta página ofrece una solución.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d20e66e2721560b8409eb63c3546a79adc188c7c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477577"
---
# <a name="cant-cancel-a-packing-slip-after-its-posted-from-a-sales-order"></a>No se puede cancelar un albarán después de que se haya registrado desde un pedido de cliente

## <a name="symptoms"></a>Síntomas

Cuando los procesos de recolección y envío están habilitados para gestión de almacén avanzada (WMS), no puede cancelar un albarán después de que se haya publicado desde un pedido de cliente.

## <a name="resolution"></a>Resolución

Para corregir las notas de empaque publicadas para los artículos que están habilitados para WMS, la publicación debe ocurrir desde la carga, no desde el pedido. Microsoft ha evaluado este problema y ha determinado que es una limitación de funciones.  

En general, una orden de venta que se ha seleccionado y enviado a través de los procesos de gestión de almacén puede actualizarse con un albarán de la carga o envío y el documento de la orden de venta en sí. Sin embargo, si actualiza el albarán, la orden de venta desde el documento de la orden de venta, la reversión del albarán aún no se puede realizar desde la carga o la orden de venta. Por lo tanto, le recomendamos que utilice la publicación del albarán de la carga. En este caso, se habilitará la inversión que se debe hacer desde la carga.
