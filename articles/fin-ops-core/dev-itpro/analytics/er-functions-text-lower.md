---
title: Función LOWER de ER
description: Este tema proporciona información general sobre cómo usar la función LOWER de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/11/2019
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
ms.openlocfilehash: b016feb0c907ef384eae91840791c357d61cf634
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916830"
---
# <span data-ttu-id="43659-103"><a name="LOWER">Función LOWER de ER</a></span><span class="sxs-lookup"><span data-stu-id="43659-103"><a name="LOWER">LOWER ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="43659-104">La función `LOWER` devuelve la cadena de texto especificada como un valor de tipo *Cadena* después de convertirla a letras minúsculas.</span><span class="sxs-lookup"><span data-stu-id="43659-104">The `LOWER` function returns the specified text string as a *String* value after it has been converted to lowercase letters.</span></span>

## <a name="syntax"></a><span data-ttu-id="43659-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="43659-105">Syntax</span></span>

```
LOWER (text)
```

## <a name="arguments"></a><span data-ttu-id="43659-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="43659-106">Arguments</span></span>

<span data-ttu-id="43659-107">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="43659-107">`text`: *String*</span></span>

<span data-ttu-id="43659-108">Valor de tipo *Cadena* que especifica el texto.</span><span class="sxs-lookup"><span data-stu-id="43659-108">A *String* value that specifies the text.</span></span>

## <a name="return-values"></a><span data-ttu-id="43659-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="43659-109">Return values</span></span>

<span data-ttu-id="43659-110">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="43659-110">*String*</span></span>

<span data-ttu-id="43659-111">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="43659-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="43659-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="43659-112">Example</span></span>

<span data-ttu-id="43659-113">`LOWER ("Sample")` devuelve **"sample"**.</span><span class="sxs-lookup"><span data-stu-id="43659-113">`LOWER ("Sample")` returns **"sample"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="43659-114">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="43659-114">Additional resources</span></span>

[<span data-ttu-id="43659-115">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="43659-115">Text functions</span></span>](er-functions-category-text.md)
