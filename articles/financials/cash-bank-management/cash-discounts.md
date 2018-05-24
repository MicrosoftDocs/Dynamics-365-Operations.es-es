---
title: Descuentos por pronto pago
description: "Los descuentos por pronto pago se configuran y se comparten para Proveedores y Clientes.  El descuento por pronto pago disponible se puede definir en la factura de cliente o la factura de proveedor, y se tomará si la factura se paga dentro de la fecha de descuento por pronto pago."
author: kweekley
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CashDisc
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 3741
ms.assetid: c25f9d85-2702-46aa-8e61-0b4886e069b3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 5ccf41d1184280d3c4a000db13847733fd2cf4d2
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---

# <a name="cash-discounts"></a>Descuentos por pronto pago

[!include [banner](../includes/banner.md)]

Los descuentos por pronto pago se configuran y se comparten para Proveedores y Clientes.  El descuento por pronto pago disponible se puede definir en la factura de cliente o la factura de proveedor, y se tomará si la factura se paga dentro de la fecha de descuento por pronto pago. 

## <a name="cash-discounts"></a>Descuentos por pronto pago

Los descuentos por pronto pago para clientes o proveedores se pueden crear en la página Descuentos por pronto pago. También puede definir, mediante el campo Código de descuento siguiente, una serie de descuentos por pronto pago que se sucederán uno tras otro cuando venzan las fechas de descuento por pronto pago anteriores. Para obtener más información, consulte el apartado "Ejemplo: serie de descuentos por pronto pago" más adelante en este tema. Si la factura, la transacción de crédito (ya sea un pago o una nota de abono) o ambas se introducen en una divisa diferente a la divisa de contabilidad de la entidad jurídica, el descuento por pronto pago se calcula mediante el tipo de cambio basado en la fecha del pago o la nota de abono. Si la factura y el documento de crédito se especifican en entidades jurídicas diferentes y las divisas de contabilidad de dichas entidades jurídicas son diferentes, el tipo de cambio se toma de la entidad jurídica de la factura, a partir de la fecha del documento de crédito. Para obtener más información, consulte el apartado "Ejemplo: tipos de cambio para los descuentos por pronto pago" más adelante en este tema.

## <a name="defaulting-order-of-cash-discount-main-account"></a>Orden predeterminado de la cuenta principal del descuento por pronto pago

Si una factura se liquida a tiempo para obtener un descuento por pronto pago, el descuento por pronto pago se registra automáticamente en una cuenta principal de descuento para la siguiente prioridad predeterminada:
1.  La cuenta principal especificada en el campo Cuenta alternativa de descuento por pronto pago en la página Liquidar transacciones abiertas del cliente o la página Liquidar transacciones abiertas del proveedor.
2.  La cuenta principal que se especifica en el campo Descuento por pronto pago del cliente o el campo Descuento por pronto pago del proveedor del grupo de registro contable que se asigna al grupo de impuestos de la factura. Configure grupos de registro de contabilidad en la página Grupos de registro y asígnelos a códigos de impuestos en la página Códigos de impuestos.
3.  La cuenta de registro principal de la página Descuentos por pronto pago o la página Cuenta principal para descuentos de cliente para el código de descuento por pronto pago que se encuentra en la factura liquidada.
4.  La cuenta principal para descuentos por pronto pago, como se define en la página de Cuentas para transacciones automáticas.

## <a name="example-series-of-cash-discounts"></a> Ejemplo: serie de descuentos por pronto pago
Configure tres códigos de descuento por pronto pago de la siguiente forma:
-   Código 5D10%: un descuento por pronto pago del 10% cuando el importe se paga en un período de 5 días.
-   Código 10D5%: un descuento por pronto pago del 5% cuando el importe se paga en un período de 10 días.
-   Código 14D2%: un descuento por pronto pago del 2% cuando el importe se paga en un período de 14 días.

En el campo Código de descuento siguiente:
-   Para el código 5D10%, seleccione 10D5%.
-   Para el código 10D5%, seleccione 14D2%.
-   Para el código 14D2%, deje en blanco el campo Código de descuento siguiente.

Los tres descuentos por pronto pago se suceden uno tras otro a medida que la fecha de pago sobrepasa la fecha de descuento por pronto pago en la factura. Solo se concede un descuento por pronto pago cuando se paga la factura, en función de cuál es la fecha de descuento por pronto pago satisfecha en la secuencia de descuentos por pronto pago.

## <a name="example-exchange-rates-for-cash-discounts"></a> Ejemplo: tipos de cambio para los descuentos por pronto pago
La divisa de contabilidad de su entidad jurídica es el euro y se especifican los siguientes tipos de cambio para el dólar estadounidense:
-   1 de febrero = 110
-   1 de marzo = 80

El 15 de febrero se registra una factura de 1000 dólares con términos de descuento por pronto pago de 20D2%. El importe en la divisa de contabilidad de la factura es de 1100 euros. Se liquida un pago de 980 dólares con la factura el día 1 de marzo. El importe del descuento por pronto pago es de 20 dólares. El importe en la divisa de contabilidad del pago es de 784 euros. El importe en la divisa de contabilidad del descuento por pronto pago se calcula mediante el tipo de cambio del 1 de marzo: 20 \* 80 / 100 = 16 EUR.

> [!NOTE]
> Si está seleccionada la opción Calcular descuento por pronto pago para pagos parciales en la página Parámetros de clientes o Parámetros de proveedores, se usa el tipo de cambio que esté en vigor en la fecha de cada pago parcial. 


