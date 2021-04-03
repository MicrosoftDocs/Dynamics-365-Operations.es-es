---
title: Lista de funciones ER en la categoría de recopilación de datos
description: Este tema proporciona información sobre las funciones de recopilación de datos que son compatibles con los informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: ba3a1f031a4a98592081b04a4128450aeb8218ef
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561743"
---
# <a name="list-of-er-functions-in-the-data-collection-category"></a>Lista de funciones ER en la categoría de recopilación de datos

[!include [banner](../includes/banner.md)]

Las funciones de recopilación de datos de informes electrónicos (ER) se utilizan para contar y sumar en un formato ER que se está ejecutando, en función de los datos de la salida que ya se ha generado en formato **Texto** o **Xml**. Este enfoque se utiliza para ayudar a mejorar el rendimiento de un formato ER que se ejecuta, para ingresar valores de totales acumulados en documentos generados y para otros fines. Este tema proporciona un resumen de estas funciones.

## <a name="list-of-supported-functions"></a>Lista de funciones permitidas.

| Función | Descripción |
|----------|-------------|
| [CollectedList](er-functions-datacollection-collectedlist.md) | Esta función devuelve un valor *Lista de registros* que contiene la lista de valores que fueron devueltos por la propiedad **Valor de clave de datos recopilados** de elementos de formato y recopilada cuando los elementos de formato se utilizaron para generar un documento saliente durante la ejecución del formato, y eso satisface las condiciones especificadas. Cada condición consta de un rango clave y un valor clave. |
| [CountIF](er-functions-datacollection-countif.md) | Esta función devuelve un valor *Entero* que representa el número de elementos de formato que se recopiló cuando los elementos de formato se usaron para generar un documento saliente durante la ejecución del formato y que cumple la condición especificada. La condición consta de un rango clave y un valor clave. |
| [CountIFs](er-functions-datacollection-countifs.md) | Esta función devuelve un valor *Entero* que representa el número de elementos de formato que se recopiló cuando los elementos de formato se usaron para generar un documento saliente durante la ejecución del formato y que cumple las condiciones especificadas. Cada condición consta de un rango clave y un valor clave. |
| [FormatElementName](er-functions-datacollection-formatelementname.md) | Esta función devuelve un valor *Cadena* que representa el nombre del elemento del formato ER actual. |
| [SumIF](er-functions-datacollection-sumif.md) | Esta función devuelve un valor *Real* que representa la suma de valores que fueron devueltos por las vinculaciones de elementos de formato que se recopiló cuando los elementos de formato se usaron para generar un documento saliente durante la ejecución del formato y que cumple la condición especificada. La condición consta de un rango clave y un valor clave. |
| [SumIFs](er-functions-datacollection-sumifs.md) | Esta función devuelve un valor *Real* que representa la suma de valores que fueron devueltos por las vinculaciones de elementos de formato que se recopiló cuando los elementos de formato se usaron para generar un documento saliente durante la ejecución del formato y que cumple las condiciones especificadas. Cada condición consta de un rango clave y un valor clave. |

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de los informes electrónicos](general-electronic-reporting.md)

[Diseñador de fórmulas en los informes electrónicos](general-electronic-reporting-formula-designer.md)

[Idioma de fórmulas en los informes electrónicos](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]