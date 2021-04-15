---
title: Función FIRST de ER
description: Este tema proporciona información general sobre cómo usar la función FIRST de informes electrónicos (ER).
author: NickSelin
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
ms.openlocfilehash: d30c8481866ccf3f7080197b37586a0460a4ad2c
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746588"
---
# <a name="first-er-function"></a><span data-ttu-id="a4471-103">Función FIRST de ER</span><span class="sxs-lookup"><span data-stu-id="a4471-103">FIRST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a4471-104">La función `FIRST` devuelve el primer registro de la lista especificada como un valor *Contenedor (registro)*, si esa lista no está vacía.</span><span class="sxs-lookup"><span data-stu-id="a4471-104">The `FIRST` function returns the first record of the specified list as a *Container (record)* value, if that list isn't empty.</span></span> <span data-ttu-id="a4471-105">Si la lista está vacía, esta función genera una excepción.</span><span class="sxs-lookup"><span data-stu-id="a4471-105">If the list is empty, this function throws an exception.</span></span>

## <a name="syntax"></a><span data-ttu-id="a4471-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a4471-106">Syntax</span></span>

```vb
FIRST (list)
```

## <a name="arguments"></a><span data-ttu-id="a4471-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a4471-107">Arguments</span></span>

<span data-ttu-id="a4471-108">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="a4471-108">`list`: *Record list*</span></span>

<span data-ttu-id="a4471-109">La ruta válida de un origen de datos del tipo de datos *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="a4471-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="a4471-110">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="a4471-110">Return values</span></span>

<span data-ttu-id="a4471-111">*Contenedor (registro)*</span><span class="sxs-lookup"><span data-stu-id="a4471-111">*Container (record)*</span></span>

<span data-ttu-id="a4471-112">El valor de registro resultante.</span><span class="sxs-lookup"><span data-stu-id="a4471-112">The resulting record value.</span></span>

## <a name="example-1"></a><span data-ttu-id="a4471-113">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="a4471-113">Example 1</span></span>

<span data-ttu-id="a4471-114">La expresión `FIRST(SPLIT("ABC",1)).Value` devuelve el valor del texto **"A"**.</span><span class="sxs-lookup"><span data-stu-id="a4471-114">The expression `FIRST(SPLIT("ABC",1)).Value` returns the text value **"A"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="a4471-115">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="a4471-115">Example 2</span></span>

<span data-ttu-id="a4471-116">La expresión `FIRST(SPLIT("",1)).Value` lanza una excepción en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a4471-116">The expression `FIRST(SPLIT("",1)).Value` throws an exception at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a4471-117">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a4471-117">Additional resources</span></span>

[<span data-ttu-id="a4471-118">Funciones de lista</span><span class="sxs-lookup"><span data-stu-id="a4471-118">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]