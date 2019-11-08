---
title: Descuentos basados en forma de pago
description: Este tema proporciona una visión general de la funcionalidad que permite a minoristas configurar descuentas para tipos de forma de pago específicos.
author: bebeale
manager: AnnBe
ms.date: 10/25/19
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTenderDiscount
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: Version 10.0.7
ms.openlocfilehash: 245ee647a3b86303df046fda5bba406c7a2485b5
ms.sourcegitcommit: b0c176d5d24939307c6d0a6dbe7656007ca53710
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "2673574"
---
# <a name="tender-based-discounts"></a>Descuentos basados en forma de pago

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Es un una práctica común entre minoristas emitir tarjetas de crédito con marca, privadas. Los minoristas se benefician porque obtienen tasas preferidas de los bancos. Además, ya que estas tarjetas de crédito pueden animar a los clientes a visitar el almacén más con frecuencia, ayudan a mejorar el balance del distribuidor. Por lo tanto, los minoristas tienen el incentivo de aumentar el uso por parte del cliente de tarjetas de crédito con marca. Para lograr este objetivo, con frecuencia proporcionan una descuentos adicionales a los clientes que usan estas tarjetas de crédito.

Como alternativa, los minoristas que no proporcionan tarjetas de crédito de la marca pueden estar interesados en animar a los clientes a pagar con otros tipos de forma de pago, como efectivo, tarjetas regalo, o puntos de fidelidad. De esta manera, ayudan reducir el gasto de tarifas de tramitación de la tarjeta de crédito. Por lo tanto, los minoristas pueden proporcionar descuentos a los clientes que usan estos tipos de forma de pago alternativos.

En Microsoft Dynamics 365 Retail, los minoristas pueden configurar un porcentaje de descuento que se aplica a las líneas elegibles si el cliente paga mediante el tipo de forma de pago preferido. El cliente podrá decidir si desea hacer un pago parcial o un pago completo, y Retail determina el importe de descuento adecuado. Tenga en cuenta que el descuento siempre se da sobre el importe de antes de impuestos de los artículos elegibles.

Los descuentos basados en la forma de pago no compiten con los descuentos basados en artículos, como los descuentos periódicos o manuales. Se componen siempre sobre los descuentos de artículos. Por lo tanto, incluso si un descuento periódico exclusivo se aplica a un artículo, el descuento basado en la forma de pago se seguirá aplicando encima del descuento periódico exclusivo. Del mismo modo, si un descuento de umbral se aplica a la transacción, y el descuento basado en la forma de pago reduce el total por debajo del umbral, el descuento de umbral se seguirá aplicando a la transacción.

Aunque los descuentos basados en formas de pago reducen el subtotal de la transacción, los cargos automáticos que se aplican a la transacción no se ven afectados. Por ejemplo, si los gastos de entrega se calculan como $5 porque el subtotal era más de $100, y el descuento basado en formas de pago reduce el importe de modo que sea inferior a $100, los gastos de entrega seguirán siendo $5.

> [!NOTE]
> Los descuentos basados en formas de pago se distribuyen proporcionalmente a las líneas de ventas elegibles y reducen el importe de antes de impuestos de las líneas individuales. Si varios descuentos basados en forma de pago están configurados para un tipo de forma de pago (por ejemplo, efectivo), sólo se aplicará el mejor descuento basado en forma de pago.

Los descuentos basados en forma de pago solo se pueden aplicar a las líneas de ventas donde los precios no están bloqueados. Si nuevas líneas de ventas se agregan a un pedido, el descuento basado en la forma de pago se aplica a las nuevas líneas de ventas sólo durante el pago. Mientras se efectúa un pedido de cliente para su recogida o envío, el descuento basado en la forma de pago sólo se aplica al importe del depósito. Una vez que el pedido se haya realizado, durante su ejecución, los precios de las líneas de ventas se bloquean. Por lo tanto, no se aplica ningún descuento basado en la forma de pago a ningún saldo que se pague durante la recogida o se autorice durante el envío. El descuento basado en la forma de pago se puede aplicar al importe completo de un pedido del cliente únicamente si el minorista obtiene el importe completo como depósito mientras se realiza el pedido.

> [!IMPORTANT]
> En Retail, los descuentos basados en la forma de pago están limitados a dos tipos de pago: tarjetas de crédito y efectivo.

## <a name="pos-user-experience"></a>Experiencia de usuario PDV

Si el descuento basado en la forma de pago se configura para el efectivo, y el cajero del punto de venta (PDV) selecciona un botón asignado a la operación de pago en efectivo, el descuento basado en la forma de pago se aplicará automáticamente a la transacción. El importe reducido se muestra como saldo. Sin embargo, si el cajero selecciona el botón **Atrás** en la pantalla de pago, se elimina el descuento, y el importe original se muestra en la pantalla de la transacción. Se quita el descuento basado en la forma de pago si se anula la línea de pago.

Para los pagos con tarjetas, los minoristas pueden establecer un descuento basado en la forma de pago en uno o más tipos de tarjetas de crédito. Sin embargo, el sistema no puede comprobar el tipo de tarjeta de crédito que se utiliza a menos que se autorice la tarjeta. Si el descuento se aplica después de la autorización, la autorización de pago será para un importe mayor, pero la captura de pago será para un importe más pequeño.

Para ayudar a evitar esta situación, si un cliente paga con una tarjeta de crédito, el cajero ve un cuadro de diálogo que enumera las tarjetas de crédito que aportarán al cliente ahorros adicionales. El cajero podrá preguntar si el cliente desea usar una de las tarjetas preferidas para obtener un descuento adicional. Si el cajero usa una tarjeta preferida, el descuento basado en la forma de pago se aplica a la transacción, y el importe reducido se muestra en la pantalla de pago. La autorización será para el importe reducido. Si el cliente inserta una tarjeta que es diferente de la tarjeta que el cajero ha seleccionado, se verá un mensaje de error, y se anulará la autorización.

## <a name="call-center-user-experience"></a>Experiencia del usuario del centro de asistencia telefónica

Cuando el usuario seleccione **Completado** durante un pedido de centro de asistencia telefónica, se mostrará la pantalla **Totales**. Inicialmente, los totales de esta pantalla no incluyen descuentos basados en la forma de pago, ya que el método de pago todavía no se ha seleccionado. En la pantalla **Agregar pago**, si el usuario selecciona el método de pago para el que el está configurado el descuento basado en la forma de pago, el importe de pago se ajustará automáticamente de modo que refleje el importe descontado. Como el cliente en el PDV, el cliente del centro de asistencia telefónica puede decidir si desea pagar el pago completo o un pago parcial. En función del importe que se paga, el descuento basado en la forma de pago se aplica al pedido de ventas.

> [!NOTE]
> La validación de la tarjeta no se hace para los pedidos del centro de llamadas. Por ejemplo, si el usuario del centro de asistencia telefónica selecciona Visa como tarjeta de crédito, pero el cliente usa Mastercard, el sistema seguirá aplicando el descuento.

## <a name="exclude-items-from-discounts"></a>Excluir artículos de los descuentos

Los minoristas eligen a menudo excluir algunos productos, como artículos nuevos o artículos con demanda, de los descuentos. Sin embargo, es posible que aún deseen aplicar descuentos basados en la forma de pago. Por ejemplo, un minorista configura Retail para que no permita descuentos basados en artículos o descuentos manuales. Sin embargo, si el cliente paga mediante la forma de pago preferida, Retail aplicará el descuento basado en la forma de pago. Para configurar Retail de esta manera, los minoristas deben desactivar las opciones **Evite todos los descuentos** y **Evitar descuentos basados en la forma de pago**, y activar las opciones **Evitar los descuentos al por menor** y **Evitar los descuentos manuales**. Las opciones se encuentran en la página **Productos emitidos**, en la pestaña **Retail**.

> [!NOTE]
> Cuando está activada la configuración **Evite todos los descuentos**, no se aplicará ningún descuento al producto. Ni siquiera se aplicarán descuentos basados en la forma de pago.
