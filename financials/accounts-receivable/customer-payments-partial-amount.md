---
title: Pagos de cliente para un importe parcial
description: "A veces, los clientes realizan un pago inferior al importe de la factura. Este artículo describe las diferentes opciones para gestionar esta situación. Las opciones disponibles dependen de la configuración y de los requisitos empresariales."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 13011
ms.assetid: 20423a2d-6997-4e1c-a596-a77016600071
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 795d13a07065a125a750970beaff85b59307f623
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="customer-payments-for-a-partial-amount"></a>Pagos de cliente para un importe parcial

[!include[banner](../includes/banner.md)]


A veces, los clientes realizan un pago inferior al importe de la factura. Este artículo describe las diferentes opciones para gestionar esta situación. Las opciones disponibles dependen de la configuración y de los requisitos empresariales.

<a name="partial-payment-with-no-discount"></a>Pagos parciales sin descuento
--------------------------------

Los clientes pueden realizar un pago parcial porque no dispongan de efectivo disponible para pagar la factura por completo, o porque haya desacuerdo acerca de un artículo en la factura. En esta situación, la factura se puede liquidar parcialmente con el pago. La factura permanecerá abierta y mostrará un saldo.

## <a name="discount-amounts"></a>Importes de descuento
Puede ofrecer a los clientes un descuento por pronto pago al pagar una factura antes de la fecha de vencimiento. Por ejemplo, introduce una factura de 100,00 que especifica un descuento por pronto pago del 2% si se paga en 10 días. La fecha de vencimiento es 30 días. Si recibe un pago de 98,00 en 10 días, especificará el pago de 98,00. Entonces, si la factura está marcada para liquidación, el descuento por pronto pago se realiza automáticamente.

## <a name="partial-payments-with-cash-discounts"></a>Pagos parciales con descuentos por pronto pago
Cuando los clientes realizan un pago parcial, pueden planear realizar otro pago parcial adicional para liquidar por completo la factura. Para obtener un descuento por pronto pago para un pago parcial, debe establecer la opción **Calcular descuento por pronto pago** para pagos parciales en **Sí** en la página **Parámetros de clientes**. 

Por ejemplo, ofrece un descuento por pronto pago del 2% si la factura se paga en menos de 10 días tras su emisión. Se registra una factura de 100,00. Si recibe un pago de 49,00 en 10 días, especificará un crédito de 49,00 en un diario de pagos. Al liquidar el pago parcial en la página **Liquidar transacciones**, **1,00** aparece en el campo **Importe de descuento por pronto pago para aplicar**. El importe del descuento se registra en una cuenta de descuento por pronto pago. 

> [!NOTE] 
> Si especifica un pago parcial y deja el importe de la factura completo en el campo **Importe para liquidar**, el campo **Importe de descuento por pronto pago para aplicar** se vuelve a calcular automáticamente al registrar las transacciones.

## <a name="credit-notes-with-discounts"></a>Notas de crédito con descuentos
Si los clientes devuelven algunos de los artículos de una factura, es posible que emita una nota de abono. Si se obtuvo un descuento por pronto pago en la factura original, la nota de abono al cliente debe ser del importe neto del descuento por pronto pago obtenido por el cliente. Si la opción **Calcular descuentos por pronto pago para notas de abono** está definida en **Sí** en la página **Parámetros de clientes**, se calcula automáticamente el descuento para la nota de abono. 

Por ejemplo, ofrece unas condiciones de pago que especifican un 2% de descuento si la factura se paga en menos de 10 días tras su emisión. Se registra una factura por un valor de 100,00 y el cliente obtiene el descuento por pronto pago. Si el cliente devuelve las mercancías y usted emite una nota de abono, puede especificar la nota de abono por -100,00. Al ver la nota de abono en la página **Liquidar transacciones abiertas**, aparece**98,00** en el campo **Importe para liquidar** y **-2,00** en **Importe de descuento por pronto pago**. El importe del descuento se registra en una cuenta de descuento por pronto pago.

## <a name="overpaymentunderpayment-amounts"></a>Importes de sobrepago/pago insuficiente
Cuando los clientes realizan un pago, puede quedar un importe muy pequeño por liquidar. Por ejemplo, realiza una factura al cliente de 1.000,00 y el cliente paga 999,90. Si el importe restante es inferior al especificado por sobrepagos o pagos insuficientes en la página **Parámetros de clientes**, la diferencia se registra automáticamente en una cuenta contable de sobrepago o pago insuficiente.

## <a name="full-settlement"></a>Liquidación completa
Los clientes pueden realizar un pago parcial que no pagará el importe restante pero que es superior al importe de pago insuficiente especificado en la página **Parámetros de proveedores**. Si desea marcar la factura como totalmente liquidada, puede usar la opción **Liquidación completa** en la página **Liquidar transacciones**. (Puede habilitar la funcionalidad de liquidación completa mediante una clave de configuración). Por ejemplo, se registra una factura por un valor de 1.000,00 y el cliente realiza un pago de 990,00. Ha acordado que el cliente no tiene que pagar los 10,00 restantes. Tras marcar la factura para su liquidación, también puede seleccionar **Liquidación completa**. La factura se considerará totalmente liquidada. La diferencia de 10,00 se registra en una cuenta de descuento por pronto pago como un importe descontado adicional.




