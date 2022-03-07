---
title: La cantidad seleccionada no es suficiente durante la generación del albarán
description: Cuando genera un albarán, la carga de salida contiene una cantidad seleccionada que no coincide con la cantidad de trabajo creada en la línea de carga.
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
ms.openlocfilehash: fa6054dc26e4306ec16e37b0e6c320342ed40fe0
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249168"
---
# <a name="picked-quantity-isnt-sufficient-during-packing-slip-generation"></a>La cantidad seleccionada no es suficiente durante la generación del albarán

Código de error: SYS54073

## <a name="symptoms"></a>Síntomas

Cuando genera un albarán, la carga de salida contiene una cantidad seleccionada que no coincide con la cantidad de trabajo creada en la línea de carga.

Cuando intenta generar un albarán, el sistema muestra el siguiente mensaje de error:

> Como %1 se han seleccionado, no es suficiente actualizar %2, cuando, por consiguiente, el resto debe ser %3.

Por lo tanto, no puede generar el albarán de la carga.

## <a name="cause"></a>Causa

El albarán no se puede generar en su estado actual porque podría existir una de las siguientes condiciones:

- El trabajo relacionado aún no se ha seleccionado y trasladado a la ubicación de envío final.
- La cantidad de trabajo escogido no coincide con la cantidad de trabajo creada en la línea de carga.
- La cantidad de línea de carga, la cantidad de trabajo creada y la cantidad elegida no coinciden.

## <a name="resolution"></a>Resolución

La carga o el envío se encuentran actualmente en un estado en el que falla la generación del albarán. Para solucionar este problema, complete una o más de las siguientes tareas:

- Revise las líneas de carga y asegúrese de que todo el trabajo relacionado se haya completado en la ubicación de envío final y que las cantidades coincidan.
- Ajuste la cantidad de la línea de carga.
- Invierta todos los registros de picking y vuelva a realizar el picking.

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a>Revise las líneas de carga y asegúrese de que todo el trabajo relacionado se haya completado en la ubicación de envío final y que las cantidades coincidan

Use el siguiente procedimiento para revisar las líneas de carga y asegúrese de que todo el trabajo relacionado se haya completado en la ubicación de envío final y que las cantidades coincidan.

1. Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.
1. Seleccione la carga para la que el albarán no se puede generar.
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

El problema puede ocurrir porque alguien usó el registro de picking para cerrar una línea de carga sin trabajo. En este caso, se debe revertir el registro de picking manual y luego se debe completar el picking mediante la aplicación móvil Warehouse Management.

Utilice el siguiente procedimiento para invertir el registro de recogida.

1. Vaya a **Clientes \> Pedidos \> Todos los pedidos**.
1. Seleccione el pedido de cliente para el que no puede contabilizar un albarán para la carga.
1. Sobre la pesetaña **Líneas de orden de venta**, seleccione la línea de orden de venta para la que se realizó el registro de picking.
1. Seleccione **Línea de actualización \> Elegir** para despegar los artículos.
