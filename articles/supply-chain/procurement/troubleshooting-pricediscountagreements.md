---
title: Solucionar problemas de precios, descuentos, acuerdos y devoluciones
description: En este tema se describe cómo solucionar problemas que pueden surgir al trabajar con precios, descuentos, acuerdos y devoluciones.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 14fdddabde7739cbf9ba0fcee0fa0b8b816e74dd
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007375"
---
# <a name="troubleshoot-prices-discounts-agreements-and-rebates"></a>Solucionar problemas de precios, descuentos, acuerdos y devoluciones

En este tema se describe cómo solucionar problemas que pueden surgir al trabajar con precios, descuentos, acuerdos y devoluciones.

## <a name="i-cant-link-a-purchase-agreement-to-a-purchase-order-line-after-the-purchase-order-is-created"></a>No puedo vincular un acuerdo de compra a una línea de pedido de compra después de que se haya creado el pedido de compra.

Un acuerdo de compra debe asociarse a un pedido de compra cuando se crea el pedido de compra. De lo contrario, las líneas del pedido de compra no se pueden asociar a las líneas del acuerdo de compra.

## <a name="what-check-triggers-the-update-prices-and-discounts-entered-manually-or-external-document-message"></a>¿Qué comprobación genera el mensaje "Actualizar precios y descuentos introducidos manualmente o documento externo"?

Al cambiar la fecha de envío, es posible que reciba el mensaje "Actualizar precios y descuentos introducidos manualmente o documento externo". Recibe este mensaje porque, si la fecha de envío cambia, es posible que se active un acuerdo comercial o de venta diferente y esto provoque un cambio de precio. Un cambio en la fecha de envío también puede afectar a la programación del almacén y a otra información relacionada.

El mensaje se genera cada vez que se cambia alguna de las fechas u otros parámetros. El propósito del mensaje es asegurarse de que esté al tanto de los cambios de precios que pueden ocurrir a causa de esos cambios.

El mensaje es el aviso de evaluación del acuerdo comercial (TAE). Para obtener una descripción completa, consulte [Políticas de evaluación de acuerdos comerciales](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper).

## <a name="a-purchase-order-receipt-doesnt-include-all-charges"></a>El recibo de un pedido de compra no incluye todos los cargos.

### <a name="reproduce-the-issue"></a>Reproducir el problema

El siguiente procedimiento muestra una manera de reproducir el problema.

1. En la página **Parámetros de adquisición y abastecimiento**, en la pestaña **Entrega**, asegúrese de que la opción **Generar cargos al recibir el producto** está establecida en *Sí*.
1. Cree un pedido de compra que incluya cargos.
1. Confirme el pedido de compra.
1. Reciba el pedido de compra.
1. Vea el total de recepción y compárelo con el total esperado.
1. Observe que no todos los cargos están incluidos en la recepción del pedido de compra.

### <a name="issue-resolution"></a>Solución del problema

La resolución depende de la forma en que se hayan configurado los distintos cargos. Para obtener información sobre cómo configurar diversos cargos para cumplir con los requisitos, consulte la siguiente publicación de blog: [Contabilizar cargos varios en la recepción del producto](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).

## <a name="trade-agreement-prices-and-discounts-arent-applied-on-sales-or-purchase-order-lines-that-are-imported-through-data-management"></a>Los precios y descuentos de acuerdos comerciales no se aplican a las líneas de pedidos de ventas o de compra que se importan a través de la administración de datos.

### <a name="issue-description"></a>Descripción del problema

Los acuerdos comerciales que son aplicables a las líneas de pedidos de ventas o de compra no se aplican a líneas que se importan a través de la administración de datos. Sin embargo, los mismos acuerdos comerciales se aplican a las líneas de pedido de compra o de venta que se crean manualmente.

### <a name="reason-for-the-issue"></a>Motivo del problema

Si las líneas del pedido de compra que se importan a través de la administración de datos ya incluyen información de precios, el acuerdo comercial no se volverá a evaluar para esas líneas. Por ejemplo, si **Porcentaje de descuento de línea** o cualquiera de los valores de precio y descuento se establecen para una línea, los acuerdos comerciales no se buscarán para esa línea.

### <a name="issue-workaround"></a>Solución del problema

Se espera este comportamiento y es similar tanto para los pedidos de ventas como para los pedidos de compra.

Como solución temporal, importe las líneas del pedido de compra sin establecer ninguna información de precio. A continuación se aplicarán los acuerdos comerciales y las líneas de pedido de compra se actualizarán en función de los acuerdos comerciales definidos.

## <a name="a-vendor-rebate-isnt-cumulated-based-on-invoices"></a>Una devolución de proveedor no se acumula según las facturas.

### <a name="issue-description"></a>Descripción del problema

Si las facturas que se registran tienen diferentes fechas de vencimiento, esas facturas no se reflejan en las devoluciones de proveedores que se generan a partir de ellas.

### <a name="issue-resolution"></a>Solución del problema

Porque se ha diseñado así, no se tiene en cuenta la fecha de vencimiento al calcular el reembolso del proveedor. Considere la posibilidad de personalizar el sistema para que la fecha de vencimiento y la relación con la factura sean más evidentes con respecto al reembolso real del proveedor.

## <a name="unit-prices-on-purchase-orders-arent-calculated-based-on-the-unit-conversion"></a>Los precios unitarios de los pedidos de compra no se calculan en función de la conversión de unidades.

### <a name="issue-description"></a>Descripción del problema

Cuando se cambia una unidad en un pedido de compra, los precios de los acuerdos comerciales no se vuelven a calcular de acuerdo con las definiciones de conversión de unidades.

### <a name="issue-resolution"></a>Solución del problema

Los precios siempre se obtienen de acuerdos comerciales (u otras configuraciones de precios en el sistema, como acuerdos de venta o precios de artículos) y se establecen para una unidad.

Si se cambia la unidad en una línea de pedido, el sistema busca un precio para la nueva unidad y aplica ese precio. Si no se encuentra un precio para la unidad, el sistema no aplica un precio. La conversión de unidades no se puede utilizar para volver a calcular el precio en otra unidad. En teoría, el precio de una caja de diez podría no ser igual a diez veces el precio de una caja.

### <a name="issue-workaround"></a>Solución del problema

Una forma de solucionar este problema es asegurarse de que existen acuerdos comerciales para las unidades que espera que se utilicen en las líneas de pedido de artículo.

## <a name="currency-conversion-issues-occur-with-trade-agreements"></a>En los acuerdos comerciales se producen problemas de conversión de divisa.

Los precios de los acuerdos comerciales no se vuelven a calcular según la divisa cuando esta difiere en un pedido de compra.

La característica *Divisa genérica* permite definir precios y descuentos en una sola divisa. A continuación, puede convertir a otras divisas que necesite. Además, una vez realizada la conversión, la función puede aplicar automáticamente el redondeo psicológico.

## <a name="when-i-open-the-purchase-agreement-page-in-a-line-view-mode-i-cant-personalize-the-page-by-adding-the-price-unit-field-in-the-overview-of-the-line"></a>Cuando abro la página Acuerdo de compra en un modo de vista de línea, no puedo personalizar la página agregando el campo Unidad de precio en la descripción general de la línea.

Algunos campos compartidos en el marco del acuerdo no se pueden incluir en las personalizaciones. Esta limitación se produce debido al modelo de datos implementado. Por lo tanto, no puede personalizar el campo **Precio unitario**.

## <a name="the-maximum-limit-from-a-purchase-agreement-isnt-effective-on-a-purchase-requisition"></a>El límite máximo de un acuerdo de compra no es efectivo en una solicitud de compra.

### <a name="issue-description"></a>Descripción del problema

Cuando una solicitud de compra está vinculada a un acuerdo de compra, el límite máximo del acuerdo de compra no es efectivo en la solicitud de compra. La información de precio predeterminada se especificó correctamente, pero en la solicitud de compra se puede pedir más del límite máximo del acuerdo de compra.

### <a name="issue-resolution"></a>Solución del problema

Este comportamiento es esperado. Debido a que las solicitudes no siempre se aprueban, no se debe reservar una cantidad o un importe en el acuerdo de compra. Por lo tanto, no se alcanzará el límite máximo del acuerdo de compra.

## <a name="trade-agreements-can-be-created-from-rejected-rfqs-therefore-the-system-doesnt-prevent-trade-agreement-journals-from-being-created-if-the-rfq-line-hasnt-been-accepted"></a>Se pueden crear acuerdos comerciales a partir de solicitudes de presupuesto rechazadas. Por lo tanto, el sistema no impide que se creen diarios de acuerdos comerciales si no se ha aceptado la línea de solicitud de presupuesto.

Puede crear acuerdos comerciales para cualquier respuesta a una solicitud de presupuesto (RFQ), independientemente de si se aceptaron o rechazaron. Para obtener más información, consulte [Información general sobre solicitudes de presupuesto (RFQ)](request-quotations.md).

