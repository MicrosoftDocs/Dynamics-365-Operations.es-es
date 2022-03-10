---
title: No se puede confirmar un envío porque la cantidad supera el porcentaje de infraentrega
description: No se puede confirmar un envío porque la cantidad supera el porcentaje de infraentrega
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm,WHSContainerCloseDiag_WHSShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: a6a5b1140d1bc5d09a1bc582fb1d2ac9446fae0920cbb9957797dbdea4c684e6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6760331"
---
# <a name="you-cant-confirm-a-shipment-because-the-quantity-exceeds-the-underdelivery-percentage"></a>No se puede confirmar un envío porque la cantidad supera el porcentaje de infraentrega

Código de error: WAX1686

## <a name="symptoms"></a>Síntomas

Cuando intenta confirmar un envío, el sistema muestra el siguiente mensaje de error:

> El envío para carga %1 no se pudo confirmar porque la cantidad del artículo %2 supera el porcentaje definido para la infraentrega.

Por lo tanto, no puede confirmar el envío de la carga.

## <a name="cause"></a>Causa

La cantidad de carga o envío se ha recogido solo parcialmente. La cantidad es actualmente inferior a la cantidad seleccionada en un porcentaje que está fuera del porcentaje de infraentrega permitido.

## <a name="resolution"></a>Resolución

Para solucionar este problema, complete una o más de las siguientes tareas:

- Establezca la cantidad de la línea de carga.
- Establezca el porcentaje de infraentrega.

### <a name="set-the-load-line-quantity"></a>Establezcer la cantidad de línea de carga

Para definir la cantidad de línea de carga, siga estos pasos.

1. Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.
1. Seleccione la carga para la que el envío no se puede confirmar.
1. En la ficha desplegable **Líneas de carga**, seleccione la línea de carga del artículo que supera el porcentaje de entrega insuficiente.
1. En la ficha desplegable **Detalles de línea**, seleccione **Pedido**.
1. En el campo **Cantidad**, establezca el valor en la cantidad recogida (es decir, en el valor **Cantidad creada por trabajo**), para que pueda ocurrir la confirmación del envío.

### <a name="set-the-underdelivery-percentage"></a>Establecer el porcentaje de infraentrega

Para establecer el porcentaje de infraentrega, siga estos pasos.

1. Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.
1. Seleccione la carga para la que el envío no se puede confirmar.
1. En la ficha desplegable **Líneas de carga**, seleccione la línea de carga del artículo que supera el porcentaje de entrega insuficiente.
1. En la ficha desplegable **Detalles de línea**, seleccione **General**.
1. En el campo **Infraentrega**, establezca el valor en un porcentaje mayor que se adapte a la cantidad que se ha recogido frente a la cantidad de carga, de modo que pueda producirse la confirmación del envío.
