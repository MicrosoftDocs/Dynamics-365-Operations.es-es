---
title: Múltiples transacciones de inventario para números de lote cuando Con Actualización física está desactivada
description: Se crean varias transacciones de inventario después de ajustar una línea de pedido de compra para artículos en los que la opción Con Actualización física del grupo de número de lote está establecida en No.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventNumGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1fa54cdfdbc5608fb6c7114dced0f96bab47253e
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026895"
---
# <a name="multiple-inventory-transactions-for-batch-numbers-when-on-physical-update-is-disabled"></a>Múltiples transacciones de inventario para números de lote cuando Con Actualización física está desactivada

Número de KB: 4613390

## <a name="symptoms"></a>Síntomas

Se crean varias transacciones de inventario después de ajustar una línea de pedido de compra para artículos en los que la opción **Con Actualización física** del grupo de número de lote está establecida en *No*.

Cuando crea un artículo donde la opción **Con Actualización física** del grupo de número de lote es *No*, el sistema crea automáticamente un nuevo número de lote si modifica una cantidad de línea de compra y guarda la página de pedido de compra.

## <a name="resolution"></a>Resolución

El ajuste **Con Actualización física** para grupos de números de lote funciona de la siguiente manera:

- Cuando la opción se establece en *Sí*, los nuevos números de lote se crean solo después de una actualización física (por ejemplo, cuando los artículos se envían o reciben).
- Cuando la opción se establece en *No*, se crea un nuevo número de lote cada vez que se produce una actualización aplicable (por ejemplo, cuando se agrega una nueva cantidad a un pedido de compra).
