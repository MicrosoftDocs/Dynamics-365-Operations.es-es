---
title: Albaranes de empresas vinculadas
description: Este artículo describe cómo generar e imprimir albaranes para transacciones entre empresas vinculadas
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 3516058bbf925df4b0a0c75286a3d97457cc1e69
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900865"
---
# <a name="intercompany-packing-slips"></a>Albaranes de empresas vinculadas

## <a name="generate-intercompany-packing-slips"></a>Generar albaranes de empresas vinculadas

[!include [banner](../../includes/banner.md)]

Si trabaja con la entrega directa, el albarán siempre se genera automáticamente en el pedido de compra de empresas vinculadas y en el pedido de ventas original cuando se genera el albarán en el pedido de ventas de empresas vinculadas. La factura de pedido de compra de empresas vinculadas se basa en el albarán del pedido de empresas vinculadas generado previamente.

Las actualizaciones del albarán del pedido de ventas de empresas vinculadas se reflejarán en el pedido de compra de empresas vinculadas y en el pedido de ventas original.

Si no trabaja con la entrega directa, debe generar manualmente el albarán en el pedido de ventas de empresas vinculadas, en el pedido de compra de empresas vinculadas y en el pedido de ventas original.

## <a name="print-intercompany-packing-slips"></a>Imprimir albaranes de empresas vinculadas

[!include [banner](../../includes/banner.md)]

Si trabaja con entrega directa, el albarán para el pedido de compra de empresas vinculadas y el pedido de ventas original puede imprimirse automáticamente al registrar el albarán en el pedido de ventas de empresas vinculadas.

Para imprimir los albaranes de forma automática, en la página **Empresas vinculadas** página para pedidos de compra, seleccione los dos campos **Imprimir albarán automáticamente**.

Si actualiza el albarán del pedido de ventas de empresas vinculadas, los cambios se reflejarán automáticamente en el pedido de compra de empresas vinculadas y en el pedido de ventas original.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
