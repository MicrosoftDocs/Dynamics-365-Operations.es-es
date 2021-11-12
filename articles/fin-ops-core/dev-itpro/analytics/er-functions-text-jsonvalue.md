---
title: Función JSONVALUE de ER
description: Este tema proporciona información general sobre cómo usar la función JSONVALUE de informes electrónicos (ER).
author: NickSelin
ms.date: 10/25/2021
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
ms.openlocfilehash: ff33098e5be4dd9748d01d45b596360617305724
ms.sourcegitcommit: f8b597b09157d934b62bd5fb9a4d05b8f82b5a0e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2021
ms.locfileid: "7700072"
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
