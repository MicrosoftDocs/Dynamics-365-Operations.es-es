---
title: Convenciones de depreciación de activos fijos
description: Este tema proporciona información general de convenciones de depreciación de los activos fijos.
author: saraschi2
manager: AnnBe
ms.date: 03/21/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13891
ms.assetid: 36d1112d-921c-4fff-abe0-0ff2429848d3
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ad44282de9d999aa211548601eb416f4bdba2047
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1840778"
---
# <a name="fixed-asset-depreciation-conventions"></a>Convenciones de depreciación de activos fijos

[!include [banner](../includes/banner.md)]

Las convenciones de depreciación se usan para determinar cuándo y cómo la depreciación se calcula para tanto para el año en que se adquiere el activo fijo como para el año en que se cancela el activo fijo.

Las convenciones de depreciación se pueden asignar a la configuración para un libro del grupo de activos fijos. Para ver o asignar la convención de depreciación, en el área de instalación de activos fijos, seleccione los grupos **Activo fijo**. Seleccione el botón **Libros**. En este caso, las convenciones de depreciación que se asignan se usan como valores predeterminados cuando se crean los libros de activos fijos. Las convenciones de depreciación también se pueden establecer en un libro de activo fijo individual. Para ello, seleccione **Libros** en el área de instalación de activos fijos, y seleccione el botón **Grupos de activos fijos**.


|  Convención de amortizaciones  |   Descripción  |
|---------------------------|-----------------|
|           Ninguno            |  Los activos empiezan a depreciarse en la fecha <strong>Puesta en servicio</strong>.|
|         Medio año         |  Deduce un semestre de depreciación del primer año y del último año en el que se deprecia la propiedad. Deduce un año completo de depreciación por cada dos años durante el período de la recuperación. |
|        Mes completo         | Activos que tengan una fecha <strong>Puesta en servicio</strong> que ocurra en cualquier momento durante el inicio del mes comienzan a depreciarse el primer día ese mes. Los activos que se retiran en cualquier momento durante el mes se consideran retirados para la depreciación en el último día del mes anterior.  |
|        Medio trimestre        | Para calcular su deducción de depreciación para el año en que puso la propiedad en servicio, multiplique la depreciación de un año completo por el porcentaje para el trimestre en el que la propiedad se pone en servicio, como se muestra en la tabla siguiente.<table><thead><tr><th>Trimestre</th><th>Porcentaje</th></tr></thead><tbody><tr><td>Primera</td><td>87,5</td></tr><tr><td>Segunda</td><td>62,5</td></tr><tr><td>Tercera</td><td>37,5</td></tr><tr><td>Cuarta</td><td>12,5</td></tr></tbody></table>Una mitad del trimestre de depreciación se admite en el trimestre de disposición (o trimestre depreciado completamente). |
| Medio mes (primero de mes)  | Activos que tienen una fecha de <strong>Puesta en servicio</strong> en la primera mitad inicial del mes días (1 a 15) empiezan a depreciarse en el primer día del mes de la fecha de <strong>Puesta en servicio</strong>. Activos que tienen una fecha de <strong>Puesta en servicio</strong> en la segunda mitad inicial del mes días (16 a final del mes) empiezan a depreciarse en el primer día del mes después de la fecha de <strong>Puesta en servicio</strong>. Los activos que se retiran en la primera mitad del mes (del 1 al 15) se consideran retirados para la depreciación en el último día del mes anterior. Los activos que se retiran en la segunda mitad del mes (del 16 al final del mes) se consideran retirados para la depreciación en el último día del mes de la retirda. |
| Medio mes (el día 15 del mes) |  Para calcular su deducción de depreciación para el año en el que se la propiedad se pone en servicio, multiplique la depreciación de un año completo por una fracción. El numerador (número superior) de esta fracción es el número de meses completos en el año que la propiedad se encuentra en servicio, más el 1/2 o (0,5). El denominador (número inferior) es 12. Si se dispone de la propiedad antes de final del período de la recuperación, use el mismo método para calcular su deducción de depreciación para el año de disposición.   |
| Medio año (inicio de año) | Activos que tengan una fecha de <strong>Puesta en servicio</strong> en la primera mitad del año empiezan la depreciación el primer día del año (año completo). Activos que tengan una fecha de <strong>Puesta en servicio</strong> en la segunda mitad del año empiezan la depreciación a mitad de año.|
|   Medio año (próximo año)   |   Activos que tengan una fecha de <strong>Puesta en servicio</strong> en la primera mitad del año empiezan la depreciación el primer día del año (año completo). Activos que tengan una fecha de <strong>Puesta en servicio</strong> en la segunda mitad del año empiezan la depreciación el primer día del año siguiente. Los activos que se retiran en la primera mitad del año se consideran retirados para la depreciación en el último día del año anterior. Cualquier depreciación que se registre en el año actual se debe revertir o ajustar. Los activos se retiran en la segunda mitad del año se consideran retirados para la depreciación el último día del año de retirada.|

