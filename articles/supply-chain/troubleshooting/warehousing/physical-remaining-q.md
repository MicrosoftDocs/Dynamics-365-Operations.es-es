---
title: La cantidad física de actualización en la unidad tiene que ser distinta de cero
description: Cuando genera un albarán, los datos que se le proporcionan tienen una cantidad de inventario distinta de cero pero una cantidad de ventas cero.
author: GalynaFedorova
ms.date: 5/31/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadPlanningListPage_WHSSalesPackingSlipPost, WHSLoadTable_WHSSalesPackingSlipPost
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 187363db3030ee0741f0c7e7746295b88320162c156120112332bb78593bb673
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6744663"
---
# <a name="physical-remaining-quantity-in-the-unit-must-not-be-zero"></a>La cantidad física de actualización en la unidad tiene que ser distinta de cero

Código de error: SYS19591

## <a name="symptoms"></a>Síntomas

Cuando genera un albarán, los datos que se le proporcionan tienen una cantidad de inventario distinta de cero pero una cantidad de ventas cero.

Cuando intenta generar un albarán, el sistema muestra el siguiente mensaje de error:

> La cantidad física de actualización en la unidad %1 tiene que ser distinta de cero.

Por lo tanto, no puede generar el albarán de la carga.

## <a name="cause"></a>Causa

El sistema evalúa la cantidad física restante en la unidad de inventario y la cantidad física restante en la unidad de envío. Si el sistema encuentra que la cantidad física restante en la unidad de envío es 0 (cero), pero la cantidad física restante en la unidad de inventario no es 0, no puede generar el albarán. Por ejemplo, este problema puede ocurrir si la unidad de ventas y la unidad de inventario del artículo difieren y la conversión entre unidades no es precisa.

## <a name="resolution"></a>Resolución

La carga o el envío se encuentran actualmente en un estado en el que falla la generación del albarán. Para solucionar este problema, complete una o más de las siguientes tareas:

- Revise las líneas de carga y asegúrese de que todo el trabajo relacionado se haya completado en la ubicación de envío final y que las cantidades coincidan.
- Revise sus líneas de carga y realice ajustes para asegurarse de que la cantidad se pueda convertir limpiamente sin problemas de redondeo.
- Revise sus líneas de carga y realice ajustes para asegurarse de que la unidad y la cantidad estén alineadas con la precisión decimal de la unidad.
- Asegúrese de que la unidad de medida del inventario sea menor que la unidad de medida de las ventas.

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a>Revise las líneas de carga y asegúrese de que todo el trabajo relacionado se haya completado en la ubicación de envío final y que las cantidades coincidan

Use el siguiente procedimiento para revisar las líneas de carga y asegúrese de que todo el trabajo relacionado se haya completado en la ubicación de envío final y que las cantidades coincidan.

1. Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.
1. Seleccione la carga para la que el envío no se puede confirmar.
1. En la ficha desplegable **Líneas de carga**, seleccione la línea de carga.
1. Anote el valor del campo **Cantidad de trabajo creado**.
1. En el panel de acciones, en la pestaña **Cargas** del grupo **Información relacionada**, seleccione **Trabajo**.
1. Verifique que el trabajo se haya completado en la ubicación de envío final y que la cantidad de trabajo recogido coincida con la cantidad de trabajo creada en la línea de carga.
1. Repita este procedimiento para todas las líneas de carga para asegurarse de que se cumplan todos los criterios.

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-quantity-can-be-cleanly-converted-without-rounding-issues"></a>Revise sus líneas de carga y realice ajustes para asegurarse de que la cantidad se pueda convertir limpiamente sin problemas de redondeo

Use el siguiente procedimiento para revisar las líneas de carga y realizar ajustes para asegurarse de que la cantidad se pueda convertir limpiamente sin problemas de redondeo.

1. Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.
1. Seleccione la carga para la que el albarán no se puede generar.
1. En el panel de acciones, en la pestaña **Enviar y recibir**, en el grupo **Contrarrestar**, seleccione **Invertir confirmación de envíos**.
1. En la ficha **Líneas de carga**, seleccione la línea de carga del artículo que supera la sobreentrega.
1. Seleccione **Reducir la cantidad recolectada** para ajustar la cantidad recogida.
1. En la pestaña  **Detalles de la línea**, seleccione **Pedido**.
1. Establezca el campo **Cantidad** en la cantidad recogida (es decir, el valor del campo **Cantidad creada por trabajo**), para que pueda ocurrir la generación del albarán.

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-unit-and-quantity-are-aligned-with-the-decimal-precision-of-the-unit"></a>Revise sus líneas de carga y realice ajustes para asegurarse de que la unidad y la cantidad estén alineadas con la precisión decimal de la unidad

Use el procedimiento siguiente para revisar sus líneas de carga y realice ajustes para asegurarse de que la unidad y la cantidad estén alineadas con la precisión decimal de la unidad.

1. Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.
1. Seleccione la carga para la que el albarán no se puede generar.
1. En la ficha desplegable **Líneas de carga**, seleccione la línea de carga para el artículo que causa un problema. Anote el valor de los campos **Cantidad** y **Unidad**.
1. Vaya a **Administración de la organización \> Unidades \> Unidades**.
1. Seleccione la unidad para la que el albarán no se puede generar.
1. Ajuste el valor del campo **Precisión decimal** según sea necesario.

### <a name="make-sure-that-the-inventory-unit-of-measure-is-smaller-than-the-sales-unit-of-measure"></a>Asegúrese de que la unidad de medida del inventario sea menor que la unidad de medida de las ventas

Asegúrese de que la unidad de medida del inventario sea menor que la unidad de medida de las ventas. Considere la posibilidad de reconfigurar la unidad de medida del artículo según sea necesario.
