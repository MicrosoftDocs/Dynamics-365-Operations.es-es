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
ms.openlocfilehash: 6784384bac31d8c7cdc9c6f71b7dbab79c15a934
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041110"
---
# <span data-ttu-id="e158c-103"><a name="LOWER">Función LOWER de ER</a></span><span class="sxs-lookup"><span data-stu-id="e158c-103"><a name="LOWER">LOWER ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e158c-104">La función `LOWER` devuelve la cadena de texto especificada como un valor de tipo *Cadena* después de convertirla a letras minúsculas.</span><span class="sxs-lookup"><span data-stu-id="e158c-104">The `LOWER` function returns the specified text string as a *String* value after it has been converted to lowercase letters.</span></span>

## <a name="syntax"></a><span data-ttu-id="e158c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e158c-105">Syntax</span></span>

```vb
LOWER (text)
```

## <a name="arguments"></a><span data-ttu-id="e158c-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e158c-106">Arguments</span></span>

<span data-ttu-id="e158c-107">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="e158c-107">`text`: *String*</span></span>

<span data-ttu-id="e158c-108">Valor de tipo *Cadena* que especifica el texto.</span><span class="sxs-lookup"><span data-stu-id="e158c-108">A *String* value that specifies the text.</span></span>

## <a name="return-values"></a><span data-ttu-id="e158c-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="e158c-109">Return values</span></span>

<span data-ttu-id="e158c-110">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="e158c-110">*String*</span></span>

<span data-ttu-id="e158c-111">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="e158c-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="e158c-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e158c-112">Example</span></span>

<span data-ttu-id="e158c-113">`LOWER ("Sample")` devuelve **"sample"**.</span><span class="sxs-lookup"><span data-stu-id="e158c-113">`LOWER ("Sample")` returns **"sample"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e158c-114">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e158c-114">Additional resources</span></span>

[<span data-ttu-id="e158c-115">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="e158c-115">Text functions</span></span>](er-functions-category-text.md)
