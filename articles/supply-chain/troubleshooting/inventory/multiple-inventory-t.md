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
# <a name="multiple-inventory-transactions-for-batch-numbers-when-on-physical-update-is-disabled"></a><span data-ttu-id="0b454-103">Múltiples transacciones de inventario para números de lote cuando Con Actualización física está desactivada</span><span class="sxs-lookup"><span data-stu-id="0b454-103">Multiple inventory transactions for batch numbers when On physical update is disabled</span></span>

<span data-ttu-id="0b454-104">Número de KB: 4613390</span><span class="sxs-lookup"><span data-stu-id="0b454-104">KB number: 4613390</span></span>

## <a name="symptoms"></a><span data-ttu-id="0b454-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="0b454-105">Symptoms</span></span>

<span data-ttu-id="0b454-106">Se crean varias transacciones de inventario después de ajustar una línea de pedido de compra para artículos en los que la opción **Con Actualización física** del grupo de número de lote está establecida en *No*.</span><span class="sxs-lookup"><span data-stu-id="0b454-106">Multiple inventory transactions are created after you adjust a purchase order line for items where the **On physical update** option of the batch number group is set to *No*.</span></span>

<span data-ttu-id="0b454-107">Cuando crea un artículo donde la opción **Con Actualización física** del grupo de número de lote es *No*, el sistema crea automáticamente un nuevo número de lote si modifica una cantidad de línea de compra y guarda la página de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="0b454-107">When you create an item where the **On physical update** option of the batch number group is set to *No*, the system automatically creates a new batch number if you modify a purchase line quantity and save the purchase order page.</span></span>

## <a name="resolution"></a><span data-ttu-id="0b454-108">Resolución</span><span class="sxs-lookup"><span data-stu-id="0b454-108">Resolution</span></span>

<span data-ttu-id="0b454-109">El ajuste **Con Actualización física** para grupos de números de lote funciona de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="0b454-109">The **On physical update** setting for batch number groups works in the following way:</span></span>

- <span data-ttu-id="0b454-110">Cuando la opción se establece en *Sí*, los nuevos números de lote se crean solo después de una actualización física (por ejemplo, cuando los artículos se envían o reciben).</span><span class="sxs-lookup"><span data-stu-id="0b454-110">When the option is set to *Yes*, new batch numbers are created only after a physical update (for example, when items are shipped or received).</span></span>
- <span data-ttu-id="0b454-111">Cuando la opción se establece en *No*, se crea un nuevo número de lote cada vez que se produce una actualización aplicable (por ejemplo, cuando se agrega una nueva cantidad a un pedido de compra).</span><span class="sxs-lookup"><span data-stu-id="0b454-111">When the option is set to *No*, a new batch number is created every time that an applicable update occurs (for example, when a new quantity is added to a purchase order).</span></span>
