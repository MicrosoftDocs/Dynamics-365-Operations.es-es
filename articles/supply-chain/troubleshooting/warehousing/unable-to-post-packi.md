---
title: No se puede registrar el albarán para una línea de pedido de ventas detenida.
description: No puede registrar el albarán para una línea de pedido de ventas detenida.
author: smithanataraj
ms.date: 03/07/2022
ms.topic: article
ms.search.form: WHSLoadTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mfp
ms.search.validFrom: 2022-03-07
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: 115cfe79e075eb36f73203818acdbb5e31fc0bad
ms.sourcegitcommit: c0f7ee7f8837fec881e97b2a3f12e7f63cf96882
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2022
ms.locfileid: "8462859"
---
# <a name="cant-post-packing-slip-for-a-stopped-a-sales-order-line"></a>No se puede registrar el albarán para una línea de pedido de ventas detenida.

Código de error: SYS13203

## <a name="symptoms"></a>Síntomas

Cuando intenta registrar un albarán para una carga, el sistema muestra el siguiente mensaje de error:

> No se puede registrar el albarán al detener una línea de pedido de ventas después de confirmar el envío de salida. No se puede seleccionar una cantidad.

## <a name="cause"></a>Causa

Una o más de las líneas de pedidos de venta relacionadas pueden estar detenidas, lo que significa que el sistema evitará el procesamiento posterior de ese pedido de venta. Entre otras cosas, esto significa que el sistema no registrará un albarán para el pedido.

Por ejemplo, un usuario puede haber decidido detener una o más líneas de pedido porque el cliente le devolvió la llamada y canceló su pedido. Sin embargo, si el envío de salida ya se había confirmado, entonces el envío que contiene el pedido de venta ya habría salido físicamente del almacén, así que detener las líneas del pedido de venta no tendrá ningún efecto. Debido a que ya no es posible detener físicamente el envío, también puede cancelar la detención de líneas para poder registrar el albarán. A continuación, deberá gestionar el pedido cancelado como una devolución.

## <a name="resolution"></a>Resolución

Para poder registrar el albarán, asegúrese de que ninguna de las líneas de pedido de venta relevantes esté detenida; para ellos, siga estos pasos.

1. Vaya a **Todos los pedidos de ventas \> Ventas y marketing \> Todos los pedidos de ventas**.
1. Busque y abra el pedido de ventas con el que tiene problemas.
1. En la ficha desplegable **Líneas de pedido de ventas**, seleccione una línea de pedido de ventas.
1. En la ficha desplegable **Detalles de línea**, abra la pestaña **General** y compruebe que el campo **Detenido** esté en *No*.
1. Continúe trabajando hasta que todas las líneas de venta relevantes ya no estén detenidas.
1. Vuelva a intentar registrar el albarán para la carga o el pedido de ventas.
