---
title: Solución de problemas de flujos de trabajo de adquisición y abastecimiento
description: Este tema describe cómo solucionar problemas que pueden surgir al trabajar con flujos de trabajo de adquisición y abastecimiento.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: cdedc45b8f057310801f134104156a732fb58d86
ms.sourcegitcommit: e3f4dd2257a3255c2982f4fc7b72a1121275b88a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "4018546"
---
# <a name="troubleshoot-procurement-and-sourcing-workflows"></a>Solución de problemas de flujos de trabajo de adquisición y abastecimiento

Este tema describe cómo solucionar problemas que pueden surgir al trabajar con flujos de trabajo de adquisición y abastecimiento.

## <a name="error-when-re-submitting-a-purchase-order-to-the-workflow-after-a-change-changes-to-purchase-order-x-are-allowed-only-in-a-draft-state-when-change-management-is-activated"></a>Error al volver a enviar un pedido de compra al flujo de trabajo después de un cambio: "Los cambios en el pedido de compra X solo se permiten en un estado Borrador cuando la administración de cambios está activada".

Este problema solo se produce si el pedido de compra estaba en estado *Confirmado* antes de que se soliciten los cambios. Si solicita cambios mientras el pedido de compra está en estado *Aprobado* , el flujo de trabajo se puede procesar correctamente.

### <a name="error-description"></a>Error de descripción

El siguiente error se produce en el flujo de trabajo cuando se vuelve a enviar un pedido de compra después de un cambio:

> Detenido (error): excepción de X++: Los cambios en el pedido de compra PO0000569 solo se permiten en el estado Borrador cuando la administración de cambios está activada en<br>
SysWorkflowParticipantProvider-resolve<br>
SysWorkflowParticipantProvider-resolveParticipants<br>
SysWorkflowServiceProvider-resolveParticipant<br>
SysWorkflowQueue-resume

### <a name="issue-resolution"></a>Solución del problema

Este problema se puede producir debido a incoherencias en las distribuciones de pedidos de compra.

Para desbloquear este problema y restablecer el pedido de compra al estado *Borrador* , vaya a **Adquisiciones y abastecimiento \> Tareas periódicas \> Limpiar \> Restablecimiento de distribución de pedido de compra**. Para obtener más información, consulte la siguiente publicación de blog: [Resolver errores de distribución de pedidos de compra en Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

El problema se solucionará con [este artículo de Microsoft Knowledge Base (KB)](https://msdyneng.visualstudio.com/FinOps/_workitems/edit/467138).

## <a name="one-or-more-accounting-distributions-are-either-over-distributed-or-under-distributed"></a>Una o más distribuciones contables están distribuidas en exceso o en defecto.

Este problema se puede producir debido a incoherencias en las distribuciones de pedidos de compra.

Para desbloquear este problema y restablecer el pedido de compra al estado *Borrador* , vaya a **Adquisiciones y abastecimiento \> Tareas periódicas \> Limpiar \> Restablecimiento de distribución de pedido de compra**. Para obtener más información, consulte la siguiente publicación de blog: [Resolver errores de distribución de pedidos de compra en Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

## <a name="if-a-delivery-remainder-is-canceled-on-a-purchase-order-where-change-management-is-turned-on-the-purchase-order-goes-to-a-confirmed-state"></a>Si se cancela un remanente de entrega en un pedido de compra donde la administración de cambios está activada, el pedido de compra pasa a un estado Confirmado.

### <a name="issue-description"></a>Descripción del problema

Para un pedido de compra sujeto a la administración de cambios, si el único cambio que se solicita es la cancelación de un remanente de entrega en una o más de las líneas, el pedido de compra pasará directamente al estado *Confirmado* cuando se apruebe, y no se creará ningún diario.

### <a name="issue-resolution"></a>Solución del problema

La cancelación de un remanente de entrega no afecta el contenido del diario de confirmación. Esta funcionalidad debe usarse cuando la línea se ha recibido parcialmente y la calidad restante debe cancelarse en el paso del proceso después de que se haya confirmado el pedido de compra con el proveedor.

Si esto tuviera que reflejarse en la confirmación del pedido de compra, la cantidad debe ajustarse en la línea del pedido de compra para que se requiera la confirmación. Como alternativa, si no se ha recibido nada en la línea, se puede quitar la cantidad. En este caso, se requerirá una reconfirmación.

## <a name="canceled-purchase-orders-appear-in-the-draft-list-in-the-purchase-order-preparation-workspace"></a>Los pedidos de compra cancelados aparecen en la lista de borradores en el espacio de trabajo Preparación del pedido de compra.

### <a name="issue-description"></a>Descripción del problema

Después de cancelar pedidos de compra que estaban en estado *Confirmado* , los pedidos de compra cancelados todavía aparecen en la lista de borradores de pedidos de compra en el espacio de trabajo **Preparación del pedido de compra**.

### <a name="issue-resolution"></a>Solución del problema

Este problema solo se produce para los pedidos de compra que están sujetos a la administración de cambios. Se produce porque se considera que la cancelación es un cambio que debe ser aprobado. La aprobación la puede realizar el sistema automáticamente. Por lo tanto, el proceso consiste en enviar el pedido de compra cancelado al flujo de trabajo de aprobación para que pueda pasar al estado *Aprobado*. En ese momento, el pedido de compra ya no aparecerá en la lista de borradores de pedido de compra en el espacio de trabajo **Preparación del pedido de compra**.

