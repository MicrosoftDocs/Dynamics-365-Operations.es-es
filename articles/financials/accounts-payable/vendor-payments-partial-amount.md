---
title: Pagos de proveedor para un importe parcial
description: "En ocasiones, puede crear un pago a un proveedor inferior al importe de una factura. Este artículo describe las diferentes opciones para gestionar esta situación. Las opciones disponibles dependen de la configuración y de los requisitos empresariales."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14321
ms.assetid: 9a17075e-5325-4d55-a1e5-1791b8c460a0
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: aeef806980665c523f10b373f7662ecf509a8172
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---

# <a name="vendor-payments-for-a-partial-amount"></a>Pagos de proveedor para un importe parcial

[!INCLUDE [banner](../includes/banner.md)]

En ocasiones, puede crear un pago a un proveedor inferior al importe de una factura. Este artículo describe las diferentes opciones para gestionar esta situación. Las opciones disponibles dependen de la configuración y de los requisitos empresariales. 

<a name="cash-discount-amounts"></a>Importes de descuento por pronto pago
---------------------

Un proveedor puede ofrecerle un descuento por pronto pago por pagar una factura antes de la fecha de vencimiento. Por ejemplo, introduce una factura de 100,00 que especifica un descuento por pronto pago del 2% si se paga en 10 días. La fecha de vencimiento es 30 días. Si una propuesta de pago usa el descuento por pronto pago como criterio para seleccionar una factura, y si la propuesta se ejecuta en la fecha de descuento por pronto pago o antes, la factura se selecciona para su pago y se crea el pago de 98,00. También se puede obtener un descuento por pronto pago por un único pago que creado manualmente.

## <a name="partial-payments-with-cash-discounts"></a>Pagos parciales con descuentos por pronto pago
Cuando se realiza un pago parcial, se puede planificar realizar otro pago parcial adicional para liquidar por completo la factura. Para obtener un descuento por pronto pago para un pago parcial, debe establecer la **opción** <strong>Calcular descuento por pronto pago para pagos parciales</strong> en Sí en la página P<strong>arámetros de proveedores</strong>. 

Por ejemplo, recibe un descuento por pronto pago del 2% si la factura se paga en menos de 10 días tras su emisión. Se registra una factura de 100,00. Si hace un pago de 49,00 en 10 días, debe especificar un débito de 49,00 en el diario de pagos. Al liquidar el pago parcial en la página **Liquidar transacciones abiertas**, aparece **1,00** en el campo **Importe de descuento por pronto pago para aplicar**. 

> [!NOTE] 
> Si especifica un pago parcial y deja el importe de la factura completo en el campo **Importe para liquidar**, el campo **Importe de descuento por pronto pago para aplicar** se vuelve a calcular automáticamente al registrar las transacciones.

## <a name="credit-notes-with-cash-discounts"></a>Notas de crédito con descuentos por pronto pago
Puede devolver algunos de los artículos de una factura y recibir una nota de abono. Si el descuento por pronto pago se ha tomado de la factura original, puede restar el valor del descuento y recibir una devolución por el importe correcto. Si la **opción** <strong>Calcular descuentos por pronto pago para notas de abono</strong> está definida en Sí en la página <strong>Parámetros de proveedores</strong>, se calcula automáticamente el descuento para la nota de abono. 

Por ejemplo, recibe un descuento por pronto pago del 2% si la factura se paga en menos de 10 días tras su emisión. Se registra una factura de 100,00. Si devuelve los artículos y recibe una nota de abono, puede especificar una nota de abono para el importe total de la factura original, 100,00, junto con el descuento por pronto pago del 2 por ciento que también está definido en la nota de abono.  Al ver la nota de abono en la página **Liquidar transacciones**, aparece **98,00** en el campo **Importe para liquidar** y **-2,00** en **Importe de descuento por pronto pago**. El importe del descuento se registra en una cuenta de descuento por pronto pago.

## <a name="overpaymentunderpayment-amounts"></a>Importes de sobrepago/pago insuficiente
Puede realizar un pago parcial donde el importe por liquidar sea muy pequeño. Por ejemplo, la factura de proveedor es por 1.000,00 y paga 999,90. Si el importe restante es inferior al especificado para sobrepagos o pagos insuficientes en la página **Parámetros de proveedores**, la diferencia se registra automáticamente en una cuenta contable de sobrepago o pago insuficiente.


Para obtener más información, consulte [Resumen de pagos del proveedor](../cash-bank-management/tasks/vendor-payment-overview.md).

