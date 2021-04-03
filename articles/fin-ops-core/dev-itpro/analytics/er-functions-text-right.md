---
title: Función RIGHT de ER
description: Este tema proporciona información general sobre cómo usar la función RIGHT de informes electrónicos (ER).
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
ms.openlocfilehash: 75255eccf4da468b0946253f7570b1621f905cd7
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570249"
---
# <a name="right-er-function"></a><span data-ttu-id="6717f-103">Función RIGHT de ER</span><span class="sxs-lookup"><span data-stu-id="6717f-103">RIGHT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6717f-104">La función `RIGHT` devuelve un valor de tipo *Cadena* que presenta el número especificado de caracteres desde el final de la cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="6717f-104">The `RIGHT` function returns a *String* value that presents the specified number of characters from the end of the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="6717f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6717f-105">Syntax</span></span>

```vb
RIGHT (text, number)
```

## <a name="arguments"></a><span data-ttu-id="6717f-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="6717f-106">Arguments</span></span>

<span data-ttu-id="6717f-107">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="6717f-107">`text`: *String*</span></span>

<span data-ttu-id="6717f-108">Valor de tipo *Cadena* que representa el texto original.</span><span class="sxs-lookup"><span data-stu-id="6717f-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="6717f-109">`number`: *Entero*</span><span class="sxs-lookup"><span data-stu-id="6717f-109">`number`: *Integer*</span></span>

<span data-ttu-id="6717f-110">El número de caracteres que se deben devolver desde el final del texto original.</span><span class="sxs-lookup"><span data-stu-id="6717f-110">The number of characters that must be returned from the end of the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="6717f-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="6717f-111">Return values</span></span>

<span data-ttu-id="6717f-112">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="6717f-112">*String*</span></span>

<span data-ttu-id="6717f-113">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="6717f-113">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="6717f-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6717f-114">Example</span></span>

<span data-ttu-id="6717f-115">`RIGHT ("Sample", 3)` devuelve **"ple"**.</span><span class="sxs-lookup"><span data-stu-id="6717f-115">`RIGHT ("Sample", 3)` returns **"ple"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6717f-116">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="6717f-116">Additional resources</span></span>

[<span data-ttu-id="6717f-117">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="6717f-117">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]