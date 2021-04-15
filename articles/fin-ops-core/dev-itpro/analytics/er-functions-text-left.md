---
title: Función LEFT de ER
description: Este tema proporciona información general sobre cómo usar la función LEFT de informes electrónicos (ER).
author: NickSelin
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
ms.openlocfilehash: 69b1d95ea0e82b1947b665b0724cff6c5b319633
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746348"
---
# <a name="left-er-function"></a><span data-ttu-id="c2463-103">Función LEFT de ER</span><span class="sxs-lookup"><span data-stu-id="c2463-103">LEFT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c2463-104">La función `LEFT` devuelve un valor de tipo *Cadena* que representa la cantidad de caracteres especificados desde el principio de la cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="c2463-104">The `LEFT` function returns a *String* value that presents the specified number of characters from the start of the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="c2463-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c2463-105">Syntax</span></span>

```vb
LEFT (text, number)
```

## <a name="arguments"></a><span data-ttu-id="c2463-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c2463-106">Arguments</span></span>

<span data-ttu-id="c2463-107">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="c2463-107">`text`: *String*</span></span>

<span data-ttu-id="c2463-108">Valor de tipo *Cadena* que representa el texto original.</span><span class="sxs-lookup"><span data-stu-id="c2463-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="c2463-109">`number`: *Entero*</span><span class="sxs-lookup"><span data-stu-id="c2463-109">`number`: *Integer*</span></span>

<span data-ttu-id="c2463-110">El número de caracteres que se deben devolver desde el inicio del texto original.</span><span class="sxs-lookup"><span data-stu-id="c2463-110">The number of characters that must be returned from the start of the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="c2463-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="c2463-111">Return values</span></span>

<span data-ttu-id="c2463-112">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="c2463-112">*String*</span></span>

<span data-ttu-id="c2463-113">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="c2463-113">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="c2463-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c2463-114">Example</span></span>

<span data-ttu-id="c2463-115">`LEFT ("Sample", 3)` devuelve **"Sam"**.</span><span class="sxs-lookup"><span data-stu-id="c2463-115">`LEFT ("Sample", 3)` returns **"Sam"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c2463-116">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c2463-116">Additional resources</span></span>

[<span data-ttu-id="c2463-117">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="c2463-117">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]