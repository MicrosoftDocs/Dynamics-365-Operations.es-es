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
# <a name="quantity-on-a-started-quarantine-order-isnt-updated-when-the-order-is-split"></a>La cantidad de pedido de cuarentena iniciado no se actualiza cuando se divide el pedido

Número de KB: 4613113

## <a name="symptoms"></a>Síntomas

Cuando crea un pedido de cuarentena e intenta dividirlo, la cantidad del pedido no se actualiza a la cantidad restante después de la división.

## <a name="resolution"></a>Resolución

El sistema no cambia la cantidad original de un pedido de cuarentena para garantizar que pueda realizar un seguimiento de la cantidad original que se creó para ese pedido de cuarentena. Sin embargo, el sistema realiza un seguimiento de la cantidad que se divide de un pedido de cuarentena. Para hacer este seguimiento, utiliza un campo de base de datos que se denomina `QuantityThatHasSplitIntoOtherQuarantineOrders`. Sin embargo, este campo no es visible en la interfaz de usuario (UI).
