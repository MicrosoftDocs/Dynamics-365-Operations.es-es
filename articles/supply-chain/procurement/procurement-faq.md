---
title: Preguntas frecuentes sobre adquisición
description: Este tema proporciona respuestas a las preguntas más frecuentes (FAQ) sobre la funcionalidad de compras de Supply Chain Management.
author: GalynaFedorova
ms.date: 05/31/2021
ms.topic: article
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 718108447dcb5cec488b7fa626feb551808e8dd8
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "8669359"
---
# <a name="procurement-faq"></a>Preguntas frecuentes sobre adquisición

[!include [banner](../includes/banner.md)]

Este tema proporciona respuestas a las preguntas más frecuentes (FAQ) sobre la funcionalidad de compras de Supply Chain Management.

## <a name="can-i-show-only-purchase-orders-that-i-created"></a>¿Puedo mostrar solo los pedidos de compra que he creado?

Esta funcionalidad no está disponible actualmente.

## <a name="can-i-reserve-inventory-and-create-transactions-against-registered-inventory-on-a-purchase-order"></a>¿Puedo reservar inventario y crear transacciones con el inventario registrado en un pedido de compra?

### <a name="issue-description"></a>Descripción del problema

Puede reservar el inventario incluso cuando los elementos están en un *Registrado* en un pedido de compra. En otras palabras, puede crear transacciones con el inventario registrado.

### <a name="reproduce-the-issue"></a>Reproducir el problema

El siguiente procedimiento muestra una manera de reproducir el problema.

1. Cree un pedido de compra.
2. Registre la línea de pedido de compra.
3. Tenga en cuenta que puede generar reservas o transacciones con el inventario registrado.

### <a name="issue-resolution"></a>Solución del problema

Este comportamiento se debe al diseño. La expectativa es que los artículos registrados hayan llegado físicamente al almacén o al inventario y, por lo tanto, estén disponibles para reserva.

## <a name="can-i-find-the-user-who-canceled-a-purchase-order"></a>¿Puedo encontrar al usuario que canceló un pedido de compra?

Esta información solo se sigue si el pedido de compra está sujeto a la administración de cambios. Si usa la administración de cambios, puede ver quién envió el cambio (la cancelación) y quién lo aprobó.

## <a name="why-cant-i-link-a-purchase-agreement-to-an-existing-purchase-order"></a>¿Por qué no puedo vincular un acuerdo de compra a una orden de compra existente?

Un acuerdo de compra debe asociarse a un pedido de compra cuando se crea el pedido de compra. De lo contrario, las líneas del pedido de compra no se pueden asociar a las líneas del acuerdo de compra.

## <a name="what-check-triggers-the-update-prices-and-discounts-entered-manually-or-external-document-message"></a>¿Qué comprobación genera el mensaje "Actualizar precios y descuentos introducidos manualmente o documento externo"?

Al cambiar la fecha de envío, es posible que reciba el mensaje "Actualizar precios y descuentos introducidos manualmente o documento externo". Recibe este mensaje porque, si la fecha de envío cambia, es posible que se active un acuerdo comercial o de venta diferente y esto provoque un cambio de precio. Un cambio en la fecha de envío también puede afectar a la programación del almacén y a otra información relacionada.

El mensaje se genera cada vez que se cambia alguna de las fechas u otros parámetros. El propósito del mensaje es asegurarse de que esté al tanto de los cambios de precios que pueden ocurrir a causa de esos cambios.

El mensaje es el aviso de evaluación del acuerdo comercial (TAE). Para obtener una descripción completa, consulte [Políticas de evaluación de acuerdos comerciales](/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper).

## <a name="why-cant-i-post-more-than-one-invoice-for-a-purchase-order-line-that-has-category-based-items"></a>¿Por qué no puedo registrar más de una factura para una línea de pedido de compra que tiene artículos basados en categorías?

Es obligatorio especificar una cantidad si desea contabilizar facturas. Por lo tanto, si la cantidad total de una línea se ha facturado solo por un importe parcial, no podrá facturar el importe restante en otra factura.
