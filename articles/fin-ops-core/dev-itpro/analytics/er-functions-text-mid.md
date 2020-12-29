---
title: Función MID de ER
description: Este tema proporciona información general sobre cómo usar la función MID de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 1d8a7d2e9beb0fc8724d26de0acaf1d61e3834c6
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680299"
---
# <a name="mid-er-function"></a><span data-ttu-id="de461-103">Función MID de ER</span><span class="sxs-lookup"><span data-stu-id="de461-103">MID ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="de461-104">La función `MID` devuelve un valor de tipo *Cadena* que presenta el número especificado de caracteres de la cadena especificada, empezando en la posición especificada.</span><span class="sxs-lookup"><span data-stu-id="de461-104">The `MID` function returns a *String* value that presents the specified number of characters from the specified string, starting at the specified position.</span></span>

## <a name="syntax"></a><span data-ttu-id="de461-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="de461-105">Syntax</span></span>

```vb
MID (text, starting position, number of characters)
```

## <a name="arguments"></a><span data-ttu-id="de461-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="de461-106">Arguments</span></span>

<span data-ttu-id="de461-107">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="de461-107">`text`: *String*</span></span>

<span data-ttu-id="de461-108">Valor de tipo *Cadena* que especifica el texto del que se devuelven los caracteres.</span><span class="sxs-lookup"><span data-stu-id="de461-108">A *String* value that specifies the text to return characters from.</span></span>

<span data-ttu-id="de461-109">`starting position`: *Entero*</span><span class="sxs-lookup"><span data-stu-id="de461-109">`starting position`: *Integer*</span></span>

<span data-ttu-id="de461-110">Valor de tipo *Entero* que especifica la posición del primer carácter que se debe devolver del texto especificado.</span><span class="sxs-lookup"><span data-stu-id="de461-110">An *Integer* value that specifies the position of the first character that must be returned from the specified text.</span></span>

<span data-ttu-id="de461-111">`number of characters`: *Entero*</span><span class="sxs-lookup"><span data-stu-id="de461-111">`number of characters`: *Integer*</span></span>

<span data-ttu-id="de461-112">Valor de tipo *Entero* que especifica el número de caracteres que se deben devolver desde la posición de inicio especificada.</span><span class="sxs-lookup"><span data-stu-id="de461-112">An *Integer* value that specifies the number of characters that must be returned, starting at the specified starting position.</span></span>

## <a name="return-values"></a><span data-ttu-id="de461-113">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="de461-113">Return values</span></span>

<span data-ttu-id="de461-114">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="de461-114">*String*</span></span>

<span data-ttu-id="de461-115">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="de461-115">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="de461-116">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="de461-116">Usage notes</span></span>

<span data-ttu-id="de461-117">Si el valor del argumento `starting position` es menor que 0 (cero), los caracteres que se devuelven se cuentan desde la primera posición en la cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="de461-117">If the value of the `starting position` argument is less than 0 (zero), the characters that are returned are counted from the first position in the specified string.</span></span>

<span data-ttu-id="de461-118">Si el valor del argumento `starting position` supera la longitud de la cadena especificada, se devuelve una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="de461-118">If the value of the `starting position` argument exceeds length of the specified string, an empty string is returned.</span></span>

## <a name="example"></a><span data-ttu-id="de461-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="de461-119">Example</span></span>

<span data-ttu-id="de461-120">`MID ("Sample", 2, 3)` devuelve **"amp"**.</span><span class="sxs-lookup"><span data-stu-id="de461-120">`MID ("Sample", 2, 3)` returns **"amp"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="de461-121">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="de461-121">Additional resources</span></span>

[<span data-ttu-id="de461-122">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="de461-122">Text functions</span></span>](er-functions-category-text.md)
