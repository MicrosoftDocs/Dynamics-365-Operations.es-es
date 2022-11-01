---
title: Calcule las fechas de entrega de pedidos de ventas usando CTP
description: La funcionalidad capaz de prometer (CTP) le permite dar a los clientes fechas realistas para cuando puede prometer productos específicos. Este artículo describe cómo configurar y utilizar CTP para cada motor de planificación (Planning Optimization y el motor integrado).
author: t-benebo
ms.date: 07/20/2022
ms.topic: article
ms.search.form: SalesAvailableDlvDates, SalesTable, CustParameters, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-07-20
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 3b8e3dc9f0e7aaf019aa4d7284458206e7daadb2
ms.sourcegitcommit: 86c0562ce1ecdf7937125c0f5a6771f178b459e7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2022
ms.locfileid: "9714870"
---
# <a name="calculate-sales-order-delivery-dates-using-ctp"></a>Calcule las fechas de entrega de pedidos de ventas usando CTP

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

La funcionalidad capaz de prometer (CTP) le permite dar a los clientes fechas realistas para cuando puede prometer productos específicos. Para cada línea de ventas, puede proporcionar una fecha que tenga en cuenta el inventario disponible existente, la capacidad de producción y los tiempos de transporte.

CTP se extiende la funcionalidad de [neto no comprometido](../../sales-marketing/delivery-dates-available-promise-calculations.md) (ATP) teniendo en cuenta la información de capacidad. Mientras que ATP considera solo la disponibilidad de materiales y asume recursos de capacidad infinita, CTP considera la disponibilidad tanto de materiales como de capacidad. Por lo tanto, proporciona una imagen más realista de si la demanda se puede satisfacer dentro de un marco de tiempo determinado.

La página Requisitos netos se comporta de forma ligeramente diferente en función de si está utilizando Optimización de planificación o el motor de planificación maestra integrado. Este artículo describe cómo configurarlo para cada motor. Actualmente, CTP para la optimización de la planificación solo admite un subconjunto de los escenarios de CTP que son compatibles con el motor integrado.

## <a name="turn-on-ctp-for-planning-optimization"></a>Active CTP para Optimización de planificación

CTP para el motor de planificación maestro integrado siempre está disponible. Sin embargo, si desea utilizar CTP para la optimización de la planificación, debe activarlo para su sistema. Los administradores pueden usar la configuración de [administración de características](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla. En el espacio de trabajo **Administración de características**, la función aparece de la siguiente forma:

- **Módulo:** *Planificación maestra*
- **Nombre de la característica:** *(Versión preliminar) CTP para optimización de planificación*

## <a name="how-ctp-compares-to-atp"></a>Cómo se compara CTP con ATP

CTP y ATP son similares, pero CTP a menudo puede proporcionar un resultado más preciso, como muestra el siguiente ejemplo.

El artículo A es un artículo que se compone de los artículos B y C, y la cantidad disponible del artículo A es 0 (cero). Si realiza una verificación de ATP que considera solo materiales, la cantidad de ATP también será 0 (cero). Sin embargo, si realiza una verificación de CTP, el sistema verificará la disponibilidad de los artículos B y C, verificará los recursos necesarios para convertirlos en el artículo A y calculará cuántos del artículo A se pueden fabricar. Además, el cálculo de CTP puede verificar los recursos y materiales que se requieren para hacer más artículos B y C, y usarlos para hacer más artículos A.

Un cálculo de CTP que considera tanto los materiales como los recursos puede mostrar una cantidad mayor que un cálculo que verifica solo los materiales, especialmente cuando el artículo que se verifica es un artículo ensamblado a pedido. En otras palabras, la funcionalidad CTP se basa en la función de explosión y se puede ejecutar para una línea de orden de venta seleccionada para calcular la fecha de entrega prevista.

## <a name="how-ctp-differs-depending-on-the-master-planning-engine-that-you-use"></a>Cómo difiere CTP según el motor de planificación maestra que utilice

La siguiente tabla resume las diferencias entre CTP para la optimización de la planificación y CTP para el motor de planificación maestro incorporado.

| Elemento | Optimización de planificación | Motor de planificación maestro incorporado |
|---|---|---|
| **Control de fecha de entrega** configuración para pedidos, líneas de pedido y productos | *CTP para Optimización de planificación* | *CTP* |
| Hora de cálculo | El cálculo se activa al ejecutar un plan dinámico como una tarea programada. | El cálculo se activa inmediatamente cada vez que ingresa o actualiza una línea de orden de venta. |
| Valor del campo **Estado de CTP para Optimización de planificación** | <p>Un valor de *No está listo* se muestra para pedidos y líneas de pedidos en los que el plan dinámico no se ha ejecutado desde que se crearon o actualizaron por última vez los pedidos y las líneas.</p><p>Un valor de *Listo* se muestra para pedidos y líneas donde se ha utilizado CTP para calcular fechas de entrega confirmadas mediante la ejecución del plan dinámico.</p> | Un valor de *Listo* siempre se muestra. |

## <a name="set-default-delivery-date-control-methods"></a><a name="default-methods"></a>Establecer métodos de control de fecha de entrega predeterminados

El sistema puede utilizar cualquiera de varios métodos para calcular estimaciones de fecha de entrega para cada pedido y línea de pedido. Debe establecer el método de control de fecha de entrega que desee utilizar con más frecuencia como método predeterminado global. También puede establecer anulaciones individuales para cada producto. Más tarde, podrá anular los métodos predeterminados para cada orden y/o línea de orden según lo requiera.

### <a name="set-the-global-default-delivery-date-control"></a><a name="global-default"></a>Establezca el control de fecha de entrega predeterminado global

El método de control de fecha de entrega predeterminado se aplicará a todas las líneas de pedido nuevas en las que no se aplique una anulación. Para seleccionar uno, siga estos pasos:

1. Vaya a **Clientes \> Configuración \> Parámetros de clientes**.
1. En la pestaña **Envíos**, en la ficha **Control de entrega**, en el campo **Control de fecha de entrega**, seleccione el método que desea utilizar como método predeterminado para su empresa:

    - *Ninguno*: Calcular las fechas de entrega.
    - *Plazo de ventas*: el plazo de ventas es el tiempo entre la creación del pedido de ventas y el envío de los artículos. El cálculo de la fecha de entrega se basa en un número predeterminado de días y no considera la disponibilidad de existencias, la demanda conocida o el suministro planificado.
    - *ATP*: ATP es la cantidad de un artículo que esté disponible y se pueda prometer a un cliente en una fecha específica. El cálculo del NNC incluye inventario no comprometido, fechas disponibles, recepciones planificadas y emisiones.
    - *ATP + Días de emisión*: la fecha de envío es igual que la fecha de neto no comprometido (NNC) más el margen de emisión del artículo. El margen de emisión es el tiempo que necesario para preparar los artículos para el envío.
    - *CTP* – Utilice el cálculo de CTP proporcionado por el motor de planificación maestro integrado. Si utiliza la Optimización de la planificación, el método de control de fecha de entrega *CTP* no está permitido y, si se selecciona, provocará un error cuando se ejecute el cálculo.
    - *CTP para la optimización de la planificación* – Utilice el cálculo de CTP proporcionado por Planning Optimization. Esta opción no tiene efecto si está utilizando el motor de planificación maestra integrado, se admiten los productos controlados por lotes.

### <a name="set-delivery-date-control-overrides-for-individual-products"></a>Establecer anulaciones de control de fecha de entrega para productos individuales

Puede asignar anulaciones para productos específicos en los que desee utilizar un método de control de fecha de entrega diferente al que está establecido como su método predeterminado global.

1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. Seleccione el producto que desea configurar.
1. En el panel de acciones, en la pestaña **Administrar inventario**, en el grupo **Configuración de pedido**, seleccione **Configuración de pedido predeterminada**.
1. En la página **Configuración de pedido predeterminada**, en la ficha **Órdenes de venta**, establezca la opción **Anular el control de entrega** en *Sí*.
1. En el campo **Control de fecha de entrega**, seleccione el método a utilizar para el producto seleccionado. Las mismas opciones que se describen en la sección [Establecer el control de fecha de entrega predeterminado global](#global-default) están disponibles.

## <a name="schedule-ctp-for-planning-optimization-calculations"></a><a name="batch-job"></a>Programar CTP para cálculos de optimización de planificación

Cuando utiliza CTP para la optimización de la planificación, debe ejecutar un plan dinámico para activar el sistema para realizar los cálculos de CTP y luego establecer las fechas confirmadas de envío y recepción para todos los pedidos relevantes. El plan debe incluir todos los artículos para los que se requieren fechas confirmadas de envío y recepción. (Cuando usa CTP para el motor de planificación integrado, los cálculos de CTP se realizan inmediatamente de forma local. Por lo tanto, no tiene que ejecutar un plan dinámico para ver los resultados de CTP).

Para asegurarse de que las fechas estén disponibles a tiempo para todos los usuarios, le recomendamos que configure trabajos por lotes para ejecutar los planes relevantes de forma recurrente. Por ejemplo, un trabajo por lotes configurado para ejecutar un plan dinámico cada 30 minutos establecerá las fechas de envío y recepción confirmadas cada 30 minutos. Por lo tanto, los usuarios que ingresen e importen pedidos tendrán que esperar un máximo de 30 minutos para obtener el envío confirmado y las fechas de recepción.

Para configurar un trabajo por lotes para ejecutar un plan dinámico en un horario regular, siga estos pasos.

1. Vaya a **Planificación maestra \> Planificación maestra \> Ejecutar \> Planificación maestra**.
1. En el cuadro de diálogo **Planificacion maestra**, en la ficha **Parámetros**, establecer el campo **Plan Maestro** en el plan dinámico que desea ejecutar.
1. En la ficha **Ejecutar en segundo plano**, establezca la opción **Procesamiento por lotes** en *Sí*.
1. Seleccione **Reaparición** y configure la programación según sea necesario.
1. Seleccione **Aceptar** para guardar el programa.
1. Seleccione **Aceptar** para crear el trabajo por lotes y cerrar el cuadro de diálogo.

## <a name="use-ctp-for-built-in-master-planning"></a>Usar CTP para la planificación maestra incorporada

### <a name="create-a-new-order-by-using-ctp-for-built-in-master-planning"></a>Cree un nuevo pedido utilizando CTP para la planificación maestra integrada

Cada vez que agrega una nueva orden de venta o línea de orden, el sistema le asigna un método de control de fecha de entrega predeterminado. El encabezado del pedido siempre comienza con el método predeterminado global. Si se asigna una anulación a un artículo pedido, la nueva línea de pedido utilizará esa anulación. De lo contrario, la nueva línea de pedido también utilizará el método predeterminado global. Por tanto, debería establecer los métodos preteterminados para que coincidan con el método de control de fechas de enrega que más usa. Después de crear un pedido, puede anular el método predeterminado en el encabezado del pedido y/o nivel de línea del pedido según lo requiera. Para más información, vea [Establecer métodos de control de fecha de entrega predeterminados](#default-methods) y [Cambiar los pedidos de venta existentes para usar CTP](#change-orders).

### <a name="view-confirmed-delivery-dates-when-you-use-ctp-for-built-in-master-planning"></a>Ver fechas de entrega confirmadas cuando usa CTP para la planificación maestra integrada

Si está utilizando el motor de planificación maestra incorporado, los cálculos de CTP se aplican a los pedidos y/o líneas de pedido donde el campo **Control de fecha de entrega** se establece en *CTP*.

Para las líneas de ventas que utilizan CTP para la planificación maestra integrada, el sistema establece automáticamente los campos **Fecha de envío confirmada** y **Fecha de recepción confirmada** cada vez que guarde una línea de ventas. Si luego realiza un cambio relevante en una línea de ventas (por ejemplo, cambiando su cantidad o sitio), las fechas se recalcularán inmediatamente.

- Para ver las fechas de entrega confirmadas para una línea de orden de venta, abra la orden de venta y seleccione la línea de venta. Luego, en la ficha desplegable **Detalles de línea**, en la pestaña **Entrega**, revise los valores de **Fecha de entrega confirmada** y **Fecha de recepción confirmada**.
- Para ver las fechas de entrega confirmadas para una orden entera, abra la orden de venta y seleccione la vista **Encabezado**. Luego, en la ficha desplegable **Entrega**, revise los valores de **Fecha de entrega confirmada** y **Fecha de recepción confirmada**.

## <a name="use-ctp-for-planning-optimization"></a>Usar CTP para Optimización de planificación

### <a name="create-a-new-order-by-using-ctp-for-planning-optimization"></a>Cree un nuevo pedido utilizando CTP para la optimización de planificación

Cada vez que agrega una nueva orden de venta o línea de orden, el sistema le asigna un método de control de fecha de entrega predeterminado. El encabezado del pedido siempre comienza con el método predeterminado global. Si se asigna una anulación a un artículo pedido, la nueva línea de pedido utilizará esa anulación. De lo contrario, la nueva línea de pedido también utilizará el método predeterminado global. Por tanto, debería establecer los métodos preteterminados para que coincidan con el método de control de fechas de enrega que más usa. Después de crear un pedido, puede anular el método predeterminado en el encabezado del pedido y/o nivel de línea del pedido según lo requiera. Para más información, vea [Establecer métodos de control de fecha de entrega predeterminados](#default-methods) y [Cambiar los pedidos de venta existentes para usar CTP](#change-orders).

### <a name="view-confirmed-delivery-dates-when-using-ctp-for-planning-optimization"></a>Ver fechas de entrega confirmadas al usar CTP para la optimización de la planificación

Si está utilizando Optimización de planificación, los cálculos de CTP se aplican a los pedidos y/o líneas de pedido donde el campo **Control de fecha de entrega** se establece en *CTP para Optimización de planificación*.

Para las líneas de ventas que usan CTP para la optimización de la planificación, los campos **Fecha de envío confirmada** y **Fecha de recepción confirmada** estarán en blanco hasta que ejecute el plan dinámico adecuado (normalmente mediante el uso de un trabajo por lotes periódico). A continuación, se configuran automáticamente. Para obtener más información, consulte [Programar CTP para cálculos de optimización de planificación](#batch-job).

El campo **CTP para el estado de optimización de la planificación** indica si las fechas confirmadas ya se calcularon para cada línea que usa CTP para la optimización de la planificación. El campo muestra un valor de *No está listo* para líneas y pedidos donde las fechas de entrega confirmadas aún no se han calculado o ya no son válidas debido a otros cambios. Muestra un valor de *Listo* para líneas y órdenes que han sido calculadas. Puede ver el estado de cada línea y de todo el pedido.

- Para ver el estado de una línea de orden de venta, abra la orden de venta y seleccione la línea de venta. Entonces, en la ficha **Detalles de línea**, en la pestaña **Entrega**, revise el valor **CTP para el estado de optimización de la planificación**. Los campos **Fecha de envío confirmada** y **Fecha de recepción confirmada** de la línea también se muestran en esta pestaña después de que se hayan calculado.
- Para ver el estado de una orden entera, abra la orden de venta y seleccione la vista **Encabezado**. Entonces, en la ficha **Entrega**, revise el valor **CTP para el estado de optimización de la planificación**. Los campos **Fecha de envío confirmada** y **Fecha de recepción confirmada** de la orden también se muestran en esta pestaña después de que se hayan calculado.

<!-- KFM: The following text may be untrue and needs to be reviewed with the PM for next revision:

The sales orders that are *Ready* or *Not ready* are shown in the **All sales orders** list page. You can check the sales order that are *Ready* or *Not ready* from the sales order list page by filtering on this new status field.

-->

> [!NOTE]
> - Si actualiza una línea de orden de venta después de que CTP for Planning Optimization haya calculado las fechas confirmadas para ella, el sistema borrará esas fechas hasta la próxima vez que se ejecute el plan dinámico adecuado.
> - Si edita una configuración relacionada que podría afectar las fechas confirmadas existentes (por ejemplo, al cambiar los plazos de entrega, las reservas o las marcas), debe borrar las fechas confirmadas de los pedidos existentes relevantes. Esta acción hará que el estado de cada línea relevante cambie a *No está listo*. Este cambio, a su vez, hará que el sistema vuelva a calcular las fechas confirmadas la próxima vez que ejecute el plan dinámico.

## <a name="change-existing-sales-orders-so-that-they-use-ctp"></a><a name="change-orders"></a>Cambiar los pedidos de venta existentes para que utilicen CTP

Puede cambiar el valor **Control de fecha de entrega** para cualquier orden abierta en cualquier momento. Puede cambiar el valor en el nivel de encabezado y/o para cada línea según lo requiera.

### <a name="change-to-ctp-at-the-order-header-level"></a>Cambiar a CTP en el nivel de encabezado de pedido

<!-- KFM: Would be nice to mention how changing this setting on the header affects the individual lines. -->

Para cambiar un pedido para que use CTP en el nivel de encabezado del pedido, siga estos pasos.

1. Vaya a **Clientes \> Pedidos \> Todos los pedidos de venta**.
1. Abra la orden de venta que desea configurar o cree una nueva.
1. Seleccione **Encabezado** para abrir la información de encabezado de la página **Detalles de orden de venta**.
1. En la ficha **Entrega**, establezca el campo **Control de fecha de entrega** en uno de los siguientes valores, según el motor de planificación que esté utilizando:

    - *CTP* – Utilice el cálculo de CTP proporcionado por el motor de planificación maestro integrado. Si está utilizando la optimización de la planificación, el el método de control de fecha de entrega *CTP* no está permitido. Por lo tanto, si selecciona este valor, se producirá un error cuando se ejecute el cálculo.
    - *CTP para la optimización de la planificación* – Utilice el cálculo de CTP proporcionado por Planning Optimization. Esta configuración no tiene efecto si está utilizando el motor de planificación maestra integrado, se admiten los productos controlados por lotes.

<!-- KFM: Additional dialogs are shown here. Review these with the PM and expand this procedure at next revision. -->
1. Seleccione **OK** para aplicar sus cambios.

### <a name="change-to-ctp-at-the-order-line-level"></a>Cambiar a CTP en el nivel de línea de pedido

Si creó una línea de pedido utilizando un método de control de fecha de entrega diferente, puede cambiar a CTP en cualquier momento. Los cambios que realice en el nivel de línea no afectarán a ninguna otra línea. Sin embargo, pueden hacer que las fechas generales de entrega del pedido se adelanten o se retrasen, según cómo cambie cada cálculo de línea actualizado. <!-- KFM: Confirm this intro at next revision -->

Para cambiar un pedido para que use CTP para la planificación maestra integrada en el nivel de línea, siga estos pasos.

1. Vaya a **Clientes \> Pedidos \> Todos los pedidos de venta**.
1. Abra la orden de venta que desea configurar o cree una nueva.
1. Sobre la página **Detalles de la orden de venta**, en la ficha **Línea de orden de venta**, seleccione la línea de orden de venta que desea configurar.
1. En la ficha **Detalles de línea**, en la pestaña **Entrega**, establezca el campo **Control de fecha de entrega** en uno de los siguientes valores, según el motor de planificación que esté utilizando:

    - *CTP* – Utilice el cálculo de CTP proporcionado por el motor de planificación maestro integrado. Si está utilizando la optimización de la planificación, el el método de control de fecha de entrega *CTP* no está permitido. Por lo tanto, si selecciona este valor, se producirá un error cuando se ejecute el cálculo.
    - *CTP para la optimización de la planificación* – Utilice el cálculo de CTP proporcionado por Planning Optimization. Esta configuración no tiene efecto si está utilizando el motor de planificación maestra integrado, se admiten los productos controlados por lotes.

    Aparece el cuadro de diálogo **Fechas de envío y recepción disponibles** con las fechas de envío y recepción disponibles. Este cuadro de diálogo funciona de la misma manera para las líneas de pedido que para el encabezado del pedido, como se describe en la sección anterior.

1. En el panel Acciones, seleccione **Guardar**.
