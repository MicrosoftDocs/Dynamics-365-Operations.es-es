---
title: Consolidar los envíos utilizando el área de trabajo de consolidación de envíos
description: Este tema presenta un escenario en el que se despachan múltiples pedidos al almacén en la misma carga y luego se consolidan en envíos usando el área de trabajo de consolidación de envíos.
author: GarmMSFT
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSShipConsolidationSetShipment
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 916d83c3773b557ae2d89d554846263a740111ea
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7578665"
---
# <a name="consolidate-shipments-by-using-the-shipment-consolidation-workbench"></a>Consolidar los envíos utilizando el área de trabajo de consolidación de envíos

[!include [banner](../includes/banner.md)]

Este tema presenta un escenario en el que se despachan múltiples pedidos al almacén en la misma carga y luego se consolidan en envíos usando el área de trabajo de consolidación de envíos.

## <a name="make-demo-data-available"></a>Hacer que los datos de demostración estén disponibles

El escenario de este tema hace referencia a valores y registros que se incluyen en los datos de demostración estándar que se proporcionan para Microsoft Dynamics 365 Supply Chain Management. Si desea utilizar los valores que se proporcionan aquí mientras realiza los ejercicios, asegúrese de trabajar en un entorno donde estén instalados los datos de demostración y configure la entidad jurídica en **USMF** antes de empezar.

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a>Configurar directivas de consolidación de envíos y filtros de productos

El escenario que se describe aquí supone que ya ha activado la función, realizado los ejercicios de [Configurar directivas de consolidación de envíos](configure-shipment-consolidation-policies.md) y creado las directivas y otros registros que se describen allí. Asegúrese de hacer esos ejercicios antes de continuar con este escenario.

## <a name="turn-on-the-manual-shipment-consolidation-feature"></a>Activar la función manual de consolidación de envíos

Antes de poder usar la función *Consolidación manual de envíos*, debe activarla en su sistema. Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla. En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:

- **Módulo:** *Gestión de almacén*
- **Nombre de función:** *Consolidación manual de envíos*

Como se mencionó en [Configurar directivas de consolidación de envíos](configure-shipment-consolidation-policies.md), también debe activar la función *Consolidar envío* antes de poder crear directivas. Sin embargo, ya debería haber completado ese paso.

## <a name="create-the-sales-orders-for-this-scenario"></a>Crear los pedidos de ventas para este escenario

Comience creando una colección de pedidos de ventas con los que pueda trabajar. Debe trabajar con un almacén habilitado para procesos de almacén avanzado (WMS). A menos que se mencione explícitamente un almacén diferente, ese mismo almacén debe utilizarse para cada uno de los siguientes conjuntos de pedidos.

Vaya a **Clientes \> Pedidos \> Todos los pedidos de ventas** y cree una colección de pedidos de ventas que tengan la configuración que se describe en las siguientes subsecciones.

### <a name="create-order-set-1"></a>Crear conjunto de pedidos 1

#### <a name="sales-orders-1-1-and-1-2"></a>Pedidos de ventas 1-1 y 1-2

1. Cree dos pedidos de venta idénticos que tengan la siguiente configuración:

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
    - **Modo de entrega:** *Airwa-Air*

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

## <a name="release-the-orders-to-the-warehouse"></a>Despachar los pedidos al almacén

Siga estos pasos para despachar cada pedido de ventas que creó para este escenario al almacén.

1. Vaya a **Clientes \> Pedidos \> Todos los pedidos de venta**.
1. Busque y seleccione el pedido de ventas a despachar.
1. En el panel Acciones, en la pestaña **Almacén**, seleccione **Acciones \> Liberar al almacén** para despachar el pedido de ventas seleccionado.
1. Repita este procedimiento para cada pedido de ventas restante que creó para este escenario.

## <a name="consolidate-the-shipments-by-using-the-shipment-consolidation-workbench"></a>Consolidar los envíos utilizando el área de trabajo de consolidación de envíos

1. Vaya a **Gestión de almacén \> Despachar al almacén \> Área de trabajo de consolidación de envíos**.
1. En el panel Acciones, seleccione **Editar consulta**.
1. En el cuadro de diálogo del editor de consultas, en la pestaña **Rango**, seleccione **Añadir** para agregar una fila que tenga la siguiente configuración a la cuadrícula:

    - **Tabla:** *Pedidos de ventas*
    - **Campo:** *Pedido de ventas*
    - **Criterio:** Introduzca una lista separada por comas de los números de pedido de ventas para cada conjunto de pedidos que creó para este escenario.

1. Seleccione **Aceptar** para guardar su consulta y cerrar el cuadro de diálogo.
1. En el panel Acciones, seleccione **Consolidar envíos**.
1. Seleccione todos los envíos y, a continuación, en el panel Acciones, seleccione **Consolidar**.

## <a name="verify-the-shipments"></a>Verificar los envíos

El siguiente procedimiento le permite verificar los envíos que se han creado o actualizado como resultado de la consolidación de envíos. Úselo para revisar cada conjunto de pedidos que creó para este escenario y luego revise las subsecciones siguientes para asegurarse de haber obtenido los resultados esperados.

1. Vaya a **Gestión de almacenes \> Envíos \> Todos los envíos**.
1. Encuentre y seleccione el envío requerido.
1. Si se utilizó una directiva de consolidación cuando se creó o actualizó el envío, debería verla en el campo **Directiva de consolidación de envío**.

### <a name="related-shipments-for-order-set-1"></a>Envíos relacionados para el conjunto de pedidos 1

Deben haberse creado dos envíos:

- El primer envío contiene tres líneas y se creó utilizando la directiva de consolidación de envíos *CustomerMode*.
- El segundo envío, que no utiliza el modo de transporte de entrega *Vías aéreas*, se creó usando la directiva de consolidación de envíos *CustomerOrderNo*.

### <a name="related-shipments-for-order-set-2"></a>Envíos relacionados para el conjunto de pedidos 2

Deben haberse creado tres envíos:

- El primer envío contiene artículos *Inflamables*.
- Cada uno de los otros dos envíos contiene una línea que tiene el artículo *Explosivo*.

### <a name="related-shipments-for-order-set-3"></a>Envíos relacionados para el conjunto de pedidos 3

Deben haberse creado dos envíos:

- El primer envío contiene líneas de pedido del pedido de ventas donde el campo **Solicitud del cliente** está establecido en *1*.
- El segundo envío contiene líneas de pedido del pedido de ventas donde el campo **Solicitud del cliente** está establecido en *2*.

### <a name="related-shipments-for-order-set-4"></a>Envíos relacionados para el conjunto de pedidos 4

Deben haberse creado cuatro envíos:

- Las líneas de dos pedidos del cliente *US-003* se han agrupado en un envío, utilizando la directiva de consolidación de envíos *Grupo de pedidos*.
- Las líneas de dos pedidos del cliente *US-004* se han agrupado en un envío, utilizando la directiva de consolidación de envíos *Grupo de pedidos*.
- Las líneas de pedido de ventas 4-5 y 4-6 para clientes *US-007* se han agrupado en un envío, utilizando la directiva de consolidación de envíos *Grupo de pedidos*.
- Las líneas de pedido de ventas 4-7 y 4-8 para clientes *US-007* se han agrupado en un envío, utilizando la directiva de consolidación de envíos *CrossOrder*.

## <a name="additional-resources"></a>Recursos adicionales

- [Directivas de consolidación de envíos](about-shipment-consolidation-policies.md)
- [Configurar directivas de consolidación de envíos](configure-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]