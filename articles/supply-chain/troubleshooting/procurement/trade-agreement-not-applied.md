---
title: Las condiciones del acuerdo comercial no se aplican a las líneas de pedido importadas
description: Los precios y descuentos de acuerdos comerciales no se aplican a las líneas de pedidos de ventas o de compra que se importan a través de la administración de datos
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
ms.openlocfilehash: fef38819efaff2f2a927cf09fc7f469490149574
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477552"
---
# <a name="trade-agreement-conditions-arent-applied-to-imported-order-lines"></a>Las condiciones del acuerdo comercial no se aplican a las líneas de pedido importadas

## <a name="symptoms"></a>Síntomas

Los acuerdos comerciales que son aplicables a las líneas de pedidos de ventas o de compra no se aplican a líneas que se importan a través de la administración de datos. Sin embargo, los mismos acuerdos comerciales se aplican a las líneas de pedido de compra o de venta que se crean manualmente.

## <a name="cause"></a>Causa

Si las líneas del pedido de compra que se importan a través de la administración de datos ya incluyen información de precios, el acuerdo comercial no se volverá a evaluar para esas líneas. Por ejemplo, si **Porcentaje de descuento de línea** o cualquiera de los valores de precio y descuento se establecen para una línea, los acuerdos comerciales no se buscarán para esa línea.

## <a name="workaround"></a>Solución alternativa

Se espera este comportamiento y es similar tanto para los pedidos de ventas como para los pedidos de compra.

Como solución temporal, importe las líneas del pedido de compra sin establecer ninguna información de precio. A continuación se aplicarán los acuerdos comerciales y las líneas de pedido de compra se actualizarán en función de los acuerdos comerciales definidos.
