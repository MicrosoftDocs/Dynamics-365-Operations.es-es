---
title: Función LISTOFFIRSTITEM de ER
description: En este tema se proporciona información sobre cómo usar la función LISTOFFIRSTITEM de informes electrónicos (ER).
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
ms.openlocfilehash: 4d985ef5015bc104a83260b64418821cc715e8cb
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917267"
---
# <span data-ttu-id="53794-103"><a name="LISTOFFIRSTITEM">Función LISTOFFIRSTITEM de ER</a></span><span class="sxs-lookup"><span data-stu-id="53794-103"><a name="LISTOFFIRSTITEM">LISTOFFIRSTITEM ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="53794-104">La función `LISTOFFIRSTITEM` devuelve un valor *Lista de registros* que consiste en solo el primer registro de la lista especificada.</span><span class="sxs-lookup"><span data-stu-id="53794-104">The `LISTOFFIRSTITEM` function returns a *Record list* value that consists of only the first record of the specified list.</span></span>

## <a name="syntax"></a><span data-ttu-id="53794-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53794-105">Syntax</span></span>

```
LISTOFFIRSTITEM (list)
```

## <a name="arguments"></a><span data-ttu-id="53794-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="53794-106">Arguments</span></span>

<span data-ttu-id="53794-107">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="53794-107">`list`: *Record list*</span></span>

<span data-ttu-id="53794-108">La ruta válida de un origen de datos del tipo de datos *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="53794-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="53794-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="53794-109">Return values</span></span>

<span data-ttu-id="53794-110">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="53794-110">*Record list*</span></span>

<span data-ttu-id="53794-111">La lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="53794-111">The resulting list of records.</span></span>

## <a name="example"></a><span data-ttu-id="53794-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="53794-112">Example</span></span>

<span data-ttu-id="53794-113">La expresión `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` devuelve el valor del texto **"A"**.</span><span class="sxs-lookup"><span data-stu-id="53794-113">The expression `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` returns the text value **"A"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="53794-114">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="53794-114">Additional resources</span></span>

[<span data-ttu-id="53794-115">Funciones de lista</span><span class="sxs-lookup"><span data-stu-id="53794-115">List functions</span></span>](er-functions-category-list.md)
