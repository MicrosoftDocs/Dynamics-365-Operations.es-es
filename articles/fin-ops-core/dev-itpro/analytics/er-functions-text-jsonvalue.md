---
title: Función JSONVALUE de ER
description: Este artículo proporciona información general sobre cómo usar la función JSONVALUE de informes electrónicos (ER).
author: kfend
ms.date: 10/25/2021
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
ms.openlocfilehash: fba1141bce91fd7c9da3cd21aef13ce99329f379
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9267975"
---
# <a name="jsonvalue-er-function"></a>Función JSONVALUE de ER

[!include [banner](../includes/banner.md)]

La función `JSONVALUE` analiza los datos en formato JavaScript Object Notation (JSON) a los que se accede por la ruta especificada y extrae un valor escalar que se basa en el id. especificado. Luego devuelve el valor escalar extraído como valor *Cadena*.

## <a name="syntax"></a>Sintaxis

```vb
JSONVALUE (input, path)
```

## <a name="arguments"></a>Argumentos

`input`: *Cadena*

La ruta válida de un origen de datos de tipo *Cadena* que contiene datos JSON.

`path`: *Cadena*

El identificador de un valor escalar de datos JSON. Utilice una barra inclinada (/) para separar los nombres de los nodos JSON relacionados. Utilice el soporte (\[\]) para especificar el índice de un valor particular en una matriz JSON. Tenga en cuenta que la numeración de base cero se utiliza para este índice.

## <a name="return-values"></a>Valores de retorno

*Cadena*

El valor de texto resultante.

## <a name="example-1"></a>Ejemplo 1

El origen de datos **JsonField** contiene los siguientes datos en formato JSON: **{BuildNumber:7.3.1234.1", "KeyThumbprint":"7366E"}**. En este caso, la expresión `JSONVALUE (JsonField, "BuildNumber")` devuelve el siguiente valor de tipo *Cadena*: **"7.3.1234.1"**.

## <a name="example-2"></a>Ejemplo 2

El origen de datos **JsonField** del tipo *Campo calculado* contiene la expresión siguiente: `"{""workers"": [ {""name"": ""Adam"", ""age"": 30, ""emails"": [""AdamS@Contoso.com"", ""AdamS@Hotmail.com"" ]}, { ""name"": ""John"", ""age"": 21, ""emails"": [""JohnS@Contoso.com"", ""JohnS@Aol.com""]}]}"`

Esta expresión configurada para devolver un valor de [*Cadena*](er-formula-supported-data-types-primitive.md#string) que representa los siguientes datos en formato JSON.

```json
{
    "workers": [
        {
            "name": "Adam",
            "age": 30,
            "emails": [ "AdamS@Contoso.com", "AdamS@Hotmail.com" ]
        },
        {
            "name": "John",
            "age": 21,
            "emails": [ "JohnS@Contoso.com", "JohnS@Aol.com" ]
        }
    ]
}
```

En este caso, la expresión `JSONVALUE(json, "workers/[1]/emails/[0]")` devuelve el siguiente valor de tipo *Cadena*: `JohnS@Contoso.com`.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de texto](er-functions-category-text.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
