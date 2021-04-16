---
title: Función GUIDVALUE de ER
description: Este tema proporciona información general sobre cómo usar la función GUIDVALUE de informes electrónicos (ER).
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
ms.openlocfilehash: ec8222708b999a17794a396b5bf807dab037799d
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746396"
---
# <a name="guidvalue-er-function"></a>Función GUIDVALUE de ER

[!include [banner](../includes/banner.md)]

La función `GUIDVALUE` convierte la entrada especificada de tipo *Cadena* en un elemento de datos de tipo *GUID*.

## <a name="syntax"></a>Sintaxis

```vb
GUIDVALUE (input)
```

## <a name="arguments"></a>Argumentos

`input`: *Cadena*

La ruta válida de un origen de datos de tipo *Cadena*.

## <a name="return-values"></a>Valores de retorno

*GUID*

El valor del identificador único global (GUID) resultante.

## <a name="usage-notes"></a>Notas de uso

Para hacer una conversión en sentido contrario (es decir, convertir la entrada especificada con tipo de datos *GUID* en un elemento de datos de tipo *Cadena*), puede utilizar la función [TEXT()](er-functions-text-text.md).

## <a name="example"></a>Ejemplo

Defina los siguientes orígenes de datos en la asignación de su modelo:

- Un origen de datos **myID** de tipo *Campo calculado* que contiene la expresión `GUIDVALUE ("AF5CCDAC-F728-4609-8C8B- A4B30B0C0AA0")`
- Un origen de datos **Users** de tipo *Registros de tabla* que hace referencia a la tabla UserInfo

Después puede usar una expresión como `FILTER (Users, Users.objectId = myID)` para filtrar la tabla UserInfo por el campo **objectId** con tipo de datos *GUID*.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de texto](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]