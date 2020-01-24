---
title: Función CN_GBT_ADDITIONALDIMENSIONID de ER
description: Este tema proporciona información general sobre cómo usar la función CN_GBT_ADDITIONALDIMENSIONID de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: df693d745d1fe74b4500dd3fda0cc0c4be21142d
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917037"
---
# <span data-ttu-id="1cdfc-103"><a name="CN_GBT_ADDITIONALDIMENSIONID">Función CN_GBT_ADDITIONALDIMENSIONID de ER</a></span><span class="sxs-lookup"><span data-stu-id="1cdfc-103"><a name="CN_GBT_ADDITIONALDIMENSIONID">CN_GBT_ADDITIONALDIMENSIONID ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1cdfc-104">La función `CN_GBT_ADDITIONALDIMENSIONID` devuelve un valor *Cadena* que representa un solo Id. de dimensión financiera que se toma de una cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="1cdfc-104">The `CN_GBT_ADDITIONALDIMENSIONID` function returns a *String* value that represents a single financial dimension ID that is taken from the specified string.</span></span> <span data-ttu-id="1cdfc-105">La cadena especificada presenta todas las dimensiones como una lista de ID separadas por comas.</span><span class="sxs-lookup"><span data-stu-id="1cdfc-105">The specified string presents all dimensions as a comma-separated list of IDs.</span></span>

## <a name="syntax"></a><span data-ttu-id="1cdfc-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1cdfc-106">Syntax</span></span>

```
CN_GBT_ADDITIONALDIMENSIONID (text, number)
```

## <a name="arguments"></a><span data-ttu-id="1cdfc-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="1cdfc-107">Arguments</span></span>

<span data-ttu-id="1cdfc-108">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="1cdfc-108">`text`: *String*</span></span>

<span data-ttu-id="1cdfc-109">El valor de *Cadena* que presenta todas las dimensiones como una lista de identificadores separadas por comas.</span><span class="sxs-lookup"><span data-stu-id="1cdfc-109">A *String* value that presents all dimensions as a comma-separated list of IDs.</span></span>

<span data-ttu-id="1cdfc-110">`number`: Entero</span><span class="sxs-lookup"><span data-stu-id="1cdfc-110">`number`: Integer</span></span>

<span data-ttu-id="1cdfc-111">Un valor *Entero* que define el código de la secuencia de la dimensión solicitada en la cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="1cdfc-111">An *Integer* value that defines the sequence code of the requested dimension in the specified string.</span></span>

## <a name="return-values"></a><span data-ttu-id="1cdfc-112">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="1cdfc-112">Return values</span></span>

<span data-ttu-id="1cdfc-113">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="1cdfc-113">*String*</span></span>

<span data-ttu-id="1cdfc-114">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="1cdfc-114">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="1cdfc-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1cdfc-115">Example</span></span>

<span data-ttu-id="1cdfc-116">`CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` devuelve **"CC"**.</span><span class="sxs-lookup"><span data-stu-id="1cdfc-116">`CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` returns **"CC"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1cdfc-117">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="1cdfc-117">Additional resources</span></span>

[<span data-ttu-id="1cdfc-118">Otras funciones (específicas de dominio empresarial)</span><span class="sxs-lookup"><span data-stu-id="1cdfc-118">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)