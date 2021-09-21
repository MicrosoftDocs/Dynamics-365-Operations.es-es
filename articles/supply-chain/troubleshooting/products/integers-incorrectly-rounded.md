---
title: Enteros redondeados incorrectamente en los cálculos del modelo de configuración del producto
description: Los resultados enteros no siempre se redondean correctamente cuando se calculan los modelos de configuración del producto. Solucione el problema con un atributo decimal y un cálculo agregados.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: b17145d7d17cb784fe11b3fbf65ddf5aa5530f27
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477543"
---
# <a name="integers-incorrectly-rounded-when-product-configuration-models-are-calculated"></a>Enteros redondeados incorrectamente cuando se calculan los modelos de configuración del producto

## <a name="symptoms"></a>Síntomas

Este problema puede ocurrir cuando realiza la siguiente serie de acciones:

1. Configure estos atributos en un modelo de configuración de producción:

    - Entrada (entero)
    - Porcentaje (decimal)
    - Resultado (entero)

2. Cree un cálculo que tenga la siguiente expresión:

    *Resultado* = *Entrada* × *Porcentaje* ÷ 100

En este caso, el resultado entero no siempre se redondea correctamente. Por ejemplo, si la entrada es 1000 y el porcentaje es 2,40, espera que el resultado entero sea 24 porque el 2,40 por ciento de 1000 es 24 (o 24,00 en forma decimal). En cambio, el resultado se muestra como 23. Sin embargo, cuando el porcentaje es 2,39, el cálculo se redondea a 24 en lugar de 23. Cuando el porcentaje es 2,50, el cálculo se redondea a 25, como era previsto.

## <a name="cause"></a>Causa

Este problema se produce debido a la forma en que Microsoft Solver Foundation representa internamente números usando fracciones. Para el ejemplo anterior, el resultado del cálculo donde el porcentaje es 2,40 se representa como 27021597764222975 ÷ 1125899906842624 = 23.99999999999999911182158029987476766109466552734375. Cuando .NET lanza este valor como un número entero, devolverá 23.

## <a name="resolution"></a>Resolución

Este comportamiento no cambiará, porque otros escenarios dependen de él. Para el ejemplo anterior, puede solucionar el problema introduciendo un atributo decimal adicional y cálculos.

Por ejemplo, configure los siguientes atributos en un modelo de configuración de producción:

- Entrada (entero)
- Porcentaje (decimal)
- ResultDecimal (decimal)
- ResultInteger (entero)

A continuación, puede agregar los siguientes cálculos:

- *ResultDecimal* = *Entrada* × *Porcentaje* ÷ 100
- *ResultInteger* = *ResultDecimal*
