---
title: Función NULLCONTAINER de ER
description: Este tema proporciona información general sobre cómo usar la función NULLCONTAINER de informes electrónicos (ER).
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
ms.openlocfilehash: dac6283ec35d3d03f586ca157048bd3ecc4bfa8a
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743936"
---
# <a name="nullcontainer-er-function"></a><span data-ttu-id="a8c3b-103">Función NULLCONTAINER de ER</span><span class="sxs-lookup"><span data-stu-id="a8c3b-103">NULLCONTAINER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a8c3b-104">La función `NULLCONTAINER` devuelve un valor nulo de tipo *Contenedor (registro)* que tiene la misma estructura que la lista de registros o el registro especificados.</span><span class="sxs-lookup"><span data-stu-id="a8c3b-104">The `NULLCONTAINER` function returns a null *Container (record)* value that has the same structure as the specified record list or record.</span></span>

## <a name="syntax"></a><span data-ttu-id="a8c3b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a8c3b-105">Syntax</span></span>

```vb
NULLCONTAINER (list)
```

## <a name="arguments"></a><span data-ttu-id="a8c3b-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a8c3b-106">Arguments</span></span>

<span data-ttu-id="a8c3b-107">`list`: *Lista de registros* o *Contenedor (registro)*</span><span class="sxs-lookup"><span data-stu-id="a8c3b-107">`list`: *Record list* or *Container (record)*</span></span>

<span data-ttu-id="a8c3b-108">La ruta válida de un origen de datos de tipo *Lista de registros* o *Contenedor (registro)*.</span><span class="sxs-lookup"><span data-stu-id="a8c3b-108">The valid path of a data source of either the *Record list* or *Container (record)* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="a8c3b-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="a8c3b-109">Return values</span></span>

<span data-ttu-id="a8c3b-110">*Contenedor (registro)*</span><span class="sxs-lookup"><span data-stu-id="a8c3b-110">*Container (record)*</span></span>

<span data-ttu-id="a8c3b-111">El valor de registro resultante.</span><span class="sxs-lookup"><span data-stu-id="a8c3b-111">The resulting record value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="a8c3b-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="a8c3b-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="a8c3b-113">Esta función es obsoleta.</span><span class="sxs-lookup"><span data-stu-id="a8c3b-113">This function is obsolete.</span></span> <span data-ttu-id="a8c3b-114">Use en su lugar la función `EMPTYRECORD`.</span><span class="sxs-lookup"><span data-stu-id="a8c3b-114">Use the `EMPTYRECORD` function instead.</span></span> <span data-ttu-id="a8c3b-115">Para obtener más información, consulte [EMPTYRECORD](er-functions-record-emptyrecord.md)</span><span class="sxs-lookup"><span data-stu-id="a8c3b-115">For more information, see [EMPTYRECORD](er-functions-record-emptyrecord.md).</span></span>

## <a name="example"></a><span data-ttu-id="a8c3b-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8c3b-116">Example</span></span>

<span data-ttu-id="a8c3b-117">`NULLCONTAINER (SPLIT ("abc", 1))` devuelve un nuevo registro vacío que tiene la misma estructura que la lista que devuelve la función `SPLIT` utilizada.</span><span class="sxs-lookup"><span data-stu-id="a8c3b-117">`NULLCONTAINER (SPLIT ("abc", 1))` returns a new empty record that has the same structure as the list that is returned by the `SPLIT` function.</span></span> <span data-ttu-id="a8c3b-118">Para obtener más información, consulte [SPLIT](er-functions-list-split.md)</span><span class="sxs-lookup"><span data-stu-id="a8c3b-118">For more information, see [SPLIT](er-functions-list-split.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a8c3b-119">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a8c3b-119">Additional resources</span></span>

[<span data-ttu-id="a8c3b-120">Funciones de registro</span><span class="sxs-lookup"><span data-stu-id="a8c3b-120">Record functions</span></span>](er-functions-category-record.md)
