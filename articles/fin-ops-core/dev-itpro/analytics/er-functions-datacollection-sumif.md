---
title: Función SUMIF ER
description: Este tema proporciona información general sobre cómo usar la función SUMIF de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 04/27/2020
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
ms.openlocfilehash: 6f5069d197abf2e38d09012defeb982a9e5e1234
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565973"
---
# <a name="sumif-er-function"></a>Función SUMIF ER

[!include [banner](../includes/banner.md)]

La función `SUMIF` devuelve un valor *Real* que representa la suma de valores que fueron devueltos por las vinculaciones de elementos de formato que se recopiló cuando los elementos de formato se usaron para generar un documento saliente durante la ejecución del formato y que cumple la condición especificada. La condición consta de un rango clave y un valor clave.

## <a name="syntax"></a>Sintaxis

```vb
SUMIF (key name for summing, condition range, condition value)
```

## <a name="arguments"></a>Argumentos

`key name for summing`: *Cadena*

Un valor que devuelve la expresión que se ha configurado en la propiedad **Nombre de clave de datos recopilados** del componente de formato de informe electrónico (ER) para el cual el valor del enlace debe utilizarse para fines de suma.

La propiedad **Valor de clave de datos recopilados** se puede configurar para un componente **Secuencia** o un componente **Elemento XML** de un formato ER que reside bajo el componente **Común\\Archivo** donde la opción **Recopilar detalles de salida** está activada.

## <a name="return-values"></a>Valores de retorno

*Real*

El valor numérico resultante.

## <a name="usage-notes"></a>Notas de uso

Esta función devuelve un valor **0** (cero) cuando la opción **Recopilar detalles de salida** del componente actual **Común\\Archivo** está desactivado.

En el argumento `condition range`, el carácter comodín **"\*"** se puede usar para representar cualquier carácter múltiple.

En el argumento `condition value`, el carácter comodín **"\*"** se puede usar para representar cualquier carácter múltiple.

## <a name="example"></a>Ejemplo

Para obtener más información sobre cómo usar esta función, consulte la guía de tareas de los [datos de uso de ER del formato generados para contar y calcular](tasks/er-format-counting-summing-1.md), que forma parte del proceso empresarial de **Adquirir/desarrollar los componentes de servicio/solución de IT**.

Para obtener más información y ejemplos sobre el uso de esta función, consulte [Aplazar la ejecución de elementos de secuencia en formatos ER](er-defer-sequence-element.md#Example) y [Aplazar la ejecución de elementos XML en formatos ER](er-defer-xml-element.md#Example).

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de recopilación de datos](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]