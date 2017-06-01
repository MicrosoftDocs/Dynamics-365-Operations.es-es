---
title: Calcular el consumo de materiales
description: "En este artículo se proporciona información acerca de las diversas opciones relacionadas con el cálculo del consumo de materiales."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMDesignerEditBOM, BOMTable, ProdBOM
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 53401
ms.assetid: 9cff88e4-0425-4707-9178-3c2cb10df7c2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 1bd3168e80719c86e9a0541200fdb1608410c8f5
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="calculate-material-consumption"></a>Calcular el consumo de materiales

[!include[banner](../includes/banner.md)]


En este artículo se proporciona información acerca de las diversas opciones relacionadas con el cálculo del consumo de materiales. 

Las siguientes opciones relacionadas con el cálculo del consumo de materiales están disponibles en las fichas **Configuración** y **Consumo de pasos** en la ficha desplegable **Detalles de línea** de la página **Lista de materiales**.

## <a name="variable-and-constant-consumption"></a>Consumo constante y variable
En el campo **El consumo es** puede seleccionar si el consumo se debe calcular como una cantidad constante o una cantidad variable. Seleccione **Constante** si se precisa una cantidad o un volumen fijo para la producción, independientemente de la cantidad producida. Seleccione **Variable**, el ajuste predeterminado, si la cantidad necesaria de material en los productos terminados es proporcional al número de productos terminados que se produzcan.

## <a name="calculating-consumption-from-a-formula"></a>Cálculo del consumo a partir de una fórmula
En el campo **Fórmula** puede configurar varias fórmulas para calcular el consumo de materiales. Si usa el valor predeterminado **Estándar**, no se calcula el consumo a partir de una fórmula. Las fórmulas siguientes funcionan conjuntamente con los campos **Alto**, **Ancho**, **Profundidad**, **Densidad** y **Constante**:

-   Alto \* Constante
-   Alto \* Ancho \* Constante
-   Alto \* Ancho \* Profundidad \* Constante
-   (Alto \* Ancho \* Profundidad/Densidad) \* Constante

## <a name="rounding-up-and-multiples"></a>Redondeo y múltiplos
Juntos, los campos **Redondeo para arriba** y **Múltiplos** permiten redondear hacia arriba del valor del consumo de materiales. Por ejemplo, puede redondear el valor en función de la unidad de gestión de material en la que se selecciona la materia prima para producción. Las siguientes opciones están disponibles en el campo **Redondeo para arriba**: **Cantidad**, **Medida** y **Consumo**.

### <a name="quantity"></a>Cantidad

Si selecciona **Cantidad** como mecanismo de redondeo, la cantidad debe ser un múltiplo de la cantidad especificada. Por ejemplo, si se precisan números enteros, seleccione **1** en el campo **Múltiplos**. Los números se redondean a una cantidad divisible por 1.

### <a name="measurement"></a>Medida

Normalmente, se selecciona **Medida** como mecanismo de redondeo cuando la materia prima proviene de dimensiones específicas. Por ejemplo, hace falta una pieza de tubo de metal de dos metros para un producto terminado, y el tubo de metal se almacena en longitudes de 4,5 metros. En este caso, el mecanismo de redondeo **Medida** se puede usar para calcular cuántos tubos de metal se requieren para producir un número específico de piezas del producto terminado. En este ejemplo, el campo **Fórmula** se ha establecido en **Alto \* Constante**. El campo **Alto** se ha establecido en **2** para indicar la longitud del tubo necesaria para el producto terminado. El campo **Múltiplo** se ha establecido en **4,5** para indicar que el tubo se selecciona en longitudes de 4,5 metros. Este es el cálculo:

1.  Número de múltiplos necesarios para 10 piezas del producto terminado: 10 ÷ 2 = 5 piezas
2.  Consumo total: 4,5 × 5 = 22,5 metros de tubo de metal

Se asume que se desechan 0,5 metros de tubo por cada cinco piezas de tubo consumidas.

### <a name="consumption"></a>Consumo

Normalmente, se selecciona**Consumo** como mecanismo de redondeo cuando la materia prima se debe seleccionar en cantidades completas de una unidad de gestión de material del producto específico. Por ejemplo, se usan dos cuartos de pintura para producir una pieza de un producto terminado, y la pintura se selecciona en botes de 25 cuartos. En este caso, se puede usar el mecanismo de redondeo **Consumo** para redondear el consumo a números enteros de botes de 25 cuartos de galón. Este es el cálculo de la cantidad de pintura requerida si se deben producir 180 piezas del producto terminado:

1.  Pintura necesaria, sin la parte desechada: 180 × 2 = 360 cuartos de galón
2.  Número de botes: 360 ÷ 25 = 14,4, que se redondea a 15
3.  Pintura necesaria, con la parte desechada: 15 × 25 = 375 cuartos de galón

## <a name="step-consumption"></a>Consumo de pasos
El consumo de pasos se usa para calcular el consumo constante en intervalos de cantidad. Si selecciona **Consumo de pasos** en el campo **Fórmula** de la ficha **Configuración**, puede agregar información acerca de los pasos en la ficha **Consumo de pasos**. La cantidad consumida fija se puede configurar en intervalos de la cantidad producida. Por ejemplo, el consumo de pasos se ha configurado como se muestra en la siguiente tabla.

| Serie inicial | Cantidad |
|-------------|----------|
| 0,00        | 10,0000  |
| 100,00      | 20,0000  |
| 200,00      | 40,0000  |

La cantidad de la lista de materiales es 1 y la cantidad de producción es 110. La fórmula para el consumo es de (cantidad) de serie = Consumo. Dado que la cantidad de producción es 110, entra en la serie inicial 100. Así pues, la cantidad es 20.




