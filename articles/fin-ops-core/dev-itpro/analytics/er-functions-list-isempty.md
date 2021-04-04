---
title: Función ISEMPTY de ER
description: En este tema se proporciona información sobre cómo usar la función ISEMPTY de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: b689e6d4bb849f07db5d00cf8a9dc5c16646a927
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563881"
---
# <a name="isempty-er-function"></a><span data-ttu-id="1b9fc-103">Función ISEMPTY de ER</span><span class="sxs-lookup"><span data-stu-id="1b9fc-103">ISEMPTY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1b9fc-104">La función `ISEMPTY` devuelve un valor *Booleano* de **TRUE** si la lista especificada no contiene registros.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-104">The `ISEMPTY` function returns a *Boolean* value of **TRUE** if the specified list contains no records.</span></span> <span data-ttu-id="1b9fc-105">De lo contrario, la expresión devuelve un valor *Booleano* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="1b9fc-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1b9fc-106">Syntax</span></span>

```vb
ISEMPTY (list)
```

## <a name="arguments"></a><span data-ttu-id="1b9fc-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="1b9fc-107">Arguments</span></span>

<span data-ttu-id="1b9fc-108">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="1b9fc-108">`list`: *Record list*</span></span>

<span data-ttu-id="1b9fc-109">La ruta válida de un origen de datos del tipo de datos *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="1b9fc-110">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="1b9fc-110">Return values</span></span>

<span data-ttu-id="1b9fc-111">*Booleano*</span><span class="sxs-lookup"><span data-stu-id="1b9fc-111">*Boolean*</span></span>

<span data-ttu-id="1b9fc-112">El valor *Booleano* resultante.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-112">The resulting *Boolean* value.</span></span>

## <a name="example-1"></a><span data-ttu-id="1b9fc-113">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="1b9fc-113">Example 1</span></span>

<span data-ttu-id="1b9fc-114">Si especifica el origen de datos **DS** del tipo *Campo calculado* y contiene la expresión `SPLIT ("A|B|C", "|")`, la expresión `ISEMPTY(DS)` devuelve **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-114">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `ISEMPTY(DS)` returns **FALSE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="1b9fc-115">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="1b9fc-115">Example 2</span></span>

<span data-ttu-id="1b9fc-116">La expresión `ISEMPTY (SPLIT ("",1))` devuelve **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-116">The expression `ISEMPTY (SPLIT ("",1))` returns **TRUE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1b9fc-117">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="1b9fc-117">Additional resources</span></span>

[<span data-ttu-id="1b9fc-118">Funciones de lista</span><span class="sxs-lookup"><span data-stu-id="1b9fc-118">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]