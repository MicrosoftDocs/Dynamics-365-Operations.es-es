---
title: Métodos de pago
description: Al configurar el sistema, se deben configurar todos los tipos de pago que acepte un minorista. Este artículo describe los tipos de pago que puede configurar y describe el proceso para configurarlos.
author: BrianShook
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailTenderTypeTable
audience: Application User
ms.reviewer: josaw
ms.custom: 15831
ms.assetid: 465893a5-6b4f-4c5f-b305-db071df2d33f
ms.search.region: global
ms.search.industry: Retail
ms.author: yabinl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 0450dbaa37365705ca59fd2223c9d3866054c12a
ms.sourcegitcommit: f4823a97c856e9a9b4ae14116a43c87f9482dd90
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/09/2021
ms.locfileid: "7779579"
---
# <a name="payment-methods"></a>Métodos de pago

[!include [banner](includes/banner.md)]

Al configurar el sistema, se deben configurar todos los tipos de pago que acepte un minorista. Este artículo describe los tipos de pago que puede configurar y describe el proceso para configurarlos.

Los minoristas pueden aceptar distintos tipos de pago a cambio de los productos y los servicios que venden. Aunque el efectivo es la forma más habitual de pago, los minoristas pueden recibir el pago también mediante cheques, tarjetas, cupones, etc. Al configurar el sistema, se deben configurar en Dynamics 365 Commerce todos los tipos de pago que acepte el minorista. En la lista siguiente se describen todos los tipos de pago que se pueden configurar:

- **Efectivo**: dinero con la forma física de la divisa, tales como billetes y monedas. Esta divisa puede ser la de la empresa o la divisa local de la tienda.
- **Cheque**: instrumento negociable que dicta el pago de un importe específico en una divisa concreta, librado en un banco determinado. Normalmente, un cheque tiene una validez indefinida o de seis meses a partir de la fecha de emisión, a menos que se indique otro período de validez. Este período varía en función del banco en el que se libra el cheque. Existen varios tipos de cheques, tales como los cheques nominativos, cheques de mostrador, cheques al portador y cheques para abono en cuenta. Puede configurar los cheques como método de pago de cada tienda. Los cheques se pueden aceptar en la divisa definida en la empresa o en la tienda. Debe configurar los cheques como método de pago para poder aceptar un cheque como pago en una tienda.
- **Divisa**: forma principal de pago, aparte de la divisa predeterminada de la empresa. Tanto las monedas como los billetes son formas de divisa. El método de pago en divisa representa todas las divisas que se usan. Para poder usar este método de pago, debe configurar divisas y especificar su información de cambio para las divisas.
- **Tarjeta**: todos los tipos de tarjetas que se usan en, como tarjetas de débito y crédito. Le recomendamos que, en la organización, configure un método de pago con tarjeta que represente todos los tipos de tarjeta. A continuación, configure en cada tienda un método de pago para cada tarjeta o grupo de tarjetas que se procesen con la misma configuración. Debe configurar las tarjetas de fabricantes disponibles en el mercado, como tarjetas de débito y crédito, para poder aceptar las tarjetas como pago en una tienda.
- **Nota de crédito**: notas de crédito emitidas o canjeadas en el punto de venta. La nota de crédito puede ser un crédito o una nota de crédito de devolución que se utiliza con una devolución. Si las notas de crédito se canjean parcialmente, el programa emite una nueva nota de crédito para el nuevo saldo. La nueva nota de crédito tiene un nuevo número. Una nota de crédito solo se puede usar una vez y el sistema guarda un registro de todos los números que se usan. El registro se puede ver en la página **Tabla de notas de crédito**. Los clientes no pueden canjear por un valor superior al de la nota de crédito.
- **Tarjeta regalo**: tarjetas regalo emitidas y canjeadas en el punto de venta. No se permite el sobrepago con tarjetas regalo. Todas las tarjetas de regalo deben tener asignaciones de números de tarjeta. 
- **Cuenta de cliente**: permite cargar los pagos desde la caja registradora a una cuenta de cliente en el momento de la venta. También puede usar este método de pago para recopilar información de ventas o descuentos específicos del cliente si este realiza el pago mediante otro método. En tal caso, debe configurar información específica del cliente.
- **Puntos de fidelidad**: los puntos que los clientes acumulan mediante programas de fidelización. Si crea los programas de fidelización, los clientes pueden conseguir puntos y canjearlos de distintas maneras. Por ejemplo, en algunos programas de fidelización, los clientes pueden canjear los puntos de fidelidad en un formulario de descuento o incluso usarlos como forma de pago.

Para configurar los métodos de pago, debe completar las tareas siguientes.

1. Configure los métodos de pago para una organización. Cree métodos de pago aceptados en toda la organización.
2. Creación de tipos y números de tarjeta de la organización. Si desea aceptar tarjetas de crédito o de débito, debe crear un método de pago para tarjetas y, a continuación, los tipos y números de tarjeta de la organización.
3. Configurar métodos de pago en tienda. Asocie métodos de pago a cada tienda e indique la configuración específica de la tienda para cada método de pago.
4. Configurar tipos de pago con tarjeta para tiendas. Complete la configuración de tarjeta para todos los métodos de pago con tarjeta que acepte la tienda.

## <a name="handle-change-tendering-for-payment-methods"></a>Gestionar cambios en la forma de pago para métodos de pago

Algunos métodos de pago no admiten cambios directos en la forma de pago si los fondos se deben devolver a los clientes durante las transacciones en el punto de venta. Solo los métodos de pago **Efectivo** y **Divisa** se pueden utilizar para cambios en la forma de pago. 

Para gestionar casos en los que se requieren cambios en la forma de pago durante una transacción, pero el método de pago no lo admite, puede definir un método de pago **Cambio de la forma de pago**. Cuando configure los métodos de pago en tienda para la tienda, seleccione el método de pago que desee utilizar. A continuación, en la sección **Cambio**, en el campo **Cambio de la forma de pago**, ingrese una opción de cambio de forma de pago. Por ejemplo, puede ingresar **1** para indicar que el efectivo se puede utilizar como opción de cambio de forma de pago.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
