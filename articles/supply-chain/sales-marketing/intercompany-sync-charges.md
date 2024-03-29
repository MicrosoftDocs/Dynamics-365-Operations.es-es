---
title: Sincronizar cargos de empresas vinculadas
description: Este artículo explica la sincronización de cargos entre empresas vinculadas
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
ms.openlocfilehash: e7b3de3d7da7be6c1c8b5c3842862e7bccd78277
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857297"
---
# <a name="synchronize-intercompany-charges"></a>Sincronizar cargos de empresas vinculadas

[!include [banner](../../includes/banner.md)]

Los gastos solo se sincronizan entre el pedido de ventas y de compra de empresas vinculadas. Esta sincronización se realiza siempre.

Si el campo **Permitir la edición de precio** está seleccionado en el pedido de compra o de ventas de la empresa vinculada, puede agregar manualmente gastos al pedido de ventas o de compra de la empresa vinculada. De lo contrario, no es posible.

Si el campo **Permitir edición de precio** no está seleccionado en el pedido de ventas de la empresa vinculada, no puede agregar gastos manualmente a un pedido de ventas de empresas vinculadas.

Si el campo **Permitir edición de precio** no está seleccionado en el pedido de compra de la empresa vinculada, no puede agregar gastos en el pedido de ventas de empresas vinculadas.

Si el campo **Permitir edición de precio** está habilitado en el pedido de compra y de ventas de la empresa vinculada, puede agregar gastos a ambos pedidos manualmente. No obstante, esto puede provocar que se agreguen muchos gastos de forma incorrecta.

Para evitar estos tipos de conflictos, lo mejor es permitir la adición de gastos al pedido de ventas o de compras de empresas vinculadas, pero no a ambos.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
