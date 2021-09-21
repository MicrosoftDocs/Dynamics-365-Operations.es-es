---
title: Los pedidos de compra cancelados aparecen en la lista de borradores en el espacio de trabajo
description: Los pedidos de compra cancelados aparecen en la lista de borradores en el espacio de trabajo Preparación del pedido de compra
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
ms.openlocfilehash: f1dc23cd7e5b4b99cb7a9440d7d4666d8396511f
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477546"
---
# <a name="canceled-purchase-orders-appear-in-the-draft-list-in-the-workspace"></a>Los pedidos de compra cancelados aparecen en la lista de borradores en el espacio de trabajo

## <a name="symptoms"></a>Síntomas

Después de cancelar pedidos de compra que estaban en estado *Confirmado*, los pedidos de compra cancelados todavía aparecen en la lista de borradores de pedidos de compra en el espacio de trabajo **Preparación del pedido de compra**.

## <a name="resolution"></a>Resolución

Este problema solo se produce para los pedidos de compra que están sujetos a la administración de cambios. Se produce porque se considera que la cancelación es un cambio que debe ser aprobado. La aprobación la puede realizar el sistema automáticamente. Por lo tanto, el proceso consiste en enviar el pedido de compra cancelado al flujo de trabajo de aprobación para que pueda pasar al estado *Aprobado*. En ese momento, el pedido de compra ya no aparecerá en la lista de borradores de pedido de compra en el espacio de trabajo **Preparación del pedido de compra**.
