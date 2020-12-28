---
title: Solucionar problemas del configurador de productos
description: Este tema describe cómo solucionar problemas que pueden surgir al trabajar con configurador del producto.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: dacc7205eaf2084f6fbd3be9d8ac0572f9e1bcde
ms.sourcegitcommit: 8eefb4e14ae0ea27769ab2cecca747755560efa3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "4516871"
---
# <a name="troubleshoot-the-product-configurator"></a>Solucionar problemas del configurador de productos

Este tema describe cómo solucionar problemas que pueden surgir al trabajar con el configurador del producto.

## <a name="item-text-is-overwritten-when-i-configure-a-product-on-a-sales-order-line"></a>El texto del artículo se sobrescribe cuando configuro un producto en una línea de orden de venta.

### <a name="issue-description"></a>Descripción del problema

Este problema ocurre cuando crea una línea de orden de venta para un artículo configurable y luego modifica el texto del artículo. Cuando configura el elemento y luego selecciona **Aceptar**, el texto se sobrescribe con el texto estándar.

### <a name="issue-resolution"></a>Solución del problema

Este comportamiento es esperado. El campo de texto incluye el nombre de la variante, que se completa solo después de configurar la línea. Por lo tanto, debe cambiar el texto después de haber configurado la línea, no antes.

## <a name="integer-attributes-are-incorrectly-rounded-when-product-configuration-models-are-calculated"></a>Los atributos enteros se redondean incorrectamente cuando se calculan los modelos de configuración del producto.

### <a name="issue-description"></a>Descripción del problema

Este problema puede ocurrir cuando realiza la siguiente serie de acciones:

1. Configure los siguientes atributos en un modelo de configuración de producción:

    - Entrada (entero)
    - Porcentaje (decimal)
    - Resultado (entero)

2. Cree un cálculo que tenga la siguiente expresión:

    *Resultado* = *Entrada* × *Porcentaje* ÷ 100

En este caso, el resultado entero no siempre se redondea correctamente. Por ejemplo, la entrada es 1000 y el porcentaje es 2,40. Por lo tanto, espera que el resultado entero sea 24, porque el 2,40 por ciento de 1000 es 24 (o 24,00 en forma decimal). En cambio, el resultado se muestra como 23. Sin embargo, cuando el porcentaje es 2,39, el cálculo se redondea a 24 en lugar de 23. Cuando el porcentaje es 2,50, el cálculo se redondea a 25, como era previsto.

### <a name="issue-resolution"></a>Solución del problema

Este problema se produce debido a la forma en que Microsoft Solver Foundation representa internamente números usando fracciones. Para el ejemplo anterior, el resultado del cálculo donde el porcentaje es 2,40 se representa como 27021597764222975 ÷ 1125899906842624 = 23.99999999999999911182158029987476766109466552734375. Cuando .NET lanza este valor como un número entero, devolverá 23.

Este comportamiento no cambiará, porque otros escenarios dependen de él. Para el ejemplo anterior, puede solucionar el problema introduciendo un atributo decimal adicional y un cálculo.

Por ejemplo, puede configurar los siguientes atributos en un modelo de configuración de producción:

- Entrada (entero)
- Porcentaje (decimal)
- ResultDecimal (decimal)
- ResultInteger (entero)

A continuación, puede agregar los siguientes cálculos:

- *ResultDecimal* = *Entrada* × *Porcentaje* ÷ 100
- *ResultInteger* = *ResultDecimal*
