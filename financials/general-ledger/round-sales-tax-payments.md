---
title: Pagos de impuestos y reglas de redondeo
description: "En este artículo se explica cómo funciona la configuración de la regla de redondeo en las autoridades fiscales y el redondeo del saldo de impuestos durante el trabajo Liquidar y registrar impuestos."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 7ec117598a6a008e5b274179659b515824029874
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="sales-tax-payments-and-rounding-rules"></a>Pagos de impuestos y reglas de redondeo

[!include[banner](../includes/banner.md)]


En este artículo se explica cómo funciona la configuración de la regla de redondeo en las autoridades fiscales y el redondeo del saldo de impuestos durante el trabajo Liquidar y registrar impuestos.

Periódicamente, los impuestos se deben notificar y pagar a las autoridades fiscales. Esto puede hacerse ejecutando el proceso de liquidación y registro de impuestos en la página Impuestos. Los impuestos para un período se liquidarán contra las cuentas de impuestos y el saldo de impuestos se registrará en la cuenta de liquidación Impuestos. El saldo de impuestos, que se registra en la cuenta de liquidación Impuestos, se podrá redondear según exijan las autoridades fiscales configurando una regla de redondeo en la página Impuestos. 

La diferencia de redondeo se registra en la cuenta de redondeo de impuestos seleccionada en el campo Cuentas para transacciones automáticas de la contabilidad general.

El ejemplo siguiente muestra cómo funciona la regla de redondeo en la autoridad fiscal.

### <a name="example"></a>Ejemplo:

El total de impuestos para un período muestra un saldo de crédito de -98.765,43. La entidad jurídica acumuló más impuestos de venta de los que canceló. Por lo tanto, la entidad debe dinero a la autoridad tributaria. 

La entidad jurídica desea utilizar un método de redondeo que redondee el saldo al 1,00 más cercano. El usuario a cargo de contabilizar las cuentas de los impuestos sobre las ventas debe seguir los siguientes pasos.

1.  Haga clic en Impuestos &gt; Impuestos indirectos &gt; Impuestos &gt; Autoridades fiscales.
2.  En la ficha desplegable General, seleccione Normal en el campo Forma de redondear.
3.  En el campo Redondear, escriba 1,00.
4.  A la hora de pagar impuestos a la autoridad fiscal, abra la página Liquidar y registrar impuestos. (Haga clic en Impuestos &gt; Declaraciones &gt; Impuestos &gt; Liquidar y registrar impuestos).
5.  En la cuenta de liquidación de impuestos, el monto de deuda tributaria 98.765,43 se redondea a 98.765.

La siguiente tabla muestra cómo el monto 98.765,43 se redondea mediante cada uno de los métodos de redondeo disponibles en el campo Forma de redondeo en la página Autoridades fiscales.

| Opción Forma de redondeo                | Valor de redondeo = 0,01 | Valor de redondeo = 0,10 | Valor de redondeo = 1,00 | Valor de redondeo = 100,00 |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|
| Normal                              | 98.765,43              | 98,765,40              | 98.765,00              | 98.800,00                |
| Hacia abajo                            | 98.765,43              | 98.765,40              | 98.765,00              | 98.700,00                |
| Redondeo por arriba                         | 98.765,43              | 98.765,50              | 98.766,00              | 98,800.00                |
| Ventaja propia, para un saldo de crédito | 98.765,43              | 98.765,40              | 98.765,00              | 98.700,00                |
| Ventaja propia, para un saldo de débito  | 98.765,43              | 98.765,50              | 98.766,00              | 98.800,00                |

> [!NOTE]                                                                                  
> Si selecciona Ventaja propia, el redondeo siempre se realizará a favor de la entidad jurídica. 

Para obtener más información, consulte [Visión general de impuestos](indirect-taxes-overview.md). 




