---
title: Función de ER CONTAINS
description: Este tema proporciona información general sobre cómo usar la función CONTAINS de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 02/11/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-02-01
ms.dyn365.ops.version: AX 10.0.18
ms.openlocfilehash: 81964681688cebf870bc9b6c59aff0b7fdd82449
ms.sourcegitcommit: 08ac570bece3e4ee4a0f632f51623e328536dfcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2021
ms.locfileid: "5557551"
---
# <a name="contains-er-function"></a>Función de ER CONTAINS

[!include [banner](../includes/banner.md)]

La función `CONTAINS` determina si la entrada especificada contiene el texto especificado. Devuelve un valor *Booleano* **VERDADERO** si la entrada especificada contiene el texto especificado. De lo contrario, la expresión devuelve un valor *Booleano* de **FALSE**.

## <a name="syntax"></a>Sintaxis

```vb
CONTAINS (input, search text)
```

## <a name="arguments"></a>Argumentos

`input`: *Cadena*

La ruta válida de un elemento de una fuente de datos del tipo *Cadena* o una constante de cadena, cuyo valor podría contener el segundo argumento.

`search text`: *Cadena*

La ruta válida de un elemento de un origen de datos del tipo de datos *Cadena* o una constante de cadena, cuyo valor podría estar contenido en el primer argumento.

## <a name="return-values"></a>Valores de retorno

*Booleano*

El valor *Booleano* resultante.

## <a name="usage-notes"></a>Notas de uso

Esta función se puede utilizar para especificar una expresión de condición de la función [FILTRAR](er-functions-list-filter.md) solo cuando la asignación relevante está configurada en [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) para acceder a [Microsoft Dataverse](../data-entities/data-integration-cds.md). De lo contrario, se lanza una excepción en el momento de diseño. El mensaje que recibe recomienda que utilice la función [DONDE](er-functions-list-where.md) en lugar de la función `FILTER`.

## <a name="example-1"></a>Ejemplo 1

La expresion `CONTAINS ("abc", "d")` devuelve **FALSO**, mientras que la expresión `CONTAINS ("abc", "C")` devuelve **VERDADERO**.

## <a name="example-2"></a>Ejemplo 2

La expresion `CONTAINS (model.InvoiceBase.Customer.PostalAddress.Address, "DEU")` devuelve **VERDADERO** si el valor del campo **Dirección** del origen de datos **modelo** contiene la cadena **DEU**. En caso contrario, devuelve **FALSO**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones lógicas](er-functions-category-logical.md)
