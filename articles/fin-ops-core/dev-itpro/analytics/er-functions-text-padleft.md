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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 28306b2e5fb1febce49ab55240c6d84ff240282a
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916784"
---
# <span data-ttu-id="d417f-103"><a name="PADLEFT">Función PADLEFT de ER</a></span><span class="sxs-lookup"><span data-stu-id="d417f-103"><a name="PADLEFT">PADLEFT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d417f-104">La función `PADLEFT` devuelve un valor de tipo *Cadena* de la longitud especificada en la que el inicio de la cadena especificada se rellena con los caracteres especificados.</span><span class="sxs-lookup"><span data-stu-id="d417f-104">The `PADLEFT` function returns a *String* value of the specified length, where the start of the specified string is padded with the specified characters.</span></span>

## <a name="syntax"></a><span data-ttu-id="d417f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d417f-105">Syntax</span></span>

```
PADLEFT (text, length, padding chars)
```

## <a name="arguments"></a><span data-ttu-id="d417f-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d417f-106">Arguments</span></span>

<span data-ttu-id="d417f-107">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="d417f-107">`text`: *String*</span></span>

<span data-ttu-id="d417f-108">Valor de tipo *Cadena* que representa el texto original.</span><span class="sxs-lookup"><span data-stu-id="d417f-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="d417f-109">`length`: *Entero*</span><span class="sxs-lookup"><span data-stu-id="d417f-109">`length`: *Integer*</span></span>

<span data-ttu-id="d417f-110">Un valor de tipo *Entero* que representa el número final de caracteres en la cadena rellenada.</span><span class="sxs-lookup"><span data-stu-id="d417f-110">An *Integer* value that represents the final number of characters in the padded string.</span></span>

<span data-ttu-id="d417f-111">`padding chars`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="d417f-111">`padding chars`: *String*</span></span>

<span data-ttu-id="d417f-112">Los caracteres que se van a utilizar para el relleno.</span><span class="sxs-lookup"><span data-stu-id="d417f-112">The characters to use for padding.</span></span>

## <a name="return-values"></a><span data-ttu-id="d417f-113">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="d417f-113">Return values</span></span>

<span data-ttu-id="d417f-114">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="d417f-114">*String*</span></span>

<span data-ttu-id="d417f-115">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="d417f-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="d417f-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d417f-116">Example</span></span>

<span data-ttu-id="d417f-117">`PADLEFT ("1234", 10, "`&nbsp;`")` devuelve la cadena de texto **"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234"**.</span><span class="sxs-lookup"><span data-stu-id="d417f-117">`PADLEFT ("1234", 10, "`&nbsp;`")` returns the text string **"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d417f-118">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="d417f-118">Additional resources</span></span>

[<span data-ttu-id="d417f-119">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="d417f-119">Text functions</span></span>](er-functions-category-text.md)
