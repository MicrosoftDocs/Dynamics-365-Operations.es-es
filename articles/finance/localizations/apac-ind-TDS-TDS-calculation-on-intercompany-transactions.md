---
title: Cálculo de TDS en transacciones de empresas vinculadas
description: Este artículo describe el proceso que se utiliza para calcular los impuestos deducidos en el origen (TDS) en transacciones entre empresas vinculadas.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: c27bea997804f2c5eff6be2b20064b272ccd062f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8888984"
---
# <a name="tds-calculation-on-intercompany-transactions"></a>Cálculo de TDS en transacciones de empresas vinculadas

[!include [banner](../includes/banner.md)]

Este artículo describe el proceso que se utiliza para calcular los impuestos deducidos en el origen (TDS) en transacciones entre empresas vinculadas.

Cuando se crea un pedido de compra o pedido de venta entre empresas vinculadas, el grupo de TDS predeterminado que se define para el cliente o proveedor se utiliza para calcular el importe de TDS. El importe de TDS se registra en las cuentas recuperables o de proveedor después de que se registre la factura.

Se crea automáticamente un pedido de venta o un pedido de compra entre empresas vinculadas para el pedido de compra o el pedido de venta original. El grupo de TDS predeterminado se muestra en el pedido entre empresas vinculadas, de modo que se puedan calcular los TDS. Es posible cambiar el grupo de TDS. La factura se puede registrar solo si el importe neto de la factura en el pedido de empresas vinculadas que se crea automáticamente coincide con el importe neto de la factura en el pedido original. (El importe neto es el importe de la factura después de deducir los TDS).

Por ejemplo, se crea una factura de venta por 50 000 y se adjunta el grupo de TDS del **10 %**. El importe de la factura registrada es de 45 000 y el importe de TDS registrado para la factura de venta es de 5000. Se crea automáticamente un pedido de compra para el pedido de venta de empresas vinculadas y se adjunta el grupo de TDS del **10 %**. Si cambia el grupo de TDS a **15 %**, no puede registrar la factura porque el importe neto de la factura del pedido de ventas de empresas vinculadas que se creó automáticamente no coincide con el importe neto de la factura del pedido de venta original.

Un diario de pagos que se crea para una factura de empresas vinculadas se registra automáticamente. Ese diario de pagos se puede registrar solo si el importe del pago neto en él coincide con el importe del pago neto en el diario de pagos original.
