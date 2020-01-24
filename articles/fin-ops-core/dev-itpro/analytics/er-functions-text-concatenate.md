---
title: Función CONCATENATE de ER
description: En este tema se proporciona información sobre cómo usar la función CONCATENATE de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: e3d3ff87a59632d58a7c34ef96f856b38f005651
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915772"
---
# <span data-ttu-id="16b11-103"><a name="CONCATENATE">Función CONCATENATE de ER</a></span><span class="sxs-lookup"><span data-stu-id="16b11-103"><a name="CONCATENATE">CONCATENATE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="16b11-104">La función `CONCATENATE` devuelve todas las cadenas de texto especificadas como un valor de tipo *Cadena* después de unirlas en una sola cadena.</span><span class="sxs-lookup"><span data-stu-id="16b11-104">The `CONCATENATE` function returns all the specified text strings as a *String* value after they have been joined into one string.</span></span>

## <a name="syntax"></a><span data-ttu-id="16b11-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="16b11-105">Syntax</span></span>

```
CONCATENATE (text 1[, text 2, …, text N])
```

## <a name="arguments"></a><span data-ttu-id="16b11-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="16b11-106">Arguments</span></span>

<span data-ttu-id="16b11-107">`text 1`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="16b11-107">`text 1`: *String*</span></span>

<span data-ttu-id="16b11-108">Una referencia a un origen de datos del tipo de datos *Cadena*.</span><span class="sxs-lookup"><span data-stu-id="16b11-108">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="16b11-109">Este argumento es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="16b11-109">This argument is required.</span></span>

<span data-ttu-id="16b11-110">`text N`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="16b11-110">`text N`: *String*</span></span>

<span data-ttu-id="16b11-111">Una referencia a un origen de datos del tipo de datos *Cadena*.</span><span class="sxs-lookup"><span data-stu-id="16b11-111">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="16b11-112">Estos argumentos adicionales son opcionales.</span><span class="sxs-lookup"><span data-stu-id="16b11-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="16b11-113">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="16b11-113">Return values</span></span>

<span data-ttu-id="16b11-114">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="16b11-114">*String*</span></span>

<span data-ttu-id="16b11-115">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="16b11-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="16b11-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="16b11-116">Example</span></span>

<span data-ttu-id="16b11-117">`CONCATENATE ("abc", "def")` devuelve **"abcdef"**.</span><span class="sxs-lookup"><span data-stu-id="16b11-117">`CONCATENATE ("abc", "def")` returns **"abcdef"**.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="16b11-118">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="16b11-118">Usage notes</span></span>

<span data-ttu-id="16b11-119">La expresión `"abc" & "def"` también devuelve **"abcdef"**.</span><span class="sxs-lookup"><span data-stu-id="16b11-119">The expression `"abc" & "def"` also returns **"abcdef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="16b11-120">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="16b11-120">Additional resources</span></span>

[<span data-ttu-id="16b11-121">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="16b11-121">Text functions</span></span>](er-functions-category-text.md)
