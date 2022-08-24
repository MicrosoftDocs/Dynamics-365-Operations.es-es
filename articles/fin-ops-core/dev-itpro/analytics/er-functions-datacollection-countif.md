---
title: Función COUNTIF ER
description: En este artículo se proporciona información sobre cómo usar la función COUNTIF de informes electrónicos (ER).
author: kfend
ms.date: 12/05/2019
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 61ac05d30845eae7c107c8a1edc66e4ff547c8a9
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274181"
---
# <a name="countif-er-function"></a>Función COUNTIF ER

[!include [banner](../includes/banner.md)]

La función `COUNTIF` devuelve un valor *Entero* que representa el número de elementos de formato que se recopiló cuando los elementos de formato se usaron para generar un documento saliente durante la ejecución del formato y que cumple la condición especificada. La condición consta de un rango clave y un valor clave.

## <a name="syntax"></a>Sintaxis

```vb
COUNTIF (condition range, condition value)
```

## <a name="arguments"></a>Argumentos

`condition range`: *Cadena*

Un valor que devuelve la expresión que se ha configurado en la propiedad **Nombre de clave de datos recopilados** de un componente de formato de informe electrónico (ER).

`condition value`: *Cadena*

Un valor que devuelve la expresión que se ha configurado en la propiedad **Valor de clave de datos recopilados** de un componente de formato de ER.

## <a name="return-values"></a>Valores de retorno

*Entero*

El valor numérico resultante.

## <a name="usage-notes"></a>Notas de uso

Las propiedades **Nombre de clave de datos recopilados** y **Valor de clave de datos recopilados** se pueden configurar para el componente **Secuencia** o el componente **Elemento XML** de un formato ER que reside bajo el componente **Común \\Archivo** donde la opción **Recopilar detalles de salida** está activada.

Esta función devuelve un valor **0** (cero) cuando la opción **Recopilar detalles de salida** del componente actual **Común \\Archivo** está desactivado.

En el argumento `condition range`, el carácter comodín **"\*"** se puede usar para representar cualquier carácter múltiple.

En el argumento `condition value`, el carácter comodín **"\*"** se puede usar para representar cualquier carácter múltiple.

## <a name="example"></a>Ejemplo

Para obtener más información sobre cómo usar esta función, consulte la guía de tareas de los [datos de uso de ER del formato generados para contar y calcular](tasks/er-format-counting-summing-1.md), que forma parte del proceso empresarial de **Adquirir/desarrollar los componentes de servicio/solución de IT**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de recopilación de datos](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
