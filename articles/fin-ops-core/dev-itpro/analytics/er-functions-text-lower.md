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
ms.openlocfilehash: 12577e571c8e87db79395895e2a22e66ee7df32c
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745690"
---
# <a name="lower-er-function"></a><span data-ttu-id="4bb00-103">Función LOWER de ER</span><span class="sxs-lookup"><span data-stu-id="4bb00-103">LOWER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4bb00-104">La función `LOWER` devuelve la cadena de texto especificada como un valor de tipo *Cadena* después de convertirla a letras minúsculas.</span><span class="sxs-lookup"><span data-stu-id="4bb00-104">The `LOWER` function returns the specified text string as a *String* value after it has been converted to lowercase letters.</span></span>

## <a name="syntax"></a><span data-ttu-id="4bb00-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4bb00-105">Syntax</span></span>

```vb
LOWER (text)
```

## <a name="arguments"></a><span data-ttu-id="4bb00-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="4bb00-106">Arguments</span></span>

<span data-ttu-id="4bb00-107">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="4bb00-107">`text`: *String*</span></span>

<span data-ttu-id="4bb00-108">Valor de tipo *Cadena* que especifica el texto.</span><span class="sxs-lookup"><span data-stu-id="4bb00-108">A *String* value that specifies the text.</span></span>

## <a name="return-values"></a><span data-ttu-id="4bb00-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="4bb00-109">Return values</span></span>

<span data-ttu-id="4bb00-110">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="4bb00-110">*String*</span></span>

<span data-ttu-id="4bb00-111">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="4bb00-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="4bb00-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4bb00-112">Example</span></span>

<span data-ttu-id="4bb00-113">`LOWER ("Sample")` devuelve **"sample"**.</span><span class="sxs-lookup"><span data-stu-id="4bb00-113">`LOWER ("Sample")` returns **"sample"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4bb00-114">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="4bb00-114">Additional resources</span></span>

[<span data-ttu-id="4bb00-115">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="4bb00-115">Text functions</span></span>](er-functions-category-text.md)
