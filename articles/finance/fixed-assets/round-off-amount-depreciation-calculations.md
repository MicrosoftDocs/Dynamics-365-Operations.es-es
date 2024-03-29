---
title: Importe de redondeo para cálculos de depreciación
description: Este artículo describe el campo Depreciación de redondeo que se encuentra en las páginas de Configuración del libro.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBookTable, AssetDepBookTable
audience: Application User
ms.reviewer: kfend
ms.custom: 13931
ms.assetid: faf7db87-046f-41d1-9baf-0df66e373e97
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a93842f7cca483df89188695c945edf77e118cef
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8870115"
---
# <a name="round-off-amount-for-depreciation-calculations"></a>Importe de redondeo para cálculos de depreciación

[!include [banner](../includes/banner.md)]

Este artículo describe el campo **Depreciación de redondeo** que se encuentra en las páginas de **Configuración del libro**.

Los importes de depreciación de redondeo se establecen para cada libro. Los importes de depreciación de redondeo se usan en el perfil de depreciación de activos fijos que muestra la depreciación futura y el valor del activo fijo, y también en las propuestas de depreciación. Introduzca el importe más bajo de la depreciación permitido para el libro. 

Independientemente del redondeo configurado, el importe de depreciación en el período de la última depreciación no se redondea. Al final del período de la última depreciación, el valor del activo fijo debe ser 0 (cero) o el valor residual, si se usa el valor residual.

### <a name="example"></a>Ejemplo

La depreciación sin redondeo se calcula como 2.444,44. En función de la configuración del redondeo, se sugieren distintos importes, como se indica en la tabla siguiente.

| Método de redondeo | Importe de depreciación |
|-----------------|---------------------|
| Redondeo 0,1    | 2.444,40            |
| Redondeo 1,00   | 2.444,00            |
| Redondeo 10,00  | 2.440,00            |
| Redondeo 100,00 | 2.400,00            |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
