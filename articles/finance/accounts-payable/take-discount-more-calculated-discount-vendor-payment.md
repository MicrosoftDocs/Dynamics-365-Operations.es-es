---
title: Utilizar más que el descuento calculado para un pago de proveedor
description: Este artículo le guía por un escenario en el que se toma un descuento por pronto pago para un importe superior al descuento que estaba originalmente disponible en la factura. Este escenario podría surgir si una organización llega a un acuerdo con el proveedor para pagar un importe menor en la factura.
author: angelad116
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14281
ms.assetid: 7f0a4197-95dd-4969-ade9-154815cf659e
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cd74c6677f80a9075449908411350f1c81b95b02
ms.sourcegitcommit: 9c4638c4bb5b5f8adc7508542a0a2c3e1de5190c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2022
ms.locfileid: "9778367"
---
# <a name="take-more-than-the-calculated-discount-for-a-vendor-payment"></a>Utilizar más que el descuento calculado para un pago de proveedor

[!include [banner](../includes/banner.md)]

Este artículo le guía por un escenario en el que se toma un descuento por pronto pago para un importe superior al descuento que estaba originalmente disponible en la factura. Este escenario podría surgir si una organización llega a un acuerdo con el proveedor para pagar un importe menor en la factura. 

El proveedor 3.051 ofrece a Fabrikam un descuento por pronto pago del 4 por ciento si una factura se paga en siete días. El 29 de junio April introduce una factura de 1.000,00. El proveedor permite a April que aproveche un descuento de 60,00 en lugar del descuento predeterminado de 40,00 que está disponible para la factura. April registra un pago único mediante el diario de pagos de proveedores. Especifica el proveedor para el pago y luego abre la página **Liquidar transacciones**. Marca la factura y cambia el valor del campo **Importe de descuento por pronto pago** a **60,00**.

| Marcar     | Utilizar el descuento por pronto pago | Comprobante   | Cuenta | Fecha      | Fecha de vencimiento  | Factura | Importe en divisa de la transacción | Divisa | Importe para liquidar |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Seleccionado | Normal            | Inv-10040 | 3051    | 29/6/2020 | 29/7/2020 | 10040   | 1.000,00                       | USD      | 940,00           |

La información de descuento aparece en la parte inferior de la página **Liquidar transacciones**.

| Campo                        | Valor     |
|------------------------------|-----------|
| Fecha del descuento por pronto pago           | 12/7/2020 |
| Importe de descuento por pronto pago         | 60.00     |
| Utilizar el descuento por pronto pago            | Normal    |
| Descuento por pronto pago aplicado          | 0,00      |
| Importe de descuento por pronto pago para aplicar | 60,00     |

April registra el diario de pagos. La factura se liquida con un pago de 940,00 y un descuento de 60,00.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
