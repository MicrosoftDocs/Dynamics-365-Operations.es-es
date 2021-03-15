---
title: Pagos de impuestos y reglas de redondeo
description: En este artículo se explica cómo funciona la configuración de la regla de redondeo en las autoridades fiscales y el redondeo del saldo de impuestos durante el trabajo Liquidar y registrar impuestos.
author: ShylaThompson
manager: AnnBe
ms.date: 04/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: roschlom
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e8d7e402614b35a77a0283d31377a073b0a6b357
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990198"
---
# <a name="sales-tax-payments-and-rounding-rules"></a>Pagos de impuestos y reglas de redondeo

[!include [banner](../includes/banner.md)]

En este artículo se explica cómo funciona la configuración de la regla de redondeo en las autoridades fiscales y el redondeo del saldo de impuestos durante el trabajo Liquidar y registrar impuestos.

Periódicamente, los impuestos se deben notificar y pagar a las autoridades fiscales. Esto puede hacerse ejecutando el proceso de liquidación y registro de impuestos en la página Impuestos. Los impuestos para un período se liquidarán contra las cuentas de impuestos y el saldo de impuestos se registrará en la cuenta de liquidación Impuestos. El saldo de impuestos, que se registra en la cuenta de liquidación Impuestos, se podrá redondear según exijan las autoridades fiscales configurando una regla de redondeo en la página Impuestos. 

La diferencia de redondeo se registra en la cuenta de redondeo de impuestos seleccionada en el campo Cuentas para transacciones automáticas de la contabilidad general.

El ejemplo siguiente muestra cómo funciona la regla de redondeo en la autoridad fiscal.

## <a name="examples"></a>Ejemplo

El total de impuestos para un período muestra un saldo de crédito de -98.765,43. La entidad jurídica acumuló más impuestos de venta de los que canceló. Por lo tanto, la entidad debe dinero a la autoridad tributaria. 

La entidad jurídica desea utilizar un método de redondeo que redondee el saldo al 1,00 más cercano. El usuario a cargo de contabilizar las cuentas de los impuestos sobre las ventas debe seguir los siguientes pasos.

1. Haga clic en **Impuestos** > **Impuestos indirectos** > **Impuestos** > **Autoridades fiscales**.
2. En la ficha desplegable **General**, seleccione **Normal** en el campo **Forma de redondear**.
3. En el campo **Redondear**, escriba 1,00.
4. A la hora de pagar impuestos a la autoridad fiscal, vaya a **Impuesto** > **Declaraciones** > **Impuestos** > **Liquidar y registrar impuestos**. En la cuenta de liquidación de impuestos, puede ver que el monto de deuda tributaria **98 765,43** se redondea a **98 765**.

La siguiente tabla muestra cómo el monto 98 765,43 se redondea mediante cada uno de los métodos de redondeo disponibles en el campo **Forma de redondeo** en la página **Autoridades fiscales**.

> [!NOTE]                                                                                  
> Si el valor de redondeo se establece como 0,00, entonces:
>
> - Para el redondeo normal, el comportamiento de redondeo es el mismo que para **Redondeo = 0,01**.
> - Para **Opciones de forma de redondeo**, **A la baja**, **Al alza** y **Ventaja propia**, el comportamiento es el mismo que para **Redondeo = 1,00**.

| Opción Forma de redondeo                | Valor de redondeo = 0,01 | Valor de redondeo = 0,10 | Valor de redondeo = 1,00 | Valor de redondeo = 100,00 | Valor de redondeo = 0,00   |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|--------------------------|
| Normal                              | 98,765.43              | 98,765.40              | 98,765.00              | 98,800.00                | 98,765.43                |
| Hacia abajo                            | 98,765.43              | 98,765.40              | 98,765.00              | 98,700.00                | 98,765.00                |
| Redondeo al alza                         | 98,765.43              | 98,765.50              | 98,766.00              | 98,800.00                | 98,766.00                |
| Ventaja propia, para un saldo de crédito | 98,765.43              | 98,765.40              | 98,765.00              | 98,700.00                | 98,765.00                |
| Ventaja propia, para un saldo de débito  | 98,765.43              | 98,765.50              | 98,766.00              | 98,800.00                | 98,766.00                |

### <a name="normal-round-and-round-precision-is-001"></a>Redondeo normal y precisión de redondeo de 0,01

<table>
  <tr>
    <td>Redondeo
    </td>
    <td>Proceso de cálculo
    </td>
  </tr>
    <tr>
    <td>round(1,015, 0,01) = 1,02
    </td>
    <td>
      <ol>
        <li>round(1,015 / 0,01, 0) = round(101,5, 0) = 102
        </li>
        <li>102 * 0,01 = 1,02
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td>round(1,014, 0,01) = 1,01
    </td>
    <td> <ol>
        <li>round(1,014 / 0,01, 0) = round(101,4, 0) = 101
        </li>
        <li>101 * 0,01 = 1,01
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td>round(1,011, 0,02) = 1,02
    </td>
    <td> <ol>
        <li>round(1,011 / 0,02, 0) = round(50,55, 0) = 51
        </li>
        <li>51 * 0,02 = 1,02
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td>round(1,009, 0,02) = 1,00
    </td>
    <td> <ol>
        <li>round(1,009 / 0,02, 0) = round(50,45, 0) = 50
        </li>
        <li>50 * 0,02 = 1,00
        </li>
      </ol>
    </td>
  </tr>
</table>

> [!NOTE]                                                                                  
> Si selecciona Ventaja propia, el redondeo siempre se realizará a favor de la entidad jurídica. 

Para obtener más información, consulte los siguientes temas:
- [Visión general de impuestos](indirect-taxes-overview.md)
- [Crear un pago de impuestos](tasks/create-sales-tax-payment.md)
- [Crear transacciones de impuestos en documentos](tasks/create-sales-tax-transactions-documents.md)
- [Ver transacciones de impuestos registradas](tasks/view-posted-sales-tax-transactions.md)
- [Función round](https://msdn.microsoft.com/library/aa850656.aspx)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]