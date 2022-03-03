---
title: Discrepancias en los datos de la línea de pedido de compra
description: Ve discrepancias de datos o corrupción de datos en sus líneas de pedido de compra.
author: SmithaNataraj
ms.date: 12/07/2021
ms.topic: troubleshooting
ms.search.form: PurchLineManualCorrection, PurchTable, PurchLine, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-12-07
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: ee2cb9a07c8a00a92c71e3e99d8ec20aa27fb20e
ms.sourcegitcommit: b9799a58d6ec221df86788bc37c4fbd28b435e89
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2022
ms.locfileid: "8100808"
---
# <a name="purchase-order-line-data-discrepancies"></a>Discrepancias en los datos de la línea de pedido de compra

## <a name="symptoms"></a>Síntomas

Cuando inspecciona las líneas de un pedido de compra, observa uno o más de los siguientes problemas:

- Hay una discrepancia de datos o corrupción en los restos de línea de pedido de compra (entrega o factura).
- Hay corrupción en una línea de pedido de compra o en el estado del encabezado.
- No puede facturar un pedido de compra porque, por ejemplo, recibe uno o más de los siguientes mensajes de error:

    - "Detenido (error): la transacción ya se ha registrado".
    - "No se puede facturar la cantidad ya que las transacciones de inventario con estado Recibido son insuficientes".
    - "Transacciones de inventario insuficientes con el estado "Comprado" para el artículo %0, cantidad %1."

- No puede finalizar o cerrar un pedido de compra debido, por ejemplo, a uno de los siguientes problemas:

    - El botón **Finalizar** no está disponible.
    - No puede cancelar la cantidad pedida de una línea de pedido de compra para un pedido de compra que se encuentra en un estado confirmado y recibido.

## <a name="cause"></a>Causa

Estos problemas generalmente son causados por corrupción de datos o una discrepancia en las cantidades restantes para una o más líneas de pedido de compra.

## <a name="resolution"></a>Resolución

Por lo general, puede solucionar estos problemas actualizando el estado de compra, los restos de entrega y los restos de facturas para las líneas de pedido de compra relevantes, como se describe en el siguiente procedimiento.

1. Vaya a **Adquisición y abastecimiento \> Tareas periódicas \> Limpieza \> Corregir líneas de pedido de compra manualmente**.
1. En el campo **Pedido de compra**, busque y seleccione el pedido de compra que le está dando problemas.
1. En la sección **Líneas de pedido de compra**, seleccione una línea donde encontró una discrepancia.
1. En la sección **Transacciones de inventario**, inspeccione los datos que se muestran. Si nota alguna incoherencia entre una línea de pedido de compra y sus transacciones de inventario, seleccione uno de los siguientes comandos en el Panel de acciones, según dónde vea las incoherencias:

    - **Volver a calcular \> Volver a calcular entrega restante**: actualiza automáticamente la línea del pedido de compra y los estados del encabezado. Esta función funciona solo para líneas de pedido de compra almacenadas (es decir, líneas en las que el artículo es un artículo almacenado). Los artículos no almacenados y los artículos con peso capturado no se admiten actualmente.
    - **Volver a calcular \> Volver a calcular factura restante**: actualiza automáticamente la línea del pedido de compra y los estados del encabezado. Esta función funciona solo para líneas de pedido de compra almacenadas (es decir, líneas en las que el artículo es un artículo almacenado). Los artículos no almacenados y los artículos con peso capturado no se admiten actualmente.
    - **Volver a calcular \> Volver a calcular estado**: vuelve a calcular el estado de la línea seleccionada. Este cálculo se basa en la lógica existente. Por lo tanto, el estado del encabezado del pedido de compra se actualizará según sea necesario, según el estado de la nueva línea del pedido de compra.

1. Si aún ve inconsistencias en las cantidades restantes, puede usar los siguientes campos para editarlas directamente según sea necesario:

    - Pendiente de entrega
    - Pendiente de entrega de inventario
    - Recordatorio de factura
    - Resto de factura de inventario
