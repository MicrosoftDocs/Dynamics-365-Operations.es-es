---
title: No puede confirmar un envío porque los artículos no se han recogido
description: No puede confirmar un envío porque los artículos no se han recogido
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
ms.openlocfilehash: 23a517e7769dc86ebec30e4f17c62172a6ad8801
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938546"
---
# <a name="you-cant-confirm-a-shipment-because-items-havent-been-picked"></a>No puede confirmar un envío porque los artículos no se han recogido

Código de error: LoadNotPickedAndMovedToFinalShippingLocation

## <a name="symptoms"></a>Síntomas

Cuando intenta confirmar un envío, el sistema muestra el siguiente mensaje de error:

> Algunos de los artículos necesarios para la carga %1 todavía no se han recogido y movido a la ubicación de envío final.

Por lo tanto, no puede confirmar el envío de la carga.

## <a name="cause"></a>Causa

La carga o el envío no se puede confirmar en su estado actual porque podría existir una de las siguientes condiciones:

- El trabajo relacionado aún no se ha seleccionado y trasladado a la ubicación de envío final.
- La cantidad de trabajo escogido no coincide con la cantidad de trabajo creada en la línea de carga.

## <a name="resolution"></a>Resolución

Compruebe los pedidos de ventas o pedidos de transferencia seleccionados para la carga o envío. Asegúrese de que todo el trabajo relacionado se haya completado en la ubicación de envío final y que las cantidades coincidan.

1. Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.
1. Seleccione la carga para la que el envío no se puede confirmar.
1. En la ficha desplegable **Líneas de carga**, seleccione la línea de carga.
1. Anote el valor del campo **Cantidad de trabajo creado**.
1. En el panel de acciones, en la pestaña **Cargas** del grupo **Información relacionada**, seleccione **Trabajo**.
1. Verifique que el trabajo se haya completado en la ubicación de envío final y que la cantidad de trabajo recogido coincida con la cantidad de trabajo creada en la línea de carga.
1. Repita este procedimiento para todas las líneas de carga para asegurarse de que se cumplan todos los criterios.
