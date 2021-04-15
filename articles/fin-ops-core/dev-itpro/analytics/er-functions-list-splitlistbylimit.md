---
title: Función SPLITLISTBYLIMIT de ER
description: En este tema se proporciona información sobre cómo usar la función SPLITLISTBYLIMIT de informes electrónicos (ER).
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: eb492560a453ec59bb82d24dd6717f409bd8b257
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745554"
---
# <a name="splitlistbylimit-er-function"></a>Función SPLITLISTBYLIMIT de ER

[!include [banner](../includes/banner.md)]

La función `SPLITLISTBYLIMIT` divide la lista especificada en una nueva lista de sublistas (lotes). El número de registros en cada lote se calcula dinámicamente. La función devuelve luego el resultado como un nuevo valor *Lista de registros* que consiste en los lotes.

## <a name="syntax"></a>Sintaxis

```vb
SPLITLISTBYLIMIT (list, limit value, limit source)
```

## <a name="arguments"></a>Argumentos

`list`: *Lista de registros*

La ruta válida de un origen de datos del tipo de datos *Lista de registros*.

`limit value`: *Entero* o *Real*

El valor máximo del límite que se utiliza para dividir la lista original en lotes.

`limit source`: *Campo*

La ruta válida de un campo del tipo *Entero* o *Real* en la lista especificada. El valor de este campo define el paso en el que se aumenta la suma total.

## <a name="return-values"></a>Valores de retorno

*Lista de registros*

La lista de registros resultante.

## <a name="usage-notes"></a>Notas de uso

La lista de lotes que se devuelve contiene los elementos siguientes:

- **Valor**: *Lista*

    La lista de registros que pertenecen al lote actual.

- **Número de lote**: *Entero*

    El número del lote actual en la lista devuelta.

El límite no se aplica a un único artículo de la lista original si el origen del límite supera el límite definido.

## <a name="example"></a>Ejemplo

La ilustración siguiente muestra un formato de informes electrónicos (ER).

<a href="./media/ger-splitlistbylimit-format.png"><img src="./media/ger-splitlistbylimit-format.png" alt="Format" class="alignnone size-full wp-image-1204063" width="396" height="195" /></a>

La siguiente ilustración muestra los orígenes de datos que se usan para el formato.

<a href="./media/ger-splitlistbylimit-datasources.png"><img src="./media/ger-splitlistbylimit-datasources.png" alt="Data sources" class="alignnone size-full wp-image-1204073" width="320" height="208" /></a>

La siguiente ilustración muestra el resultado cuando se ejecuta el formato. En este caso, la salida es una lista plana de artículos de mercancía.

<a href="./media/ger-splitlistbylimit-output.png"><img src="./media/ger-splitlistbylimit-output.png" alt="Output" class="alignnone size-full wp-image-1204083" width="462" height="204" /></a>

En las siguientes ilustraciones, se ha ajustado el mismo formato para que presente la lista de artículos de mercancías en lotes si un único lote debe incluir mercancías y el peso total no debe superar un límite de 9.

<a href="./media/ger-splitlistbylimit-format-1.png"><img src="./media/ger-splitlistbylimit-format-1.png" alt="Adjusted format" class="alignnone size-full wp-image-1204103" width="466" height="438" /></a>

<a href="./media/ger-splitlistbylimit-datasources-1.png"><img src="./media/ger-splitlistbylimit-datasources-1.png" alt="Data sources for the adjusted format" class="alignnone size-full wp-image-1204093" width="645" height="507" /></a>

La siguiente ilustración muestra el resultado cuando se ejecuta el formato ajustado.

<a href="./media/ger-splitlistbylimit-output-1.png"><img src="./media/ger-splitlistbylimit-output-1.png" alt="Output of the adjusted format" class="alignnone size-full wp-image-1204113" width="676" height="611" /></a>

> [!NOTE] 
> El límite no se aplica al último artículo de la lista original ya que el valor (**11**) del origen de su límite (**peso**) supera el límite definido (**9**). Para omitir las sublistas durante la generación del informe, use la función `WHERE` o la expresión **Habilitado** del elemento de formato correspondiente, según necesite.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de lista](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]