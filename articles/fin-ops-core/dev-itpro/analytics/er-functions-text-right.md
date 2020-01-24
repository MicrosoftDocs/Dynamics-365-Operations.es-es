---
title: Función RIGHT de ER
description: Este tema proporciona información general sobre cómo usar la función RIGHT de informes electrónicos (ER).
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 01718f9b153c1d6c46d50a9b17e899ccfba16915
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916738"
---
# <span data-ttu-id="7d9d1-103"><a name="RIGHT">Función RIGHT de ER</a></span><span class="sxs-lookup"><span data-stu-id="7d9d1-103"><a name="RIGHT">RIGHT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7d9d1-104">La función `RIGHT` devuelve un valor de tipo *Cadena* que presenta el número especificado de caracteres desde el final de la cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="7d9d1-104">The `RIGHT` function returns a *String* value that presents the specified number of characters from the end of the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="7d9d1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7d9d1-105">Syntax</span></span>

```
RIGHT (text, number)
```

## <a name="arguments"></a><span data-ttu-id="7d9d1-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="7d9d1-106">Arguments</span></span>

<span data-ttu-id="7d9d1-107">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="7d9d1-107">`text`: *String*</span></span>

<span data-ttu-id="7d9d1-108">Valor de tipo *Cadena* que representa el texto original.</span><span class="sxs-lookup"><span data-stu-id="7d9d1-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="7d9d1-109">`number`: *Entero*</span><span class="sxs-lookup"><span data-stu-id="7d9d1-109">`number`: *Integer*</span></span>

<span data-ttu-id="7d9d1-110">El número de caracteres que se deben devolver desde el final del texto original.</span><span class="sxs-lookup"><span data-stu-id="7d9d1-110">The number of characters that must be returned from the end of the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="7d9d1-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="7d9d1-111">Return values</span></span>

<span data-ttu-id="7d9d1-112">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="7d9d1-112">*String*</span></span>

<span data-ttu-id="7d9d1-113">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="7d9d1-113">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="7d9d1-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7d9d1-114">Example</span></span>

<span data-ttu-id="7d9d1-115">`RIGHT ("Sample", 3)` devuelve **"ple"**.</span><span class="sxs-lookup"><span data-stu-id="7d9d1-115">`RIGHT ("Sample", 3)` returns **"ple"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7d9d1-116">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="7d9d1-116">Additional resources</span></span>

[<span data-ttu-id="7d9d1-117">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="7d9d1-117">Text functions</span></span>](er-functions-category-text.md)
