---
title: Consultas sobre costos de destino
description: Este tema describe cómo encontrar y utilizar los distintos tipos de consultas que están disponibles para el módulo de costos de entrega.
author: sherry-zheng
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMLine, ITMItemTracking, ITMContainerActivityTracking, ITMContainerTracking
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-21
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 22a2e76780adb43b053b6cf7fd08411a4a60aeac
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823370"
---
# <a name="landed-cost-inquiries"></a>Consultas sobre costos de destino

[!include [banner](../../includes/banner.md)]

## <a name="voyage-line-inquiries"></a>Consultas sobre la línea de viaje

La consulta **Líneas de viaje** muestra todas las líneas de viaje en lo que respecta al inventario. Esta consulta se puede utilizar como filtro para ayudarlo a encontrar un artículo, una orden de compra u otra información útil. También se puede usar para identificar la fecha de entrega esperada de un artículo que podría estar en uno o más viajes. De esta manera, puede ayudarlo a administrar la recepción de inventario esperada.

Para abrir esta consulta, vaya a **Coste de aterrizaje \> Consultas \> Líneas de viaje**.

### <a name="overview-tab"></a>Pestaña Visión general

La pestaña **Visión general** de la página de consulta **Líneas de viaje** incluye una cuadrícula que muestra información básica sobre cada línea de viaje relevante. En la tabla siguiente se proporciona una descripción de las columnas de la cuadrícula.

| Columna | Descripción |
|---|---|
| **Número de artículo** | Artículo de la línea de viaje. |
| **Referencia** | El tipo de orden (orden de compra u orden de transferencia). |
| **Número** | El número de orden de compra u orden de transferencia. |
| **Folio** | El folio asociado a la línea de viaje. |
| **Contenedor de envío** | El contenedor de envío asociado con la línea de viaje. |
| **Viaje** | El viaje asociado a la línea de viaje. |
| **Cantidad** | La cantidad del artículo para la línea de viaje. |
| (Otras dimensiones) | Puede mostrar columnas para dimensiones adicionales según lo requiera. Esas dimensiones incluyen el número de lote, el estado del inventario y el almacén. En el panel de acciones, seleccione **Inventario \> Dimensiones de la pantalla** para abrir un cuadro de diálogo donde puede seleccionar las dimensiones a incluir. |

### <a name="general-tab"></a>Pestaña General

Seleccione la pestaña **General** para ver más información sobre la línea que está actualmente seleccionada en la pestaña **Visión general**.

### <a name="dimensions-tab"></a>Pestaña Dimensiones

Seleccione la pestaña **Dimensiones** para ver los valores de todas las dimensiones de inventario disponibles para la línea seleccionada en la pestaña **Descripción general**, independientemente de las dimensiones que haya elegido mostrar allí.

## <a name="cost-estimate-inquiries"></a>Consultas de estimación de costos

Cada vez que genera una estimación de costos, la estimación se agrega a la página de consulta **Coste estimado**. Para obtener detalles completos sobre cómo generar, ver y trabajar con estimaciones de costos (incluidas las estimaciones en la página de consulta), consulte [Estimar y administrar los costos de aterrizaje](estimate-manage-landed-costs.md).

## <a name="item-tracking"></a>Seguimiento de artículo

Utilice la página **Seguimiento de artículo** para ver las líneas de órdenes de compra abiertas y su estado actual. Las líneas no tienen que estar asociadas con un viaje para aparecer aquí. Sin embargo, si un artículo está asociado con un viaje, la línea de registro de seguimiento del artículo muestra el ID del viaje.

Para abrir esta página, vaya a **Coste de aterrizaje \> Consultas \> Seguimiento \> Seguimiento de artículo**.

Debido a que su sistema probablemente contiene una gran cantidad de líneas de orden de compra, la página **Seguimiento de artículo** inicialmente no muestra registros. Comience usando los campos de filtro en la parte superior de la página para definir el conjunto de líneas de orden de compra que está buscando. Luego seleccione **Actualizar** en el Panel de acciones para generar la lista. Puede utilizar un asterisco (\*) como carácter comodín en cualquiera de los campos de filtro. Por ejemplo, para buscar todas las líneas de pedido de compra de artículos que incluyen la palabra "DVD" en su nombre, establezca el campo **Tipo** en **Nombre del producto** y entre *\*DVD\** en el campo **Valor de campo**.

> [!NOTE]
> Actualmente, los pedidos pendientes incluyen solo pedidos de venta. Las cotizaciones de ventas no se muestran ni se consideran pedidos pendientes.

La siguiente tabla describe las columnas de la cuadrícula en la página **Seguimiento de artículo**.

| Columna | Descripción |
|---|---|
| **Puerto de destino** | El destino final. |
| **Confirmado** | Fecha confirmada de la línea del pedido de compra. |
| **Fecha de entrega** | Fecha de entrega de la línea del pedido de compra. |
| **Viaje** | Si la línea está asociada a un viaje, el id. de viaje. |
| **Contenedor de envío** | Si la línea está conectada a un contenedor de envío, el ID del contenedor. |
| **Puerto de envío** | El puerto actual, basado en el primer tramo en el formulario de seguimiento donde no se establece una fecha real para el contenedor de envío que está asociado con la línea de la orden de compra. |
| **Actividad** | La actividada actual, basado en el primer tramo en el formulario de seguimiento donde no se establece una fecha real para el contenedor de envío que está asociado con la línea de la orden de compra. |
| **Fecha final estimada** | La fecha en la que se espera recibir el viaje en el almacén de destino. |
| **Nombre** | Nombre del proveedor. |
| **Estado de viaje** | El estado de viaje asociado a la línea de la orden de compra. |
| **Número de artículo** | El número de artículo para la línea de pedido de compra. |
| **Externo** | Nombre de artículo del proveedor. |
| **Nombre de producto** | El nombre del artículo de la línea de orden de compra. |
| **Cantidad** | Cantidad de la línea de pedido de compra. |
| **Unidad** | Unidad de medida para la línea de pedido de compra. |
| **Referencia** | El tipo de orden (orden de compra u orden de transferencia) |
| **Número de referencia** | El número de orden de compra u orden de transferencia. |
| **Pedido pendiente** | Un símbolo indica que hay pedidos pendientes de venta del artículo. |
| (Otras dimensiones) | Puede mostrar columnas para dimensiones adicionales según lo requiera. Esas dimensiones incluyen el número de lote, el estado del inventario y el almacén. En el panel de acciones, seleccione **Dimensiones de la pantalla** para abrir un cuadro de diálogo donde puede seleccionar las dimensiones a incluir. |

### <a name="related-information-about-backorders"></a>Información relacionada sobre pedidos pendientes

Para ver más información sobre pedidos atrasados, seleccione la pestaña **Información relacionada** en el lado derecho de la página, y luego seleccione **Pedidos atrasados**. Para ver aún más información sobre un pedido pendiente específico, seleccione la fila correspondiente y luego seleccione el enlace **Más**.

## <a name="individual-shipping-container-tracking"></a>Seguimiento de contenedor de envío individual

La consulta **Seguimiento individual de contenedores de envío** proporciona un filtro que le permite encontrar un contenedor de envío y luego identificar todas las líneas de viaje en ese contenedor.

Para abrir esta consulta, vaya a **Coste de aterrizaje \> Consultas \> Seguimiento \> Seguimiento de contenedor de envío individual**.

## <a name="multiple-shipping-container-tracking"></a>Seguimiento de contenedor con varios envíos

La consulta **Seguimiento de contenedores de envío múltiples** proporciona un filtro que le permite encontrar un conjunto de contenedores de envío y luego identificar todas las líneas de viaje en esos contenedores.

Para abrir esta consulta, vaya a **Coste de aterrizaje \> Consultas \> Seguimiento \> Seguimiento de contenedores de envío múltiples**.
