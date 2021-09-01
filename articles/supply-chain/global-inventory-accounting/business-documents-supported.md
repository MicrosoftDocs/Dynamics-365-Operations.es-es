---
title: Documentos comerciales respaldados por la contabilidad de inventario global
description: Este tema enumera los documentos comerciales que son compatibles con la Contabilidad de inventario global. También proporciona un ejemplo detallado de documentos de órdenes de compra.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: cdb2d119e9b49887bb66fa737f97c3d91e5b793ceea1b2389072a02b5c463ba9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6726881"
---
# <a name="business-documents-supported-by-global-inventory-accounting"></a>Documentos comerciales respaldados por la contabilidad de inventario global

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Una vez que el complemento Contabilidad de inventario global está completamente configurado, está listo para procesar documentos relacionados con el inventario que se ingresan en Microsoft Dynamics 365 Supply Chain Management.

## <a name="supported-business-documents"></a>Documentos empresariales admitidos

Existen dos tipos de documentos empresariales:

- **Documentos que tienen un diario** - Estos documentos incluyen el recibo del producto, la factura de compra, el albarán y los documentos de la factura de venta.
- **Documentos que no tienen diario** - Estos documentos incluyen documentos de recuento, movimiento y ajuste de inventario.

Más adelante en este tema, las órdenes de compra se utilizarán como ejemplo para ilustrar el proceso.

La siguiente tabla enumera los documentos que admite la versión actual.

| Tipo de documento      | Documento        |
|--------------------|-----------------|
| Pedido de compra     | Recepción de producto |
| Pedido de compra     | Factura         |
| Pedido de ventas        | Traslado    |
| Pedido de ventas        | Factura         |
| Diarios de inventario | Movimiento        |
| Diarios de inventario | Ajuste      |
| Diarios de inventario | Recuento        |
| Diarios de inventario | Transferir        |
| Pedido de transferencia     | Envío        |
| Pedido de transferencia     | Recibir         |

> [!IMPORTANT]
> La Contabilidad de inventario global procesa de forma asincrónica los documentos que se ingresan en Supply Chain Management. No se mostrarán mensajes de error para documentos problemáticos.

## <a name="example-purchase-order"></a>Ejemplo: pedido de compra

### <a name="product-receipt"></a>Recepción de producto

Publique los recibos de productos de la forma habitual. En la página **Todas las órdenes de compra**, seleccione una orden de compra y, a continuación, en el Panel de acciones, en la pestaña **Recibir**, seleccione **Recibo de producto** para abrir la página **Diario de recepción de productos**. Se generan un evento de operación y un evento de Contabilidad global de invntroy para cada línea. Por lo tanto, seleccione la pestaña **Líneas** y luego seleccione **Inventario \> Eventos y mediciones** para abrir la página **Eventos y mediciones**.

La Contabilidad de Inventario Global es un sistema de contabilidad que se basa en eventos y mediciones. La cuadrícula de la línea de medición en la página **Eventos y mediciones** muestra una lista de medidas. Cada medida tiene una lista de dimensiones.

Para cada evento de operación, hay dos tipos de medición:

- **Medidas de operaciones** - Estas medidas describen documentos comerciales en términos genéricos. Una medida es la cantidad de producto utilizando la unidad de medida que se utiliza en el documento. También hay medidas que afectan el valor del inventario, como el precio extendido, el descuento, el porcentaje de descuento y el cargo por línea.
- **Medidas de contabilidad de recursos** - Estas medidas son desde la perspectiva del registro de inventario. Describen el impacto del documento en el inventario en la unidad de medida del inventario. Si hay varios registros de inventario, hay varias líneas de mediciones de contabilidad de recursos.

Las dimensiones se organizan de la siguiente manera:

- **Dualidad** - La dualidad describe a los agentes que participan en los eventos económicos. Para los documentos comerciales externos, las dimensiones primarias describen la entidad legal donde se ingresa el documento, mientras que las dimensiones duales describen el proveedor, el cliente, etc. Para los documentos comerciales internos (por ejemplo, órdenes de transporte), las dimensiones dobles describen el almacén de contraparte.
- **Tipo de dimensión** - Los tipos de dimensión categorizan las dimensiones.
- **Dimensiónn** – El nombre de la dimensión financiera.
- **Valor de dimensión** – El valor de la dimensión.

### <a name="global-inventory-accounting-event"></a>Evento de contabilidad de inventario global

La Contabilidad de Inventario Global toma los eventos operativos y las mediciones como entrada. Luego, realiza la contabilidad adecuada para cada libro mayor relacionado, según la moneda y la convención adjuntas. Puede elegir **Eventos y mediciones de contabilidad de inventario global** para ver el evento Contabilidad de inventario global. El evento de Contabilidad de Inventario Global sigue la misma metodología que los eventos de operación, pero utiliza diferentes medidas. Hay tres tipos principales de medición: cantidad de costo del producto, costo del producto y variación.

Las cuentas del libro mayor auxiliar se utilizan para clasificar mejor las mediciones. Puede haber varios libros de contabilidad. Estos libros mayores están vinculados a la entidad jurídica donde se ingresa el documento. Puede ver los eventos y las medidas de cada libro mayor cambiando el valor del campo **Libro mayor**.

### <a name="cost-element"></a>Elemento de coste

Según la política de elementos de costo que se adjunta al libro mayor, el sistema asigna un elemento de costo a cada medición de evento de operación contabilizada que afecta el costo de inventario. Estas medidas incluyen precio extendido, descuento, porcentaje de descuento y cargo de línea.

### <a name="measurement-line-details"></a>Detalles de línea de medida

La pestaña **Descripción general** muestra los detalles de las políticas adjuntas. Las dimensiones del objeto de coste muestran el objeto de coste, según la política de objetos de coste. Las dimensiones de identificación específicas muestran el número de lote si el supuesto de flujo de costos es *Específico - Lote*.

### <a name="purchase-invoice"></a>Factura de compra

Publique la factura de la forma habitual. Luego, en el Panel de acciones, en la pestaña **Factura**, en el grupo **Diarios**, seleccione **Factura** para abrir el diario de facturas. Se generan un evento de operación y un evento de Contabilidad global de invntroy para cada línea. Por lo tanto, seleccione la pestaña **Líneas** y luego seleccione **Inventario \> Eventos y mediciones** para abrir la página **Eventos y mediciones**. La página **Eventos y mediciones** muestra el mismo tipo de medida. Sin embargo, debido a que la página muestra una función de medida y un modificador de medida diferentes, el impacto en el agente (entidad jurídica) es diferente.

Seleccione **Eventos y mediciones de contabilidad de inventario global** para ver el evento Contabilidad de inventario global. La cantidad de inventario y el costo ahora fluyen desde cuenta del libro mayor auxiliar *Bienes recibidos inventario no facturado* y en la cuenta del libro mayor auxiliar *Costo de los bienes adquiridos*.
