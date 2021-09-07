---
title: No puede confirmar un envío porque el cliente está en espera
description: No puede confirmar un envío porque el cliente está en espera.
author: GalynaFedorova
ms.date: 07/30/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 801778fc8f04b106bf168a3dcd5a89767a837740
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2021
ms.locfileid: "7344273"
---
# <a name="you-cant-confirm-a-shipment-because-the-customer-is-on-hold"></a>No puede confirmar un envío porque el cliente está en espera

Código de error: WAX: CustomerOnHoldShipmentCannotBeConfirmed

## <a name="symptoms"></a>Síntomas

Cuando intenta confirmar un envío, el sistema muestra el siguiente mensaje de error:

> El envío %1 no se pudo confirmar porque el cliente está en espera para %2.

Por lo tanto, no puede confirmar el envío de la carga.

## <a name="cause"></a>Causa

La cuenta de cliente de la carga o envío está retenida. Por tanto, el estado del cliente impide la confirmación del envío.

## <a name="resolution"></a>Resolución

Utilice el siguiente procedimiento para desbloquear la cuenta del cliente.

1. Vaya a **Clientes \> Clientes \> Todos los clientes**.
1. Abra la cuenta de cliente para la que el envío no se puede confirmar.
1. En la ficha desplegable **Crédito y cobros**, establezca el campo **Facturación y entrega en espera** a *No*.
1. Repita este procedimiento para todos los clientes bloqueados para la carga.
