---
title: Función RIGHT de ER
description: Este tema proporciona información general sobre cómo usar la función RIGHT de informes electrónicos (ER).
author: NickSelin
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
ms.openlocfilehash: f59b12f0b3f7b100b953b2072677c83c836746ff
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746132"
---
# <a name="right-er-function"></a><span data-ttu-id="bd910-103">Función RIGHT de ER</span><span class="sxs-lookup"><span data-stu-id="bd910-103">RIGHT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bd910-104">La función `RIGHT` devuelve un valor de tipo *Cadena* que presenta el número especificado de caracteres desde el final de la cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="bd910-104">The `RIGHT` function returns a *String* value that presents the specified number of characters from the end of the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="bd910-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bd910-105">Syntax</span></span>

```vb
RIGHT (text, number)
```

## <a name="arguments"></a><span data-ttu-id="bd910-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="bd910-106">Arguments</span></span>

<span data-ttu-id="bd910-107">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="bd910-107">`text`: *String*</span></span>

<span data-ttu-id="bd910-108">Valor de tipo *Cadena* que representa el texto original.</span><span class="sxs-lookup"><span data-stu-id="bd910-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="bd910-109">`number`: *Entero*</span><span class="sxs-lookup"><span data-stu-id="bd910-109">`number`: *Integer*</span></span>

<span data-ttu-id="bd910-110">El número de caracteres que se deben devolver desde el final del texto original.</span><span class="sxs-lookup"><span data-stu-id="bd910-110">The number of characters that must be returned from the end of the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="bd910-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="bd910-111">Return values</span></span>

<span data-ttu-id="bd910-112">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="bd910-112">*String*</span></span>

<span data-ttu-id="bd910-113">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="bd910-113">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="bd910-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bd910-114">Example</span></span>

<span data-ttu-id="bd910-115">`RIGHT ("Sample", 3)` devuelve **"ple"**.</span><span class="sxs-lookup"><span data-stu-id="bd910-115">`RIGHT ("Sample", 3)` returns **"ple"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bd910-116">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="bd910-116">Additional resources</span></span>

[<span data-ttu-id="bd910-117">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="bd910-117">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]