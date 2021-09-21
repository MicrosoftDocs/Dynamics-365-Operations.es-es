---
title: Error al volver a enviar un pedido de compra a un flujo de trabajo después de un cambio
description: Error al volver a enviar un pedido de compra a un flujo de trabajo después de un cambio
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 4b8465d198c440f27a4b3cc4268445e0aa450f5b
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477571"
---
# <a name="error-on-resubmitting-a-purchase-order-to-a-workflow-after-a-change"></a>Error al volver a enviar un pedido de compra a un flujo de trabajo después de un cambio


## <a name="symptoms"></a>Síntomas

El siguiente error se produce en el flujo de trabajo cuando se vuelve a enviar un pedido de compra después de un cambio:

> Detenido (error): excepción de X++: Los cambios en el pedido de compra PO0000569 solo se permiten en el estado Borrador cuando la administración de cambios está activada en<br>
SysWorkflowParticipantProvider-resolve<br>
SysWorkflowParticipantProvider-resolveParticipants<br>
SysWorkflowServiceProvider-resolveParticipant<br>
SysWorkflowQueue-resume

Este problema solo se produce si el pedido de compra estaba en estado *Confirmado* antes de que se soliciten los cambios. Si solicita cambios mientras el pedido de compra está en estado *Aprobado*, el flujo de trabajo se puede procesar correctamente.

## <a name="resolution"></a>Resolución

Este problema se puede producir debido a incoherencias en las distribuciones de pedidos de compra.

Para desbloquear este problema y restablecer el pedido de compra al estado *Borrador*, vaya a **Adquisiciones y abastecimiento \> Tareas periódicas \> Limpiar \> Restablecimiento de distribución de pedido de compra**. Para obtener más información, consulte la siguiente publicación de blog: [Resolver errores de distribución de pedidos de compra en Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

El problema se solucionará con [este artículo de Microsoft Knowledge Base (KB)](https://msdyneng.visualstudio.com/FinOps/_workitems/edit/467138).
