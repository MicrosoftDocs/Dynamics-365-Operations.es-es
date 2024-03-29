---
title: Función de ER ENDSWITH
description: En este artículo se proporciona información sobre cómo usar la función ENDSWITH de informes electrónicos (ER).
author: kfend
ms.date: 02/11/2021
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2021-02-01
ms.dyn365.ops.version: AX 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 2608593238e5b2f738b452fb042837238f17e44e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9271625"
---
# <a name="endswith-er-function"></a>Función de ER ENDSWITH

[!include [banner](../includes/banner.md)]

La función `ENDSWITH` determina si la entrada especificada termina con el texto especificado. Devuelve un valor *Booleano* **VERDADERO** si la entrada especificada termina con el texto especificado. De lo contrario, la expresión devuelve un valor *Booleano* de **FALSE**.

## <a name="syntax"></a>Sintaxis

```vb
ENDSWITH (input, end text)
```

## <a name="arguments"></a>Argumentos

`input`: *Cadena*

La ruta válida de un elemento de una fuente de datos del tipo *Cadena* o una constante de cadena, cuyo valor podría terminar con el segundo argumento.

`start text`: *Cadena*

La ruta válida de un elemento de un origen de datos del tipo de datos *Cadena* o una constante de cadena, cuyo valor podría estar al final del segundo argumento.

## <a name="return-values"></a>Valores de retorno

*Booleano*

El valor *Booleano* resultante.

## <a name="usage-notes"></a>Notas de uso

Esta función se puede utilizar para especificar una expresión de condición de la función [FILTRAR](er-functions-list-filter.md) solo cuando la asignación relevante está configurada en [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) para acceder a [Microsoft Dataverse](/power-platform/admin/data-integrator). De lo contrario, se lanza una excepción en el momento de diseño. El mensaje que recibe recomienda que utilice la función [DONDE](er-functions-list-where.md) en lugar de la función `FILTER`.

## <a name="example-1"></a>Ejemplo 1

La expresion `ENDSWITH ("abc", "d")` devuelve **FALSO**, mientras que la expresión `ENDSWITH ("abc", "C")` devuelve **VERDADERO**.

## <a name="example-2"></a>Ejemplo 2

La expresion `ENDSWITH (model.InvoiceBase.Customer.PostalAddress.Address, "USA")` devuelve **VERDADERO** si el valor del campo **Dirección** del origen de datos **modelo** termina con la cadena **USA**. En caso contrario, devuelve **FALSO**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones lógicas](er-functions-category-logical.md)
