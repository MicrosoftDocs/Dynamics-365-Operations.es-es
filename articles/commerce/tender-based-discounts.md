---
title: Descuentos basados en forma de pago
description: Este artículo describe funcionalidad basada en formas de pago que permite a minoristas configurar descuentas para tipos de forma de pago específicos en Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 08/19/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2018-10-31
ms.openlocfilehash: 3c28297e62e5b2880a7a39381702d5a1448c91ac
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2022
ms.locfileid: "9336725"
---
# <a name="tender-based-discount"></a>Descuento basado en forma de pago

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Este artículo describe funcionalidad basada en formas de pago que permite a minoristas configurar descuentas para tipos de forma de pago específicos en Microsoft Dynamics 365 Commerce.

Es un una práctica común entre minoristas emitir tarjetas de crédito con marca, privadas. Los minoristas se benefician porque obtienen tasas preferidas de los bancos. Además, ya que estas tarjetas de crédito pueden animar a los clientes a visitar el almacén más con frecuencia, ayudan a mejorar el balance del distribuidor. Por lo tanto, los minoristas tienen el incentivo de aumentar el uso por parte del cliente de tarjetas de crédito con marca. Para lograr este objetivo, con frecuencia proporcionan una descuentos adicionales a los clientes que usan estas tarjetas de crédito.

Como alternativa, los minoristas que no proporcionan tarjetas de crédito de la marca pueden estar interesados en animar a los clientes a pagar con otros tipos de forma de pago, como efectivo, tarjetas regalo, o puntos de fidelidad. De esta manera, ayudan reducir el gasto de tarifas de tramitación de la tarjeta de crédito. Por lo tanto, los minoristas pueden proporcionar descuentos a los clientes que usan estos tipos de forma de pago alternativos.

## <a name="tender-based-discount"></a>Descuento basado en forma de pago

Commerce apoya un *descuento por licitación* que permite a los minoristas configurar un porcentaje de descuento que se aplica a una transacción si el total de la transacción supera un monto específico y el cliente paga utilizando el tipo de pago preferido. El descuento basado en licitaciones se basa en niveles, por lo que se pueden asociar diferentes porcentajes de descuento con diferentes umbrales de cantidad. El cliente podrá decidir si desea hacer un pago parcial o un pago completo, y el motor de precios determina el importe de descuento adecuado. El descuento basado en pago siempre se aplica sobre el importe antes de impuestos de las líneas de venta.

El descuento basado en formas de pago solo se puede aplicar a líneas de ventas donde los precios no están bloqueados y se distribuyen proporcionalmente a las líneas que reúnen los requisitos. Si nuevas líneas de ventas se agregan a un pedido, el descuento basado en la forma de pago se aplica solo a las nuevas líneas de ventas durante el pago. Cuando se efectúa un pedido de cliente para su recogida o entrega, el descuento basado en la forma de pago sólo se aplica al importe del depósito. Una vez que el pedido se haya realizado, durante su ejecución, los precios de las líneas de ventas se bloquean. No se aplica ningún descuento basado en la forma de pago a ningún saldo que se pague durante la recogida o se autorice durante el envío. El descuento basado en la forma de pago se puede aplicar al importe completo de un pedido del cliente únicamente si el minorista obtiene el importe completo como depósito mientras se realiza el pedido.

Los descuentos basados en la licitación no compiten con los descuentos basados en artículos, como los descuentos simples, los descuentos por cantidad, los descuentos por umbral, los descuentos combinados y los descuentos manuales. Los descuentos basados en licitaciones siempre se calculan sobre los descuentos basados en artículos. Por lo tanto, incluso si un descuento exclusivo se aplica a un artículo, el descuento basado en la forma de pago todavía se seguirá aplicando encima del descuento exclusivo. Del mismo modo, si un descuento de umbral se aplica a la transacción, y el descuento basado en la forma de pago reduce el total por debajo del umbral, el descuento de umbral se seguirá aplicando a la transacción.

Aunque los descuentos basados en formas de pago reducen el subtotal de una transacción, los cargos automáticos que se aplican a la transacción no se ven afectados. Por ejemplo, si los gastos de entrega se calculan como $5 porque el subtotal era más de $100, y el descuento basado en formas de pago reduce el importe de modo que sea inferior a $100, los gastos de entrega seguirán siendo $5.

El descuento basado en la forma de pago están limitados a dos tipos de pago: tarjetas de crédito y efectivo. Si varios descuentos basados en forma de pago están configurados para un tipo de pago, sólo se aplicará el mejor descuento basado en forma de pago.

## <a name="pos-user-experience"></a>Experiencia de usuario PDV

Si un descuento basado en la forma de pago se configura para el efectivo, y un cajero del punto de venta (PDV) selecciona el botón **Pagar efectivo** para pagar y realizar la transacción, el descuento basado en la forma de pago se aplicará automáticamente a la transacción. El importe reducido se muestra como saldo. Sin embargo, si el cajero selecciona el botón **Atrás** en la pantalla de pago, se elimina el descuento, y el importe original se muestra en la pantalla de la transacción. Se quita el descuento basado en la forma de pago si se anula la línea de pago.

Para los pagos con tarjeta de crédito, los minoristas pueden establecer un descuento basado en la forma de pago en uno o más tipos de tarjetas de crédito. Sin embargo, el sistema no puede comprobar el tipo de tarjeta de crédito que se utiliza a menos que se autorice la tarjeta. Si el descuento se aplica después de la autorización, la autorización de pago será para un importe mayor, pero la captura de pago será para un importe más pequeño. Para ayudar a evitar esta situación, si un cliente paga con una tarjeta de crédito, el cajero ve un cuadro de diálogo que enumera las tarjetas de crédito preferidas que darán al cliente un descuento adicional. El cajero podrá preguntar si el cliente desea usar una de las tarjetas preferidas para obtener un descuento adicional. Si el cajero selecciona una tarjeta preferida, el descuento basado en la forma de pago se aplica a la transacción, y el importe reducido se muestra en la pantalla de pago. La autorización será para el importe reducido. Si el cliente inserta una tarjeta que es diferente de la tarjeta que el cajero ha seleccionado, se verá un mensaje de error, y se anulará la autorización.

## <a name="call-center-user-experience"></a>Experiencia del usuario del centro de asistencia telefónica

Si un usuario del centro de llamadsa selecciona **Completado** durante un pedido de centro de asistencia telefónica, aparece la pantalla **Totales**. Inicialmente, los totales de esta pantalla no incluyen descuentos basados en la forma de pago, ya que el método de pago todavía no se ha seleccionado. En la pantalla **Agregar pago**, si el usuario selecciona el método de pago para el que el está configurado el descuento basado en la forma de pago, el importe de pago se ajustará automáticamente de modo que refleje el importe descontado. Como un cliente en el PDV, el cliente del centro de asistencia telefónica puede decidir si desea pagar el pago completo o un pago parcial. En función del importe que se paga, el descuento basado en la forma de pago se aplica al pedido de ventas.

> [!NOTE]
> La validación de la tarjeta no se hace para los pedidos del centro de llamadas. Por ejemplo, si el usuario del centro de asistencia telefónica selecciona Visa como tarjeta de crédito, pero el cliente usa Mastercard, el sistema seguirá aplicando el descuento.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
