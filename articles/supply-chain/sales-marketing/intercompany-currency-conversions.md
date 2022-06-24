---
title: Conversiones de divisa de empresas vinculadas
description: En este artículo se explican las conversiones de moneda para transacciones entre empresas vinculadas
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
ms.openlocfilehash: 41bfafc0dcb3bd356931b67dc63b717c0d098116
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8851489"
---
# <a name="intercompany-currency-conversions"></a>Conversiones de divisa de empresas vinculadas

[!include [banner](../../includes/banner.md)]

Si el código de divisa del pedido de ventas original y del pedido de compra de empresas vinculadas difiere y la sincronización está habilitada, se convierte la divisa de los campos siguientes:

- **Precio unitario**
- **Cargos de venta** o **Cargos por compras**
- **Descuento**
- **Descuento multilínea**

A continuación, estos campos se sincronizan con la línea de pedido de ventas de empresas vinculadas.

Sin embargo, dado que la divisa del pedido de compra y de ventas de empresas vinculadas siempre está sincronizada, los campos siguientes se sincronizan sin conversión de divisa:

- **Precio unitario**
- **Cargos de venta** o **Cargos por compras**
- **Descuento**
- **Porcentaje de descuento**
- **Descuento multilínea**
- **Porcentaje de descuento multilínea**

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
