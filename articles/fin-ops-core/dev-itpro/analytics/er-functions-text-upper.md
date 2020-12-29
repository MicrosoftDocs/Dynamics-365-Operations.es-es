---
title: Función UPPER de ER
description: Este tema proporciona información general sobre cómo usar la función UPPER de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: c3e594138ef8e28f1b3aaf333026fa8f9e55cca0
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4688350"
---
# <a name="upper-er-function"></a><span data-ttu-id="d8174-103">Función UPPER de ER</span><span class="sxs-lookup"><span data-stu-id="d8174-103">UPPER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d8174-104">La función `UPPER` devuelve la cadena de texto especificada como un valor de tipo *Cadena* después de convertirla a letras mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="d8174-104">The `UPPER` function returns the specified text string as a *String* value after it has been converted to uppercase letters.</span></span>

## <a name="syntax"></a><span data-ttu-id="d8174-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d8174-105">Syntax</span></span>

```vb
UPPER (text )
```

## <a name="arguments"></a><span data-ttu-id="d8174-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d8174-106">Arguments</span></span>

<span data-ttu-id="d8174-107">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="d8174-107">`text`: *String*</span></span>

<span data-ttu-id="d8174-108">La ruta válida de un origen de datos de tipo *Cadena*.</span><span class="sxs-lookup"><span data-stu-id="d8174-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="d8174-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="d8174-109">Return values</span></span>

<span data-ttu-id="d8174-110">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="d8174-110">*String*</span></span>

<span data-ttu-id="d8174-111">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="d8174-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="d8174-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d8174-112">Example</span></span>

<span data-ttu-id="d8174-113">`UPPER ("Sample")` devuelve **"SAMPLE"**.</span><span class="sxs-lookup"><span data-stu-id="d8174-113">`UPPER ("Sample")` returns **"SAMPLE"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d8174-114">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="d8174-114">Additional resources</span></span>

[<span data-ttu-id="d8174-115">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="d8174-115">Text functions</span></span>](er-functions-category-text.md)
