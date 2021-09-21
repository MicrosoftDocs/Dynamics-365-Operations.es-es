---
title: Los precios unitarios de los pedidos de compra no se calculan en función de la conversión de unidades
description: Los precios unitarios de los pedidos de compra no se calculan en función de la conversión de unidades
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 4695f4661c3abb8ab38e3ca74b513e8529e37d20
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477519"
---
# <a name="unit-prices-on-purchase-orders-arent-calculated-based-on-the-unit-conversion"></a>Los precios unitarios de los pedidos de compra no se calculan en función de la conversión de unidades

## <a name="symptoms"></a>Síntomas

Cuando se cambia una unidad en un pedido de compra, los precios de los acuerdos comerciales no se vuelven a calcular de acuerdo con las definiciones de conversión de unidades.

## <a name="cause"></a>Causa

Los precios siempre se obtienen de acuerdos comerciales (u otras configuraciones de precios en el sistema, como acuerdos de venta o precios de artículos) y se establecen para una unidad.

Si se cambia la unidad en una línea de pedido, el sistema busca un precio para la nueva unidad y aplica ese precio. Si no se encuentra un precio para la unidad, el sistema no aplica un precio. La conversión de unidades no se puede utilizar para volver a calcular el precio en otra unidad. En teoría, el precio de una caja de diez podría no ser igual a diez veces el precio de una caja.

## <a name="workaround"></a>Solución alternativa

Una forma de solucionar este problema es asegurarse de que existen acuerdos comerciales para las unidades que espera que se utilicen en las líneas de pedido de artículo.
