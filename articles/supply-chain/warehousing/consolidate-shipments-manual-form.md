---
title: Consolidar los envíos manualmente utilizando la página Consolidar envíos
description: Este tema presenta un escenario en el que se despachan múltiples pedidos al almacén en la misma carga y luego se consolidan usando la página Consolidar envíos.
author: GarmMSFT
manager: tfehr
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: ac60bef797d8e0bbe0d20f1585d5c3c0163f8788
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "3986801"
---
# <a name="consolidate-shipments-manually-by-using-the-consolidate-shipments-page"></a>Consolidar los envíos manualmente utilizando la página Consolidar envíos

[!include [banner](../includes/banner.md)]

Este tema presenta un escenario en el que se despachan múltiples pedidos al almacén en la misma carga y luego se consolidan usando la página **Consolidar envíos**.

## <a name="make-demo-data-available"></a>Hacer que los datos de demostración estén disponibles

El escenario de este tema hace referencia a valores y registros que se incluyen en los datos de demostración estándar que se proporcionan para Microsoft Dynamics 365 Supply Chain Management. Si desea utilizar los valores que se proporcionan aquí mientras realiza los ejercicios, asegúrese de trabajar en un entorno donde estén instalados los datos de demostración y configure la entidad jurídica en **USMF** antes de empezar.

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a>Configurar directivas de consolidación de envíos y filtros de productos

El escenario que se describe aquí supone que ya ha activado la función, realizado los ejercicios de [Configurar directivas de consolidación de envíos](configure-shipment-consolidation-policies.md) y creado las directivas y otros registros que se describen allí. Asegúrese de hacer esos ejercicios antes de continuar con este escenario.

## <a name="create-the-sales-orders-for-this-scenario"></a>Crear los pedidos de ventas para este escenario

Comience creando una colección de pedidos de ventas con los que pueda trabajar. Debe trabajar con un almacén habilitado para procesos de almacén avanzado (WMS). A menos que se mencione explícitamente un almacén diferente, ese mismo almacén debe utilizarse para cada uno de los siguientes conjuntos de pedidos.

Vaya a **Clientes \> Pedidos \> Todos los pedidos de ventas** y cree una colección de pedidos de ventas que tengan la configuración que se describe en las siguientes subsecciones.

### <a name="create-sales-orders-1-and-2"></a>Crear pedidos de ventas 1 y 2

1. Cree dos pedidos de venta idénticos que tengan la siguiente configuración:

    - **Cuenta de cliente:** *US-007*
    - **Grupo:** *ShipCons*

1. Agregue una línea de pedido que tenga la siguiente configuración:

    - **Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)
    - **Cantidad:** *1.00*

1. Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la línea de pedido.

### <a name="create-sales-orders-3-and-4"></a>Crear pedidos de ventas 3 y 4

1. Cree dos pedidos de venta idénticos que tengan la siguiente configuración:

    - **Cuenta de cliente:** *US-007*
    - **Grupo:** Deje este campo en blanco.

1. Agregue una línea de pedido que tenga la siguiente configuración:

    - **Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)
    - **Cantidad:** *1.00*

1. Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la línea de pedido.

## <a name="release-the-orders-to-the-warehouse"></a>Despachar los pedidos al almacén

Siga estos pasos para despachar cada pedido de ventas que creó para este escenario al almacén.

1. Vaya a **Clientes \> Pedidos \> Todos los pedidos de venta**.
1. Busque y seleccione el pedido de ventas a despachar.
1. En el panel Acciones, en la pestaña **Almacén**, seleccione **Acciones \> Liberar al almacén** para despachar el pedido de ventas seleccionado.
1. Repita este procedimiento para cada pedido de ventas restante que creó para este escenario.

## <a name="consolidate-shipments"></a>Consolidar envíos

1. Vaya a **Gestión de almacenes \> Envíos \> Todos los envíos**.
1. Busque y seleccione un envío que se creó cuando el pedido de ventas 1 se despachó al almacén. (Su campo **Directiva de consolidación de envíos** debe establecerse en *Grupo de pedidos*).
1. En el panel Acciones, en la pestaña **Envíos**, seleccione **Envíos \> Consolidar envíos**.
1. Verifique los envíos que se sugieren para consolidación. Solo se debe sugerir para consolidación un envío que tenga la misma directiva.
1. Cierre la página **Consolidación de envíos**.
1. Busque y seleccione un envío que se creó cuando el pedido de ventas 3 se despachó al almacén. (Su campo **Directiva de consolidación de envíos** debe establecerse en *Predeterminada*).
1. En el panel Acciones, en la pestaña **Envíos**, seleccione **Envíos \> Consolidar envíos**.
1. Verifique lno se sugiere ningún envío para consolidación.
1. Seleccione **Mostrar filtros**.
1. En el panel **Filtros**, quite el filtro **Número de pedido** y luego seleccione **Aplicar**.
1. Verifique los envíos que se sugieren para consolidación. Solo se debe sugerir para consolidación un envío que tenga la misma directiva.

## <a name="additional-resources"></a>Recursos adicionales

- [Directivas de consolidación de envíos](about-shipment-consolidation-policies.md)
- [Configurar directivas de consolidación de envíos](configure-shipment-consolidation-policies.md)