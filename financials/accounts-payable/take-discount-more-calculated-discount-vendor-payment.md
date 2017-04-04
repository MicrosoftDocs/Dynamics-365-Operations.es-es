---
title: Tome un descuento superior al descuento calculado para un pago de proveedor
description: "Este artículo le guía por un escenario en el que se toma un descuento por pronto pago para un importe superior al descuento que estaba originalmente disponible en la factura. Este escenario podría surgir si una organización llega a un acuerdo con el proveedor para pagar un importe menor en la factura."
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
ms.custom: 14281
ms.assetid: 7f0a4197-95dd-4969-ade9-154815cf659e
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 22ba73681faa509a5144517163cc173a1267a534
ms.lasthandoff: 03/31/2017


---

# <a name="take-a-discount-that-is-more-than-the-calculated-discount-for-a-vendor-payment"></a>Tome un descuento superior al descuento calculado para un pago de proveedor

Este artículo le guía por un escenario en el que se toma un descuento por pronto pago para un importe superior al descuento que estaba originalmente disponible en la factura. Este escenario podría surgir si una organización llega a un acuerdo con el proveedor para pagar un importe menor en la factura. 

El proveedor 3.051 ofrece a Fabrikam un descuento por pronto pago del 4 por ciento si una factura se paga en siete días. El 29 de junio April introduce una factura de 1.000,00. El proveedor permite a April que aproveche un descuento de 60,00 en lugar del descuento predeterminado de 40,00 que está disponible para la factura. April registra un pago único mediante el diario de pagos de proveedores. Ella escribe el proveedor para el pago y después abre ** liquidar las transacciones ** la página. Ella marca la factura y cambia el valor en ** importe de descuento por pronto pago ** el campo a ** ** 60.00.
| Marcar     | Utilizar el descuento por pronto pago | Comprobante   | Cuenta | Fecha      | Fecha de vencimiento  | Factura | Importe en divisa de la transacción | Divisa | Importe para liquidar |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Seleccionado | Normal            | Inv-10040 | 3051    | 29/6/2015 | 29/7/2015 | 10040   | 1.000,00                       | USD      | 940,00           |

La información de descuento aparece en la parte inferior de la página **Liquidar transacciones**.
|                              |           |
|------------------------------|-----------|
| Fecha del descuento por pronto pago           | 12/7/2015 |
| Importe de descuento por pronto pago         | 60,00     |
| Utilizar el descuento por pronto pago            | Normal    |
| Descuento por pronto pago aplicado          | 0,00      |
| Importe de descuento por pronto pago para aplicar | 60,00     |

April registra el diario de pagos. La factura se liquida con un pago de 940,00 y un descuento de 60,00.


