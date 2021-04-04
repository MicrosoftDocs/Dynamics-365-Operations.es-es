---
title: Función NUMBERFORMAT de ER
description: En este tema se proporciona información sobre cómo usar la función NUMBERFORMAT de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: a05a1e1c4cdb050bff30ea4710da927a537da14c
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562718"
---
# <a name="numberformat-er-function"></a><span data-ttu-id="cbbd8-103">Función NUMBERFORMAT de ER</span><span class="sxs-lookup"><span data-stu-id="cbbd8-103">NUMBERFORMAT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cbbd8-104">La función `NUMBERFORMAT` devuelve un valor de tipo *Cadena* que presenta el número especificado en el formato especificado y en una [referencia cultural](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) especificada opcionalmente.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-104">The `NUMBERFORMAT` function returns a *String* value that presents the specified number in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="cbbd8-105">Para obtener información acerca de los formatos admitidos, vea [estándar](https://msdn.microsoft.com/library/dwhawy9k(v=vs.110).aspx) y [personalizado](https://msdn.microsoft.com/library/0c899ak8(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="cbbd8-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/dwhawy9k(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/0c899ak8(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="cbbd8-106">Sintaxis 1</span><span class="sxs-lookup"><span data-stu-id="cbbd8-106">Syntax 1</span></span>

```vb
NUMBERFORMAT (number, format)
```

## <a name="syntax-2"></a><span data-ttu-id="cbbd8-107">Sintaxis 2</span><span class="sxs-lookup"><span data-stu-id="cbbd8-107">Syntax 2</span></span>

```vb
NUMBERFORMAT (number, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="cbbd8-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="cbbd8-108">Arguments</span></span>

<span data-ttu-id="cbbd8-109">`number`: *Entero* o *Real*</span><span class="sxs-lookup"><span data-stu-id="cbbd8-109">`number`: *Integer* or *Real*</span></span>

<span data-ttu-id="cbbd8-110">Valor numérico que especifica el número al que se debe aplicar formato.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-110">A numeric value that specifies the number that must be formatted.</span></span>

<span data-ttu-id="cbbd8-111">`format`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="cbbd8-111">`format` : *String*</span></span>

<span data-ttu-id="cbbd8-112">Valor de tipo *Cadena* que representa el formato.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-112">A *String* value that represents the format.</span></span>

<span data-ttu-id="cbbd8-113">`culture`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="cbbd8-113">`culture`: *String*</span></span>

<span data-ttu-id="cbbd8-114">Valor de tipo *Cadena* que representa la referencia cultural que se debe utilizar para aplicar formato.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-114">A *String* value that represents the culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="cbbd8-115">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="cbbd8-115">Return values</span></span>

<span data-ttu-id="cbbd8-116">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="cbbd8-116">*String*</span></span>

<span data-ttu-id="cbbd8-117">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-117">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="cbbd8-118">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="cbbd8-118">Usage notes</span></span>

<span data-ttu-id="cbbd8-119">Si la referencia cultural no se define como un argumento de la función llamada, el contexto en el que se ejecuta esta función determina la cultura que se utiliza para aplicar formato a números.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-119">If the culture isn't defined as an argument of the called function, the context that this function is run in determines the culture that is used to format numbers.</span></span>

## <a name="example-1"></a><span data-ttu-id="cbbd8-120">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="cbbd8-120">Example 1</span></span>

<span data-ttu-id="cbbd8-121">Para la referencia cultural **EN-US**, `NUMBERFORMAT (0.45, "p")` devuelve **"45.00 %"** y `NUMBERFORMAT (10.45, "#")` devuelve **"10"**.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-121">For the **EN-US** culture, `NUMBERFORMAT (0.45, "p")` returns **"45.00 %"**, and `NUMBERFORMAT (10.45, "#")` returns **"10"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="cbbd8-122">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="cbbd8-122">Example 2</span></span>

<span data-ttu-id="cbbd8-123">`NUMBERFORMAT (10/3, "F2", "de")` devuelve **3,33**, mientras que `NUMBERFORMAT (10/3, "F2", "en-us")` devuelve **3.33**.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-123">`NUMBERFORMAT (10/3, "F2", "de")` returns **3,33**, whereas `NUMBERFORMAT (10/3, "F2", "en-us")` returns **3.33**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cbbd8-124">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="cbbd8-124">Additional resources</span></span>

[<span data-ttu-id="cbbd8-125">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="cbbd8-125">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]