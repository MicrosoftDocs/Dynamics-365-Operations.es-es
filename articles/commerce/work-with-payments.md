---
title: Métodos de pago en centros de llamadas
description: En este tema se describen los distintos métodos de pago que puede utilizar en un centro de llamadas de Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 03/28/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: MCRSalesTableOrderHistory, MCRCCAuthManagement
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 92163
ms.assetid: 8e738907-870b-466c-ab0c-07f4a4aa47f3
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: e7636f5c664634c680edf2ff9d8bae5ebb9035af
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415550"
---
# <a name="payment-methods-in-call-centers"></a>Métodos de pago en centros de llamadas

[!include [banner](includes/banner.md)]

En Dynamics 365 Commerce, la configuración del canal de centro de llamadas incluye una configuración que se denomina **Habilitar finalización de pedidos**. Esta configuración ayuda a garantizar que todos los pedidos que crean los usuarios del canal se liberan para su procesamiento solo si disponen de un pago por adelantado o un pago preautorizado que se encuentra dentro de las tolerancias aprobadas. Si está activada la configuración **Habilitar finalización de pedidos**, los usuarios de centro de llamadas pueden introducir pagos de pedidos de ventas para clientes mediante el uso de las funciones de procesamiento de pagos del Centro de llamadas. Si se desactiva la configuración, los usuarios de centro de llamadas no pueden utilizar las funciones de procesamiento de pagos del Centro de llamadas, pero aún pueden aplicar pagos por adelantado para pedidos de ventas mediante el uso de la función estándar Proveedor.

Como parte de la configuración del canal, una empresa puede definir los métodos de pago permitidos para un canal de centro de llamadas. El canal de centro de llamadas usa los mismos métodos de pago definidos para los canales de ventas.

Para configurar los métodos de pago para un canal de centro de llamadas, vaya a **Retail y Commerce** \> **Canales** \> **Centros de llamadas** \> **Todos los centros de llamadas** y, a continuación, en el menú **Configurar**, seleccione la opción **Métodos de pago** .

Al crear un método de pago, hay cinco funciones del método de pago que puede asignar.

| Función            | Descripción |
|---------------------|-------------|
| Normal              | Use la función **Normal** en su método de pago al definir métodos de pago como efectivo o asientos. Cuando se aplican estos tipos de pagos a un pedido de ventas en el centro de asistencia telefónica, el indicador **Pagar por adelantado** tomará de forma predeterminada el valor **Sí**. Esto inmediatamente enviará un asiento del pago por adelantado a la cuenta del cliente cuando se envíe este pedido. Los usuarios pueden cambiar el indicador **Pagar por adelantado** a **No** si así lo desean para que no se cree el asiento de pago por adelantado hasta el registro de la factura. El asiento de anticipos se registra en el historial de transacciones del cliente, donde se liquidará sistemáticamente con la factura del pedido de ventas. |
| Comprobación               | Use la función **Cheque** al definir un instrumento de cheque bancario como forma de pago. Cuando este tipo de pago se aplica a un pedido de ventas, el usuario debe introducir el número de cheque del cliente como parte del procesamiento de solicitud de pago. Los pagos de cheques siempre se tratan como pagos por adelantado cuando se aplican y los asientos de pago se crean inmediatamente tras el envío del pedido. Estos asientos de anticipo se liquidarán sistemáticamente con las facturas que se crean para el pedido. |
| Tarjetas               | Los tipos de pago con tarjeta representan cualquier tipo de pago que requiera la entrada de un número de tarjeta definido en la tarjeta de pago del cliente. Los ejemplos incluyen tarjetas de crédito y tarjetas regalo. Cuando configure estos tipos de pagos, debe utilizar el menú **Configuración de tarjeta** para definir los id. de tarjeta asociados a este método de pago. A la hora de la entrada de pedidos, los usuarios pueden indicar si el pago con tarjeta se pagará por adelantado, mediante la opción **Pagar por adelantado** que aparece en la página de entrada de pago. A menos que el negocio requiera anticipos, el flujo típico de un pago con tarjeta de crédito verdadera es un proceso de dos pasos, donde la autorización se obtiene en el momento de la entrada de pedidos y, a continuación, el pago se liquida y se cobra de la tarjeta del cliente en el momento de la facturación. Para pagos con tarjeta regalo, se recomienda un anticipo, ya que el saldo de la tarjeta regalo debe reducirse inmediatamente para que el cliente no pueda aplicar ese mismo valor en otro lugar. |
| Cliente            | La función **Cliente** en un método de pago implica que el pago se aplicará al límite de crédito del cliente o se pondrá "a cuenta". En Commerce, un cliente puede asignar un límite de crédito que se puede validar en el momento de la entrada de pedidos. Los pagos que se realizan mediante un método de pago vinculado a la función **Cliente** crean un pasivo en la cuenta del cliente. A continuación, cuando se factura el pedido de ventas, se muestra el saldo pendiente. En estos casos, los clientes suelen enviar un pago, de acuerdo con los términos que se han otorgado. De forma alternativa, un asiento de crédito abierto anteriormente en la cuenta del cliente se puede aplicar para liquidar el saldo adeudado. Tenga en cuenta que incluso si define este método de pago, no aparece entre las opciones de selección de pago en la entrada de pedidos del centro de llamadas salvo que se establezca el indicador **Permitir a cuenta** en el registro del cliente para el cliente con el que está trabajando. Este indicador se encuentra en la pestaña **Valores predeterminados del pago** del registro del cliente. |
| Quitar forma de pago/flotante | El centro de llamadas no utiliza la función **Quitar forma de pago/flotante**. Se aplica solo cuando define los métodos de pago que utiliza la aplicación de punto de venta (PDV) en un canal de tienda. |

A medida que se definen los métodos de pago, deben vincularse a un libro mayor o una cuenta bancaria. Si omite este paso, los usuarios recibirán errores al intentar guardar el tipo de pago.

## <a name="refund-payment-methods"></a>Métodos de pago de devolución

Para escenarios de procesamiento de devolución, el Centro de llamadas también utiliza algunos de los métodos de pago definidos en Proveedores. Para configurar estos métodos de pago, vaya a **Retail y Commerce** \> **Configuración de canal** \> **Configuración de centro de llamadas** \> **Métodos de devolución de centro de llamadas**. Debe completar esta configuración para procesar cheques de devolución a los clientes. Por ejemplo, si un cliente pagó originalmente un pedido mediante efectivo o un cheque, puede que el usuario desee enviar al cliente un cheque de devolución a través de Clientes. En este caso, los tipos de pago en efectivo y en cheque en el centro de llamadas deben asignarse al método de pago correcto en Clientes para ayudar a garantizar que la devolución se procesa correctamente.

Además, si un usuario procesa un pedido de devolución como usuario del centro de llamadas en Commerce, pero no puede vincular la devolución a una venta original, el método de pago **Devolución** debe definirse en los parámetros del Centro de llamadas. Vaya a **Retail y Commerce** \> **Configuración de canal** \> **Configuración del centro de llamadas** \> **Parámetros del centro de llamadas** y, a continuación, en la pestaña **RMA/Devolución**, en el campo **Método de pago**, asegúrese de que se define un método de pago. El método de pago será el método de pago que se utiliza para las devoluciones. Normalmente, se definirá como un método de comprobación o un método de cuenta del cliente.
