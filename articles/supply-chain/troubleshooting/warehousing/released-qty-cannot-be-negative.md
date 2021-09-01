---
title: No se puede actualizar una línea de carga porque la cantidad liberada sería negativa
description: Este problema ocurre cuando la actualización o eliminación de una línea de carga causaría una cantidad liberada negativa.
author: GalynaFedorova
ms.date: 6/30/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadPlanningListPage_WHSLoadLineUnShipQty,WHSLoadTable_WHSLoadLineUnShipQty,WHSLoadPlanningWorkbench_WHSLoadLineUnShipQty,WHSShipmentDetails_WHSLoadLineUnShipQty,WHSLoadPlanningListPage_DeleteButtonLoadLine,WHSLoadTable_DeleteButtonLoadLine,WHSLoadPlanningWorkbench_DeleteButtonLoadLine,WHSShipmentDetails_DeleteButtonShipment
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: a6325a632e1f68a0a3a9cb6b6091c48da014a405e8ce9ad69ea841f5cceb216f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6728468"
---
# <a name="cant-update-a-load-line-because-the-released-quantity-would-be-negative"></a>No se puede actualizar una línea de carga porque la cantidad liberada sería negativa

Código de error: @WAX: ReleasedQtyCannotBeNegative

## <a name="symptoms"></a>Síntomas

Este problema ocurre cuando la actualización o eliminación de una línea de carga causaría una cantidad liberada negativa. En este caso, cuando intenta actualizar o eliminar la línea de carga, el sistema muestra el siguiente mensaje de error:

> La cantidad liberada no puede ser negativa para el artículo %1, lote %2.

Por lo tanto, no puede actualizar ni eliminar la línea de carga.

## <a name="cause"></a>Causa

Después de actualizar o eliminar una línea de carga, el sistema actualiza la cantidad liberada de la línea de ventas relacionada (*whsSalesLine.ReleaseQty*). El sistema evalúa la cantidad liberada y, si encuentra que la cantidad liberada de la línea sería negativa después de la actualización, no le permitirá actualizar ni eliminar la línea. Esta validación ocurre cada vez que intenta actualizar la cantidad de la línea de carga o la unidad de medida a través de varias acciones, como eliminar una línea de carga, eliminar un envío, cambiar la cantidad de una línea de carga, reducir la cantidad recogida y realizar una selección corta.

La causa raíz más común de este problema es un cambio en la conversión de la unidad que se utiliza para las líneas de carga abiertas. Por ejemplo, la conversión de unidades cuando se liberó un pedido de ventas fue *50 Ea = 1 PL*. Sin embargo, antes de finalizar el envío de carga relacionado, la conversión de unidades se cambió a *100 Ea = 1 PL*.

## <a name="resolution"></a>Resolución

La solución es revertir los cambios de conversión de unidades, actualizar o eliminar la línea de carga y luego volver a implementar la conversión. Debe evitar que se procesen otras cargas que incluyan el artículo que causó el problema hasta que se solucione el problema. De lo contrario, las nuevas conversiones podrían usarse para otras cargas que ya están abiertas.

Para solucionar este problema, complete las siguientes tareas:

1. Revise la conversión de unidades que se utilizó para la línea de carga.
2. Revise la conversión de unidades actual para el artículo y realice los ajustes que permitirán actualizar o eliminar la línea de carga.
3. Actualice o elimine la línea de carga y revierta los ajustes de conversión de unidades.

### <a name="review-the-unit-conversion-that-was-used-for-the-load-line"></a>Revisar la conversión de unidades que se utilizó para la línea de carga

Utilice el siguiente procedimiento para revisar sus líneas de carga y anote la conversión de unidades que se utilizó para la línea de carga.

1. Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.
1. Seleccione la carga que incluye la línea de carga que no se puede eliminar ni actualizar.
1. En el panel de acciones, en la pestaña **Cargas** del grupo **Información relacionada**, seleccione **Trabajo**.
1. En la cuadrícula superior, seleccione el ID de trabajo relevante.
1. En la ficha **General** de la parte inferior de la página, calcule la tasa de conversión entre el valor de **Cantidad de trabajo de inventario** y el valor de **Cantidad de trabajo**. Anote la tasa.
1. Repita este procedimiento para todos los ID de trabajo relevantes para asegurarse de que se utilizó la misma conversión.

### <a name="review-the-current-unit-conversion-for-the-item-and-make-adjustments"></a>Revise la conversión de unidades actual para el artículo y realice ajustes.

Use el procedimiento siguiente para revisar la conversión de unidades de su producto y realice ajustes para asegurarse de que la conversión de unidades está alineada con la línea de carga.

1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. Abra el producto relevante para ir a su página de **Detalles de producto lanzado**.
1. En el panel Acciones, en la pestaña **Producto** del grupo **Configurar**, haga clic en **Conversiones de unidades**.
1. Seleccione la conversión entre las unidades y realice ajustes utilizando la conversión que encontró en la sección anterior.

### <a name="update-or-delete-the-load-line-and-revert-the-unit-conversion-adjustments"></a>Actualizar o eliminar la línea de carga y revertir los ajustes de conversión de unidades

Utilice el siguiente procedimiento para procesar la línea de carga según sea necesario y revertir las conversiones de unidades.

1. Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.
1. Abra la carga que incluye la línea de carga que no se puede eliminar ni actualizar.
1. En la ficha desplegable **Líneas de carga**, seleccione la línea de carga.
1. Continúe con las acciones necesarias según sea necesario. (Por ejemplo, elimine la línea de carga o cambie su cantidad).
1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. Abra el producto relevante para ir a su página de **Detalles de producto lanzado**.
1. En el panel Acciones, en la pestaña **Producto** del grupo **Configurar**, haga clic en **Conversiones de unidades**.
1. Seleccione la conversión entre las unidades y revierta los ajustes que realizó en la sección anterior.
