---
title: No puede confirmar un envío porque las líneas de carga tienen una cantidad cero
description: No puede confirmar un envío porque las líneas de carga tienen una cantidad cero.
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
ms.openlocfilehash: 15aa7f5e72ff8f2c027b5b020a23328978aa02b0
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2021
ms.locfileid: "7344243"
---
# <a name="you-cant-confirm-a-shipment-because-load-lines-have-zero-quantity"></a>No puede confirmar un envío porque las líneas de carga tienen una cantidad cero

Código de error: WAX: LoadTableWarningAllLinesZero, WAX2543

## <a name="symptoms"></a>Síntomas

Cuando intenta confirmar un envío, el sistema muestra el siguiente mensaje de error:

> Todas las líneas de la carga %1 tienen cantidad cero.  
> No se pudo confirmar el envío para la carga %1.

Por lo tanto, no puede confirmar el envío de la carga.

## <a name="cause"></a>Causa

El sistema evalúa si la línea de carga se puede enviar confirmada, según los ID de trabajo que se crean, la cantidad de la línea de carga y el porcentaje de entrega insuficiente. Si el sistema encuentra que no hay ID de trabajo y si el porcentaje de entrega insuficiente se establece en 100 por ciento, no puede confirmar el envío.

Por ejemplo, este problema puede ocurrir si se canceló el trabajo y el porcentaje de entrega insuficiente en la línea de carga es del 100 por cien.

## <a name="resolution"></a>Resolución

La carga o el envío se encuentran actualmente en un estado en el que falla la confirmación del envío. Para solucionar este problema, complete una o más de las siguientes tareas:

- Revise las líneas de carga para asegurarse de que todo el trabajo relacionado se haya completado en la ubicación de envío final y que las cantidades coincidan.
- Revise sus líneas de carga para asegurarse de que el porcentaje de entrega insuficiente y las cantidades estén alineadas con el trabajo seleccionado.

### <a name="review-your-load-lines-to-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a>Revisar las líneas de carga para asegurarse de que todo el trabajo relacionado se haya completado en la ubicación de envío final y que las cantidades coincidan

Use el siguiente procedimiento para revisar las líneas de carga para asegurarse de que todo el trabajo relacionado se haya completado en la ubicación de envío final y que las cantidades coincidan.

1. Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.
1. Abra la carga para la que el envío no se puede confirmar.
1. En la ficha desplegable **Líneas de carga**, seleccione la línea de carga.
1. Anote el valor del campo **Cantidad de trabajo creado**.
1. En el panel de acciones, en la pestaña **Cargas** del grupo **Información relacionada**, seleccione **Trabajo**.
1. Verifique que el trabajo se haya completado en la ubicación de envío final y que la cantidad de trabajo recogido coincida con la cantidad de trabajo creada en la línea de carga.
1. Si encuentra una discrepancia, cancele el trabajo relevante, reconfigure la directiva de ubicación y vuelva a liberar la carga. Para obtener instrucciones, consulte [No puede confirmar un envío porque los artículos no se han recogido](picked-quantity-is-not-on-final.md).
1. Repita este procedimiento para todas las líneas de carga para asegurarse de que se cumplan todos los criterios.

### <a name="review-your-load-lines-to-make-sure-that-the-underdelivery-percentage-and-quantities-are-aligned-with-the-picked-work"></a>Revisar sus líneas de carga para asegurarse de que el porcentaje de entrega insuficiente y las cantidades estén alineadas con el trabajo seleccionado

Siga esta procedimiento para revisar sus líneas de carga para asegurarse de que el porcentaje de entrega insuficiente y las cantidades estén alineadas con el trabajo seleccionado.

1. Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.
1. Abra la carga para la que el envío no se puede confirmar.
1. En la ficha desplegable **Líneas de carga**, seleccione la línea de carga del artículo que supera el porcentaje de entrega insuficiente.
1. Ajuste el valor del campo **Entrega insuficiente** o el campo **Cantidad** según sea necesario.

> [!TIP]
> Si el problema aún no se soluciona, es posible que deba completar más trabajo de selección para los pedidos de ventas o los pedidos de transferencia relacionados hasta que la cantidad disponible esté alineada con la carga o el envío.
