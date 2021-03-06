---
title: Función de ER STARTSWITH
description: En este tema se proporciona información sobre cómo usar la función STARTSWITH de informes electrónicos (ER).
author: NickSelin
ms.date: 02/11/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 50883bb604d2d1f2947545ce27fa02099e70b0e6
ms.sourcegitcommit: 17cee26b03f7b5afe8a089a0a9b2380e8d377d70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2021
ms.locfileid: "6048851"
---
# <a name="startswith-er-function"></a>Función de ER STARTSWITH

[!include [banner](../includes/banner.md)]

La función `STARTSWITH` determina si la entrada especificada comienza con el texto especificado. Devuelve un valor *Booleano* **VERDADERO** si la entrada especificada comienza con el texto especificado. De lo contrario, la expresión devuelve un valor *Booleano* de **FALSE**.

## <a name="syntax"></a>Sintaxis

```vb
STARTSWITH (input, start text)
```

## <a name="arguments"></a>Argumentos

`input`: *Cadena*

La ruta válida de un elemento de una fuente de datos del tipo *Cadena* o una constante de cadena, cuyo valor podría comenzar con el segundo argumento.

`start text`: *Cadena*

La ruta válida de un elemento de una fuente de datos del tipo de datos *Cadena* o una constante de cadena, cuyo valor podría estar al comienzo del segundo argumento.

## <a name="return-values"></a>Valores de retorno

*Booleano*

El valor *Booleano* resultante.

## <a name="usage-notes"></a>Notas de uso

Esta función se puede utilizar para especificar una expresión de condición de la función [FILTRAR](er-functions-list-filter.md) solo cuando la asignación relevante está configurada en [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) para acceder a [Microsoft Dataverse](/power-platform/admin/data-integrator). De lo contrario, se lanza una excepción en el momento de diseño. El mensaje que recibe recomienda que utilice la función [DONDE](er-functions-list-where.md) en lugar de la función `FILTER`.

## <a name="example-1"></a>Ejemplo 1

La expresion `STARTSWITH ("abc", "d")` devuelve **FALSO**, mientras que la expresión `STARTSWITH ("abc", "A")` devuelve **VERDADERO**.

## <a name="example-2"></a>Ejemplo 2

La expresion `STARTSWITH (model.InvoiceBase.Customer.PostalAddress.Address, "123 Coffee Street")` devuelve **VERDADERO** si el valor del campo **Dirección** del origen de datos **modelo** comienza con la cadena **123 Coffee Street**. En caso contrario, devuelve **FALSO**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones lógicas](er-functions-category-logical.md)
