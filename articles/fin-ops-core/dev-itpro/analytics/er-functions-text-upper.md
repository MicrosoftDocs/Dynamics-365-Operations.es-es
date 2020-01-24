---
title: Función UPPER de ER
description: Este tema proporciona información general sobre cómo usar la función UPPER de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: ed862ab823cfc3539c420d3066c9397e1e6d870e
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916692"
---
# <span data-ttu-id="aa8ee-103"><a name="UPPER">Función UPPER de ER</a></span><span class="sxs-lookup"><span data-stu-id="aa8ee-103"><a name="UPPER">UPPER ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="aa8ee-104">La función `UPPER` devuelve la cadena de texto especificada como un valor de tipo *Cadena* después de convertirla a letras mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="aa8ee-104">The `UPPER` function returns the specified text string as a *String* value after it has been converted to uppercase letters.</span></span>

## <a name="syntax"></a><span data-ttu-id="aa8ee-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aa8ee-105">Syntax</span></span>

```
UPPER (text )
```

## <a name="arguments"></a><span data-ttu-id="aa8ee-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="aa8ee-106">Arguments</span></span>

<span data-ttu-id="aa8ee-107">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="aa8ee-107">`text`: *String*</span></span>

<span data-ttu-id="aa8ee-108">La ruta válida de un origen de datos de tipo *Cadena*.</span><span class="sxs-lookup"><span data-stu-id="aa8ee-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="aa8ee-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="aa8ee-109">Return values</span></span>

<span data-ttu-id="aa8ee-110">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="aa8ee-110">*String*</span></span>

<span data-ttu-id="aa8ee-111">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="aa8ee-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="aa8ee-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="aa8ee-112">Example</span></span>

<span data-ttu-id="aa8ee-113">`UPPER ("Sample")` devuelve **"SAMPLE"**.</span><span class="sxs-lookup"><span data-stu-id="aa8ee-113">`UPPER ("Sample")` returns **"SAMPLE"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="aa8ee-114">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="aa8ee-114">Additional resources</span></span>

[<span data-ttu-id="aa8ee-115">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="aa8ee-115">Text functions</span></span>](er-functions-category-text.md)
