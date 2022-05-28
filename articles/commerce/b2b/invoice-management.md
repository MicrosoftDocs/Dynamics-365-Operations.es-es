---
title: Administración de facturas para sitios web de comercio electrónico B2B
description: Este tema describe las capacidades de administración de facturas de los sitios web de comercio electrónico de empresa a empresa (B2B) de Microsoft Dynamics 365 Commerce.
author: shajain
ms.date: 02/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 60cb0c8aaede4a0eaeed80cf5ebe41068da57836
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686309"
---
# <a name="invoice-management-for-b2b-e-commerce-websites"></a>Administración de facturas para sitios web de comercio electrónico B2B

[!include [banner](../../includes/banner.md)]

Este tema describe las capacidades de administración de facturas de los sitios web de comercio electrónico de empresa a empresa (B2B) de Microsoft Dynamics 365 Commerce.

Es una práctica común que las empresas que manejan transacciones B2B acepten pedidos a crédito del cliente y luego envíen una factura a los clientes después de cumplir con el pedido. Los términos de pago están definidos para los clientes y puede haber algunos descuentos para motivar a los clientes a pagar a tiempo o antes de tiempo. Para ayudar a aumentar la probabilidad de que los pagos se reciban a tiempo, los sitios web de comercio electrónico B2B permiten a los clientes ver todas sus facturas. El cliente puede filtrar fácilmente las facturas para ver las facturas pagadas, no pagadas y parcialmente pagadas junto con las fechas de vencimiento.

![Página de facturas en un sitio web B2B.](../media/ViewInvoices.png)

> [!NOTE]
> Un usuario registrado puede ver y pagar solo sus propias facturas. Si una cuenta de organización está configurada en el menú desplegable **Cuenta de factura** en la ficha desplegable **Factura y entrega** del registro del cliente en la sede de Commerce, el usuario podrá ver y pagar las facturas de la cuenta de la organización.

En la página **Facturas** de un sitio web B2B, un usuario puede seleccionar una factura no pagada o parcialmente pagada y luego seleccionar **Factura de pago**. La factura seleccionada se agrega al carrito y el usuario puede proceder con el pago. El usuario puede entonces decidir si pagar el importe total de la factura o un importe parcial. El usuario no puede utilizar el método de pago de la cuenta del cliente para pagar facturas.

> [!NOTE]
> Las facturas se pueden agregar al carrito solo si no hay artículos actualmente en él. Por el contrario, los artículos se pueden agregar al carrito solo si no hay facturas actualmente en él. Microsoft planea eliminar esta restricción en futuras versiones de Commerce.

![Página de carrito en un sitio web B2B.](../media/PayInvoice.png)

En la página **Facturas**, un usuario también puede seleccionar **Solicitar factura** junto a una factura. De esta forma, el usuario puede solicitar que se le envíen los detalles de la factura a su dirección de correo electrónico registrada.

![Cuadro de diálogo Solicitar factura.](../media/RequestInvoice2.png)

Después de que un usuario solicite una factura, la solicitud se mueve a la sección **Solicitudes B2B** de la página **Mi cuenta**. Entonces, después de que se ejecuten los trabajos **P-0001** y **Sincronizar pedidos y canalizar solicitudes** en la sede de Commerce, se activa el correo electrónico de la factura y el estado de la solicitud B2B se marca como completado.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
