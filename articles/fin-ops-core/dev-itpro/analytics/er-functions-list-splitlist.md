---
title: Función SPLITLIST de ER
description: En este tema se proporciona información acerca de cómo se usa la función SPLITLIST de informes electrónicos (ER).
author: NickSelin
ms.date: 03/15/2021
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
ms.openlocfilehash: 99e199e238b3132622a8b305895637b430e8f6d2
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745578"
---
# <a name="splitlist-er-function"></a><span data-ttu-id="60726-103">Función SPLITLIST de ER</span><span class="sxs-lookup"><span data-stu-id="60726-103">SPLITLIST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="60726-104">La función `SPLITLIST` función divide la lista especificada en sublistas (o lotes), cada uno conteniendo el número de registros especificado.</span><span class="sxs-lookup"><span data-stu-id="60726-104">The `SPLITLIST` function splits the specified list into sublists (or batches), each of which contains the specified number of records.</span></span> <span data-ttu-id="60726-105">Devuelve luego el resultado como un nuevo valor *Lista de registros* que consiste en los lotes.</span><span class="sxs-lookup"><span data-stu-id="60726-105">It then returns the result as a new *Record list* value that consists of the batches.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="60726-106">Sintaxis 1</span><span class="sxs-lookup"><span data-stu-id="60726-106">Syntax 1</span></span>

```vb
SPLITLIST (list, number)
```

## <a name="syntax-2"></a><span data-ttu-id="60726-107">Sintaxis 2</span><span class="sxs-lookup"><span data-stu-id="60726-107">Syntax 2</span></span>

```vb
SPLITLIST (list, number, on-demand reading flag)
```

## <a name="arguments"></a><span data-ttu-id="60726-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="60726-108">Arguments</span></span>

<span data-ttu-id="60726-109">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="60726-109">`list`: *Record list*</span></span>

<span data-ttu-id="60726-110">La ruta válida de un origen de datos del tipo de datos *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="60726-110">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="60726-111">`number`: *Entero*</span><span class="sxs-lookup"><span data-stu-id="60726-111">`number`: *Integer*</span></span>

<span data-ttu-id="60726-112">El número máximo de registros por lote.</span><span class="sxs-lookup"><span data-stu-id="60726-112">The maximum number of records per batch.</span></span>

<span data-ttu-id="60726-113">`on-demand reading flag`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="60726-113">`on-demand reading flag`: *Boolean*</span></span>

<span data-ttu-id="60726-114">Un valor *Booleano* que especifica si los elementos de las sublistas deben generarse a petición.</span><span class="sxs-lookup"><span data-stu-id="60726-114">A *Boolean* value that specifies whether elements of sublists should be generated on demand.</span></span>

## <a name="return-values"></a><span data-ttu-id="60726-115">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="60726-115">Return values</span></span>

<span data-ttu-id="60726-116">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="60726-116">*Record list*</span></span>

<span data-ttu-id="60726-117">La lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="60726-117">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="60726-118">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="60726-118">Usage notes</span></span>

<span data-ttu-id="60726-119">La lista de lotes que se devuelve contiene los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="60726-119">The list of batches that is returned contains the following elements:</span></span>

 - <span data-ttu-id="60726-120">**Valor:** *Lista*</span><span class="sxs-lookup"><span data-stu-id="60726-120">**Value:** *List*</span></span>

    <span data-ttu-id="60726-121">La lista de registros que pertenecen al lote actual.</span><span class="sxs-lookup"><span data-stu-id="60726-121">The list of records that belong to the current batch.</span></span>

- <span data-ttu-id="60726-122">**Número de lote:** *Entero*</span><span class="sxs-lookup"><span data-stu-id="60726-122">**BatchNumber:** *Integer*</span></span>

    <span data-ttu-id="60726-123">El número del lote actual en la lista devuelta.</span><span class="sxs-lookup"><span data-stu-id="60726-123">The number of the current batch in the returned list.</span></span>

<span data-ttu-id="60726-124">Cuando el indicador de lectura bajo demanda se establece en **Verdadero**, las sublistas se generan a petición, lo que permite una reducción en el consumo de memoria, pero puede causar una degradación del rendimiento si los elementos no se utilizan secuencialmente.</span><span class="sxs-lookup"><span data-stu-id="60726-124">When the on-demand reading flag is set to **True**, sublists are generated upon request which allows for a reduction in memory consumption but may cause performance degradation if elements aren't used sequentially.</span></span>

## <a name="example"></a><span data-ttu-id="60726-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="60726-125">Example</span></span>

<span data-ttu-id="60726-126">En la siguiente ilustración, se crea un origen de datos **Líneas** como una lista de registro que tiene tres registros.</span><span class="sxs-lookup"><span data-stu-id="60726-126">In the following illustration, a **Lines** data source is created as a record list that has three records.</span></span> <span data-ttu-id="60726-127">Esta lista se divide en lotes, cada uno contiene hasta dos registros.</span><span class="sxs-lookup"><span data-stu-id="60726-127">This list is divided into batches, each of which contains up to two records.</span></span>

<a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

<span data-ttu-id="60726-128">La siguiente ilustración muestra el diseño del formato.</span><span class="sxs-lookup"><span data-stu-id="60726-128">The following illustration shows the designed format layout.</span></span> <span data-ttu-id="60726-129">En este diseño de formato, se crean enlaces al origen de datos **Líneas** para generar una salida en formato XML.</span><span class="sxs-lookup"><span data-stu-id="60726-129">In this format layout, bindings to the **Lines** data source are created to generate output in XML format.</span></span> <span data-ttu-id="60726-130">Esta salida presenta nodos individuales para cada lote y los registros en él.</span><span class="sxs-lookup"><span data-stu-id="60726-130">This output presents individual nodes for each batch and the records in it.</span></span>

<a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a>

<span data-ttu-id="60726-131">La siguiente ilustración muestra el resultado cuando se ejecuta el formato diseñado.</span><span class="sxs-lookup"><span data-stu-id="60726-131">The following illustration shows the result when the designed format is run.</span></span>

<a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a>

## <a name="additional-resources"></a><span data-ttu-id="60726-132">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="60726-132">Additional resources</span></span>

[<span data-ttu-id="60726-133">Funciones de lista</span><span class="sxs-lookup"><span data-stu-id="60726-133">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
