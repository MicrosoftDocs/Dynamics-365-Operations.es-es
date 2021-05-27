---
title: La cantidad de pedido de cuarentena iniciado no se actualiza cuando se divide el pedido
description: Cuando crea un pedido de cuarentena e intenta dividirlo, la cantidad del pedido no se actualiza a la cantidad restante dividida.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: shawan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: a8af535257ce217629d5ba92e624623c3ea39345
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026894"
---
# <a name="quantity-on-a-started-quarantine-order-isnt-updated-when-the-order-is-split"></a><span data-ttu-id="d6925-103">La cantidad de pedido de cuarentena iniciado no se actualiza cuando se divide el pedido</span><span class="sxs-lookup"><span data-stu-id="d6925-103">Quantity on a started quarantine order isn't updated when the order is split</span></span>

<span data-ttu-id="d6925-104">Número de KB: 4613113</span><span class="sxs-lookup"><span data-stu-id="d6925-104">KB number: 4613113</span></span>

## <a name="symptoms"></a><span data-ttu-id="d6925-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="d6925-105">Symptoms</span></span>

<span data-ttu-id="d6925-106">Cuando crea un pedido de cuarentena e intenta dividirlo, la cantidad del pedido no se actualiza a la cantidad restante después de la división.</span><span class="sxs-lookup"><span data-stu-id="d6925-106">When you create a quarantine order and try to split it, the order quantity isn't updated to the remaining quantity after the split.</span></span>

## <a name="resolution"></a><span data-ttu-id="d6925-107">Resolución</span><span class="sxs-lookup"><span data-stu-id="d6925-107">Resolution</span></span>

<span data-ttu-id="d6925-108">El sistema no cambia la cantidad original de un pedido de cuarentena para garantizar que pueda realizar un seguimiento de la cantidad original que se creó para ese pedido de cuarentena.</span><span class="sxs-lookup"><span data-stu-id="d6925-108">The system doesn't change the original quantity from a quarantine order to ensure that you can track the original quantity that was created for that quarantine order.</span></span> <span data-ttu-id="d6925-109">Sin embargo, el sistema realiza un seguimiento de la cantidad que se divide de un pedido de cuarentena.</span><span class="sxs-lookup"><span data-stu-id="d6925-109">However, the system does track the quantity that is split from a quarantine order.</span></span> <span data-ttu-id="d6925-110">Para hacer este seguimiento, utiliza un campo de base de datos que se denomina `QuantityThatHasSplitIntoOtherQuarantineOrders`.</span><span class="sxs-lookup"><span data-stu-id="d6925-110">To do this tracking, it uses a database field that is named `QuantityThatHasSplitIntoOtherQuarantineOrders`.</span></span> <span data-ttu-id="d6925-111">Sin embargo, este campo no es visible en la interfaz de usuario (UI).</span><span class="sxs-lookup"><span data-stu-id="d6925-111">However, this field isn't visible in the user interface (UI).</span></span>
