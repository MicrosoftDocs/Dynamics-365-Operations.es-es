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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ad971bd78fa1da17be916efcc6857aa32575f7ac
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680323"
---
# <a name="lower-er-function"></a><span data-ttu-id="b8440-103">Función LOWER de ER</span><span class="sxs-lookup"><span data-stu-id="b8440-103">LOWER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b8440-104">La función `LOWER` devuelve la cadena de texto especificada como un valor de tipo *Cadena* después de convertirla a letras minúsculas.</span><span class="sxs-lookup"><span data-stu-id="b8440-104">The `LOWER` function returns the specified text string as a *String* value after it has been converted to lowercase letters.</span></span>

## <a name="syntax"></a><span data-ttu-id="b8440-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b8440-105">Syntax</span></span>

```vb
LOWER (text)
```

## <a name="arguments"></a><span data-ttu-id="b8440-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b8440-106">Arguments</span></span>

<span data-ttu-id="b8440-107">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="b8440-107">`text`: *String*</span></span>

<span data-ttu-id="b8440-108">Valor de tipo *Cadena* que especifica el texto.</span><span class="sxs-lookup"><span data-stu-id="b8440-108">A *String* value that specifies the text.</span></span>

## <a name="return-values"></a><span data-ttu-id="b8440-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="b8440-109">Return values</span></span>

<span data-ttu-id="b8440-110">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="b8440-110">*String*</span></span>

<span data-ttu-id="b8440-111">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="b8440-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="b8440-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b8440-112">Example</span></span>

<span data-ttu-id="b8440-113">`LOWER ("Sample")` devuelve **"sample"**.</span><span class="sxs-lookup"><span data-stu-id="b8440-113">`LOWER ("Sample")` returns **"sample"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b8440-114">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="b8440-114">Additional resources</span></span>

[<span data-ttu-id="b8440-115">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="b8440-115">Text functions</span></span>](er-functions-category-text.md)
