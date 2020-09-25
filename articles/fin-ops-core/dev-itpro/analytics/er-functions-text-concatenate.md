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
ms.openlocfilehash: 1a21140e5636ebd96eca4be90308c915e77510e1
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743912"
---
# <a name="concatenate-er-function"></a><span data-ttu-id="9a4dc-103">Función CONCATENATE de ER</span><span class="sxs-lookup"><span data-stu-id="9a4dc-103">CONCATENATE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9a4dc-104">La función `CONCATENATE` devuelve todas las cadenas de texto especificadas como un valor de tipo *Cadena* después de unirlas en una sola cadena.</span><span class="sxs-lookup"><span data-stu-id="9a4dc-104">The `CONCATENATE` function returns all the specified text strings as a *String* value after they have been joined into one string.</span></span>

## <a name="syntax"></a><span data-ttu-id="9a4dc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a4dc-105">Syntax</span></span>

```vb
CONCATENATE (text 1[, text 2, …, text N])
```

## <a name="arguments"></a><span data-ttu-id="9a4dc-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="9a4dc-106">Arguments</span></span>

<span data-ttu-id="9a4dc-107">`text 1`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="9a4dc-107">`text 1`: *String*</span></span>

<span data-ttu-id="9a4dc-108">Una referencia a un origen de datos del tipo de datos *Cadena*.</span><span class="sxs-lookup"><span data-stu-id="9a4dc-108">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="9a4dc-109">Este argumento es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="9a4dc-109">This argument is required.</span></span>

<span data-ttu-id="9a4dc-110">`text N`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="9a4dc-110">`text N`: *String*</span></span>

<span data-ttu-id="9a4dc-111">Una referencia a un origen de datos del tipo de datos *Cadena*.</span><span class="sxs-lookup"><span data-stu-id="9a4dc-111">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="9a4dc-112">Estos argumentos adicionales son opcionales.</span><span class="sxs-lookup"><span data-stu-id="9a4dc-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="9a4dc-113">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="9a4dc-113">Return values</span></span>

<span data-ttu-id="9a4dc-114">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="9a4dc-114">*String*</span></span>

<span data-ttu-id="9a4dc-115">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="9a4dc-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="9a4dc-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9a4dc-116">Example</span></span>

<span data-ttu-id="9a4dc-117">`CONCATENATE ("abc", "def")` devuelve **"abcdef"**.</span><span class="sxs-lookup"><span data-stu-id="9a4dc-117">`CONCATENATE ("abc", "def")` returns **"abcdef"**.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="9a4dc-118">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="9a4dc-118">Usage notes</span></span>

<span data-ttu-id="9a4dc-119">La expresión `"abc" & "def"` también devuelve **"abcdef"**.</span><span class="sxs-lookup"><span data-stu-id="9a4dc-119">The expression `"abc" & "def"` also returns **"abcdef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9a4dc-120">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="9a4dc-120">Additional resources</span></span>

[<span data-ttu-id="9a4dc-121">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="9a4dc-121">Text functions</span></span>](er-functions-category-text.md)
