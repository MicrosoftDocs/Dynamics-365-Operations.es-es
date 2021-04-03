---
title: Función LOWER de ER
description: Este tema proporciona información general sobre cómo usar la función LOWER de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/11/2019
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
ms.openlocfilehash: e507a17f5125a3cba0d2434a1aaec0f04f0cd388
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562792"
---
# <a name="lower-er-function"></a><span data-ttu-id="c2b02-103">Función LOWER de ER</span><span class="sxs-lookup"><span data-stu-id="c2b02-103">LOWER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c2b02-104">La función `LOWER` devuelve la cadena de texto especificada como un valor de tipo *Cadena* después de convertirla a letras minúsculas.</span><span class="sxs-lookup"><span data-stu-id="c2b02-104">The `LOWER` function returns the specified text string as a *String* value after it has been converted to lowercase letters.</span></span>

## <a name="syntax"></a><span data-ttu-id="c2b02-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c2b02-105">Syntax</span></span>

```vb
LOWER (text)
```

## <a name="arguments"></a><span data-ttu-id="c2b02-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c2b02-106">Arguments</span></span>

<span data-ttu-id="c2b02-107">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="c2b02-107">`text`: *String*</span></span>

<span data-ttu-id="c2b02-108">Valor de tipo *Cadena* que especifica el texto.</span><span class="sxs-lookup"><span data-stu-id="c2b02-108">A *String* value that specifies the text.</span></span>

## <a name="return-values"></a><span data-ttu-id="c2b02-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="c2b02-109">Return values</span></span>

<span data-ttu-id="c2b02-110">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="c2b02-110">*String*</span></span>

<span data-ttu-id="c2b02-111">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="c2b02-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="c2b02-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c2b02-112">Example</span></span>

<span data-ttu-id="c2b02-113">`LOWER ("Sample")` devuelve **"sample"**.</span><span class="sxs-lookup"><span data-stu-id="c2b02-113">`LOWER ("Sample")` returns **"sample"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c2b02-114">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c2b02-114">Additional resources</span></span>

[<span data-ttu-id="c2b02-115">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="c2b02-115">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]