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
ms.openlocfilehash: d11e2d8b46614085156228ab1001d1f9340a05b0
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3040972"
---
# <span data-ttu-id="c0e84-103"><a name="PADLEFT">Función PADLEFT de ER</a></span><span class="sxs-lookup"><span data-stu-id="c0e84-103"><a name="PADLEFT">PADLEFT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c0e84-104">La función `PADLEFT` devuelve un valor de tipo *Cadena* de la longitud especificada en la que el inicio de la cadena especificada se rellena con los caracteres especificados.</span><span class="sxs-lookup"><span data-stu-id="c0e84-104">The `PADLEFT` function returns a *String* value of the specified length, where the start of the specified string is padded with the specified characters.</span></span>

## <a name="syntax"></a><span data-ttu-id="c0e84-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c0e84-105">Syntax</span></span>

```vb
PADLEFT (text, length, padding chars)
```

## <a name="arguments"></a><span data-ttu-id="c0e84-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c0e84-106">Arguments</span></span>

<span data-ttu-id="c0e84-107">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="c0e84-107">`text`: *String*</span></span>

<span data-ttu-id="c0e84-108">Valor de tipo *Cadena* que representa el texto original.</span><span class="sxs-lookup"><span data-stu-id="c0e84-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="c0e84-109">`length`: *Entero*</span><span class="sxs-lookup"><span data-stu-id="c0e84-109">`length`: *Integer*</span></span>

<span data-ttu-id="c0e84-110">Un valor de tipo *Entero* que representa el número final de caracteres en la cadena rellenada.</span><span class="sxs-lookup"><span data-stu-id="c0e84-110">An *Integer* value that represents the final number of characters in the padded string.</span></span>

<span data-ttu-id="c0e84-111">`padding chars`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="c0e84-111">`padding chars`: *String*</span></span>

<span data-ttu-id="c0e84-112">Los caracteres que se van a utilizar para el relleno.</span><span class="sxs-lookup"><span data-stu-id="c0e84-112">The characters to use for padding.</span></span>

## <a name="return-values"></a><span data-ttu-id="c0e84-113">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="c0e84-113">Return values</span></span>

<span data-ttu-id="c0e84-114">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="c0e84-114">*String*</span></span>

<span data-ttu-id="c0e84-115">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="c0e84-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="c0e84-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c0e84-116">Example</span></span>

<span data-ttu-id="c0e84-117">`PADLEFT ("1234", 10, "`&nbsp;`")` devuelve la cadena de texto **"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234"**.</span><span class="sxs-lookup"><span data-stu-id="c0e84-117">`PADLEFT ("1234", 10, "`&nbsp;`")` returns the text string **"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c0e84-118">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c0e84-118">Additional resources</span></span>

[<span data-ttu-id="c0e84-119">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="c0e84-119">Text functions</span></span>](er-functions-category-text.md)
