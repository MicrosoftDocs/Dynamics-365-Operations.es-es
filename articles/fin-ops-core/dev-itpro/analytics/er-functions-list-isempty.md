---
title: Función ISEMPTY de ER
description: En este tema se proporciona información sobre cómo usar la función ISEMPTY de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: c8450c17fe2de964016951197b0d4e231c550a99
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916140"
---
# <span data-ttu-id="95dc3-103"><a name="ISEMPTY">Función ISEMPTY de ER</a></span><span class="sxs-lookup"><span data-stu-id="95dc3-103"><a name="ISEMPTY">ISEMPTY ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="95dc3-104">La función `ISEMPTY` devuelve un valor *Booleano* de **TRUE** si la lista especificada no contiene registros.</span><span class="sxs-lookup"><span data-stu-id="95dc3-104">The `ISEMPTY` function returns a *Boolean* value of **TRUE** if the specified list contains no records.</span></span> <span data-ttu-id="95dc3-105">De lo contrario, la expresión devuelve un valor *Booleano* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="95dc3-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="95dc3-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="95dc3-106">Syntax</span></span>

```
ISEMPTY (list)
```

## <a name="arguments"></a><span data-ttu-id="95dc3-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="95dc3-107">Arguments</span></span>

<span data-ttu-id="95dc3-108">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="95dc3-108">`list`: *Record list*</span></span>

<span data-ttu-id="95dc3-109">La ruta válida de un origen de datos del tipo de datos *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="95dc3-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="95dc3-110">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="95dc3-110">Return values</span></span>

<span data-ttu-id="95dc3-111">*Booleano*</span><span class="sxs-lookup"><span data-stu-id="95dc3-111">*Boolean*</span></span>

<span data-ttu-id="95dc3-112">El valor *Booleano* resultante.</span><span class="sxs-lookup"><span data-stu-id="95dc3-112">The resulting *Boolean* value.</span></span>

## <a name="example-1"></a><span data-ttu-id="95dc3-113">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="95dc3-113">Example 1</span></span>

<span data-ttu-id="95dc3-114">Si especifica el origen de datos **DS** del tipo *Campo calculado* y contiene la expresión `SPLIT ("A|B|C", "|")`, la expresión `ISEMPTY(DS)` devuelve **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="95dc3-114">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `ISEMPTY(DS)` returns **FALSE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="95dc3-115">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="95dc3-115">Example 2</span></span>

<span data-ttu-id="95dc3-116">La expresión `ISEMPTY (SPLIT ("",1))` devuelve **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="95dc3-116">The expression `ISEMPTY (SPLIT ("",1))` returns **TRUE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="95dc3-117">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="95dc3-117">Additional resources</span></span>

[<span data-ttu-id="95dc3-118">Funciones de lista</span><span class="sxs-lookup"><span data-stu-id="95dc3-118">List functions</span></span>](er-functions-category-list.md)
