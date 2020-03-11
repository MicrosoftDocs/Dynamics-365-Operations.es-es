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
ms.openlocfilehash: 3e0ba19e762574dde4f9038b87ce352d13f714f4
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041064"
---
# <span data-ttu-id="64816-103"><a name="LEN">Función LEN de ER</a></span><span class="sxs-lookup"><span data-stu-id="64816-103"><a name="LEN">LEN ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="64816-104">La función `LEN` devuelve un valor de tipo *Entero* que representa el número de caracteres de la cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="64816-104">The `LEN` function returns the number of characters in the specified string as an *Integer* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="64816-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="64816-105">Syntax</span></span>

```vb
LEN (text)
```

## <a name="arguments"></a><span data-ttu-id="64816-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="64816-106">Arguments</span></span>

<span data-ttu-id="64816-107">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="64816-107">`text`: *String*</span></span>

<span data-ttu-id="64816-108">Valor de tipo *Cadena* que especifica el texto.</span><span class="sxs-lookup"><span data-stu-id="64816-108">A *String* value that specifies the text.</span></span>

## <a name="return-values"></a><span data-ttu-id="64816-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="64816-109">Return values</span></span>

<span data-ttu-id="64816-110">*Entero*</span><span class="sxs-lookup"><span data-stu-id="64816-110">*Integer*</span></span>

<span data-ttu-id="64816-111">El valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="64816-111">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="64816-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="64816-112">Example</span></span>

<span data-ttu-id="64816-113">`LEN ("Sample")` devuelve **6**.</span><span class="sxs-lookup"><span data-stu-id="64816-113">`LEN ("Sample")` returns **6**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="64816-114">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="64816-114">Additional resources</span></span>

[<span data-ttu-id="64816-115">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="64816-115">Text functions</span></span>](er-functions-category-text.md)
