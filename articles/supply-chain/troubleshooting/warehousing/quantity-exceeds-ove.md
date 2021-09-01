---
title: No se puede confirmar un envío porque la cantidad supera el porcentaje de sobreentrega
description: No se puede confirmar un envío porque la cantidad supera el porcentaje de sobreentrega
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
ms.openlocfilehash: b25050572662afebbeaa39fa5a96e70cef618ac671dceba189fab1315480ede2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755164"
---
# <a name="you-cant-confirm-a-shipment-because-the-quantity-exceeds-the-overdelivery-percentage"></a>No se puede confirmar un envío porque la cantidad supera el porcentaje de sobreentrega

Código de error: WAX1687

## <a name="symptoms"></a>Síntomas

Cuando intenta confirmar un envío, el sistema muestra el siguiente mensaje de error:

> El envío para carga %1 no se pudo confirmar porque la cantidad del artículo %2 supera el porcentaje definido para la sobreentrega.

Por lo tanto, no puede confirmar el envío de la carga.

## <a name="cause"></a>Causa

La cantidad de carga o envío se ha recogido solo parcialmente. La cantidad actualmente excede la cantidad seleccionada en un porcentaje que está fuera del porcentaje de sobreentrega permitido.

## <a name="resolution"></a>Resolución

Para solucionar este problema, complete una o más de las siguientes tareas:

- Establezca la cantidad de la línea de carga.
- Establezca el porcentaje de sobreentrega.

### <a name="set-the-load-line-quantity"></a>Establezcer la cantidad de línea de carga

Para definir la cantidad de línea de carga, siga estos pasos.

1. Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.
1. Seleccione la carga para la que el envío no se puede confirmar.
1. En la ficha desplegable **Líneas de carga**, seleccione la línea de carga del artículo que supera el porcentaje de sobreentrega.
1. En la ficha desplegable **Detalles de línea**, seleccione **Pedido**.
1. En el campo **Cantidad**, establezca el valor en la cantidad recogida (es decir, en el valor **Cantidad creada por trabajo**), para que pueda ocurrir la confirmación del envío.

### <a name="set-the-overdelivery-percentage"></a>Establezcer el porcentaje de sobreentrega

Para establecer el porcentaje de infraentrega, siga estos pasos.

1. Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.
1. Seleccione la carga para la que el envío no se puede confirmar.
1. En la ficha desplegable **Líneas de carga**, seleccione la línea de carga del artículo que supera el porcentaje de sobreentrega.
1. En la ficha desplegable **Detalles de línea**, seleccione **General**.
1. En el campo **Sobreentrega**, establezca el valor en un porcentaje mayor que se adapte a la cantidad que se ha recogido frente a la cantidad de carga, de modo que pueda producirse la confirmación del envío.
