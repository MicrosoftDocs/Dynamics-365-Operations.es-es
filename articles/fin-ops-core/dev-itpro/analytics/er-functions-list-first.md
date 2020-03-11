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
ms.openlocfilehash: 4d10abcf15b93961bd2ba4aec22914825d9ac38c
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042099"
---
# <span data-ttu-id="a6b63-103"><a name="FIRST">Función FIRST de ER</a></span><span class="sxs-lookup"><span data-stu-id="a6b63-103"><a name="FIRST">FIRST ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a6b63-104">La función `FIRST` devuelve el primer registro de la lista especificada como un valor *Contenedor (registro)*, si esa lista no está vacía.</span><span class="sxs-lookup"><span data-stu-id="a6b63-104">The `FIRST` function returns the first record of the specified list as a *Container (record)* value, if that list isn't empty.</span></span> <span data-ttu-id="a6b63-105">Si la lista está vacía, esta función genera una excepción.</span><span class="sxs-lookup"><span data-stu-id="a6b63-105">If the list is empty, this function throws an exception.</span></span>

## <a name="syntax"></a><span data-ttu-id="a6b63-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a6b63-106">Syntax</span></span>

```vb
FIRST (list)
```

## <a name="arguments"></a><span data-ttu-id="a6b63-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a6b63-107">Arguments</span></span>

<span data-ttu-id="a6b63-108">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="a6b63-108">`list`: *Record list*</span></span>

<span data-ttu-id="a6b63-109">La ruta válida de un origen de datos del tipo de datos *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="a6b63-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="a6b63-110">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="a6b63-110">Return values</span></span>

<span data-ttu-id="a6b63-111">*Contenedor (registro)*</span><span class="sxs-lookup"><span data-stu-id="a6b63-111">*Container (record)*</span></span>

<span data-ttu-id="a6b63-112">El valor de registro resultante.</span><span class="sxs-lookup"><span data-stu-id="a6b63-112">The resulting record value.</span></span>

## <a name="example-1"></a><span data-ttu-id="a6b63-113">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="a6b63-113">Example 1</span></span>

<span data-ttu-id="a6b63-114">La expresión `FIRST(SPLIT("ABC",1)).Value` devuelve el valor del texto **"A"**.</span><span class="sxs-lookup"><span data-stu-id="a6b63-114">The expression `FIRST(SPLIT("ABC",1)).Value` returns the text value **"A"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="a6b63-115">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="a6b63-115">Example 2</span></span>

<span data-ttu-id="a6b63-116">La expresión `FIRST(SPLIT("",1)).Value` lanza una excepción en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a6b63-116">The expression `FIRST(SPLIT("",1)).Value` throws an exception at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a6b63-117">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a6b63-117">Additional resources</span></span>

[<span data-ttu-id="a6b63-118">Funciones de lista</span><span class="sxs-lookup"><span data-stu-id="a6b63-118">List functions</span></span>](er-functions-category-list.md)
