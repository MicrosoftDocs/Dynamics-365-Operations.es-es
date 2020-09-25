---
title: Función LEN de ER
description: Este tema proporciona información general sobre cómo usar la función LEN de informes electrónicos (ER).
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
ms.openlocfilehash: e51e181de53cd185679110e99b9f89695bacdf92
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744272"
---
# <a name="len-er-function"></a><span data-ttu-id="17746-103">Función LEN de ER</span><span class="sxs-lookup"><span data-stu-id="17746-103">LEN ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="17746-104">La función `LEN` devuelve un valor de tipo *Entero* que representa el número de caracteres de la cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="17746-104">The `LEN` function returns the number of characters in the specified string as an *Integer* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="17746-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="17746-105">Syntax</span></span>

```vb
LEN (text)
```

## <a name="arguments"></a><span data-ttu-id="17746-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="17746-106">Arguments</span></span>

<span data-ttu-id="17746-107">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="17746-107">`text`: *String*</span></span>

<span data-ttu-id="17746-108">Valor de tipo *Cadena* que especifica el texto.</span><span class="sxs-lookup"><span data-stu-id="17746-108">A *String* value that specifies the text.</span></span>

## <a name="return-values"></a><span data-ttu-id="17746-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="17746-109">Return values</span></span>

<span data-ttu-id="17746-110">*Entero*</span><span class="sxs-lookup"><span data-stu-id="17746-110">*Integer*</span></span>

<span data-ttu-id="17746-111">El valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="17746-111">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="17746-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="17746-112">Example</span></span>

<span data-ttu-id="17746-113">`LEN ("Sample")` devuelve **6**.</span><span class="sxs-lookup"><span data-stu-id="17746-113">`LEN ("Sample")` returns **6**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="17746-114">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="17746-114">Additional resources</span></span>

[<span data-ttu-id="17746-115">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="17746-115">Text functions</span></span>](er-functions-category-text.md)
