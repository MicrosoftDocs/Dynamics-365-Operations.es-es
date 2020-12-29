---
title: Función EMPTYLIST ER
description: En este tema se proporciona información sobre cómo usar la función EMPTYLIST de informes electrónicos (ER).
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ccb52d7d88f292720360ae913ead5be239165193
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687679"
---
# <a name="emptylist-er-function"></a><span data-ttu-id="4f3cd-103">Función EMPTYLIST ER</span><span class="sxs-lookup"><span data-stu-id="4f3cd-103">EMPTYLIST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4f3cd-104">La función `EMPTYLIST` devuelve un valor *Lista de registros* vacío usando la lista especificada como origen para la estructura de la lista.</span><span class="sxs-lookup"><span data-stu-id="4f3cd-104">The `EMPTYLIST` function returns an empty *Record list* value by using the specified list as a source for the list structure.</span></span>

## <a name="syntax"></a><span data-ttu-id="4f3cd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4f3cd-105">Syntax</span></span>

```vb
EMPTYLIST (list)
```

## <a name="arguments"></a><span data-ttu-id="4f3cd-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="4f3cd-106">Arguments</span></span>

<span data-ttu-id="4f3cd-107">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="4f3cd-107">`list`: *Record list*</span></span>

<span data-ttu-id="4f3cd-108">La ruta válida de un origen de datos del tipo de datos *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="4f3cd-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="4f3cd-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="4f3cd-109">Return values</span></span>

<span data-ttu-id="4f3cd-110">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="4f3cd-110">*Record list*</span></span>

<span data-ttu-id="4f3cd-111">La lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="4f3cd-111">The resulting list of records.</span></span>

## <a name="example"></a><span data-ttu-id="4f3cd-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4f3cd-112">Example</span></span>

<span data-ttu-id="4f3cd-113">`EMPTYLIST (SPLIT ("abc", 1))` devuelve una nueva lista vacía que tiene la misma estructura que la lista que se devuelve por la función `SPLIT` utilizada.</span><span class="sxs-lookup"><span data-stu-id="4f3cd-113">`EMPTYLIST (SPLIT ("abc", 1))` returns a new empty list that has the same structure as the list that is returned by the `SPLIT` function that is used.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4f3cd-114">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="4f3cd-114">Additional resources</span></span>

[<span data-ttu-id="4f3cd-115">Funciones de lista</span><span class="sxs-lookup"><span data-stu-id="4f3cd-115">List functions</span></span>](er-functions-category-list.md)
