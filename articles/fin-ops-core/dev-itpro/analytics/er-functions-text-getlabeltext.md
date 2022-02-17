---
title: Función GETLABELTEXT de ER
description: Este tema proporciona información general sobre cómo usar la función GETLABELTEXT de informes electrónicos (ER).
author: NickSelin
ms.date: 01/04/2022
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2022-01-01
ms.dyn365.ops.version: AX 10.0.25
ms.openlocfilehash: 911567a94b80c2b762a37e83d37fc500132edb18
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2022
ms.locfileid: "8075635"
---
# <a name="getlabeltext-er-function"></a>Función GETLABELTEXT de ER

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

La función `GETLABELTEXT` busca una etiqueta específica para devolver un valor de *[cadena](er-formula-supported-data-types-primitive.md#string)* que representa la traducción de la etiqueta especificada en el idioma especificado.

## <a name="syntax"></a>Sintaxis

```vb
GETLABELTEXT (label id, language)
```

## <a name="arguments"></a>Argumentos

### <a name="label-id"></a>Id. de etiqueta

`label id`: *Cadena* o *Id. de etiqueta*

El ID válido de uno de los siguientes tipos de etiquetas:

- Etiqueta de [informes electrónicos (ER)](general-electronic-reporting.md)
- Etiqueta de Microsoft Dynamics 365 Finance

#### <a name="usage-notes"></a>Notas de uso

Este argumento solo se puede definir como una constante, utilizando uno de los siguientes patrones admitidos:

- Para etiquetas ER:

    - `@"GER_LABEL:<LABEL ID>"`
    - `"GER_LABEL:<LABEL ID>"`

- Para etiquetas de finanzas:

    - `@"<LABEL ID>"`
    - `"<LABEL ID>"`

> [!NOTE]
> En tiempo de diseño, se muestra un mensaje de error de validación en la página **[Diseñador de fórmulas](er-advanced-formula-editor.md)** si no se puede encontrar ninguna etiqueta usando la ID de etiqueta provista.

### <a name="language"></a>Idioma

`language`: *Cadena*

Una cadena que representa un código de idioma.

#### <a name="usage-notes"></a>Notas de uso

Este argumento se puede definir como una constante de texto o como la ruta de un campo de origen de datos que devuelve un valor de *Cadena*.

> [!NOTE]
> En tiempo de diseño, se muestra un mensaje de error de validación si no se puede encontrar ningún código de idioma utilizando el argumento proporcionado `language` cuando se ha definido como una constante de texto.
>
> En tiempo de ejecución, la traducción para el idioma del sistema `EN-US` se devuelve para una etiqueta específica si no se ha encontrado ningún código de idioma mediante el uso del argumento `language`.

## <a name="return-values"></a>Valores de retorno

*Cadena*

El valor de texto resultante.

## <a name="example-1-system-label"></a><a name=example-1></a>Ejemplo 1: etiqueta del sistema

Las expresiones `GETLABELTEXT (@"SYS70894", "en-us")` y `GETLABELTEXT ("SYS70894", "en-us")` devuelven la traducción al inglés "Nothing to print" para la etiqueta de aplicación `@SYS70894`.

## <a name="example-2-er-label"></a><a name=example-2></a>Ejemplo 2: etiqueta de ER

Empieza a editar una [configuración](general-electronic-reporting.md#Configuration) de ER que se ha [derivado](er-quick-start2-customize-report.md#DeriveProvidedFormat) de la configuración **Transferencia de crédito ISO20022 (DE)**, introduce una nueva fuente de datos del tipo *[Campo calculado](er-calculated-field-ds-performance.md)* y configura la expresión `GETLABELTEXT(@"GER_LABEL:VendorName", "de")` para esta fuente de datos. En este caso, en tiempo de ejecución, la fuente de datos devuelve la traducción al alemán "Kreditorenname" para la etiqueta de ER `@GER_LABEL:VendorName` que se configuró inicialmente en la configuración base **Transferencia de crédito ISO20022 (DE)** de ER.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de texto](er-functions-category-text.md)

[Diseñar informes multilingües en informes electrónicos](er-design-multilingual-reports.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
