---
title: Pedidos de almacenes para unidades de escalado en el perímetro y en la nube
description: Este artículo proporciona información sobre la capacidad de pedidos de almacén que se utiliza como parte de la carga de trabajo de la unidad de escalada de almacén.
author: perlynne
ms.date: 04/22/2021
ms.topic: article
ms.search.form: WHSWarehouseOrderLine, WHSWarehouseReceiptEntry, PurchTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-13
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: db254216e6c34b81f83c87a8fda454d0aeb1cece
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8893537"
---
# <a name="warehouse-orders-for-cloud-and-edge-scale-units"></a>Pedidos de almacenes para unidades de escalado en el perímetro y en la nube

[!include [banner](../includes/banner.md)]

> [!WARNING]
> No todas las funciones comerciales son totalmente compatibles con la versión preliminar pública cuando se utilizan cargas de trabajo de unidades de escalado. Si solo está usando unidades de escalado, asegúrese de utilizar solo los procesos que este artículo describe explícitamente como compatibles.

## <a name="what-are-warehouse-orders"></a>¿Qué son los pedidos de almacén?

Los *pedidos de almacén* son un tipo de pedido que se usó para admitir implementaciones de almacén de unidades de escalado y concentradores. Le permiten recibir y enviar inventario cuando está ejecutando una carga de trabajo de almacén en una unidad de escalado.

Los pedidos de almacén se utilizan como parte del procesamiento de gestión de almacén de entrada y salida. Se crean como parte del proceso *Liberar al almacén*, que se inicializa en el concentrador.
Para el procesamiento de entrada, Warehouse Mobile App se utiliza para registrar el inventario físico disponible durante el procesamiento de los pedidos de entrada, esto está disponible para pedidos de compra y producción que especifican un almacén de unidad de escala y artículos que están habilitados para usar procesos de administración de almacén.
Los pedidos de almacén de salida se utilizan como parte del proceso de envío de pedidos para transferencias y pedidos de venta.

> [!IMPORTANT]
> Los pedidos de almacén están disponibles solo en implementaciones que utilizan [cargas de trabajo de administración de almacenes para unidades de escalado de perímetro y en la nube](cloud-edge-workload-warehousing.md).

## <a name="create-an-inbound-warehouse-order"></a>Crear un pedido de almacén entrante

Para crear una orden de almacén de entrada para un proceso de orden de compra, siga estos pasos.

1. Inicie sesión en la instancia de Microsoft Dynamics 365 Supply Chain Management que se está ejecutando en el concentrador. (Debe iniciar el proceso *Liberar al almacén* mientras está conectado en el concentrador).
1. Vaya a **Adquisición y abastecimiento \> Pedidos de compra \> Todos los pedidos de compra**.
1. En el panel de acciones, en la pestaña **Almacén**, en el grupo **Acciones**, seleccione **Liberar al almacén**.
1. Para ver las líneas de pedido de almacén relacionadas, abra el pedido de compra relevante, seleccione una línea en la sección **Líneas de pedido de compra** y, después, en la barra de herramientas, seleccione **Almacén \> Líneas de pedido de almacén**. Para ver todas las líneas, vaya a **Gestión de almacenes \> Consultas e informes \> Líneas de pedido de almacén**.

También puede activar el proceso *Liberar al almacén* desde un trabajo por lotes yendo a **Gestión de almacén> Liberación a almacén> Liberación automática de órdenes de compra**. Al configurar el trabajo por lotes, puede seleccionar líneas de pedido de compra específicas en función de una consulta. Un escenario típico sería configurar un trabajo por lotes recurrente que libere todas las líneas de órdenes de compra confirmadas que se espera lleguen al día siguiente.

## <a name="cancel-a-warehouse-order"></a>Cancelar un pedido de almacén

Como parte del proceso *Liberar al almacén*, las transacciones de inventario de pedidos de compra están vinculadas a los pedidos de almacén y bloqueadas para que no las actualice el concentrador. Si liberó al almacén por error o si tiene alguna otra razón para revertir la creación de líneas de pedido de almacén, puede solicitar cancelar las líneas de pedido de almacén.

Para cancelar las líneas de pedido de almacén, siga estos pasos.

1. Inicie sesión en la instancia de Supply Chain Management que se está ejecutando en el concentrador.
1. Vaya a **Gestión de almacenes \> Consultas e informes \> Líneas de pedido de almacén**.
1. Seleccione la línea relevante.
1. En el panel de acciones, seleccione **Cancelar líneas de pedido de almacén**.

> [!NOTE]
> Se rechazará la solicitud de cancelación de líneas para cualquier línea que ya esté pendiente de cancelación o que se esté procesando de forma activa en un almacén que está ejecutando su carga de trabajo en una unidad de escalado.

## <a name="monitor-a-warehouse-order"></a>Supervisar un pedido de almacén

En la visualización **Líneas de pedido de almacén**, puede supervisar el progreso de la recepción entrante revisando los valores en la columna **Cantidad restante**. Para ver los detalles relacionados con el trabajo que se realiza mediante la aplicación móvil Warehouse Management, siga uno de estos pasos.

- Vaya a **Gestión de almacenes \> Consultas e informes \> Líneas de pedido de almacén** y use el filtro para encontrar las líneas que está buscando.
- Vaya a **Adquisición y abastecimiento \> Pedidos de compra \> Todos los pedidos de compra** y abra el pedido de compra relevante. En la sección **Líneas de pedido de compra**, seleccione una o más líneas y luego, en la barra de herramientas, seleccione **Almacén \> Entradas de recepción de almacén**.

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
