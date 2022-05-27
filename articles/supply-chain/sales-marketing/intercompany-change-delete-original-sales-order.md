---
title: Cambiar o eliminar un pedido de ventas original de empresas vinculadas
description: Este tema explica cómo cambiar y eliminar la funcionalidad de un pedido de cliente original
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
ms.openlocfilehash: cfacd1710aa5812230395409f1dd7c2e882faa9f
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "8673757"
---
# <a name="change-or-delete-an-original-intercompany-sales-order"></a>Cambiar o eliminar un pedido de ventas original de empresas vinculadas

[!include [banner](../../includes/banner.md)]

Al cambiar un pedido de ventas, sus cambios se sincronizan automáticamente con el pedido de compra de empresas vinculadas y con el pedido de ventas de empresas vinculadas.

> [!NOTE]
> Los pedidos de compra para los proveedores externos no se ven afectados por los cambios que realice y lo mismo sucede con las líneas de ventas originales que estén conectadas a las líneas de pedido de compra para los proveedores externos.

La siguiente tabla resume los cambios que puede realizar y los resultados esperados.

| Operación | Resultado |
|---|---|
| Borrar&nbsp;un&nbsp;pedido de&nbsp;ventas&nbsp;original. | También se elimina el pedido de compra de empresas vinculadas y el pedido de ventas de empresas vinculadas relacionadas. Si el estado del pedido es **Lista de selección** o posterior en el proceso, no puede eliminar el pedido de ventas. |
| Elimine una línea de pedido de ventas original. | Se elimina la línea de pedido de compra de empresas vinculadas y la línea de pedido de venta de empresas vinculadas relacionadas. Si el estado del pedido es **Lista de selección** o posterior en el proceso, no puede eliminar la línea del pedido de ventas. |
| Agregar una nueva línea de ventas a un pedido de ventas original. | La nueva línea de ventas se crea en el pedido de compra de empresas vinculadas y el pedido de ventas de empresas vinculadas. |
| Cambie la cantidad en una línea de pedido de ventas original. | La cantidad se sincroniza con la línea de pedido de compra de empresas vinculadas y con la línea de pedido de ventas de empresas vinculadas. El importe neto se vuelve a calcular en todos los pedidos. |
| Deshabilitar la entrega directa en un pedido de ventas original. | No puede cambiar el campo **Entrega directa** en el pedido de ventas original si la línea de pedido de ventas de empresas vinculadas ha alcanzado un estado mínimo de **Lista de selección**, **Orden de salida**, o **Diario de lista de selección**. La dirección de entrega del pedido de compra de empresas vinculadas se cambia a la dirección de entrega estándar (dirección de entrega del pedido de compra estándar). Además, las líneas del pedido de compra de empresas vinculadas se cambia a la dirección de entrega estándar de las líneas. Ambas se sincronizan con el pedido de ventas de empresas vinculadas y las líneas. El tipo de entrega de todas las líneas en el pedido de ventas original se cambia a **Ninguno** y el campo se sincroniza con las líneas de pedido de compra de empresas vinculadas. Los pedidos de compra para los proveedores externos no se ven afectados y lo mismo sucede con las líneas de ventas originales conectadas a las líneas del pedido de compra para los proveedores externos. La fecha de entrega de las líneas y el pedido de compra de empresas vinculadas (y las fechas de recepción/envío solicitadas de las líneas y el pedido de ventas de empresas vinculadas) se actualizan. |
| Habilite la entrega directa en un pedido de ventas original. | Si la línea de pedido de ventas de empresas vinculadas ha alcanzado un estado mínimo de **Lista de selección**, **Orden de salida**, o **Diario de lista de selección** puede cambiar el campo **Entrega directa** en el pedido de ventas original. La dirección de entrega del pedido de compra de empresas vinculadas se cambia a la dirección de entrega desde el pedido de ventas original y se sincroniza con el pedido de venta de empresas vinculadas. El tipo de entrega de todas las líneas en el pedido de ventas original se cambia a **Entrega directa** y el campo se sincroniza con las líneas de pedido de compra de empresas vinculadas. La dirección de entrega de cada línea de pedido de ventas original se sincroniza con las líneas del pedido de compra de empresas vinculadas y con las líneas del pedido de ventas de empresas vinculadas. La fecha de entrega de las líneas y el pedido de compra de empresas vinculadas (y las fechas de recepción/envío solicitadas de las líneas y el pedido de ventas de empresas vinculadas) se actualizan. |
| Agregar una nota a las líneas y a la cabecera del pedido de ventas original. | La nota se copia en el pedido de compra de empresas vinculadas y en el pedido de ventas de empresas vinculadas. |
| Cambiar o eliminar una nota. | Si cambia o elimina una nota, la nota correspondiente en el pedido de compra de empresas vinculadas y el pedido de ventas de empresas vinculadas se cambia o elimina de igual forma. |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
