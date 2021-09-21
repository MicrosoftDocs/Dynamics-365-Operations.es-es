---
title: Error de cantidad sin errores total al intentar finalizar un pedido
description: Al intentar finalizar una orden de producción e informar como terminada, es posible que reciba un error de cantidad total correcta. Esta página explica por qué y cómo corregir el problema.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 5f0c2c2ca64ada9d72c0ebd04e7de561aaa52039
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477514"
---
# <a name="total-good-quantity-error-when-trying-to-end-a-production-order"></a>Error de cantidad sin errores total al intentar finalizar un pedido de producción

## <a name="symptoms"></a>Síntomas

Cuando intenta publicar un informe como diario terminado en una orden de producción, recibe el siguiente mensaje de error:

> La cantidad sin errores total notificada como terminada para la producción será %1. La realimentación para la última operación es 0.00 en total.

## <a name="cause"></a>Causa

Este problema ocurre si las cantidades contabilizadas en las últimas operaciones eran incorrectas. Por ejemplo, si se inicia la producción, pero no se asigna la cantidad que debe iniciarse, el diario de la tarjeta de ruta se contabilizará sin líneas. Para confirmar la situación, abra la orden de producción y luego, en el Panel de acciones, en la pestaña **Ver**, seleccione **Tarjeta de ruta**.

## <a name="resolution"></a>Resolución

Puede solucionar este problema publicando diarios adicionales para las operaciones para las que los diarios no se publicaron correctamente. Reinicie la orden de producción y seleccione contabilizar los diarios adicionales. Esta acción no iniciará la orden de producción, pero registrará los diarios. La tarjeta de ruta debería mostrar las cantidades que se registraron y debería poder finalizar las órdenes de producción correctamente.
