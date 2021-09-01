---
title: No puede confirmar un envío porque no la cantidad es cero
description: No puede confirmar un envío porque no la cantidad es cero
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: b2f9f8deaca30e318d0393fb1d7911eebf63060ccca83dc6f1de9b04b9e30e11
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6712895"
---
# <a name="you-cant-confirm-a-shipment-because-there-is-zero-quantity"></a>No puede confirmar un envío porque no la cantidad es cero

Código de error: LoadLineWarningUpdatedToZero

## <a name="symptoms"></a>Síntomas

Cuando intenta confirmar un envío, el sistema muestra el siguiente mensaje de error:

> La línea de carga para el artículo %1 y el envío %2 se ha actualizado para que tenga una cantidad cero debido a la configuración de entrega incompleta que permite no enviar cantidades para este artículo.

Por lo tanto, no puede confirmar el envío de la carga.

## <a name="cause"></a>Causa

El sistema evalúa si la cantidad seleccionada se encuentra dentro de los límites esperados, en función de la cantidad seleccionada, la cantidad de la línea de carga y el porcentaje de entrega insuficiente. Si el sistema encuentra que la cantidad seleccionada en la línea de carga es 0 (cero), no se puede confirmar el envío. Por ejemplo, este problema puede ocurrir si se canceló el trabajo y el porcentaje de entrega insuficiente en la línea de carga es del 100 por cien.

## <a name="resolution"></a>Resolución

Compruebe que sus líneas de carga para asegurarse de que el porcentaje de entrega insuficiente y las cantidades estén alineadas con el trabajo seleccionado.

1. Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.
1. Seleccione la carga para la que el envío no se puede confirmar.
1. En la ficha desplegable **Líneas de carga**, seleccione la línea de carga del artículo que supera el porcentaje de entrega insuficiente.
1. Ajuste el valor del campo **Entrega insuficiente** o el campo **Cantidad** según sea necesario.

> [!TIP]
> Si el problema aún no se soluciona, es posible que deba completar más trabajo de selección para los pedidos de ventas o los pedidos de transferencia relacionados hasta que la cantidad disponible esté alineada con la carga o el envío.
