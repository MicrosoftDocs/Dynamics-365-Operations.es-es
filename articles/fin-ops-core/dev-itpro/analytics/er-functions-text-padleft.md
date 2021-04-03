---
title: Función PADLEFT de ER
description: En este tema se proporciona información sobre cómo usar la función PADLEFT de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 86957808ca30db87e6f8202c2024d9929969fc3d
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562694"
---
# <a name="padleft-er-function"></a><span data-ttu-id="ddb1b-103">Función PADLEFT de ER</span><span class="sxs-lookup"><span data-stu-id="ddb1b-103">PADLEFT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ddb1b-104">La función `PADLEFT` devuelve un valor de tipo *Cadena* de la longitud especificada en la que el inicio de la cadena especificada se rellena con los caracteres especificados.</span><span class="sxs-lookup"><span data-stu-id="ddb1b-104">The `PADLEFT` function returns a *String* value of the specified length, where the start of the specified string is padded with the specified characters.</span></span>

## <a name="syntax"></a><span data-ttu-id="ddb1b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ddb1b-105">Syntax</span></span>

```vb
PADLEFT (text, length, padding chars)
```

## <a name="arguments"></a><span data-ttu-id="ddb1b-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ddb1b-106">Arguments</span></span>

<span data-ttu-id="ddb1b-107">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="ddb1b-107">`text`: *String*</span></span>

<span data-ttu-id="ddb1b-108">Valor de tipo *Cadena* que representa el texto original.</span><span class="sxs-lookup"><span data-stu-id="ddb1b-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="ddb1b-109">`length`: *Entero*</span><span class="sxs-lookup"><span data-stu-id="ddb1b-109">`length`: *Integer*</span></span>

<span data-ttu-id="ddb1b-110">Un valor de tipo *Entero* que representa el número final de caracteres en la cadena rellenada.</span><span class="sxs-lookup"><span data-stu-id="ddb1b-110">An *Integer* value that represents the final number of characters in the padded string.</span></span>

<span data-ttu-id="ddb1b-111">`padding chars`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="ddb1b-111">`padding chars`: *String*</span></span>

<span data-ttu-id="ddb1b-112">Los caracteres que se van a utilizar para el relleno.</span><span class="sxs-lookup"><span data-stu-id="ddb1b-112">The characters to use for padding.</span></span>

## <a name="return-values"></a><span data-ttu-id="ddb1b-113">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="ddb1b-113">Return values</span></span>

<span data-ttu-id="ddb1b-114">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="ddb1b-114">*String*</span></span>

<span data-ttu-id="ddb1b-115">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="ddb1b-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="ddb1b-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ddb1b-116">Example</span></span>

<span data-ttu-id="ddb1b-117">`PADLEFT ("1234", 10, "`&nbsp;`")` devuelve la cadena de texto **"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234"**.</span><span class="sxs-lookup"><span data-stu-id="ddb1b-117">`PADLEFT ("1234", 10, "`&nbsp;`")` returns the text string **"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ddb1b-118">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="ddb1b-118">Additional resources</span></span>

[<span data-ttu-id="ddb1b-119">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="ddb1b-119">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]