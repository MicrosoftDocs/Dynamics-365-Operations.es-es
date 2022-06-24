---
title: Sincronizar precios y descuentos de empresas vinculadas
description: Este artículo explica la sincronización de precios y descuentos para pedidos de venta y pedidos de compra de empresas vinculadas
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
ms.openlocfilehash: 64130c400212a819f931cc36459667e4d7c83f32
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905700"
---
# <a name="synchronize-intercompany-prices-and-discounts"></a>Sincronizar precios y descuentos de empresas vinculadas

[!include [banner](../../includes/banner.md)]

Los descuentos y los precios siempre se sincronizan entre el pedido de ventas de empresas vinculadas y el pedido de compra de empresas vinculadas. También puede sincronizar el precio y los descuentos para y desde el pedido de ventas original de forma que todos los pedidos tengan los mismos precios y descuentos. Haces esto desde la página **Empresas vinculadas** a la que se accede desde la pestaña **General** en la página de la lista **Todos los clientes** - ya sea de **Ventas y marketing** o de **Adquisiciones y abastecimiento**.

El campo **Precio y descuento** está sincronizado con la línea del pedido de venta de empresas vinculadas. Esto significa que, al seleccionar el campo **Permitir edición de precio** y el campo **Permitir edición de descuentos**, se ha permitido un cambio entre el pedido de venta de empresas vinculadas y el pedido de compra de empresas vinculadas. Un cambio en el precio unitario, la unidad de precio o un cargo de gastos de ventas en el pedido de venta de empresas vinculada determina el precio en la línea del pedido de compra de empresas vinculadas.

Si el campo **Permitir edición de precio** y el campo **Permitir edición de descuento** están habilitados en el pedido de ventas de empresas vinculadas o el pedido de compra de empresas vinculadas, puede cambiar el precio o descontarlo manualmente en cada pedido. De lo contrario, no es posible.

Si el campo **Permitir edición de precio** y el campo **Permitir edición de descuento** no están habilitados en el pedido de ventas de empresas vinculadas no puede hacer un cambio manual al precio (o costes) o descuento de un pedido de ventas de empresas vinculadas.

Si el campo **Permitir edición de precio** y el campo **Permitir edición de descuento** no están habilitados en el pedido de compras de empresas vinculadas no puede hacer un cambio manual al precio (o costes) o descuento de un pedido de compras de empresas vinculadas.

Si el campo **Permitir edición de precio** y el campo **Permitir edición de descuento** están habilitados en el pedido de ventas de empresas vinculadas y el pedido de compra de empresas vinculadas, puede hacer cambios manuales a ambos pedidos. No obstante, esto puede provocar que las actualizaciones realizadas por una persona se anulen por las actualizaciones realizadas por otra persona de otra empresa del mismo pedido.

> [!NOTE]
> Si ha habilitado el campo **Precio y descuento** en el pedido de compra de empresas vinculadas y el pedido de ventas de empresas vinculadas, no tiene el control de los precios.

Para evitar estos tipos de conflictos, la práctica recomendada consiste en permitir que los precios y los descuentos se modifiquen únicamente en el pedido de ventas de empresas vinculadas o el pedido de compra de empresas vinculadas. Esto se logra habilitando los campos **Permitir edición del precio** y **Permitir edición de descuento** campos en cualquiera de estos pedidos.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
