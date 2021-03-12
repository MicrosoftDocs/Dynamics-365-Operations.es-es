---
title: Consolidar los envíos cuando se despachan al almacén mediante Despacho automático de pedidos de ventas
description: Este tema presenta un escenario en el que se despachan múltiples pedidos al almacén en el mismo procedimiento periódico automatizado de despacho al almacén.
author: GarmMSFT
manager: tfehr
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSFilterGroupTable, WHSShipmentConsolidation, WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 376c7418b61c0192f9071a879b50b9ece7699894
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4970365"
---
# <a name="consolidate-shipments-when-they-are-released-to-the-warehouse-by-using-automatic-release-of-sales-orders"></a>Consolidar los envíos cuando se despachan al almacén mediante Despacho automático de pedidos de ventas

[!include [banner](../includes/banner.md)]

Este tema presenta un escenario en el que se despachan múltiples pedidos al almacén en el mismo procedimiento periódico automatizado de despacho al almacén. Los pedidos se consolidarán automáticamente en envíos, según las reglas que se definen como directivas de consolidación de envíos.

Durante el escenario, creará conjuntos de pedidos de ventas y despachará cada conjunto al almacén. Luego revisará los envíos que se crean o actualizan durante la consolidación de envíos, según las directivas configuradas.

## <a name="make-demo-data-available"></a>Hacer que los datos de demostración estén disponibles

El escenario de este tema hace referencia a valores y registros que se incluyen en los datos de demostración estándar que se proporcionan para Microsoft Dynamics 365 Supply Chain Management. Si desea utilizar los valores que se proporcionan aquí mientras realiza los ejercicios, asegúrese de trabajar en un entorno donde estén instalados los datos de demostración y configure la entidad jurídica en **USMF** antes de empezar.

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

#### <a name="sales-order-1-2"></a>Pedido de ventas 1-2

1. Cree un pedido de ventas con la siguiente configuración:

    - **Cuenta de cliente:** *US-001*
    - **Modo de entrega:** *Airwa-Air*

1. Agregue una línea de pedido que tenga la siguiente configuración:

    - **Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)
    - **Cantidad:** *1.00*

#### <a name="sales-order-1-3"></a>Pedido de ventas 1-3

1. Cree un pedido de ventas con la siguiente configuración:

    - **Cuenta de cliente:** *US-001*
    - **Modo de entrega:** *10*

1. Agregue una línea de pedido que tenga la siguiente configuración:

    - **Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)
    - **Cantidad:** *1.00*

1. Agregue un segundo pedido que tenga la siguiente configuración:

    - **Número de artículo:** *A0002* (un artículo al que no se ha asignado el filtro **Código 4**)
    - **Cantidad:** *1.00*
    - **Modo de entrega:** *Airwa-Air*

### <a name="create-order-set-2"></a>Crear conjunto de pedidos 2

#### <a name="sales-orders-2-1-and-2-2"></a>Pedidos de ventas 2-1 y 2-2

1. Cree dos pedidos de venta idénticos que tengan la siguiente configuración:

    - **Cuenta de cliente:** *US-002*

1. Agregue una línea de pedido que tenga la siguiente configuración:

    - **Número de artículo:** *M9200* (un artículo donde el filtro **Código 4** está establecido en *Inflamable*)
    - **Cantidad:** *1.00*

1. Agregue un segundo pedido que tenga la siguiente configuración:

    - **Número de artículo:** *M9201* (un artículo donde el filtro **Código 4** está establecido en *Explosivo*)
    - **Cantidad:** *1.00*
    - **Modo de entrega:** *Airwa-Air*

### <a name="create-order-set-3"></a>Crear conjunto de pedidos 3

#### <a name="sales-order-3-1"></a>Pedido de ventas 3-1

1. Cree un pedido de ventas con la siguiente configuración:

    - **Cuenta de cliente:** *US-002*

1. Agregue una línea de pedido que tenga la siguiente configuración:

    - **Número de artículo:** *M9200* (un artículo donde el filtro **Código 4** está establecido en *Inflamable*)
    - **Cantidad:** *1.00*

1. Agregue un segundo pedido que tenga la siguiente configuración:

    - **Número de artículo:** *M9201* (un artículo donde el filtro **Código 4** está establecido en *Explosivo*)
    - **Cantidad:** *1.00*
    - **Modo de entrega:** *Airwa-Air*

> [!NOTE]
> Este pedido es idéntico a los dos pedidos que creó para el conjunto de pedidos 2. Sin embargo, aparece en su propio conjunto de órdenes porque lo despchará por separado más adelante en este escenario.

### <a name="create-order-set-4"></a>Crear conjunto de pedidos 4

#### <a name="sales-order-4-1"></a>Pedido de ventas 4-1

1. Cree un pedido de ventas con la siguiente configuración:

    - **Cuenta de cliente:** *US-001*
    - **Solicitud de cliente:** *1*

1. Agregue una línea de pedido que tenga la siguiente configuración:

    - **Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)
    - **Cantidad:** *1.00*

### <a name="create-order-set-5"></a>Crear conjunto de pedidos 5

#### <a name="sales-orders-5-1-and-5-2"></a>Pedidos de ventas 5-1 y 5-2

1. Cree dos pedidos de venta idénticos que tengan la siguiente configuración:

    - **Cuenta de cliente:** *US-001*
    - **Solicitud de cliente:** *2*

1. Agregue una línea de pedido que tenga la siguiente configuración:

    - **Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)
    - **Cantidad:** *1.00*

#### <a name="sales-order-5-3"></a>Pedido de ventas 5-3

1. Cree un pedido de ventas con la siguiente configuración:

    - **Cuenta de cliente:** *US-001*
    - **Solicitud de cliente:** *1*

1. Agregue una línea de pedido que tenga la siguiente configuración:

    - **Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)
    - **Cantidad:** *1.00*

### <a name="create-order-set-6"></a>Crear conjunto de pedidos 6

#### <a name="sales-orders-6-1-and-6-2"></a>Pedidos de ventas 6-1 y 6-2

1. Cree dos pedidos de venta idénticos que tengan la siguiente configuración:

    - **Cuenta de cliente:** *US-003*
    - **Solicitud de cliente:** *2*

1. Agregue una línea de pedido que tenga la siguiente configuración:

    - **Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)
    - **Cantidad:** *1.00*

#### <a name="sales-orders-6-3-and-6-4"></a>Pedidos de ventas 6-3 y 6-4

1. Cree dos pedidos de venta idénticos que tengan la siguiente configuración:

    - **Cuenta de cliente:** *US-004*
    - **Solicitud de cliente:** *1*

1. Agregue una línea de pedido que tenga la siguiente configuración:

    - **Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)
    - **Cantidad:** *1.00*

#### <a name="sales-orders-6-5-and-6-6"></a>Pedidos de ventas 6-5 y 6-6

1. Cree dos pedidos de venta idénticos que tengan la siguiente configuración:

    - **Cuenta de cliente:** *US-007*
    - **Sitio**: *6*
    - **Almacén**: *61*
    - **Grupo:** *ShipCons*

1. Agregue una línea de pedido que tenga la siguiente configuración:

    - **Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)
    - **Cantidad:** *1.00*

#### <a name="sales-orders-6-7-and-6-8"></a>Pedidos de ventas 6-7 y 6-8

1. Cree dos pedidos de venta idénticos que tengan la siguiente configuración:

    - **Cuenta de cliente:** *US-007*
    - **Sitio**: *6*
    - **Almacén**: *61*
    - **Grupo:** Deje este campo en blanco.

1. Agregue una línea de pedido que tenga la siguiente configuración:

    - **Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)
    - **Cantidad:** *1.00*

## <a name="automatic-release-of-sales-orders-to-the-warehouse"></a>Despacho automático de pedidos de ventas al almacén

Para cada conjunto de pedidos de ventas que creó anteriormente, completará un procedimiento para el despacho automático al almacén. En cada caso, trabajará a través del [procedimiento básico de despacho al almacén](#release-procedure) que se proporciona aquí.

### <a name="basic-release-to-warehouse-procedure"></a><a name="release-procedure"></a>Procedimiento básico de despacho al almacén

Para cada conjunto de pedidos de ventas que creó anteriormente, completará los tres procedimientos que se describen en las subsecciones siguientes.

#### <a name="update-the-wave-template-that-will-be-used-during-release"></a>Actualice la plantilla de oleada que se usará durante el despacho

1. Vaya a **Gestión de almacenes \> Configurar \> Oleadas \> Plantillas de oleada**.
1. Establezca el **Tipo de plantilla de oleada** en *Envío*.
1. Busque y seleccione la plantilla de oleada asociada con el almacén que utilizó en los conjuntos de pedidos que creó para este escenario. Por ejemplo, si usó el almacén *24*, seleccione la plantilla de oleada **Envío predeterminado 24**. Si usó el almacén *61*, seleccione la plantilla de oleada **Envío 61**.
1. En el panel Acciones, seleccione **Editar**.
1. Establezca la opción **Procesar oleada para su despacho al almacén** en *No*.

#### <a name="release-to-the-warehouse"></a>Despachar al almacén

1. Ir **Gestión de almacén \> Despachar al almacén \> Despacho automático de pedidos de ventas**.
1. Establece el campo **Cantidad a despachar** en *Todo*.
1. En la ficha desplegable **Registros a incluir**, seleccione **Filtrar** para abrir el cuadro de diálogo de consulta.
1. En la pestaña **Rango**, seleccione **Añadir** para agregar una fila que tenga la siguiente configuración a la cuadrícula:

    - **Tabla:** *Pedido de ventas*
    - **Tabla derivada:** *Pedido de ventas*
    - **Campo:** *Pedido de ventas*
    - **Criterio:** Introduzca una lista separada por comas de los números de pedido de ventas del conjunto de pedidos deseado.

1. Seleccione **Aceptar** para guardar su consulta.
1. Seleccione **Aceptar** para comenzar el procedimiento *Despacho automático al almacén*.

#### <a name="review-the-shipment-that-is-created-or-updated"></a>Revise el envío que se crea o actualiza

1. Vaya a **Gestión de almacenes \> Envíos \> Todos los envíos**.
1. Encuentre y seleccione el envío requerido.
1. Si se utilizó una directiva de consolidación cuando se creó o actualizó el envío, debería verla en el campo **Directiva de consolidación de envío**.

### <a name="release-sales-orders-from-order-set-1"></a>Despachar pedidos de ventas del conjunto de pedidos 1

Siga el [procedimiento básico de despacho al almacén](#release-procedure) para despachar los pedidos de ventas del conjunto de pedidos 1.

Cuando haya terminado, debería ver que se han creado dos envíos:

- El primer envío contiene tres líneas y se creó utilizando la directiva de consolidación de envíos *CustomerMode*.
- El segundo envío, que no utiliza el modo de transporte de entrega *Vías aéreas*, se creó usando la directiva de consolidación de envíos *CustomerOrderNo*.

### <a name="release-sales-orders-from-order-set-2"></a>Despachar pedidos de ventas del conjunto de pedidos 2

Siga el [procedimiento básico de despacho al almacén](#release-procedure) para despachar los pedidos de ventas del conjunto de pedidos 2.

Cuando haya terminado, debería ver que se han creado tres envíos:

- El primer envío contiene artículos *Inflamables*.
- Cada uno de los otros dos envíos contiene una línea que tiene el artículo *Explosivo*.

### <a name="release-sales-orders-from-order-set-3"></a>Despachar pedidos de ventas del conjunto de pedidos 3

Siga el [procedimiento básico de despacho al almacén](#release-procedure) para despachar los pedidos de ventas del conjunto de pedidos 3.

Cuando haya terminado, debería ver que han tenido lugar las siguientes acciones:

- Se actualizó un envío existente (el envío que se creó cuando el conjunto de pedidos 2 se despachó al almacén). Se ha agregado una línea que tiene el artículo *Inflamable*.
- Se ha creado un nuevo envío que contiene el artículo *Explosivo*.

### <a name="release-sales-orders-from-order-set-4"></a>Despachar pedidos de ventas del conjunto de pedidos 4

Siga el [procedimiento básico de despacho al almacén](#release-procedure) para despachar los pedidos de ventas del conjunto de pedidos 4.

Cuando haya terminado, debería ver cómo ese envío existente (donde el campo **Solicitud del cliente** está establecido en *1*) se ha actualizado. Se le ha agregado una nueva línea.

### <a name="release-sales-orders-from-order-set-5"></a>Despachar pedidos de ventas del conjunto de pedidos 5

Siga el [procedimiento básico de despacho al almacén](#release-procedure) para despachar los pedidos de ventas del conjunto de pedidos 5.

Cuando haya terminado, debería ver que han tenido lugar las siguientes acciones:

- Se ha actualizado un envío existente (donde el campo **Solicitud del cliente** está establecido n *1*). Se ha agregado una línea del pedido de ventas 5-3 (donde el campo **Solicitud del cliente** está establecido en *1*).
- Se ha creado un nuevo envío, donde las líneas de los pedidos de ventas 5-1 y 5-2 se agrupan en un único envío.

### <a name="release-sales-orders-from-order-set-6"></a>Despachar pedidos de ventas del conjunto de pedidos 6

Siga el [procedimiento básico de despacho al almacén](#release-procedure) para despachar los pedidos de ventas del conjunto de pedidos 6.

Cuando haya terminado, debería ver que se han creado cuatro envíos:

- Las líneas de dos pedidos del cliente *US-003* se han agrupado en un envío, utilizando la directiva de consolidación de envíos *Grupo de pedidos*.
- Las líneas de dos pedidos del cliente *US-004* se han agrupado en un envío, utilizando la directiva de consolidación de envíos *Grupo de pedidos*.
- Las líneas de pedido de ventas 6-5 y 6-6 para clientes *US-007* se han agrupado en un envío, utilizando la directiva de consolidación de envíos *Grupo de pedidos*.
- Las líneas de pedido de ventas 6-7 y 6-8 para clientes *US-007* se han agrupado en un envío, utilizando la directiva de consolidación de envíos *CrossOrder*.

## <a name="additional-resources"></a>Recursos adicionales

- [Directivas de consolidación de envíos](about-shipment-consolidation-policies.md)
- [Configurar directivas de consolidación de envíos](configure-shipment-consolidation-policies.md)
