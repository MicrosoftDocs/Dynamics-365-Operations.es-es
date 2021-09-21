---
title: Solo puede completar una acción de orden de compra para números de línea completamente distribuidos
description: Solo puede completar una acción en una compra después de que el número de línea esté completamente distribuido
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 1ef2a938a2a17bc2dbf38d09918eabdbccca8a28
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477562"
---
# <a name="you-can-only-complete-a-purchase-order-action-for-fully-distributed-line-numbers"></a>Solo puede completar una acción de orden de compra para números de línea completamente distribuidos

## <a name="symptom"></a>Síntoma

Solo puede completar una acción en una compra después de que el número de línea esté completamente distribuido.

## <a name="cause"></a>Causa

Este problema se puede producir debido a incoherencias en las distribuciones de pedidos de compra.

## <a name="resolution"></a>Resolución

Para desbloquear este problema y restablecer el pedido de compra al estado *Borrador*, vaya a **Adquisiciones y abastecimiento \> Tareas periódicas \> Limpiar \> Restablecimiento de distribución de pedido de compra**. Para obtener más información, consulte la siguiente publicación de blog: [Resolver errores de distribución de pedidos de compra en Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).
