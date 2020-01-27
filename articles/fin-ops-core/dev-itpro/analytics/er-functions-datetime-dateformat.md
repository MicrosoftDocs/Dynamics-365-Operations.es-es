---
title: Función DATEFORMAT ER
description: En este tema se proporciona información sobre cómo usar la función DATEFORMAT de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/03/2019
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
ms.openlocfilehash: c1453be0c93764f9f0364206822a9e3899061a58
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917589"
---
# <a name="DATEFORMAT">Función DATEFORMAT ER</a>

[!include [banner](../includes/banner.md)]

La función `DATEFORMAT` devuelve un valor *Cadena* que presenta un valor determinado de fecha como texto en el formato especificado y en una [cultura](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) opcional especificada. Para obtener información acerca de los formatos admitidos, vea [estándar](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) y [personalizado](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).

## <a name="syntax-1"></a>Sintaxis 1

```
DATEFORMAT (date, format)
```

## <a name="syntax-2"></a>Sintaxis 2

```
DATEFORMAT (date, format, culture)
```

## <a name="arguments"></a>Argumentos

`date`: *Fecha*

Un valor de fecha / hora que representa la fecha a formatear.

`format`: *Cadena*

El formato de la cadena de salida.

`culture`: *Cadena*

La cultura a utilizar para formatear.

## <a name="return-values"></a>Valores de retorno

*Cadena*

El valor de cadena resultante.

## <a name="usage-notes"></a>Notas de uso

Cuando la cultura no se define como un argumento de la función llamada, el valor de `culture` está definido por el contexto de llamada. Por ejemplo, si la función `DATEFORMAT` se llama mediante el uso de la sintaxis 1 en un formato de informe electrónico (ER) para un elemento **ARCHIVO** configurado para usar la cultura alemana, la conversión se realizará utilizando la cultura alemana. El valor de `culture` predeterminado es **EN-US**.

## <a name="example-1"></a>Ejemplo 1

`DATEFORMAT (TODAY (), "dd-MM-yyyy")` devuelve la fecha del servidor actual, 24 de diciembre de 2015, como la cadena **“24-12-2015”**, basado en el formato personalizado especificado.

## <a name="example-2"></a>Ejemplo 2

`DATEFORMAT (SESSIONTODAY (), "d", "DE")` devuelve la fecha de sesión de la aplicación actual, 24 de diciembre de 2015, como la cadena **"24-12-2015"**, basado en la cultura alemana seleccionada y el formato especificado.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de fecha y de tiempo](er-functions-category-datetime.md)
