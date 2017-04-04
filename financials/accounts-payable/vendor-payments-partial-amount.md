---
title: Pagos de proveedor para un importe parcial
description: "En ocasiones, puede crear un pago a un proveedor inferior al importe de una factura. Este artículo describe las diferentes opciones para gestionar esta situación. Las opciones disponibles dependen de la configuración y de los requisitos empresariales."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14321
ms.assetid: 9a17075e-5325-4d55-a1e5-1791b8c460a0
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 2cb439e871d57f74c296697cfc42705fb0121bb7
ms.openlocfilehash: 4d243e6a9a68b69a6b32748344fc606ff3f2d965
ms.lasthandoff: 03/31/2017


---

# <a name="vendor-payments-for-a-partial-amount"></a>Pagos de proveedor para un importe parcial

En ocasiones, puede crear un pago a un proveedor inferior al importe de una factura. Este artículo describe las diferentes opciones para gestionar esta situación. Las opciones disponibles dependen de la configuración y de los requisitos empresariales. 

<a name="cash-discount-amounts"></a>Importes de descuento por pronto pago
---------------------

Un proveedor puede ofrecerle un descuento por pronto pago por pagar una factura antes de la fecha de vencimiento. Por ejemplo, introduce una factura de 100,00 que especifica un descuento por pronto pago del 2% si se paga en 10 días. La fecha de vencimiento es 30 días. Si una propuesta de pago utiliza el descuento por pronto pago como criterio para seleccionar una factura, y si la propuesta se ejecuta en o antes de la fecha de descuento por pronto pago, la factura se ha activado para el pago, y el pago se realiza para 98.00. Un descuento por pronto pago también se puede realizar para un único pago que se creó manualmente.

## <a name="partial-payments-with-cash-discounts"></a>Pagos parciales con descuentos por pronto pago
Cuando se realiza un pago parcial, se puede planificar realizar otro pago parcial adicional para liquidar por completo la factura. Para tomar un descuento por pronto pago para un pago parcial, debe establecer Sí ** calcule los descuentos por pronto pago para pagos parciales ** de la opción ** ** ** en los parámetros de la cuenta a pagar ** la página. 

Por ejemplo, recibe un descuento por pronto pago del 2% si la factura se paga en menos de 10 días tras su emisión. Se registra una factura de 100,00. Si hace un pago de 49.00 en 10 días, debe especificar un débito de 49.00 en el diario de pagos. Al liquidar un pago parcial en ** las transacciones abiertas del Liquidar ** la página 1.00, ** ** aparece en ** importe de descuento por pronto pago a tomar ** el campo. 

> [!NOTE] 
> Si especifica un pago parcial y deja el importe de la factura completo en ** ascienda a liquidar ** campos, ** importe de descuento por pronto pago a tomar ** el campo se actualiza automáticamente cuando registre las transacciones.

## <a name="credit-notes-with-cash-discounts"></a>Notas de crédito con descuentos por pronto pago
Puede devolver algunos de los artículos de una factura y recibir una nota de abono. Si el descuento por pronto pago se ha tomado de la factura original, puede restar el valor del descuento y recibir una devolución por el importe correcto. Si ** calcule los descuentos por pronto pago para las notas de crédito ** la opción está establecida ** en Sí ** ** los parámetros de proveedores ** la página, el descuento se calcula automáticamente para la nota de abono. 

Por ejemplo, recibe un descuento por pronto pago del 2% si la factura se paga en menos de 10 días tras su emisión. Se registra una factura de 100,00. Si devuelve las mercancías y recibe una nota de abono, puede especificar una nota de crédito para el importe completo de la factura original, 100.00, así como el descuento por pronto pago del 2 por ciento que también se define en la nota de crédito.  Cuando aparezca la nota de abono en ** liquidar las transacciones ** la página 98.00, ** ** aparece en ** ascienda a liquidar ** los campos, y ** - 2.00 ** aparece en ** importes de descuento por pronto pago ** campo. El importe del descuento se registra en una cuenta de descuento por pronto pago.

## <a name="overpaymentunderpayment-amounts"></a>Importes de sobrepago/pago insuficiente
Puede realizar un pago parcial donde el importe por liquidar sea muy pequeño. Por ejemplo, la factura de proveedor es por 1.000,00 y paga 999,90. Si el importe restante es inferior al especificado para sobrepagos o pagos insuficientes en la página **Parámetros de proveedores**, la diferencia se registra automáticamente en una cuenta contable de sobrepago o pago insuficiente.


