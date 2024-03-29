---
title: Revalorización de divisa en una empresa de consolidación
description: En este artículo se describe cómo revalorizar la divisa en una empresa de consolidación.
author: aprilolson
ms.date: 10/02/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerExchAdjHist
audience: Application User
ms.reviewer: twheeloc
ms.custom: 62183
ms.assetid: 2762baaf-0c10-4ff7-8713-c506d6c29b98
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c05ef0d4d05d5113d3b858dafe49ee9c1c7211d9
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779672"
---
# <a name="currency-revaluation-in-a-consolidation-company"></a>Revalorización de divisa en una empresa de consolidación

[!include [banner](../includes/banner.md)]

Cuando se consolidan datos desde una divisa de contabilidad a otra, debe seguir ejecutando la revalorización de divisa si hay un cambio en tipos de cambio, para revalorizar los saldos de cuenta correctamente. Al consolidar por primera vez los datos, use la pestaña **Traducción de divisas** para seleccionar los tipos de cambio iniciales para su traducción durante el proceso de consolidación. Después de que se introduzcan un nuevo tipo de cambio (por ejemplo, el mes próximo), debe revalorizar los saldos de cuenta. Después se actualizarán los beneficios no realizados o las pérdidas, en función de la fecha y los nuevos tipo de cambio. En el ejemplo siguiente se muestran los asientos contables que se crean durante el proceso.

## <a name="company-setup"></a>Configuración de empresa
-   **Empresa de origen u operadora (USMF):** se usan dólares americanos (USD) como la divisa de contabilidad y de notificación.
-   **Empresa consolidada (CON):** se usan euros (EUR) como la divisa de contabilidad y de notificación.
    -   **Beneficio realizado**: cuenta contable 801500
    -   **Pérdida realizada:** cuenta contable 801600
    -   **Beneficio no realizado:** cuenta contable 801600
    -   **Pérdida no realizada:** cuenta contable 801400

## <a name="original-transactions"></a>Transacciones originales
### <a name="cash-receipt-transactions-in-usmf"></a>Transacciones de recibo de cobro en USMF

| Fecha       | Cuenta contable               | Divisa | Importe |
|------------|------------------------------|----------|--------|
| 11/10/2020 | 110110: efectivo                | USD      | 500    |
| 11/10/2020 | 130100: clientes | USD      | -500   |

## <a name="exchange-rates"></a>Tipos de cambio

| Desde divisa | A divisa | Fecha inicial | Tipo de cambio |
|---------------|-------------|------------|---------------|
| EUR           | USD         | 1/10/2020  | 200           |
| EUR           | USD         | 1/11/2020  | 150           |
| EUR           | USD         | 1/12/2017  | 100           |

## <a name="perform-the-consolidation-for-october-2020"></a>Realizar la consolidación para octubre de 2020
### <a name="balances-in-the-consolidation-company"></a>Saldos en la empresa de consolidación

| Cuenta contable | Divisa | Importe | Cálculo    |
|----------------|----------|--------|----------------|
| 110110         | EUR      | 250    | 500 USD × 50%  |
| 130100         | EUR      | -250   | -500 USD × 50% |

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2020-through-november-30-2020"></a>Realizar la revalorización de divisa para las cuentas a partir del 1 de octubre de 2020, hasta el 30 de noviembre de 2020
### <a name="balances-in-the-consolidation-company"></a>Saldos en la empresa de consolidación

| Cuenta contable | Divisa | Importe  | Cálculo                        |
|----------------|----------|---------|------------------------------------|
| 110110         | EUR      | 333.33  | Importe original de 500 × 66,6667%  |
| 130100         | EUR      | -333.33 | Importe original de -500 × 66,6667% |
| 801400         | EUR      | 83,33   | 333,33 – 250                       |
| 801600         | EUR      | -83.33  | -333,33 – (-250)                   |

Verá transacciones adicionales para los importes de divisa de notificación.

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2020-through-december-31-2020"></a>Realizar la revalorización de divisa para las cuentas a partir del 1 de octubre de 2020, hasta el 31 de diciembre de 2020
### <a name="balances-in-the-consolidation-company"></a>Saldos en la empresa de consolidación

| Cuenta contable | Divisa | Importe  | Cálculo                                          |
|----------------|----------|---------|------------------------------------------------------|
| 110110         | EUR      | 500,00  | Importe original de 500 × 1                           |
| 130100         | EUR      | -500,00 | Importe original de -500 × 1                          |
| 801400         | EUR      | 250     | 500 – 333,33 = 166,67 166,67 + 83,33 = 250           |
| 801600         | EUR      | -250    | -500 – (-333,33) = -166,67 -166,67 + (-83,33) = -250 |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
