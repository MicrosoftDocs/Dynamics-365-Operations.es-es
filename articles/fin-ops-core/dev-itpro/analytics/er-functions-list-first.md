---
title: Función FIRST de ER
description: Este tema proporciona información general sobre cómo usar la función FIRST de informes electrónicos (ER).
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
ms.openlocfilehash: 211891a0ad5dc6152ce8d980bcd40a9a6bc7e3e6
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917359"
---
# <span data-ttu-id="e0035-103"><a name="FIRST">Función FIRST de ER</a></span><span class="sxs-lookup"><span data-stu-id="e0035-103"><a name="FIRST">FIRST ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e0035-104">La función `FIRST` devuelve el primer registro de la lista especificada como un valor *Contenedor (registro)*, si esa lista no está vacía.</span><span class="sxs-lookup"><span data-stu-id="e0035-104">The `FIRST` function returns the first record of the specified list as a *Container (record)* value, if that list isn't empty.</span></span> <span data-ttu-id="e0035-105">Si la lista está vacía, esta función genera una excepción.</span><span class="sxs-lookup"><span data-stu-id="e0035-105">If the list is empty, this function throws an exception.</span></span>

## <a name="syntax"></a><span data-ttu-id="e0035-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e0035-106">Syntax</span></span>

```
FIRST (list)
```

## <a name="arguments"></a><span data-ttu-id="e0035-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e0035-107">Arguments</span></span>

<span data-ttu-id="e0035-108">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="e0035-108">`list`: *Record list*</span></span>

<span data-ttu-id="e0035-109">La ruta válida de un origen de datos del tipo de datos *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="e0035-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="e0035-110">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="e0035-110">Return values</span></span>

<span data-ttu-id="e0035-111">*Contenedor (registro)*</span><span class="sxs-lookup"><span data-stu-id="e0035-111">*Container (record)*</span></span>

<span data-ttu-id="e0035-112">El valor de registro resultante.</span><span class="sxs-lookup"><span data-stu-id="e0035-112">The resulting record value.</span></span>

## <a name="example-1"></a><span data-ttu-id="e0035-113">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="e0035-113">Example 1</span></span>

<span data-ttu-id="e0035-114">La expresión `FIRST(SPLIT("ABC",1)).Value` devuelve el valor del texto **"A"**.</span><span class="sxs-lookup"><span data-stu-id="e0035-114">The expression `FIRST(SPLIT("ABC",1)).Value` returns the text value **"A"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="e0035-115">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="e0035-115">Example 2</span></span>

<span data-ttu-id="e0035-116">La expresión `FIRST(SPLIT("",1)).Value` lanza una excepción en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e0035-116">The expression `FIRST(SPLIT("",1)).Value` throws an exception at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e0035-117">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e0035-117">Additional resources</span></span>

[<span data-ttu-id="e0035-118">Funciones de lista</span><span class="sxs-lookup"><span data-stu-id="e0035-118">List functions</span></span>](er-functions-category-list.md)
