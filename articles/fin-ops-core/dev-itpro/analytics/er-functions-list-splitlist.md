---
title: Función SPLITLIST de ER
description: En este tema se proporciona información acerca de cómo se usa la función SPLITLIST de informes electrónicos (ER).
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
ms.openlocfilehash: 950fc711f0e28eaee7fabc437ee16a022e1b705e
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744800"
---
# <a name="splitlist-er-function"></a><span data-ttu-id="a569b-103">Función SPLITLIST de ER</span><span class="sxs-lookup"><span data-stu-id="a569b-103">SPLITLIST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a569b-104">La función `SPLITLIST` función divide la lista especificada en sublistas (o lotes), cada uno conteniendo el número de registros especificado.</span><span class="sxs-lookup"><span data-stu-id="a569b-104">The `SPLITLIST` function splits the specified list into sublists (or batches), each of which contains the specified number of records.</span></span> <span data-ttu-id="a569b-105">Devuelve luego el resultado como un nuevo valor *Lista de registros* que consiste en los lotes.</span><span class="sxs-lookup"><span data-stu-id="a569b-105">It then returns the result as a new *Record list* value that consists of the batches.</span></span>

## <a name="syntax"></a><span data-ttu-id="a569b-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a569b-106">Syntax</span></span>

```vb
SPLITLIST (list, number)
```

## <a name="arguments"></a><span data-ttu-id="a569b-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a569b-107">Arguments</span></span>

<span data-ttu-id="a569b-108">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="a569b-108">`list`: *Record list*</span></span>

<span data-ttu-id="a569b-109">La ruta válida de un origen de datos del tipo de datos *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="a569b-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="a569b-110">`number`: *Entero*</span><span class="sxs-lookup"><span data-stu-id="a569b-110">`number`: *Integer*</span></span>

<span data-ttu-id="a569b-111">El número máximo de registros por lote.</span><span class="sxs-lookup"><span data-stu-id="a569b-111">The maximum number of records per batch.</span></span>

## <a name="return-values"></a><span data-ttu-id="a569b-112">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="a569b-112">Return values</span></span>

<span data-ttu-id="a569b-113">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="a569b-113">*Record list*</span></span>

<span data-ttu-id="a569b-114">La lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="a569b-114">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="a569b-115">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="a569b-115">Usage notes</span></span>

<span data-ttu-id="a569b-116">La lista de lotes que se devuelve contiene los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a569b-116">The list of batches that is returned contains the following elements:</span></span>

 - <span data-ttu-id="a569b-117">**Valor:** *Lista*</span><span class="sxs-lookup"><span data-stu-id="a569b-117">**Value:** *List*</span></span>

    <span data-ttu-id="a569b-118">La lista de registros que pertenecen al lote actual.</span><span class="sxs-lookup"><span data-stu-id="a569b-118">The list of records that belong to the current batch.</span></span>

- <span data-ttu-id="a569b-119">**Número de lote:** *Entero*</span><span class="sxs-lookup"><span data-stu-id="a569b-119">**BatchNumber:** *Integer*</span></span>

    <span data-ttu-id="a569b-120">El número del lote actual en la lista devuelta.</span><span class="sxs-lookup"><span data-stu-id="a569b-120">The number of the current batch in the returned list.</span></span>

## <a name="example"></a><span data-ttu-id="a569b-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a569b-121">Example</span></span>

<span data-ttu-id="a569b-122">En la siguiente ilustración, se crea un origen de datos **Líneas** como una lista de registro que tiene tres registros.</span><span class="sxs-lookup"><span data-stu-id="a569b-122">In the following illustration, a **Lines** data source is created as a record list that has three records.</span></span> <span data-ttu-id="a569b-123">Esta lista se divide en lotes, cada uno contiene hasta dos registros.</span><span class="sxs-lookup"><span data-stu-id="a569b-123">This list is divided into batches, each of which contains up to two records.</span></span>

<a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

<span data-ttu-id="a569b-124">La siguiente ilustración muestra el diseño del formato.</span><span class="sxs-lookup"><span data-stu-id="a569b-124">The following illustration shows the designed format layout.</span></span> <span data-ttu-id="a569b-125">En este diseño de formato, se crean enlaces al origen de datos **Líneas** para generar una salida en formato XML.</span><span class="sxs-lookup"><span data-stu-id="a569b-125">In this format layout, bindings to the **Lines** data source are created to generate output in XML format.</span></span> <span data-ttu-id="a569b-126">Esta salida presenta nodos individuales para cada lote y los registros en él.</span><span class="sxs-lookup"><span data-stu-id="a569b-126">This output presents individual nodes for each batch and the records in it.</span></span>

<a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a>

<span data-ttu-id="a569b-127">La siguiente ilustración muestra el resultado cuando se ejecuta el formato diseñado.</span><span class="sxs-lookup"><span data-stu-id="a569b-127">The following illustration shows the result when the designed format is run.</span></span>

<a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a>

## <a name="additional-resources"></a><span data-ttu-id="a569b-128">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a569b-128">Additional resources</span></span>

[<span data-ttu-id="a569b-129">Funciones de lista</span><span class="sxs-lookup"><span data-stu-id="a569b-129">List functions</span></span>](er-functions-category-list.md)
