---
title: Función PADLEFT de ER
description: En este tema se proporciona información sobre cómo usar la función PADLEFT de informes electrónicos (ER).
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
ms.openlocfilehash: 268941d8bc0bd4dc6de6d2597c05a11c1f530f15
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680155"
---
# <a name="padleft-er-function"></a><span data-ttu-id="c34b4-103">Función PADLEFT de ER</span><span class="sxs-lookup"><span data-stu-id="c34b4-103">PADLEFT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c34b4-104">La función `PADLEFT` devuelve un valor de tipo *Cadena* de la longitud especificada en la que el inicio de la cadena especificada se rellena con los caracteres especificados.</span><span class="sxs-lookup"><span data-stu-id="c34b4-104">The `PADLEFT` function returns a *String* value of the specified length, where the start of the specified string is padded with the specified characters.</span></span>

## <a name="syntax"></a><span data-ttu-id="c34b4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c34b4-105">Syntax</span></span>

```vb
PADLEFT (text, length, padding chars)
```

## <a name="arguments"></a><span data-ttu-id="c34b4-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c34b4-106">Arguments</span></span>

<span data-ttu-id="c34b4-107">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="c34b4-107">`text`: *String*</span></span>

<span data-ttu-id="c34b4-108">Valor de tipo *Cadena* que representa el texto original.</span><span class="sxs-lookup"><span data-stu-id="c34b4-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="c34b4-109">`length`: *Entero*</span><span class="sxs-lookup"><span data-stu-id="c34b4-109">`length`: *Integer*</span></span>

<span data-ttu-id="c34b4-110">Un valor de tipo *Entero* que representa el número final de caracteres en la cadena rellenada.</span><span class="sxs-lookup"><span data-stu-id="c34b4-110">An *Integer* value that represents the final number of characters in the padded string.</span></span>

<span data-ttu-id="c34b4-111">`padding chars`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="c34b4-111">`padding chars`: *String*</span></span>

<span data-ttu-id="c34b4-112">Los caracteres que se van a utilizar para el relleno.</span><span class="sxs-lookup"><span data-stu-id="c34b4-112">The characters to use for padding.</span></span>

## <a name="return-values"></a><span data-ttu-id="c34b4-113">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="c34b4-113">Return values</span></span>

<span data-ttu-id="c34b4-114">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="c34b4-114">*String*</span></span>

<span data-ttu-id="c34b4-115">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="c34b4-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="c34b4-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c34b4-116">Example</span></span>

<span data-ttu-id="c34b4-117">`PADLEFT ("1234", 10, "`&nbsp;`")` devuelve la cadena de texto **"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234"**.</span><span class="sxs-lookup"><span data-stu-id="c34b4-117">`PADLEFT ("1234", 10, "`&nbsp;`")` returns the text string **"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c34b4-118">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c34b4-118">Additional resources</span></span>

[<span data-ttu-id="c34b4-119">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="c34b4-119">Text functions</span></span>](er-functions-category-text.md)
