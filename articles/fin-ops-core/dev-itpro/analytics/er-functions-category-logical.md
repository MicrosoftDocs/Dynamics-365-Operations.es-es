---
title: Lista de funciones ER en la categoría lógica.
description: Este tema proporciona información sobre las funciones lógicas que son compatibles con los informes electrónicos (ER).
author: NickSelin
ms.date: 02/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 452eae2b710429215939b712b12fe156943d2ac5
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5749426"
---
# <a name="list-of-er-functions-in-the-logical-category"></a>Lista de funciones ER en la categoría lógica.

[!include [banner](../includes/banner.md)]

Las funciones lógicas de informes electrónicos (ER) se pueden utilizar para trabajar con valores lógicos para realizar más de una comparación en una sola expresión o probar múltiples condiciones. Este tema proporciona un resumen de estas funciones.

## <a name="list-of-supported-functions"></a>Lista de funciones permitidas.

| Función | Descripción |
|----------|-------------|
| [Y](er-functions-logical-and.md)                       | Esta función devuelve un valor *Booleano* de **TRUE** si todas las condiciones especificadas son ciertas. De lo contrario, la expresión devuelve un valor *Booleano* de **FALSE**. |
| [Caso](er-functions-logical-case.md)                     | Esta función evalúa el valor de la expresión especificada frente a las opciones alternativas especificadas y devuelve el resultado de la primera opción que es igual al valor de la expresión especificada. De lo contrario, devuelve un resultado predeterminado opcional, si se especifica un resultado predeterminado como el último argumento de la función llamada que no está precedida por una opción. El valor que se devuelve puede ser un valor de cualquiera de los tipos de datos admitidos. |
| [Contiene](er-functions-logical-contains.md)             | Esta función determina si la entrada especificada contiene el texto especificado. Devuelve un valor *Booleano* **VERDADERO** si la entrada especificada contiene el texto especificado. De lo contrario, la expresión devuelve un valor *Booleano* de **FALSE**. |
| [EndsWith](er-functions-logical-endswith.md)             | Esta función determina si la entrada especificada termina con el texto especificado. Devuelve un valor *Booleano* **VERDADERO** si la entrada especificada termina con el texto especificado. De lo contrario, la expresión devuelve un valor *Booleano* de **FALSE**. |
| [Si](er-functions-logical-if.md)                         | Esta función devuelve el primer valor especificado si se cumple la condición especificada. De lo contrario, devuelve el segundo valor especificado. El valor que se devuelve puede ser un valor de cualquiera de los tipos de datos admitidos. |
| [No](er-functions-logical-not.md)                       | Esta función devuelve el valor lógico invertido de la condición especificada como un valor *Booleano*. |
| [Or](er-functions-logical-or.md)                         | Esta función devuelve un valor *Booleano* de **FALSE** si todas las condiciones especificadas son falsas. Si cualquier condición especificada es cierta, esta función devuelve un valor *Booleano* de **TRUE**. |
| [StartsWith](er-functions-logical-startswith.md)         | Esta función determina si la entrada especificada comienza con el texto especificado. Devuelve un valor *Booleano* **VERDADERO** si la entrada especificada comienza con el texto especificado. De lo contrario, la expresión devuelve un valor *Booleano* de **FALSE**. |
| [ValueIn](er-functions-logical-valuein.md)               | Esta función determina si la entrada especificada coincide con algún valor de un elemento específico de la lista especificada. Devuelve un *Booleano* valor de **TRUE** si la entrada especificada coincide con el resultado de ejecutar la expresión especificada para al menos un registro de la lista especificada. De lo contrario, la expresión devuelve un valor *Booleano* de **FALSE**. |
| [ValueInLarge](er-functions-logical-valueinlarge.md)     | Esta función determina si la entrada especificada del tipo *Int64* o *Entero* coincide con algún valor de un elemento específico de la lista especificada. Devuelve un *Booleano* valor de **TRUE** si la entrada especificada coincide con el resultado de ejecutar la expresión especificada para al menos un registro de la lista especificada. De lo contrario, la expresión devuelve un valor *Booleano* de **FALSE**. |


## <a name="additional-resources"></a>Recursos adicionales

[Visión general de los informes electrónicos](general-electronic-reporting.md)

[Diseñador de fórmulas en los informes electrónicos](general-electronic-reporting-formula-designer.md)

[Idioma de fórmulas en los informes electrónicos](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]