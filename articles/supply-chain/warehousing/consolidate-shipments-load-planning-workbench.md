---
title: Consolidar los envíos despachando al almacén desde área de trabajo de planificación de la carga
description: Este artículo presenta un escenario en el que se despachan múltiples pedidos al almacén en la misma carga y luego se consolidan automatizadamente en envíos.
author: Mirzaab
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 862b4b4121effa3ed0a2134924b2152c8a982110
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428100"
---
# <a name="consolidate-shipments-by-releasing-to-warehouse-from-the-load-planning-workbench"></a>Consolidar los envíos despachando al almacén desde área de trabajo de planificación de la carga

[!include [banner](../includes/banner.md)]

Este artículo presenta un escenario en el que se despachan múltiples pedidos al almacén en la misma carga y luego se consolidan automatizadamente en envíos.

## <a name="make-demo-data-available"></a>Hacer que los datos de demostración estén disponibles

El escenario de este artículo hace referencia a valores y registros que se incluyen en los datos de demostración estándar que se proporcionan para Microsoft Dynamics 365 Supply Chain Management. Si desea utilizar los valores que se proporcionan aquí mientras realiza los ejercicios, asegúrese de trabajar en un entorno donde estén instalados los datos de demostración y configure la entidad jurídica en **USMF** antes de empezar.

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a>Configurar directivas de consolidación de envíos y filtros de productos

El escenario que se describe aquí supone que ya ha activado la función, realizado los ejercicios de [Configurar directivas de consolidación de envíos](configure-shipment-consolidation-policies.md) y creado las directivas y otros registros que se describen allí. Asegúrese de hacer esos ejercicios antes de continuar con este escenario.

## <a name="create-the-sales-orders-for-this-scenario"></a>Crear los pedidos de ventas para este escenario

Comience creando una colección de pedidos de ventas con los que pueda trabajar. Debe trabajar con un almacén habilitado para procesos de almacén avanzado (WMS). A menos que se mencione explícitamente un almacén diferente, ese mismo almacén debe utilizarse para cada uno de los siguientes conjuntos de pedidos.

Vaya a **Clientes \> Pedidos \> Todos los pedidos de ventas** y cree una colección de pedidos de ventas que tengan la configuración que se describe en las siguientes subsecciones.

### <a name="create-order-set-1"></a>Crear conjunto de pedidos 1

#### <a name="sales-order-1-1"></a>Pedido de ventas 1-1

1. Cree un pedido de ventas con la siguiente configuración:

    - **Cuenta de cliente:** *US-001*
    - **Modo de entrega:** *Airwa-Air*

1. Agregue una línea de pedido que tenga la siguiente configuración:

    - **Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)
    - **Cantidad:** *1.00*

1. Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la línea de pedido.

#### <a name="sales-order-1-2"></a>Pedido de ventas 1-2

1. Cree un pedido de ventas con la siguiente configuración:

    - **Cuenta de cliente:** *US-001*
    - **Modo de entrega:** *Airwa-Air*

1. Agregue una línea de pedido que tenga la siguiente configuración:

    - **Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)
    - **Cantidad:** *1.00*

1. Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la línea de pedido.

#### <a name="sales-order-1-3"></a>Pedido de ventas 1-3

1. Cree un pedido de ventas con la siguiente configuración:

    - **Cuenta de cliente:** *US-001*
    - **Modo de entrega:** *10*

1. Agregue una línea de pedido que tenga la siguiente configuración:

    - **Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)
    - **Cantidad:** *1.00*

1. Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la línea de pedido.
1. Agregue un segundo pedido que tenga la siguiente configuración:

    - **Número de artículo:** *A0002* (un artículo al que no se ha asignado el filtro **Código 4**)
    - **Cantidad:** *1.00*
    - **Modo de entrega:** *Airwa-Air*

1. Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la segunda línea de pedido.

### <a name="create-order-set-2"></a>Crear conjunto de pedidos 2

#### <a name="sales-orders-2-1-and-2-2"></a>Pedidos de ventas 2-1 y 2-2

1. Cree dos pedidos de venta idénticos que tengan la siguiente configuración:

    - **Cuenta de cliente:** *US-002*

1. Agregue una línea de pedido que tenga la siguiente configuración:

    - **Número de artículo:** *M9200* (un artículo donde el filtro **Código 4** está establecido en *Inflamable*)
    - **Cantidad:** *1.00*

1. Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la línea de pedido.
1. Agregue un segundo pedido que tenga la siguiente configuración:

    - **Número de artículo:** *M9201* (un artículo donde el filtro **Código 4** está establecido en *Explosivo*)
    - **Cantidad:** *1.00*
    - **Modo de entrega:** *Airwa-Air*

1. Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la segunda línea de pedido.

### <a name="create-order-set-3"></a>Crear conjunto de pedidos 3

#### <a name="sales-orders-3-1-and-3-2"></a>Pedidos de ventas 3-1 y 3-2

1. Cree dos pedidos de venta idénticos que tengan la siguiente configuración:

    - **Cuenta de cliente:** *US-001*
    - **Solicitud de cliente:** *1*

1. Agregue una línea de pedido que tenga la siguiente configuración:

    - **Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)
    - **Cantidad:** *1.00*

1. Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la línea de pedido.

#### <a name="sales-orders-3-3-and-3-4"></a>Pedidos de ventas 3-3 y 3-4

1. Cree dos pedidos de venta idénticos que tengan la siguiente configuración:

    - **Cuenta de cliente:** *US-001*
    - **Solicitud de cliente:** *2*

1. Agregue una línea de pedido que tenga la siguiente configuración:

    - **Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)
    - **Cantidad:** *1.00*

1. Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la línea de pedido.

### <a name="create-order-set-4"></a>Crear conjunto de pedidos 4

#### <a name="sales-orders-4-1-and-4-2"></a>Pedidos de ventas 4-1 y 4-2

1. Cree dos pedidos de venta idénticos que tengan la siguiente configuración:

    - **Cuenta de cliente:** *US-003*

1. Agregue una línea de pedido que tenga la siguiente configuración:

    - **Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)
    - **Cantidad:** *1.00*

1. Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la línea de pedido.

#### <a name="sales-orders-4-3-and-4-4"></a>Pedidos de ventas 4-3 y 4-4

1. Cree dos pedidos de venta idénticos que tengan la siguiente configuración:

    - **Cuenta de cliente:** *US-004*

1. Agregue una línea de pedido que tenga la siguiente configuración:

    - **Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)
    - **Cantidad:** *1.00*

1. Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la línea de pedido.

#### <a name="sales-orders-4-5-and-4-6"></a>Pedidos de ventas 4-5 y 4-6

1. Cree dos pedidos de venta idénticos que tengan la siguiente configuración:

    - **Cuenta de cliente:** *US-007*
    - **Sitio**: *6*
    - **Almacén**: *61*
    - **Grupo:** *ShipCons*

1. Agregue una línea de pedido que tenga la siguiente configuración:

    - **Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)
    - **Cantidad:** *1.00*

1. Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la línea de pedido.

#### <a name="sales-orders-4-7-and-4-8"></a>Pedidos de ventas 4-7 y 4-8

1. Cree dos pedidos de venta idénticos que tengan la siguiente configuración:

    - **Cuenta de cliente:** *US-007*
    - **Sitio**: *6*
    - **Almacén**: *61*
    - **Grupo:** Deje este campo en blanco.

1. Agregue una línea de pedido que tenga la siguiente configuración:

    - **Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)
    - **Cantidad:** *1.00*

1. Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la línea de pedido.

## <a name="use-the-load-planning-workbench-to-create-loads-and-release-them-to-the-warehouse"></a>Use el área de trabajo de planificación de la carga para crear cargas y despacharlas al almacén

Siga estos pasos para crear una carga para cada conjunto de pedidos que creó para este escenario y luego despacharlo al almacén.

1. Vaya a **Gestión de almacén \> Cargas \> Área de trabajo de planificación de la carga**.
1. En la pestaña **Líneas de venta**, busque y seleccione todas las líneas de pedido de ventas de uno de los conjuntos de pedidos que creó para este escenario.
1. En el Panel de acciones, en la pestaña **Oferta y demanda**, seleccione **Añadir \> A nueva carga** para agregar las líneas de pedidos seleccionadas a una nueva carga.
1. En el cuadro de diálogo **Cargar asignación de plantilla**, en el campo **Cargar id. de plantilla**, seleccione una plantilla de carga, como *Plantilla de carga estándar*.
1. Haga clic en **Aceptar** para cerrar el cuadro de diálogo. 
1. En la sección **Cargas**, busque y seleccione la carga que acaba de crear.
1. Seleccione **Despachar \> Despachar al almacén** para liberar la carga seleccionada al almacén.
1. Repita este procedimiento para los otros tres conjuntos de pedidos que creó para este escenario.

## <a name="verify-the-shipments"></a>Verificar los envíos

El siguiente procedimiento le permite verificar los envíos que se han creado o actualizado como resultado de la consolidación de envíos. Úselo para revisar cada conjunto de pedidos que creó para este escenario y luego revise las subsecciones siguientes para asegurarse de haber obtenido los resultados esperados.

1. Vaya a **Gestión de almacenes \> Envíos \> Todos los envíos**.
1. Encuentre y seleccione el envío requerido.
1. Si se utilizó una directiva de consolidación cuando se creó o actualizó el envío, debería verla en el campo **Directiva de consolidación de envío**.

### <a name="release-order-set-1-in-one-load"></a>Orden de despacho de conjunto 1 en una carga

Deben haberse creado dos envíos:

- El primer envío contiene tres líneas y se creó utilizando la directiva de consolidación de envíos *CustomerMode*.
- El segundo envío, que no utiliza el modo de transporte de entrega *Vías aéreas*, se creó usando la directiva de consolidación de envíos *CustomerOrderNo*.

### <a name="release-order-set-2-in-one-load"></a>Orden de despacho de conjunto 2 en una carga

Deben haberse creado tres envíos:

- El primer envío contiene los artículos *Inflamables*.
- Cada uno de los otros dos envíos contiene una línea que tiene el artículo *Explosivo*.

### <a name="release-order-set-3-in-one-load"></a>Orden de despacho de conjunto 3 en una carga

Deben haberse creado dos envíos:

- El primer envío contiene líneas de pedido del pedido de ventas donde el campo **Solicitud del cliente** está establecido en *1*.
- El segundo envío contiene líneas de pedido del pedido de ventas donde el campo **Solicitud del cliente** está establecido en *2*.

### <a name="release-order-set-4-in-one-load"></a>Orden de despacho de conjunto 4 en una carga

Deben haberse creado cuatro envíos:

- Las líneas de dos pedidos de la cuenta de cliente *US-003* se han agrupado en un envío, utilizando la directiva de consolidación de envíos *Grupo de pedidos*.
- Las líneas de dos pedidos de la cuenta de cliente *US-004* se han agrupado en un envío, utilizando la directiva de consolidación de envíos *Grupo de pedidos*.
- Las líneas de los pedidos de ventas 4-5 y 4-6 para la cuenta de cliente *US-007* se han agrupado en un envío, utilizando la directiva de consolidación de envíos *Grupo de pedidos*.
- Las líneas de los pedidos de ventas 4-7 y 4-8 para la cuenta de cliente *US-007* se han agrupado en un envío, utilizando la directiva de consolidación de envíos *CrossOrder*.

## <a name="additional-resources"></a>Recursos adicionales

- [Vista general de directivas de consolidación de envíos](about-shipment-consolidation-policies.md)
- [Configurar directivas de consolidación de envíos](configure-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]