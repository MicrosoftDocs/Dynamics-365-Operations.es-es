---
title: Conversiones de divisa de empresas vinculadas
description: En este tema se explican las conversiones de moneda para transacciones entre empresas vinculadas
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
ms.openlocfilehash: f0af05c324bb67744ba6650e3d7a4ba8b958040e
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "8671909"
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
