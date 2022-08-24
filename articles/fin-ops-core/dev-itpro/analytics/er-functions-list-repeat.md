---
title: Función REPEAT de ER
description: Este artículo proporciona información general sobre cómo usar la función REPEAT de informes electrónicos (ER).
author: NickSelin
ms.date: 08/01/2022
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2022-06-01
ms.dyn365.ops.version: AX 10.0.29
ms.openlocfilehash: c56139a3c63b03f907b1dcbf4365990d2a13c35a
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220699"
---
# <a name="repeat-er-function"></a>Función REPEAT de ER

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

La función `REPEAT` crea un registro que contiene el campo que tiene un valor que coincide con la entrada especificada. Luego devuelve una nueva *Lista de registros* de un registro que se repite un número determinado de veces.

## <a name="syntax"></a>Sintaxis

```vb
REPEAT (item, number)
```

## <a name="arguments"></a>Argumentos

`item`: cualquier tipo de datos [primitivo](er-formula-supported-data-types-primitive.md) o [compuesto](er-formula-supported-data-types-composite.md) compatible

El valor a repetir.

`number`: *Entero*

El número de repeticiones.

## <a name="return-values"></a>Valores de retorno

*Lista de registros*

La lista de registros resultante.

## <a name="usage-notes"></a>Notas de uso

La lista de registros repetidos que se devuelve expone los siguientes campos:

- El valor especificado (campo `Item`)
- El índice de registros actual (campo `Number`)

> [!NOTE]
> Debido a que la numeración basada en uno se usa para esta función, el campo `Number` tiene el valor **1** para el primer registro de la lista resultante.

Puede usar esta función para multiplicar los datos existentes para que pueda realizar pruebas de rendimiento y volumen de soluciones de [Informes electrónicos (ER)](general-electronic-reporting.md) mediante el uso de la [Regression Suite Automation Tool (RSAT)](../perf-test/rsat/rsat-overview.md).

## <a name="example"></a>Ejemplo

Quiere generar un documento en formato XML que debe contener tantos elementos XML `Party` que especifique en un campo de entrada de datos en el cuadro de diálogo en tiempo de ejecución, antes de que comience la ejecución de un formato ER.

La siguiente ilustración muestra el [formato](er-overview-components.md#format-component) ER. En este formato, se agrega el elemento XML `Party` único para exponer las propiedades de una sola parte.

<a href="./media/er-repeat-function-1.png"><img src="./media/er-repeat-function-1.png" alt="Format structure on the Format tab of the Format designer page." class="alignnone size-full" width="929" height="548" /></a>

La siguiente ilustración muestra las siguientes fuentes de datos configuradas:

- El origen de datos `Party` que representa a una sola parte. El campo `Party.Value` se utiliza para exponer un único valor de texto.
- El [oigen de datos](er-user-input-parameter-data-sources.md) `NumberOfRepeats` que se utiliza para ofrecer un campo de entrada de datos en el cuadro de diálogo en tiempo de ejecución, para que pueda especificar el número de partes que deben ingresarse en el documento generado.
- El origen de datos `Party2` que repite el registro `Party` el número de veces que especificó en el origen de datos `NumberOfRepeats`.

<a href="./media/er-repeat-function-2.png"><img src="./media/er-repeat-function-2.png" alt="Configured data sources on the Mapping tab of the Format designer page." class="alignnone size-full" width="1044" height="411" /></a>

La siguiente ilustración muestra enlaces de datos del formato ER editable que se crean para generar resultados en formato XML. Esta salida presenta partes individuales como nodos enumerados.

<a href="./media/er-repeat-function-3.png"><img src="./media/er-repeat-function-3.png" alt="Configured data bindings on the Mapping tab of the Format designer page." class="alignnone size-full" width="1051" height="417" /></a>

La siguiente ilustración muestra el resultado cuando se ejecuta el formato diseñado y el valor de la fuente de datos `NumberOfRepeats` se especifica como **5**.

<a href="./media/er-repeat-function-4.png"><img src="./media/er-repeat-function-4.png" alt="Result of running the format on a new web browser tab." class="alignnone wp-image-290711 size-full" width="400" height="380" /></a>

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de lista](er-functions-category-list.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
