---
title: No puede confirmar un envío debido a trabajo incompleto o que falta
description: No puede confirmar un envío debido a trabajo incompleto o que falta
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm, WHSContainerCloseDiag_WHSShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 59def4427f9fff32fd3839bb9f9b5d5cccdc7720f92a84f1af3adad596d8b352
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730067"
---
# <a name="you-cant-confirm-a-shipment-because-of-incomplete-or-missing-work"></a>No puede confirmar un envío debido a trabajo incompleto o que falta

Código de error: WAX515

## <a name="symptoms"></a>Síntomas

Cuando intenta confirmar un envío, el sistema muestra el siguiente mensaje de error:

> El envío para la carga %1 no se pudo confirmar porque todos los trabajos de la carga deben estar completos.

Por lo tanto, no puede confirmar el envío de la carga.

## <a name="cause"></a>Causa

La carga o el envío se encuentran actualmente en un estado en el que falla la confirmación del envío. Antes de que pueda confirmar el envío, debe existir al menos algún trabajo para la carga, y todo ese trabajo debe tener un estado de *Cerrado* o *Cancelado*.

## <a name="resolution"></a>Resolución

Verifique las órdenes de venta o las órdenes de transferencia relacionadas para la carga o el envío, y asegúrese de que todo el trabajo relacionado se haya completado o cancelado.

Puede trabajar con envíos y cargas en varias páginas. Las siguientes subsecciones proporcionan algunos ejemplos.

### <a name="all-loads-page"></a>Página Todas las cargas

1. Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.
1. Seleccione la carga para la que el envío no se puede confirmar.
1. En el panel de acciones, en la pestaña **Cargas** del grupo **Información relacionada**, seleccione **Trabajo**.
1. Inspeccione el estado de cada id. de trabajo. Haga un seguimiento de cada id. que no tenga un estado de *Cerrado* o *Cancelado*.
1. Cuando cada id. de trabajo tiene un estado de *Cerrado* o *Cancelado*, intente nuevamente confirmar el envío.

### <a name="all-shipments-page"></a>Página Todos los envíos

1. Vaya a **Gestión de almacenes \> Envíos \> Todos los envíos**.
1. Seleccione el envío que no se puede confirmar.
1. En el panel de acciones, en la pestaña **Envíos**, en el grupo **Trabajo**, seleccione **Detalles de trabajo**.
1. Inspeccione el estado de cada id. de trabajo. Haga un seguimiento de cada id. que no tenga un estado de *Cerrado* o *Cancelado*.
1. Cuando cada id. de trabajo tiene un estado de *Cerrado* o *Cancelado*, intente nuevamente confirmar el envío.

### <a name="all-work-page"></a>Página Todos los trabajos

1. Vaya a **Gestión de almacenes \> Trabajo\> Todos los trabajos**.
1. Seleccione el trabajo para el número de pedido para el que no se puede confirmar el envío.
1. En el panel de acciones, en la ficha **Envío**, en el grupo **Envío**, seleccione **Confirmar envío**.
1. Inspeccione el estado de cada id. de trabajo. Haga un seguimiento de cada id. que no tenga un estado de *Cerrado* o *Cancelado*.
1. Cuando cada id. de trabajo tiene un estado de *Cerrado* o *Cancelado*, intente nuevamente confirmar el envío.
