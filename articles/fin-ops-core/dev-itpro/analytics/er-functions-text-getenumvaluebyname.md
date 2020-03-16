---
title: Función GETENUMVALUEBYNAME de ER
description: Este tema proporciona información general sobre cómo usar la función GETENUMVALUEBYNAME de informes electrónicos (ER).
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 87613978c149b5d41aefc58f9896424229819626
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041201"
---
# <a name="GETENUMVALUEBYNAME">Función GETENUMVALUEBYNAME de ER</a>

[!include [banner](../includes/banner.md)]

La función `GETENUMVALUEBYNAME` busca un valor específico de tipo *Enum* en el origen de datos de enumeración especificado utilizando el nombre de enumeración especificado como un valor de tipo *Cadena*. Si el valor *Enum* se encuentra, la función lo devuelve. De lo contrario, la función devuelve el valor de enumeración **nulo**.

## <a name="syntax"></a>Sintaxis

```vb
GETENUMVALUEBYNAME (enumeration data source path, enumeration value text)
```

## <a name="arguments"></a>Argumentos

`enumeration data source path`: *Enumeración*

La ruta válida de un origen de datos de uno de los siguientes tipos de enumeración:

- Enumeración de modelo de informes electrónicos (ER)
- Enumeración de formato de ER
- Enumeración de Microsoft Dynamics 365 Finance

`enumeration value text`: *Cadena*

Un valor de cadena que representa el nombre de un valor de enumeración único.

## <a name="return-values"></a>Valores de retorno

*Enum* anulable

El valor de enumeración resultante.

## <a name="usage-notes"></a>Notas de uso

No se produce ninguna excepción si no se encuentra un valor de tipo *Enum* con el nombre del valor de enumeración especificado como un valor de tipo *Cadena*.

## <a name="example"></a>Ejemplo

En la siguiente ilustración, la enumeración **ReportDirection** se introduce en un modelo de datos. Tenga en cuenta que se definen etiquetas para los valores de enumeración.

<p><a href="./media/ER-data-model-enumeration-values.PNG"><img src="./media/ER-data-model-enumeration-values.PNG" alt="Available values for a data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

La siguiente ilustración muestra estos detalles:

- El origen de datos **$Direction** se configura en un informe de ER. Este origen de datos se configura en función de la enumeración del modelo **ReportDirection**.
- La expresión `$IsArrivals` está diseñada para usar el origen de datos **$Direction** basado en la enumeración del modelo como un parámetro de esta función.
- El valor de esta expresión de comparación es **TRUE**.

<a href="./media/ER-data-model-enumeration-usage.PNG"><img src="./media/ER-data-model-enumeration-usage.PNG" alt="Example of data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de texto](er-functions-category-text.md)
