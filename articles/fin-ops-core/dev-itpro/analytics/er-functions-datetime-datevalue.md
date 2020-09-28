---
title: Función DATEVALUE ER
description: Este tema proporciona información general sobre cómo usar la función DATEVALUE de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: 1970682db9a2278464aeff572599f0bfa6533e7d
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743600"
---
# <a name="datevalue-er-function"></a>Función DATEVALUE ER

[!include [banner](../includes/banner.md)]

La función `DATEVALUE` devuelve un valor *Fecha* que se convierte de un determinado valor de texto en el formato especificado y en una [cultura](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) opcionalmente especificada a un valor de fecha. Para obtener información acerca de los formatos admitidos, vea [estándar](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) y [personalizado](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).

## <a name="syntax-1"></a>Sintaxis 1

```vb
DATEVALUE (text, format)
```

## <a name="syntax-2"></a>Sintaxis 2

```vb
DATEVALUE (text, format, culture)
```

## <a name="arguments"></a>Argumentos

`text`: *Cadena*

Texto que representa el valor a formatear.

`format`: *Cadena*

El formato del texto proporcionado.

`culture`: *Cadena*

La cultura que se utiliza para formatear el texto dado.

## <a name="return-values"></a>Valores de retorno

*Fecha*

El valor de fecha resultante.

## <a name="usage-notes"></a>Notas de uso

Cuando la cultura no se define como un argumento de la función llamada, el valor de `culture` está definido por el contexto de llamada. Por ejemplo, si la función `DATEVALUE` se llama mediante el uso de la sintaxis 1 en un formato de informe electrónico (ER) para un elemento **ARCHIVO** configurado para usar la cultura alemana, la conversión se realizará utilizando la cultura alemana. El valor de `culture` predeterminado es **EN-US**.

## <a name="example-1"></a>Ejemplo 1

`DATEVALUE ("21-Dec-2016", "dd-MMM-yyyy")` devuelve la fecha **21 de diciembre de 2016** basada el formato especificado y la cultura predeterminada **EN-US** de la aplicación.

## <a name="example-2"></a>Ejemplo 2

`DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "IT")` devuelve el valor de la fecha **21 de enero de 2016**, según el formato y la cultura personalizados especificados.

Sin embargo, `DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "EN-US")` lanza una excepción para informar al usuario de que la cadena especificada no se reconoce como fecha válida para la cultura especificada.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de fecha y de tiempo](er-functions-category-datetime.md)
