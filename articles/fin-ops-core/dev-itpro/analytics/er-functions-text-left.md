---
title: Función LEFT de ER
description: Este tema proporciona información general sobre cómo usar la función LEFT de informes electrónicos (ER).
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
ms.openlocfilehash: 8280a05ea180d9de499d87efa53eca8ca912b0e3
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915657"
---
# <span data-ttu-id="134d2-103"><a name="LEFT">Función LEFT de ER</a></span><span class="sxs-lookup"><span data-stu-id="134d2-103"><a name="LEFT">LEFT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="134d2-104">La función `LEFT` devuelve un valor de tipo *Cadena* que representa la cantidad de caracteres especificados desde el principio de la cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="134d2-104">The `LEFT` function returns a *String* value that presents the specified number of characters from the start of the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="134d2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="134d2-105">Syntax</span></span>

```
LEFT (text, number)
```

## <a name="arguments"></a><span data-ttu-id="134d2-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="134d2-106">Arguments</span></span>

<span data-ttu-id="134d2-107">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="134d2-107">`text`: *String*</span></span>

<span data-ttu-id="134d2-108">Valor de tipo *Cadena* que representa el texto original.</span><span class="sxs-lookup"><span data-stu-id="134d2-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="134d2-109">`number`: *Entero*</span><span class="sxs-lookup"><span data-stu-id="134d2-109">`number`: *Integer*</span></span>

<span data-ttu-id="134d2-110">El número de caracteres que se deben devolver desde el inicio del texto original.</span><span class="sxs-lookup"><span data-stu-id="134d2-110">The number of characters that must be returned from the start of the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="134d2-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="134d2-111">Return values</span></span>

<span data-ttu-id="134d2-112">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="134d2-112">*String*</span></span>

<span data-ttu-id="134d2-113">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="134d2-113">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="134d2-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="134d2-114">Example</span></span>

<span data-ttu-id="134d2-115">`LEFT ("Sample", 3)` devuelve **"Sam"**.</span><span class="sxs-lookup"><span data-stu-id="134d2-115">`LEFT ("Sample", 3)` returns **"Sam"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="134d2-116">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="134d2-116">Additional resources</span></span>

[<span data-ttu-id="134d2-117">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="134d2-117">Text functions</span></span>](er-functions-category-text.md)
