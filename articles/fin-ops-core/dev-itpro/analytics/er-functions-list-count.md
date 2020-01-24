---
title: Función COUNT ER
description: Este tema proporciona información general sobre cómo usar la función COUNT de informes electrónicos (ER).
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
ms.openlocfilehash: 2d29b82a8c3b108f7651e6d593cb17e7ec8ca872
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916255"
---
# <span data-ttu-id="08c4e-103"><a name="COUNT">Función COUNT ER</a></span><span class="sxs-lookup"><span data-stu-id="08c4e-103"><a name="COUNT">COUNT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="08c4e-104">La función `COUNT` devuelve un valor *Entero* que representa el número de registros en la lista especificada, si la lista no está vacía.</span><span class="sxs-lookup"><span data-stu-id="08c4e-104">The `COUNT` function returns an *Integer* value that represents the number of records in the specified list, if the list isn't empty.</span></span> <span data-ttu-id="08c4e-105">Si la lista está vacía, esta función devuelve **0** (cero).</span><span class="sxs-lookup"><span data-stu-id="08c4e-105">If the list is empty, this function returns **0** (zero).</span></span>

## <a name="syntax"></a><span data-ttu-id="08c4e-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="08c4e-106">Syntax</span></span>

```
COUNT (list)
```

## <a name="arguments"></a><span data-ttu-id="08c4e-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="08c4e-107">Arguments</span></span>

<span data-ttu-id="08c4e-108">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="08c4e-108">`list`: *Record list*</span></span>

<span data-ttu-id="08c4e-109">La ruta válida de un origen de datos del tipo de datos *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="08c4e-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="08c4e-110">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="08c4e-110">Return values</span></span>

<span data-ttu-id="08c4e-111">*Entero*</span><span class="sxs-lookup"><span data-stu-id="08c4e-111">*Integer*</span></span>

<span data-ttu-id="08c4e-112">El valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="08c4e-112">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="08c4e-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="08c4e-113">Example</span></span>

<span data-ttu-id="08c4e-114">`COUNT (SPLIT("abcd" , 3))` devuelve **2**, porque la función `SPLIT` que se utiliza en este ejemplo crea una lista que consta de dos registros.</span><span class="sxs-lookup"><span data-stu-id="08c4e-114">`COUNT (SPLIT("abcd" , 3))` returns **2**, because the `SPLIT` function that is used in this example creates a list that consists of two records.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="08c4e-115">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="08c4e-115">Additional resources</span></span>

[<span data-ttu-id="08c4e-116">Funciones de lista</span><span class="sxs-lookup"><span data-stu-id="08c4e-116">List functions</span></span>](er-functions-category-list.md)
