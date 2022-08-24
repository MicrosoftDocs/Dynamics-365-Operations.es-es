---
title: Función ER Base64StringToContainer
description: En este artículo se proporciona información sobre cómo usar la función Base64StringToContainer de informes electrónicos (ER).
author: kfend
ms.date: 12/14/2020
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.17
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 96dfffc3d899f1106c6c931efb08c941f5b3c1a6
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291246"
---
# <a name="base64stringtocontainer-er-function"></a>Función ER Base64StringToContainer

[!include [banner](../includes/banner.md)]

La [función](er-formula-language.md#Functions) `BASE64STRINGTOCONTAINER` convierte la entrada especificada del tipo *Cadena* a un elemento de datos del tipo *[Contenedor](er-functions-category-container.md)*.

## <a name="syntax"></a>Sintaxis

```vb
BASE64STRINGTOCONTAINER (input)
```

## <a name="arguments"></a>Argumentos

`input`: *Cadena*

La ruta válida de un origen de datos de tipo *Cadena*.

## <a name="return-values"></a>Valores de retorno

*Contenedor*

El valor binario resultante en formato de objeto binario grande (BLOB).

## <a name="usage-notes"></a>Notas de uso

La excepción "El parámetro no es válido" aparece si la cadena de entrada no proporciona un grupo Base64 correcto de esquemas de codificación de binario a texto.

## <a name="example"></a>Ejemplo

Defina los siguientes orígenes de datos en la asignación de su modelo:

- El origen de datos raíz **DocuTypeGroupEnum** del tipo *Dynamics 365 for Operations/Enumeración* que se refiere a la enumeración de aplicación **DocuTypeGroup**
- El origen de datos raíz **Cliente** del tipo *Dynamics 365 for Operations/Registros de tabla* que se refiere a la tabla de aplicación **CustTable**
- El origen de datos **\#Medios** del tipo *Campo calculado* que se configura de la siguiente forma:

    - Se agrega como origen de datos secundaria del origen de datos **Cliente**.
    - Contiene la expresión `WHERE(@.'<Relations'.'<Documents', @.'<Relations'.'<Documents'.'docuType()'.TypeGroup = DocuTypeGroupEnum.Image)`.

- El origen de datos **\#MediaAsBase64String** del tipo *Campo calculado* que se configura de la siguiente forma:

    - Se agrega como origen de datos secundaria del origen de datos **Cliente.'\#Medios**.
    - Contiene la expresión `Customer.'#Media'.'getFileContentAsBase64String()'`.

- El origen de datos **\#BlobFomBase64** del tipo *Campo calculado* que se configura de la siguiente forma:

    - Se agrega como origen de datos secundaria del origen de datos **Cliente.'\#Medios**.
    - Contiene la expresión `Base64StringToContainer(Customer.'#Media'.'#MediaAsBase64String')'`.

En este ejemplo, el origen de datos **\#MediaAsBase64String** codifica el contenido binario del adjunto multimedia actual como texto que representa un grupo Base64 de esquemas de codificación de binario a texto. El origen de datos **\#BlobFomBase64** decodifica la cadena Base64 y devuelve un valor binario en formato BLOB.

![Orígenes de datos de ejemplo en la página del diseñador de asignación de modelo ER.](./media/er-functions-container-base64stringtocontainer-1.png)

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de contenedor](er-functions-category-container.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
