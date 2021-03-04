---
title: Función SPLITLIST de ER
description: En este tema se proporciona información acerca de cómo se usa la función SPLITLIST de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: d0f527dcf313a6a5e3b6601cac9a0f6495f66833
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680351"
---
# <a name="splitlist-er-function"></a>Función SPLITLIST de ER

[!include [banner](../includes/banner.md)]

La función `SPLITLIST` función divide la lista especificada en sublistas (o lotes), cada uno conteniendo el número de registros especificado. Devuelve luego el resultado como un nuevo valor *Lista de registros* que consiste en los lotes.

## <a name="syntax"></a>Sintaxis

```vb
SPLITLIST (list, number)
```

## <a name="arguments"></a>Argumentos

`list`: *Lista de registros*

La ruta válida de un origen de datos del tipo de datos *Lista de registros*.

`number`: *Entero*

El número máximo de registros por lote.

## <a name="return-values"></a>Valores de retorno

*Lista de registros*

La lista de registros resultante.

## <a name="usage-notes"></a>Notas de uso

La lista de lotes que se devuelve contiene los elementos siguientes:

 - **Valor:** *Lista*

    La lista de registros que pertenecen al lote actual.

- **Número de lote:** *Entero*

    El número del lote actual en la lista devuelta.

## <a name="example"></a>Ejemplo

En la siguiente ilustración, se crea un origen de datos **Líneas** como una lista de registro que tiene tres registros. Esta lista se divide en lotes, cada uno contiene hasta dos registros.

<a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

La siguiente ilustración muestra el diseño del formato. En este diseño de formato, se crean enlaces al origen de datos **Líneas** para generar una salida en formato XML. Esta salida presenta nodos individuales para cada lote y los registros en él.

<a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a>

La siguiente ilustración muestra el resultado cuando se ejecuta el formato diseñado.

<a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a>

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de lista](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]