---
title: El redondeo decimal de la cantidad de actualización física es incorrecto
description: Cuando genera un albarán, la carga de salida contiene una cantidad que no coincide con la precisión decimal definida en la unidad.
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
ms.openlocfilehash: 1e63440834f516879aa8ad711bd789e62b0ee993
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "6248803"
---
# <a name="decimal-rounding-of-the-physical-updating-quantity-is-incorrect"></a>El redondeo decimal de la cantidad de actualización física es incorrecto

Código de error: SYS19589

## <a name="symptoms"></a>Síntomas

Cuando genera un albarán, la carga de salida contiene una cantidad que no coincide con la precisión decimal definida en la unidad.

Cuando intenta generar un albarán, el sistema muestra el siguiente mensaje de error:

> El redondeo decimal de la cantidad de física de actualización en la unidad %1 no es correcto.

Por lo tanto, no puede generar el albarán de la carga.

## <a name="cause"></a>Causa

El sistema evalúa si el redondeo decimal de la cantidad de envío corresponde a la precisión decimal definida para la unidad de envío. Cuando el sistema redondea la cantidad de envío al número especificado de decimales, si encuentra que la cantidad de envío redondeada no coincide con la cantidad de envío real, no puede generar el albarán. Por ejemplo, este problema puede ocurrir si la cantidad de ventas es 1,75 kilogramos (kg), pero la precisión decimal se establece en *1*.

## <a name="resolution"></a>Resolución

La carga o el envío se encuentran actualmente en un estado en el que falla la generación del albarán. Para solucionar este problema, complete una o más de las siguientes tareas:

- Revise sus líneas de carga y realice ajustes para asegurarse de que la cantidad se pueda convertir limpiamente sin números decimales y cualquier otro problema de redondeo.
- Revise sus líneas de carga y realice ajustes para asegurarse de que la unidad y la cantidad estén alineadas con la precisión decimal de la unidad.

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-quantity-can-be-cleanly-converted-without-decimal-numbers-and-any-other-rounding-issues"></a>Revise sus líneas de carga y realice ajustes para asegurarse de que la cantidad se pueda convertir limpiamente sin números decimales y cualquier otro problema de redondeo

Use el siguiente procedimiento para revisar las líneas de carga y realizar ajustes para asegurarse de que la cantidad se pueda convertir limpiamente sin números decimales y cualquier otro problema de redondeo.

1. Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.
1. Seleccione la carga para la que el albarán no se puede generar.
1. En el panel de acciones, en la pestaña **Enviar y recibir**, en el grupo **Contrarrestar**, seleccione **Invertir confirmación de envíos**.
1. En la pestaña  **Líneas de carga**, seleccione la línea de carga para el artículo que causa un problema.
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
