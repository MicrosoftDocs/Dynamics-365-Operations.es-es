---
title: Depreciación de factor
description: Este artículo ofrece una visión general del método de depreciación de factor.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13831
ms.assetid: 2b6c4fe4-02ff-4191-bcad-32f1f34c15f2
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8adfc91251ba1707c688fac6da04adaa9af1a47f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815701"
---
# <a name="factor-depreciation"></a>Depreciación de factor

[!include [banner](../includes/banner.md)]

Este artículo ofrece una visión general del método de depreciación de factor.

Los factores son porcentajes que se utilizan para depreciar activos. Cuando se configura un perfil de amortización de activos fijos y se selecciona **Factor** en el campo **Método** de la página **Métodos de depreciación**, puede configurar una depreciación progresiva, degresiva o lineal:

-   En la depreciación progresiva, el importe de depreciación aumenta cada período de depreciación.
-   En la depreciación degresiva, el importe de depreciación por período aumenta con el transcurso del tiempo.
-   En la depreciación lineal, la depreciación es la misma en cada período.

Las reglas y los ejemplos siguientes indican el modo en que puede configurar los factores para cada tipo de depreciación. 

> [!NOTE] 
> Cuando selecciona **Factor** en el campo **Método**, se muestran los campos **Factor** e **Intervalo**.

## <a name="progressive-depreciation"></a>Depreciación progresiva
El valor del campo **Factor** es mayor que **50**.

### <a name="example"></a>Ejemplo

El precio de adquisición es de 100.000, el factor es 70, el tiempo de vida es de 10 años, y la depreciación comienza el 1 de enero. Las cantidades de depreciación y de valor neto en los libros sólo se muestran los primeros seis años del tiempo de vida.

| Año | Período      | Importe de depreciación | Importe del valor neto en los libros |
|------|-------------|---------------------|-----------------------|
| 1    | 31 de diciembre | 307,69              | 99.692,31             |
| 2    | 31 de diciembre | 1.447,21            | 98.245,10             |
| 3    | 31 de diciembre | 3.104,50            | 95.140,60             |
| 4    | 31 de diciembre | 5.150,21            | 89.990,39             |
| 5    | 31 de diciembre | 7.522,95            | 82.467,44             |
| 6    | 31 de diciembre | 10.184,06           | 72.283,38             |

## <a name="digressive-depreciation"></a>Depreciación degresiva
El valor del campo **Factor** es menor que **50**.

### <a name="example"></a>Ejemplo

El precio de adquisición es de 100.000, el factor es 20, el tiempo de vida es de 10 años, y la depreciación comienza el 1 de enero. Las cantidades de depreciación y de valor neto en los libros sólo se muestran los primeros seis años del tiempo de vida.

| Año | Período      | Importe de depreciación | Importe del valor neto en los libros |
|------|-------------|---------------------|-----------------------|
| 1    | 31 de diciembre | 56.080,43           | 43.919,57             |
| 2    | 31 de diciembre | 10.665,70           | 33.253,87             |
| 3    | 31 de diciembre | 7.156,22            | 26.097,65             |
| 4    | 31 de diciembre | 5.538,06            | 20.559,59             |
| 5    | 31 de diciembre | 4.579,89            | 15.979,70             |
| 6    | 31 de diciembre | 3.937,36            | 12.042,34             |

## <a name="straight-line-depreciation"></a>Depreciación lineal
El valor del campo **Factor** es igual a **50**. En este caso, la depreciación es la misma en cada período y debe tener en cuenta las consecuencias de los valores que ha especificado en otros campos, como se describe en [Depreciación con amortización lineal de vida de servicio](straight-line-service-life-depreciation.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]