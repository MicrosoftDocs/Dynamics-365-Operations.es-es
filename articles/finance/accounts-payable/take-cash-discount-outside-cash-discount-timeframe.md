---
title: Obtener un descuento por pronto pago fuera del período de descuento por pronto pago
description: Este artículo proporciona dos escenarios que muestran cómo se puede aplicar un descuento por pronto pago incluso si el pago se realiza fuera del período de descuento por pronto pago.
author: angelad116
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14301
ms.assetid: bad10b7f-e550-4742-9261-8a094c9c624d
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 26b1eb5e542acf7496d1a0cf7196716a5de75e4e
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780594"
---
# <a name="take-a-cash-discount-outside-the-cash-discount-period"></a>Obtener un descuento por pronto pago fuera del período de descuento por pronto pago

[!include [banner](../includes/banner.md)]

Este artículo proporciona dos escenarios que muestran cómo se puede aplicar un descuento por pronto pago incluso si el pago se realiza fuera del período de descuento por pronto pago.

El 28 de junio, April crea una factura de 2.000,00 del proveedor 3052. La factura tiene un descuento por pronto pago del 1 por ciento si la factura se paga en 14 días.

## <a name="use-cash-discount-option--always"></a>Opción Utilizar descuento por pronto pago = Siempre
April crea un pago el 1 de julio, posterior a la fecha de descuento. April abre la página **Liquidar transacciones** para ver las transacciones que se pueden liquidar. 

April marca la factura para su pago. No se aplica ningún descuento por pronto pago, porque el pago es posterior a la fecha de descuento. Sin embargo, el proveedor ha proporcionado aprobación a April para obtener el descuento por pronto pago. Por lo tanto, April cambia el valor en el campo **Utilizar descuento por pronto pago** a **Siempre**.

| Marcar     | Utilizar el descuento por pronto pago | Comprobante   | Cuenta | Fecha del descuento por pronto pago | Fecha de vencimiento  | Factura | Importe en divisa de la transacción | Divisa | Importe para liquidar |
|----------|-------------------|-----------|---------|--------------------|-----------|---------|--------------------------------|----------|------------------|
| Seleccionado | Siempre            | Inv-10030 | 3052    | 28/6/2020          | 12/7/2020 | 10030   | -2.000,00                      | USD      | -1.980,00        |

La información de descuento aparece en la parte inferior de la página **Liquidar transacciones**.

| Campo                        | Valor     |
|------------------------------|-----------|
| Fecha del descuento por pronto pago           | 12/7/2020 |
| Importe de descuento por pronto pago         | -20,00    |
| Utilizar el descuento por pronto pago            | Siempre    |
| Descuento por pronto pago aplicado          | 0,00      |
| Importe de descuento por pronto pago para aplicar | -20,00    |

## <a name="date-to-use-for-calculating-discounts--selected-date"></a>Fecha que se va a usar para calcular los descuentos = Fecha seleccionada
Si se han registrado la factura y el pago, el descuento por pronto pago todavía se puede obtener si las transacciones se liquidan en la página **Liquidar transacciones**. April cambia el valor en **Fecha que se va a usar para calcular los descuentos** a **Fecha seleccionada**. Después escribe la fecha en el 28 de junio, que se encuentra en el período de descuento por pronto pago para la factura. Esta fecha se usa para calcular un descuento por pronto pago para la transacción. En la página **Liquidar transacciones abiertas**, April ve que, de forma predeterminada, aparece el descuento completo de 20,00. La línea de factura muestra que el importe a liquidar es de 1.980,00.

| Marcar          | Utilizar el descuento por pronto pago | Comprobante   | Cuenta | Fecha del descuento por pronto pago | Fecha de vencimiento  | Factura | Importe en divisa de la transacción | Divisa | Importe para liquidar |
|--------------|-------------------|-----------|---------|--------------------|-----------|---------|--------------------------------|----------|------------------|
| Seleccionado y resaltado | Normal    | Inv-10030 | 3052    | 28/6/2020         | 12/7/2020 | 10030   | -2.000,00                      | USD      | -1.980,00        |
| Seleccionado                 | Normal    | APP-10030 | 3052    | 15/7/2020          | 15/7/2020 |         | 500.00                         | USD      | 500.00           |

La información de descuento aparece en la parte inferior de la página **Liquidar transacciones abiertas**. El importe de descuento que se aplica es de 20,00, dado que el importe a liquidar para la factura es el importe predeterminado, 1.980,00.

| Campo                        | Valor     |
|------------------------------|-----------|
| Fecha del descuento por pronto pago           | 12/7/2020 |
| Importe de descuento por pronto pago         | -20,00    |
| Utilizar el descuento por pronto pago            | Normal    |
| Descuento por pronto pago aplicado          | 0,00      |
| Importe de descuento por pronto pago para aplicar | -20,00    |

April actualiza el valor del campo **Importe para liquidar** a **500,00**. El valor del campo **Importe de descuento por pronto pago para aplicar** se calculará como **5,05**.

| Marcar                     | Utilizar el descuento por pronto pago | Comprobante   | Cuenta | Fecha      | Fecha de vencimiento  | Factura | Importe en divisa de la transacción | Divisa | Importe para liquidar |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Seleccionado y resaltado | Normal            | Inv-10030 | 3052    | 28/6/2020 | 12/7/2020 | 10030   | 2,000.00                       | USD      | -500,00          |
| Seleccionado                 | Normal            | APP-10030 | 3052    | 15/7/2020 | 15/7/2020 |         | 500.00                         | USD      | 500.00           |

La información de descuento aparece en la parte inferior de la página **Liquidar transacciones abiertas**. El valor del campo **Importe de descuento por pronto pago para aplicar** es **5,05**, dado que el importe que liquidar para la factura se ha cambiado por el importe de pago, 500,00.

| Campo                        | Valor     |
|------------------------------|-----------|
| Fecha del descuento por pronto pago           | 12/7/2020 |
| Importe de descuento por pronto pago         | -20,00    |
| Utilizar el descuento por pronto pago            | Normal    |
| Descuento por pronto pago aplicado          | 0,00      |
| Importe de descuento por pronto pago para aplicar | -5,05     |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
