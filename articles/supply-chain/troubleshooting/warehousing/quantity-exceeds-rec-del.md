---
title: La cantidad que está intentando actualizar supera la cantidad recibida / entregada.
description: Cuando genera un albarán, la carga de salida contiene una cantidad que excede la cantidad de trabajo que se seleccionó y reservó para la orden de venta.
author: GalynaFedorova
ms.date: 5/31/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSSalesPackingSlipPost,WHSLoadPlanningListPage_WHSSalesPackingSlipPost,WHSLoadPlanningWorkbench_WHSSalesPackingSlipPost
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 25507a482b2db7c01f56679bf3e8454249de3a6b9965f9c359a2ebe2cc8445ce
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6711696"
---
# <a name="quantity-that-youre-trying-to-update-exceeds-the-receiveddelivered-quantity"></a>La cantidad que está intentando actualizar supera la cantidad recibida / entregada

Código de error: SYS7676

## <a name="symptoms"></a>Síntomas

Cuando genera un albarán, la carga de salida contiene una cantidad que excede la cantidad de trabajo que se seleccionó y reservó para la orden de venta.

Cuando intenta generar un albarán, el sistema muestra el siguiente mensaje de error:

> La cantidad que intenta actualizar supera la cantidad recibida o entregada.

Por lo tanto, no puede generar el albarán de la carga.

## <a name="cause"></a>Causa

La cantidad de trabajo escogido no coincide con la cantidad de trabajo creada en la línea de carga. Por ejemplo, este problema puede ocurrir si la cantidad de la línea de carga, la cantidad de trabajo creado o la cantidad recolectada no son precisas.

## <a name="resolution"></a>Resolución

La carga o el envío se encuentran actualmente en un estado en el que falla la generación del albarán. Para solucionar este problema, complete una o más de las siguientes tareas:

- Revise las líneas de carga y asegúrese de que todo el trabajo relacionado se haya completado en la ubicación de envío final y que las cantidades coincidan.
- Ajuste la cantidad de la línea de carga.
- Invierta todos los registros de picking y vuelva a realizar el picking.

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a>Revise las líneas de carga y asegúrese de que todo el trabajo relacionado se haya completado en la ubicación de envío final y que las cantidades coincidan

Use el siguiente procedimiento para revisar las líneas de carga y asegúrese de que todo el trabajo relacionado se haya completado en la ubicación de envío final y que las cantidades coincidan.

1. Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.
1. Seleccione la carga para la que el envío no se puede generar.
1. En la ficha desplegable **Líneas de carga**, seleccione la línea de carga.
1. Anote el valor del campo **Cantidad de trabajo creado**.
1. En el panel de acciones, en la pestaña **Cargas** del grupo **Información relacionada**, seleccione **Trabajo**.
1. Verifique que el trabajo se haya completado en la ubicación de envío final y que la cantidad de trabajo recogido coincida con la cantidad de trabajo creada en la línea de carga.
1. Repita este procedimiento para todas las líneas de carga para asegurarse de que se cumplan todos los criterios.

### <a name="adjust-the-load-line-quantity"></a>Ajuste la cantidad de la línea de carga

Utilice el siguiente procedimiento para ajustar la cantidad de la línea de carga.

1. Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.
1. Seleccione la carga para la que el albarán no se puede generar.
1. En el panel de acciones, en la pestaña **Enviar y recibir**, en el grupo **Contrarrestar**, seleccione **Invertir confirmación de envíos**.
1. En la pestaña  **Líneas de carga**, seleccione la línea de carga para el artículo que causa un problema.
1. Seleccione **Reducir la cantidad recolectada** para ajustar la cantidad recogida.
1. Seleccione el campo **Reducir la línea de carga** para reflejar los ajustes en la línea de carga.

### <a name="reverse-all-pick-registrations-and-redo-picking"></a>Invierta todos los registros de picking y vuelva a realizar el picking

Si alguien usó el registro de recolección para cerrar una línea de carga sin trabajo, puede ocurrir una discrepancia entre la cantidad de la línea de carga y la cantidad recolectada. En este caso, se debe revertir el registro de picking manual y luego se debe completar el picking mediante la aplicación móvil Warehouse Management.

Utilice el siguiente procedimiento para invertir el registro de recogida.

1. Vaya a **Clientes \> Pedidos \> Todos los pedidos**.
1. Seleccione el pedido de cliente para el que no puede contabilizar un albarán para la carga.
1. Sobre la pesetaña **Líneas de orden de venta**, seleccione la línea de orden de venta para la que se realizó el registro de picking.
1. Seleccione **Línea de actualización \> Elegir** para despegar los artículos.
