---
title: Gestionar manualmente excepciones de selección de líneas de ventas y transferencia
description: Este artículo describe cómo los administradores pueden seleccionar (o cancelar) manualmente las transacciones de inventario para solucionar problemas causados por datos dañados de pedidos de transferencia y ventas.
author: perlynne
ms.date: 08/19/2022
ms.topic: article
ms.search.form: WHSManualSalesLinePicking, WHSManualInventTransferLinePicking, InventTransPick, WHSLoadLineManualCorrection, WHSTroubleshootingSelfService
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: d2f89a7109060e69aca6a06eadaedc017728bbae
ms.sourcegitcommit: 0220be95c007c77ba3b73fed8ac68a3d72dc2884
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "9403701"
---
# <a name="manually-handle-sales-and-transfer-line-picking-exceptions"></a>Gestionar manualmente excepciones de selección de líneas de ventas y transferencia

[!include [banner](../includes/banner.md)]

La gestión manual de excepciones de selección de líneas de transferencia y ventas permite a los administradores solucionar problemas causados por datos dañados de pedidos de transferencia y ventas. Permite que los usuarios de confianza seleccionen (o cancelen) manualmente transacciones de inventario que están relacionadas con líneas de pedidos de transferencia y ventas mientras los procesos de almacén ya están en curso.

La funcionalidad que se describe aquí debe usarse solo en los casos en que el sistema no pueda terminar de procesar la pila de procesos del almacén de la manera habitual. De forma predeterminada, solo los usuarios que tienen un rol de administrador del sistema pueden usarlo. Sin embargo, puede otorgar acceso a él asignando el privilegio *Seleccionar líneas de venta manualmente* a otros roles según lo requiera.

## <a name="turn-on-this-feature-for-your-system"></a>Activar esta función para su sistema

Antes de poder usar las funciones que se describen en este artículo, deben activarlas en su sistema. Los administradores pueden usar la configuración de [administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de las características y activarlas. En el espacio de trabajo **Administración de funciones**, las funciones aparecen con los siguientes nombres:

- *Servicio de recogida manual de línea de ventas para administración o para usuarios de confianza similares*<br>(A partir de la versión 10.0.25 de Supply Chain Management, esta característica es obligatoria y no se puede desactivar).
- *Servicio de selección manual de línea de transferencia para administración o usuarios de confianza similares*

## <a name="correct-transactions-related-to-sales-or-transfer-order-lines"></a>Corregir transacciones relacionadas con líneas de pedidos de transferencia o ventas

Utilice el siguiente procedimiento para corregir transacciones relacionadas con líneas de pedidos de transferencia o ventas.

1. Siga uno de estos pasos, según el tipo de pedido que debe corregir:

    - Para corregir una transacción relacionada con un pedido de ventas, vaya a **Gestión de almacenes \> Tareas periódicas \> Limpiar \> Seleccionar líneas de ventas manualmente**.
    - Para corregir una transacción relacionada con un pedido de transferencia, vaya a **Gestión de almacenes \> Tareas periódicas \> Limpiar \> Seleccionar manualmente líneas de transferencia**.

1. En la página **Seleccionar líneas de ventas manualmente** o **Seleccionar manualmente líneas de transferencia**, use los filtros en la parte superior de la cuadrícula para encontrar la línea que está buscando y luego seleccione la línea de pedido de destino en la cuadrícula superior.
1. Utilice las pestañas **Transacciones de inventario**, **Líneas de carga**, **Líneas de trabajo** y **Líneas de contenedores** en la sección inferior para ver más información sobre la línea seleccionada. La información de estas pestañas ofrece una descripción general básica de los procesos de almacén relacionados y sus estados.
1. En la Panel de acciones, seleccione **Seleccionar** para abrir la línea de pedido seleccionada en la página **Seleccionar** para transacciones de inventario. Puede completar este paso incluso para líneas de pedido que ya se hayan liberado al almacén. (Por lo general, las líneas de pedido que se han liberado al almacén no se pueden abrir en la página **Seleccionar**.)

    > [!NOTE]
    > Es posible que reciba varias advertencias cuando abra la página **Seleccionar**. Realice cualquier acción que recomienden estas advertencias. Por ejemplo, puede recibir una advertencia sobre líneas de pedido que están vinculadas al trabajo de almacén. En este caso, conviene intentar cancelar el trabajo usando la funcionalidad estándar [cancelar trabajo](cancel-warehouse-work.md) antes de realizar la corrección manualmente.

1. Seleccione la línea en la cuadrícula **Transacciones** y, a continuación, seleccione **Agregar línea de picking** en la barra de herramientas **Transacciones**.
1. La línea seleccionada se mueve a la cuadrícula **Líneas de picking**. Establezca valores apropiados para cualquier columna a la que le falte información requerida. (Por ejemplo, especifique la ubicación y la matrícula en la que se debe seleccionar/anular la selección del artículo).
1. Seleccione **Confirmar la selección de todo** en barra de herramientas **Líneas de picking**.

## <a name="correct-load-line-quantities"></a>Corregir cantidades de líneas de carga

Utilice el siguiente procedimiento para corregir una cantidad de líneas de carga.

1. Siga uno de estos pasos, según el tipo de pedido que debe corregir:

    - Para corregir una transacción relacionada con un pedido de ventas, vaya a **Gestión de almacenes \> Tareas periódicas \> Limpiar \> Seleccionar líneas de ventas manualmente**.
    - Para corregir una transacción relacionada con un pedido de transferencia, vaya a **Gestión de almacenes \> Tareas periódicas \> Limpiar \> Seleccionar manualmente líneas de transferencia**.

1. En la página **Seleccionar líneas de ventas manualmente** o **Seleccionar manualmente líneas de transferencia**, use los filtros en la parte superior de la cuadrícula para encontrar la línea que está buscando y luego seleccione la línea de pedido de destino en la cuadrícula superior.
1. En la pestaña **Líneas de carga** de la sección inferior, seleccione **Corregir líneas de carga manualmente** en la barra de herramientas.
1. En la página **Corregir líneas de carga manualmente**, en la cuadrícula **Transacciones de inventario**, revise las transacciones de inventario relacionadas con la línea de carga seleccionada.
1. En la cuadrícula superior, corrija las cantidades de línea de carga en las siguientes columnas según sea necesario:

    - **Cantidad de trabajo creado**
    - **Cantidad seleccionada**
    - **Cantidad planificada en tránsito directo**

    El sistema validará cualquier cambio que realice en estas columnas.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
