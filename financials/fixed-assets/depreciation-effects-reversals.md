---
title: "Efectos de depreciación con inversiones"
description: "En este artículo se describen las implicaciones potenciales de invertir una transacción de activo fijo."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetTrans
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2961
ms.assetid: 63a3ac92-c321-4379-a86a-b1b14915f340
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: d061ad8df477943259bff853d032c3df620e0b27
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="depreciation-effects-with-reversals"></a>Efectos de depreciación con inversiones

[!include[banner](../includes/banner.md)]


En este artículo se describen las implicaciones potenciales de invertir una transacción de activo fijo. 

Se pueden invertir las transacciones de activos fijos, así como las transacciones que están asociadas a un activo fijo. También se puede revocar una transacción invertida. 

Puede invertir o revocar una transacción que no era la transacción más reciente registrada para el activo en el libro. Para ello, se debe determinar primero si se ha registrado alguna transacción de depreciación después de la transacción que se desea invertir. El motivo de esta comprobación es que la depreciación no se calcula de nuevo al invertir una transacción, por lo que a menudo la depreciación es excesiva o insuficiente después de la inversión, tal como se muestra en los ejemplos. 

Para garantizar que la depreciación es correcta al invertir una transacción, no continúe con la inversión si recibe un mensaje durante el proceso en el que se indica que no se calculará de nuevo la depreciación. En su lugar, invierta primero la transacción de depreciación registrada después de la transacción que desea invertir y, a continuación, proceda con la inversión. No recibirá ningún mensaje sobre el nuevo cálculo de la depreciación y podrá continuar con la inversión. 

Los ejemplos siguientes muestran los cálculos que se efectúan si continúa a pesar del mensaje de advertencia sin invertir primero las transacciones de depreciación.

## <a name="example-1-depreciation-is-overstated"></a>Ejemplo 1: la depreciación es excesiva
Un activo fijo se configura con un tiempo de vida de 5 años y un tipo de depreciación lineal (60 períodos de depreciación). En este ejemplo, la depreciación es excesiva.
#### <a name="asset-transaction-history"></a>Historial de transacción del activo

| Fecha       | Tipo de transacción                                                          | Importe                                    |
|------------|---------------------------------------------------------------------------|-------------------------------------------|
| 1 de enero  | Adquisición                                                               | 59.000,00                                 |
| 1 de enero  | Ajuste de adquisición                                                    | 1.000,00                                  |
| 31 de enero | Depreciación (creada mediante una propuesta para un período de depreciación) | 1.000,00 Cálculo: valor neto (59.000 + 1.000) / Número de períodos de depreciación restantes (60) |

#### <a name="reversal-action"></a>Acción de inversión

| Fecha      | Tipo de transacción                | Importe    |
|-----------|---------------------------------|-----------|
| 1 de enero | Inversión del ajuste de adquisición | –1.000,00 |

#### <a name="depreciation-effect"></a>Efecto de la depreciación

| Fecha        | Tipo de transacción        | Importe                                                                                |
|-------------|-------------------------|---------------------------------------------------------------------------------------|
| 28 de febrero | Depreciación (propuesta) | 983,05 Cálculo: valor neto (59.000 - 1.000 depreciación) / Número de períodos de depreciación restantes (59) |

La depreciación se excede en 16,95 (1.000 - 983,05).

## <a name="example-2-depreciation-is-understated"></a>Ejemplo 2: Depreciación insuficiente
Un activo fijo se configura con un tiempo de vida de 5 años y un tipo de depreciación lineal (60 períodos de depreciación). En este ejemplo, la depreciación es insuficiente.
#### <a name="asset-transaction-history"></a>Historial de transacción del activo

| Fecha       | Tipo de transacción                                                          | Importe                                      |
|------------|---------------------------------------------------------------------------|---------------------------------------------|
| 1 de enero  | Adquisición                                                               | 59.000,00                                   |
| 1 de enero  | Ajuste de devaluación                                                     | 1.000,00                                    |
| 31 de enero | Depreciación (creada mediante una propuesta para un período de depreciación) | 966,67 Cálculo: valor neto (59.000 - 1.000) / Número de períodos de depreciación restantes (60) |

#### <a name="reversal-action"></a>Acción de inversión

| Fecha      | Tipo de transacción               | Importe    |
|-----------|--------------------------------|-----------|
| 1 de enero | Inversión de ajuste de devaluación | –1.000,00 |

#### <a name="depreciation-effect"></a>Efecto de la depreciación

| Fecha        | Tipo de transacción        | Importe                                                                                       |
|-------------|-------------------------|----------------------------------------------------------------------------------------------|
| 28 de febrero | Depreciación (propuesta) | 983,62 Cálculo: valor neto (59.000 - 966,67 depreciación) / Número de períodos de depreciación restantes (59) |

La depreciación es insuficiente por 16,95 (983,62 - 966,67).



<a name="see-also"></a>Consulte también
--------

[Depreciación de activos fijos](fixed-asset-depreciation.md)




