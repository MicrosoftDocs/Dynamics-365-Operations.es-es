---
title: Depreciación manual
description: Este artículo ofrece una visión general del método de depreciación manual.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13811
ms.assetid: b0e837c9-515a-4aed-9060-5ec94f37edeb
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 228e6c94042942a26793eb0bebc1186dd4767e7f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969038"
---
# <a name="manual-depreciation"></a>Depreciación manual

[!include [banner](../includes/banner.md)]

Este artículo ofrece una visión general del método de depreciación manual.

Si configura un perfil de depreciación de activos fijos y selecciona **Manual** en el campo **Método** de la página **Perfiles de depreciación**, la depreciación de los activos fijos asignados al perfil de depreciación vendrá determinada por el porcentaje que se especifique para cada intervalo del año natural. Los intervalos para los que configure porcentajes se registran de acuerdo con el valor que seleccione en el campo **Frecuencia de períodos** de la ficha desplegable **General**, en la página **Perfiles de depreciación**. Estos son los valores que se pueden seleccionar:

-   Anual
-   Mensual
-   Trimestral
-   Semestral
-   Diariamente

Tras seleccionar la frecuencia del período, haga clic en **Programaciones manuales** y configure porcentajes para cada intervalo de registro. Juntos, las programaciones manuales y los intervalos de registro definen el importe de depreciación, tal y como aparece en los siguientes ejemplos de este artículo. La depreciación manual siempre se calcula como un porcentaje del precio de adquisición. En la depreciación manual, los porcentajes especificados en los intervalos de la depreciación no tienen que sumar el 100 por cien. La depreciación manual es un método de depreciación flexible que normalmente se utiliza para definir un perfil de depreciación extraordinario en la página **Libros**, como una depreciación no periódica para objetivos especiales (por ejemplo, para cuestiones impositivas).

## <a name="examples"></a>Ejemplo
Precio de adquisición: 11.000,00 Valor residual previsto: 1.000,00 La siguiente tabla muestra los intervalos y los porcentajes que se configuran en la página **Programas de método de depreciación de activos fijos**.

| Número de intervalo | Porcentaje |
|-----------------|------------|
| 1               | 10,00      |
| 2               | 50,00      |
| 3               | 8,00       |

La tabla siguiente muestra cómo se calcula la depreciación para cada intervalo.

|  Número de intervalo | Cálculo del importe de depreciación anual | Valor neto en los libros al final del intervalo |
|------------------|-----------------------------------------------|-------------------------------------------|
| 1                | (11.000 – 1.000) × 10% = 1.000                | 10.000 (11.000 – 1.000)                   |
| 2                | (11.000 – 1.000) × 50% = 5.000                | 5.000 (10.000 – 5.000)                    |
| 3                | (11.000 – 1.000) × 8% = 800                   | 4.200 (5.000 – 800)                       |

Si selecciona **Mensual** en el campo **Frecuencia de períodos**, se configuran 12 intervalos de programación manual. La tabla que sigue muestra los importes de depreciación para los dos primeros intervalos.

| Intervalo | Importe de depreciación            |
|----------|--------------------------------|
| Enero  | (11.000 – 1.000) × 10% = 1.000 |
| Febrero | (11.000 – 1.000) × 50% = 5.000 |

Si selecciona <strong>Semestral</strong> en el campo *<strong><em>Frecuencia del período</em>*</strong>, se configuran dos intervalos de programación manual. La tabla que sigue muestra los importes de depreciación para estos dos primeros intervalos.

| Intervalo    | Importe de depreciación            |
|-------------|--------------------------------|
| 30 de junio     | (11.000 – 1.000) × 10% = 1.000 |
| 31 de diciembre | (11.000 – 1.000) × 50% = 5.000 |

El total de porcentajes de todos los intervalos no tiene que ser 100. No obstante, recibirá un mensaje si el valor en el campo **Porcentaje acumulado** en la página **Programas de método de depreciación de activos fijos** es distinto a **100**.



