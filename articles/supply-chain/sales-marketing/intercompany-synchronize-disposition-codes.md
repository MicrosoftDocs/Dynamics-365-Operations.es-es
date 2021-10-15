---
title: Sincronizar códigos de disposición
description: Este tema explica la sincronización de códigos de disposición para el comercio entre empresas
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 04a25324e79a1f9cb30a7da19d648bda995ba7b2
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548509"
---
# <a name="synchronize-intercompany-disposition-codes"></a>Sincronizar códigos de disposición de empresas vinculadas

[!include [banner](../../includes/banner.md)]

Para admitir las devoluciones de empresas vinculadas, Microsoft Dynamics 365 Supply Chain Management permite asignar códigos de disposición definidos externamente a los códigos de disposición internos correspondientes. Cuando se configura una cadena de empresas vinculadas, las acciones de disposición de ambas empresas asignadas entre ellas deben ser las mismas. Si son diferentes, el proceso de sincronización no se llevará a cabo correctamente.

## <a name="about-disposition-codes-for-three-legged-direct-returns"></a>Acerca de los códigos de disposición de devoluciones directas de tres segmentos

Los códigos de disposición se sincronizan entre la línea del pedido de ventas de empresas vinculadas y la línea del pedido de ventas original. Sin embargo, la sincronización tiene un único efecto inmediato en la línea del pedido de ventas original. Este efecto consiste en que los gastos varios de la línea se eliminan en función del código de disposición y de los gastos varios configurados en la Empresa A. La empresa A es la empresa que crea el pedido de devolución.

En una cadena de entrega directa de tres segmentos, todas las acciones de disposición se admiten en la línea del pedido de ventas de empresas vinculadas. Sin embargo, si un producto se devuelve al cliente, deberá comprobar que la dirección de entrega del pedido de devolución coincide con la dirección de entrega del cliente especificada en el pedido original.

> [!NOTE]
> Los códigos de disposición no existen para pedidos de compras. Por lo tanto, la sincronización de códigos de disposición entre el pedido de ventas de empresas vinculadas y el pedido de devolución original, se debe efectuar de pedido de ventas a pedido de ventas.

## <a name="replacing-returned-items"></a>Reemplazo de artículos devueltos

Si se reemplaza un artículo devuelto, y ya se ha creado un pedido de sustitución en la Empresa B, no se puede seleccionar ningún código de disposición y no se crea ningún pedido de sustitución adicional en la Empresa A.

## <a name="rules-for-intercompany-direct-deliveries"></a>Reglas para entregas directas de empresas vinculadas

Las siguientes reglas generales se aplican a los pedidos de devolución originales en las situaciones que implican entregas directas de empresas vinculadas:

- Si la acción de disposición vinculada en el pedido de ventas original es de crédito y residuo, crédito o devolución al cliente, se aplica la acción de disposición de Crédito. Sin embargo, el código de acción de Devolución al cliente establece el importe neto en 0 (cero) en la línea existente y en la línea recién sincronizada del pedido de ventas de empresas vinculadas. Asimismo, las líneas de residuo nunca se sincronizan. Cuando se añade una línea a un pedido de ventas de empresas vinculadas, nunca se sincroniza para un pedido de ventas que tenga una cantidad positiva y una acción de disposición de Residuo (por ejemplo, crédito y residuo, o reemplazo y residuo).
- Una acción de disposición vinculada de crédito y reemplazo, o residuo y reemplazo, no se anula. Se tratará como acción de disposición de crédito y reemplazo, o de residuo y reemplazo. Esta regla se aplica aunque no se haya creado ninguna línea de residuo en la Empresa A, ni ningún pedido de sustitución en la Empresa B (la empresa que recibe el artículo devuelto). Sólo se crea un pedido de sustitución en la Empresa A cuando se efectúa una actualización de albarán.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
