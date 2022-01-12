---
title: La cantidad excede el porcentaje de entrega en exceso durante la generación del albarán
description: Cuando genera un albarán, la carga de salida contiene una cantidad que supera el porcentaje de entrega excesiva.
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
ms.openlocfilehash: bc74c5748950b1f0f001fd89acb2e023640065ee
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920059"
---
# <a name="quantity-exceeds-over-delivery-percentage-during-packing-slip-generation"></a>La cantidad excede el porcentaje de entrega en exceso durante la generación del albarán

Código de error: SYS24920

## <a name="symptoms"></a>Síntomas

Cuando genera un albarán, la carga de salida contiene una cantidad que supera el porcentaje de entrega excesiva.

Cuando intenta generar un albarán, el sistema muestra el siguiente mensaje de error:

> La entrega en exceso de la línea es del %1 %, pero la entrega en exceso permitida es sólo del %2 %.

Por lo tanto, no puede generar el albarán de la carga.

## <a name="cause"></a>Causa

La cantidad recolectada para la carga o envío es mayor que la cantidad solicitada y no está dentro del rango del porcentaje de sobreentrega.

## <a name="resolution"></a>Resolución

La carga o el envío se encuentran actualmente en un estado en el que falla la generación del albarán. Para solucionar este problema, complete una o más de las siguientes tareas:

- Ajuste la cantidad de la línea de carga.
- Ajuste el porcentaje de sobreentrega.
- Invierta y haga ajustes.

### <a name="adjust-the-load-line-quantity"></a>Ajuste la cantidad de la línea de carga

Utilice el siguiente procedimiento para ajustar la cantidad de la línea de carga.

1. Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.
1. Seleccione la carga para la que el albarán no se puede generar.
1. En el panel de acciones, en la pestaña **Enviar y recibir**, en el grupo **Contrarrestar**, seleccione **Invertir confirmación de envíos**.
1. En la ficha **Líneas de carga**, seleccione la línea de carga del artículo que supera el porcentaje de sobreentrega.
1. Seleccione **Reducir la cantidad recolectada** para ajustar la cantidad recogida.
1. En la pestaña **Detalles de la línea**, seleccione **Pedido**.
1. Establezca el campo **Cantidad** en la cantidad recogida (es decir, el valor del campo **Cantidad creada por trabajo**), para que pueda ocurrir la generación del albarán.

### <a name="adjust-the-over-delivery-percentage"></a>Ajuste el porcentaje de sobreentrega

Utilice el siguiente procedimiento para ajustar el porcentaje de sobreentrega.

1. Vaya a **Clientes \> Pedidos \> Todos los pedidos**.
1. Seleccione el pedido de cliente para el que no puede contabilizar un albarán para la carga.
1. En la ficha **Líneas de pedido de ventas**, seleccione la línea de pedido de ventas del artículo que supera el porcentaje de sobreentrega.
1. En la pestaña **Detalles de la línea**, seleccione **Entrega**.
1. Estabelzca el campo **Sobreentrega** en un porcentaje mayor que se adapte a la cantidad que se ha recogido frente a la cantidad de carga, de modo que pueda producirse la generación del albarán.

### <a name="reverse-and-make-adjustments"></a>Invierta y haga ajustes

Invierta todo lo que se ha contabilizado para la carga (por ejemplo, el albarán, la confirmación del envío y el trabajo), realice ajustes en la orden de venta, vuelva a enviar la orden al almacén y complete el procedimiento de envío.

Utilice el siguiente procedimiento para cancelar un albarán.

1. Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.
1. En el panel de acciones, en la pestaña **Enviar y recibir**, en el grupo **Contrarrestar**, seleccione **Cancelar albaranes**.

Utilice el siguiente procedimiento para revertir una confirmación de envío.

1. Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.
1. En el panel de acciones, en la pestaña **Enviar y recibir**, en el grupo **Contrarrestar**, seleccione **Invertir confirmación de envíos**.

Utilice el siguiente procedimiento para revertir el trabajo.

1. Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.
1. En el panel de acciones, en la pestaña **Cargas**, en el grupo **Trabajo**, seleccione **Invertir el trabajo**.
