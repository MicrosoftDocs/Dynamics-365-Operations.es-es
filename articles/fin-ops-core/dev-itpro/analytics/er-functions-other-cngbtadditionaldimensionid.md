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
ms.openlocfilehash: 7fdc4527bc6115bdb3fca9d6a92d3d77a7c264c2
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744440"
---
# <a name="cn_gbt_additionaldimensionid-er-function"></a><span data-ttu-id="4116c-103">Función CN_GBT_ADDITIONALDIMENSIONID de ER</span><span class="sxs-lookup"><span data-stu-id="4116c-103">CN_GBT_ADDITIONALDIMENSIONID ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4116c-104">La función `CN_GBT_ADDITIONALDIMENSIONID` devuelve un valor *Cadena* que representa un solo Id. de dimensión financiera que se toma de una cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="4116c-104">The `CN_GBT_ADDITIONALDIMENSIONID` function returns a *String* value that represents a single financial dimension ID that is taken from the specified string.</span></span> <span data-ttu-id="4116c-105">La cadena especificada presenta todas las dimensiones como una lista de ID separadas por comas.</span><span class="sxs-lookup"><span data-stu-id="4116c-105">The specified string presents all dimensions as a comma-separated list of IDs.</span></span>

## <a name="syntax"></a><span data-ttu-id="4116c-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4116c-106">Syntax</span></span>

```vb
CN_GBT_ADDITIONALDIMENSIONID (text, number)
```

## <a name="arguments"></a><span data-ttu-id="4116c-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="4116c-107">Arguments</span></span>

<span data-ttu-id="4116c-108">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="4116c-108">`text`: *String*</span></span>

<span data-ttu-id="4116c-109">El valor de *Cadena* que presenta todas las dimensiones como una lista de identificadores separadas por comas.</span><span class="sxs-lookup"><span data-stu-id="4116c-109">A *String* value that presents all dimensions as a comma-separated list of IDs.</span></span>

<span data-ttu-id="4116c-110">`number`: Entero</span><span class="sxs-lookup"><span data-stu-id="4116c-110">`number`: Integer</span></span>

<span data-ttu-id="4116c-111">Un valor *Entero* que define el código de la secuencia de la dimensión solicitada en la cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="4116c-111">An *Integer* value that defines the sequence code of the requested dimension in the specified string.</span></span>

## <a name="return-values"></a><span data-ttu-id="4116c-112">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="4116c-112">Return values</span></span>

<span data-ttu-id="4116c-113">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="4116c-113">*String*</span></span>

<span data-ttu-id="4116c-114">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="4116c-114">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="4116c-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4116c-115">Example</span></span>

<span data-ttu-id="4116c-116">`CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` devuelve **"CC"**.</span><span class="sxs-lookup"><span data-stu-id="4116c-116">`CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` returns **"CC"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4116c-117">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="4116c-117">Additional resources</span></span>

[<span data-ttu-id="4116c-118">Otras funciones (específicas de dominio empresarial)</span><span class="sxs-lookup"><span data-stu-id="4116c-118">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
