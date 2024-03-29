---
title: Consolide los envíos cuando se anula la directiva de consolidación de envíos
description: Este artículo presenta un escenario en el que una o más líneas de ventas deben despacharse manualmente al almacén desde la página Despachar a almacén, y la directiva de consolidación de envío definida por el sistema debe anularse antes del despacho.
author: Mirzaab
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSFilterGroupTable, WHSShipConsolidationSetShipment, WHSShipmentConsolidation, WHSFilterGenerallyAvail, WHSReleaseToWarehouse
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: e2c4fed880c423790b979f27511d8d5697bd244c
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2022
ms.locfileid: "9427965"
---
# <a name="consolidate-shipments-when-the-shipment-consolidation-policy-is-overridden"></a>Consolide los envíos cuando se anula la directiva de consolidación de envíos

[!include [banner](../includes/banner.md)]

Este artículo presenta un escenario en el que una o más líneas de ventas deben despacharse manualmente al almacén desde la página **Despachar a almacén**, y la directiva de consolidación de envíos definida por el sistema debe anularse antes del despacho. Es posible que se deba anular la directiva de consolidación de envíos si, por ejemplo, un pedido que generalmente no se consolida con envíos abiertos debe consolidarse con envíos abiertos.

Durante el escenario, creará un conjunto de pedidos de ventas y luego anulará la directiva de consolidación de envíos predeterminada antes de despachar los pedidos al almacén.

## <a name="make-demo-data-available"></a>Hacer que los datos de demostración estén disponibles

El escenario de este artículo hace referencia a valores y registros que se incluyen en los datos de demostración estándar que se proporcionan para Microsoft Dynamics 365 Supply Chain Management. Si desea utilizar los valores que se proporcionan aquí mientras realiza los ejercicios, asegúrese de trabajar en un entorno donde estén instalados los datos de demostración y configure la entidad jurídica en **USMF** antes de empezar.

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a>Configurar directivas de consolidación de envíos y filtros de productos

El escenario que se describe aquí supone que ya ha activado la función, realizado los ejercicios de [Configurar directivas de consolidación de envíos](configure-shipment-consolidation-policies.md) y creado las directivas y otros registros que se describen allí. Asegúrese de hacer esos ejercicios antes de continuar con este escenario.

## <a name="create-the-sales-orders-for-this-scenario"></a>Crear los pedidos de ventas para este escenario

1. Vaya a **Clientes \> Pedidos \> Todos los pedidos de ventas** y cree tres pedidos de venta idénticos que tengan la siguiente configuración:

    - **Cuenta de cliente:** *US-002*

1. Agregue una línea de pedido que tenga la siguiente configuración:

    - **Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)
    - **Cantidad:** *1.00*

1. Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la línea de pedido.

## <a name="release-the-sales-orders-from-the-release-to-warehouse-page"></a>Despachar los pedidos de ventas desde la página Despachar al almacén

Siga estos pasos para anular la directiva de consolidación de envíos durante el deespacho al almacén.

1. Vaya a **Gestión de almacén \> Despachar al almacén \> Despachar al almacén**.
1. En el panel superior, seleccione el primer pedido de ventas que creó para este escenario.
1. Seleccione **Añadir** para agregar la línea al despacho al almacén. Tenga en cuenta que la directiva de consolidación de envíos *Predeterminada* se aplica en el panel inferior.
1. En el panel inferior, elija **Seleccionar nueva directiva de consolidación de envíos**.
1. Seleccione una directiva que permita la consolidación con otros envíos abiertos de la misma directiva. Por ejemplo, seleccione la directiva *CustomerOrderNo*.
1. Seleccione **Despachar al almacén**.
1. Seleccione los pedidos de ventas segundo y tercero que creó para este escenario.
1. Seleccione **Añadir** para agregar las líneas al despacho al almacén. Tenga en cuenta que la directiva *Predeterminada* se aplica en el panel inferior.
1. Seleccione la segunda línea y luego, en el campo **Seleccionar nueva directiva de consolidación de envíos**, seleccione la directiva *CustomerOrderNo*.
1. Seleccione **Despachar al almacén** para ambas líneas.

## <a name="verify-the-shipments"></a>Verificar los envíos

Deben haberse creado dos envíos:

- El primer envío contiene dos líneas y se creó utilizando la directiva de consolidación de envíos *CustomerOrderNo*.
- El segundo envío contiene una línea y se creó utilizando la directiva de consolidación de envíos *Predeterminada*.

Siga estos pasos para revisar los envíos que se crearon.

1. Vaya a **Gestión de almacenes \> Envíos \> Todos los envíos**.
1. Encuentre y seleccione el envío requerido.
1. En el campo **Directiva de consolidación de envíos**, revise la directiva de consolidación usada cuando se creó el envío.

## <a name="additional-resources"></a>Recursos adicionales

- [Vista general de directivas de consolidación de envíos](about-shipment-consolidation-policies.md)
- [Configurar directivas de consolidación de envíos](configure-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]