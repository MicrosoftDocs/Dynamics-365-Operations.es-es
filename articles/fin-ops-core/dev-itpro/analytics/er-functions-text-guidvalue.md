---
title: Función GUIDVALUE de ER
description: Este artículo proporciona información general sobre cómo usar la función GUIDVALUE de informes electrónicos (ER).
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
ms.openlocfilehash: cb706a3607b4443c283a91c42c4dc1c389972e44
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285197"
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
