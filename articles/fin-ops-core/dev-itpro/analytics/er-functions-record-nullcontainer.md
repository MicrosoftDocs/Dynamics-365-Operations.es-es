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
ms.openlocfilehash: ea71bfc4b30164fd32e804bf83a46c49cd18d155
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041478"
---
# <span data-ttu-id="ccd4d-103"><a name="NULLCONTAINER">Función NULLCONTAINER de ER</a></span><span class="sxs-lookup"><span data-stu-id="ccd4d-103"><a name="NULLCONTAINER">NULLCONTAINER ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ccd4d-104">La función `NULLCONTAINER` devuelve un valor nulo de tipo *Contenedor (registro)* que tiene la misma estructura que la lista de registros o el registro especificados.</span><span class="sxs-lookup"><span data-stu-id="ccd4d-104">The `NULLCONTAINER` function returns a null *Container (record)* value that has the same structure as the specified record list or record.</span></span>

## <a name="syntax"></a><span data-ttu-id="ccd4d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ccd4d-105">Syntax</span></span>

```vb
NULLCONTAINER (list)
```

## <a name="arguments"></a><span data-ttu-id="ccd4d-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ccd4d-106">Arguments</span></span>

<span data-ttu-id="ccd4d-107">`list`: *Lista de registros* o *Contenedor (registro)*</span><span class="sxs-lookup"><span data-stu-id="ccd4d-107">`list`: *Record list* or *Container (record)*</span></span>

<span data-ttu-id="ccd4d-108">La ruta válida de un origen de datos de tipo *Lista de registros* o *Contenedor (registro)*.</span><span class="sxs-lookup"><span data-stu-id="ccd4d-108">The valid path of a data source of either the *Record list* or *Container (record)* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="ccd4d-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="ccd4d-109">Return values</span></span>

<span data-ttu-id="ccd4d-110">*Contenedor (registro)*</span><span class="sxs-lookup"><span data-stu-id="ccd4d-110">*Container (record)*</span></span>

<span data-ttu-id="ccd4d-111">El valor de registro resultante.</span><span class="sxs-lookup"><span data-stu-id="ccd4d-111">The resulting record value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="ccd4d-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="ccd4d-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="ccd4d-113">Esta función es obsoleta.</span><span class="sxs-lookup"><span data-stu-id="ccd4d-113">This function is obsolete.</span></span> <span data-ttu-id="ccd4d-114">Use en su lugar la función `EMPTYRECORD`.</span><span class="sxs-lookup"><span data-stu-id="ccd4d-114">Use the `EMPTYRECORD` function instead.</span></span> <span data-ttu-id="ccd4d-115">Para obtener más información, consulte [EMPTYRECORD](er-functions-record-emptyrecord.md)</span><span class="sxs-lookup"><span data-stu-id="ccd4d-115">For more information, see [EMPTYRECORD](er-functions-record-emptyrecord.md).</span></span>

## <a name="example"></a><span data-ttu-id="ccd4d-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ccd4d-116">Example</span></span>

<span data-ttu-id="ccd4d-117">`NULLCONTAINER (SPLIT ("abc", 1))` devuelve un nuevo registro vacío que tiene la misma estructura que la lista que devuelve la función `SPLIT` utilizada.</span><span class="sxs-lookup"><span data-stu-id="ccd4d-117">`NULLCONTAINER (SPLIT ("abc", 1))` returns a new empty record that has the same structure as the list that is returned by the `SPLIT` function.</span></span> <span data-ttu-id="ccd4d-118">Para obtener más información, consulte [SPLIT](er-functions-list-split.md)</span><span class="sxs-lookup"><span data-stu-id="ccd4d-118">For more information, see [SPLIT](er-functions-list-split.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ccd4d-119">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="ccd4d-119">Additional resources</span></span>

[<span data-ttu-id="ccd4d-120">Funciones de registro</span><span class="sxs-lookup"><span data-stu-id="ccd4d-120">Record functions</span></span>](er-functions-category-record.md)
