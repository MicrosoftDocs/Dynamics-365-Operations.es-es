---
title: Función de ENUMERATE de ER
description: En este artículo se proporciona información sobre cómo usar la función ENUMERATE de informes electrónicos (ER).
author: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: adaa2582e6dced428cf1f15a235ecbfd036362e6
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273260"
---
# <a name="enumerate-er-function"></a>Función de ENUMERATE de ER

[!include [banner](../includes/banner.md)]

La función `ENUMERATE` devuelve un valor *Lista de registros* nuevo que consiste en registros enumerados de la lista especificada.

## <a name="syntax"></a>Sintaxis

```vb
ENUMERATE (list)
```

## <a name="arguments"></a>Argumentos

`list`: *Lista de registros*

La ruta válida de un origen de datos del tipo de datos *Lista de registros*.

## <a name="return-values"></a>Valores de retorno

*Lista de registros*

La lista de registros resultante.

## <a name="usage-notes"></a>Notas de uso

La lista de registros enumerados que se devuelve expone los siguientes elementos adicionales:

- El registro de campos (componente **Valor**)
- El índice de registros actual (componente **Número**)

## <a name="example"></a>Ejemplo

En la ilustración siguiente, un origen de datos **Enumerado** se crea como una lista enumerada de registros de proveedor desde el origen de los datos **Proveedores** que hace referencia a la tabla VendTable.

<a href="./media/picture-enumerate-datasource.jpg"><img src="./media/picture-enumerate-datasource.jpg" alt="Enumerated data source" class="alignnone wp-image-290711 size-full" width="387" height="136" /></a>

La ilustración siguiente muestra el formato de informes electrónicos (ER). En este formato, se crean vínculos de datos para generar una salida en formato XML. Esta salida presenta proveedores individuales como nodos enumerados.

<a href="./media/picture-enumerate-format.jpg"><img src="./media/picture-enumerate-format.jpg" alt="Format that has data bindings" class="alignnone wp-image-290721 size-full" width="414" height="138" /></a>

La siguiente ilustración muestra el resultado cuando se ejecuta el formato diseñado.

<a href="./media/picture-enumerate-result.jpg"><img src="./media/picture-enumerate-result.jpg" alt="Result of running the format" class="alignnone wp-image-290731 size-full" width="567" height="176" /></a>

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de lista](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
