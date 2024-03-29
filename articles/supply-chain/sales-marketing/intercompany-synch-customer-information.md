---
title: Sincronizar información de cliente de empresas vinculadas
description: Este artículo explica la sincronización de información de cliente para pedidos de empresas vinculadas
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
ms.openlocfilehash: a3a67c9bcf93f88375d2d4d78d87175200626d50
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897527"
---
# <a name="synchronize-intercompany-customer-information"></a>Sincronizar información de cliente de empresas vinculadas

[!include [banner](../../includes/banner.md)]

La información del cliente se sincroniza si el campo **Información del cliente** está habilitado al crear el pedido de ventas o cuando se realiza un cambio en el cliente, en la referencia del proveedor o en el número de pedido del cliente.

Siempre puede cambiar el valor en los campos de sincronización. Sin embargo, puede determinar si este valor se copia en los otros pedidos de empresas vinculadas si selecciona este parámetro. Si ha habilitado el campo **Información del cliente** en el pedido de ventas de empresas vinculadas, se sincroniza un cambio del pedido de ventas de empresas vinculadas con el pedido de compra de empresas vinculadas. Si también ha habilitado el campo **Información del cliente** en el pedido de compra de empresas vinculadas, se vuelve a sincronizar con el pedido de ventas original.

> [!NOTE]
> Si ha habilitado el campo **Información del cliente** en el pedido de compra de empresas vinculadas y en el pedido de ventas de empresas vinculadas, las actualizaciones realizadas por una persona en una empresa se anulan por las actualizaciones realizadas por otra persona de otra empresa en el mismo pedido.

La práctica recomendada es habilitar el campo **Información del cliente** en el pedido de compra de empresas vinculadas. Esto permite la sincronización entre el pedido de ventas original y el pedido de compra de la empresa vinculada y del pedido de compra de empresas vinculadas con el pedido de ventas de empresas vinculadas.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
