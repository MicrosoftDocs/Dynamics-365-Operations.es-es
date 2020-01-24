---
title: Función SPLITLISTBYLIMIT de ER
description: En este tema se proporciona información sobre cómo usar la función SPLITLISTBYLIMIT de informes electrónicos (ER).
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
ms.openlocfilehash: f9b740b7d46fcfdf0d0b08d03411017cf909265d
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916186"
---
# <span data-ttu-id="0e07e-103"><a name="SPLITLISTBYLIMIT">Función SPLITLISTBYLIMIT de ER</a></span><span class="sxs-lookup"><span data-stu-id="0e07e-103"><a name="SPLITLISTBYLIMIT">SPLITLISTBYLIMIT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0e07e-104">La función `SPLITLISTBYLIMIT` divide la lista especificada en una nueva lista de sublistas (lotes).</span><span class="sxs-lookup"><span data-stu-id="0e07e-104">The `SPLITLISTBYLIMIT` function splits the specified list into a new list of sublists (batches).</span></span> <span data-ttu-id="0e07e-105">El número de registros en cada lote se calcula dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="0e07e-105">The number of records in each batch is dynamically calculated.</span></span> <span data-ttu-id="0e07e-106">La función devuelve luego el resultado como un nuevo valor *Lista de registros* que consiste en los lotes.</span><span class="sxs-lookup"><span data-stu-id="0e07e-106">The function then returns the result as a new *Record list* value that consists of the batches.</span></span>

## <a name="syntax"></a><span data-ttu-id="0e07e-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0e07e-107">Syntax</span></span>

```
SPLITLISTBYLIMIT (list, limit value, limit source)
```

## <a name="arguments"></a><span data-ttu-id="0e07e-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0e07e-108">Arguments</span></span>

<span data-ttu-id="0e07e-109">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="0e07e-109">`list`: *Record list*</span></span>

<span data-ttu-id="0e07e-110">La ruta válida de un origen de datos del tipo de datos *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="0e07e-110">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="0e07e-111">`limit value`: *Entero* o *Real*</span><span class="sxs-lookup"><span data-stu-id="0e07e-111">`limit value`: *Integer* or *Real*</span></span>

<span data-ttu-id="0e07e-112">El valor máximo del límite que se utiliza para dividir la lista original en lotes.</span><span class="sxs-lookup"><span data-stu-id="0e07e-112">The maximum value of the limit that is used to split the original list into batches.</span></span>

<span data-ttu-id="0e07e-113">`limit source`: *Campo*</span><span class="sxs-lookup"><span data-stu-id="0e07e-113">`limit source`: *Field*</span></span>

<span data-ttu-id="0e07e-114">La ruta válida de un campo del tipo *Entero* o *Real* en la lista especificada.</span><span class="sxs-lookup"><span data-stu-id="0e07e-114">The valid path of a field of the *Integer* or *Real* type in the specified list.</span></span> <span data-ttu-id="0e07e-115">El valor de este campo define el paso en el que se aumenta la suma total.</span><span class="sxs-lookup"><span data-stu-id="0e07e-115">The value of this field defines the step that the total sum is increased on.</span></span>

## <a name="return-values"></a><span data-ttu-id="0e07e-116">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="0e07e-116">Return values</span></span>

<span data-ttu-id="0e07e-117">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="0e07e-117">*Record list*</span></span>

<span data-ttu-id="0e07e-118">La lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="0e07e-118">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="0e07e-119">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="0e07e-119">Usage notes</span></span>

<span data-ttu-id="0e07e-120">La lista de lotes que se devuelve contiene los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="0e07e-120">The list of batches that is returned contains the following elements:</span></span>

- <span data-ttu-id="0e07e-121">**Valor**: *Lista*</span><span class="sxs-lookup"><span data-stu-id="0e07e-121">**Value**: *List*</span></span>

    <span data-ttu-id="0e07e-122">La lista de registros que pertenecen al lote actual.</span><span class="sxs-lookup"><span data-stu-id="0e07e-122">The list of records that belong to the current batch.</span></span>

- <span data-ttu-id="0e07e-123">**Número de lote**: *Entero*</span><span class="sxs-lookup"><span data-stu-id="0e07e-123">**BatchNumber**: *Integer*</span></span>

    <span data-ttu-id="0e07e-124">El número del lote actual en la lista devuelta.</span><span class="sxs-lookup"><span data-stu-id="0e07e-124">The number of the current batch in the returned list.</span></span>

<span data-ttu-id="0e07e-125">El límite no se aplica a un único artículo de la lista original si el origen del límite supera el límite definido.</span><span class="sxs-lookup"><span data-stu-id="0e07e-125">The limit isn't applied to a single item of the original list if the limit source exceeds the defined limit.</span></span>

## <a name="example"></a><span data-ttu-id="0e07e-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0e07e-126">Example</span></span>

<span data-ttu-id="0e07e-127">La ilustración siguiente muestra un formato de informes electrónicos (ER).</span><span class="sxs-lookup"><span data-stu-id="0e07e-127">The following illustration shows an Electronic reporting (ER) format.</span></span>

<a href="./media/ger-splitlistbylimit-format.png"><img src="./media/ger-splitlistbylimit-format.png" alt="Format" class="alignnone size-full wp-image-1204063" width="396" height="195" /></a>

<span data-ttu-id="0e07e-128">La siguiente ilustración muestra los orígenes de datos que se usan para el formato.</span><span class="sxs-lookup"><span data-stu-id="0e07e-128">The following illustration shows the data sources that are used for the format.</span></span>

<a href="./media/ger-splitlistbylimit-datasources.png"><img src="./media/ger-splitlistbylimit-datasources.png" alt="Data sources" class="alignnone size-full wp-image-1204073" width="320" height="208" /></a>

<span data-ttu-id="0e07e-129">La siguiente ilustración muestra el resultado cuando se ejecuta el formato.</span><span class="sxs-lookup"><span data-stu-id="0e07e-129">The following illustration shows the result when the format is run.</span></span> <span data-ttu-id="0e07e-130">En este caso, la salida es una lista plana de artículos de mercancía.</span><span class="sxs-lookup"><span data-stu-id="0e07e-130">In this case, the output is a flat list of commodity items.</span></span>

<a href="./media/ger-splitlistbylimit-output.png"><img src="./media/ger-splitlistbylimit-output.png" alt="Output" class="alignnone size-full wp-image-1204083" width="462" height="204" /></a>

<span data-ttu-id="0e07e-131">En las siguientes ilustraciones, se ha ajustado el mismo formato para que presente la lista de artículos de mercancías en lotes si un único lote debe incluir mercancías y el peso total no debe superar un límite de 9.</span><span class="sxs-lookup"><span data-stu-id="0e07e-131">In the following illustrations, the same format has been adjusted so that it presents the list of commodity items in batches if a single batch must include commodities and the total weight should not exceed a limit of 9.</span></span>

<a href="./media/ger-splitlistbylimit-format-1.png"><img src="./media/ger-splitlistbylimit-format-1.png" alt="Adjusted format" class="alignnone size-full wp-image-1204103" width="466" height="438" /></a>

<a href="./media/ger-splitlistbylimit-datasources-1.png"><img src="./media/ger-splitlistbylimit-datasources-1.png" alt="Data sources for the adjusted format" class="alignnone size-full wp-image-1204093" width="645" height="507" /></a>

<span data-ttu-id="0e07e-132">La siguiente ilustración muestra el resultado cuando se ejecuta el formato ajustado.</span><span class="sxs-lookup"><span data-stu-id="0e07e-132">The following illustration shows the result when the adjusted format is run.</span></span>

<a href="./media/ger-splitlistbylimit-output-1.png"><img src="./media/ger-splitlistbylimit-output-1.png" alt="Output of the adjusted format" class="alignnone size-full wp-image-1204113" width="676" height="611" /></a>

> [!NOTE] 
> <span data-ttu-id="0e07e-133">El límite no se aplica al último artículo de la lista original ya que el valor (**11**) del origen de su límite (**peso**) supera el límite definido (**9**).</span><span class="sxs-lookup"><span data-stu-id="0e07e-133">The limit isn't applied to the last item of the original list, because the value (**11**) of the limit source (**weight**) exceeds the defined limit (**9**).</span></span> <span data-ttu-id="0e07e-134">Para omitir las sublistas durante la generación del informe, use la función `WHERE` o la expresión **Habilitado** del elemento de formato correspondiente, según necesite.</span><span class="sxs-lookup"><span data-stu-id="0e07e-134">To ignore sublists during report generation, use either the `WHERE` function or the **Enabled** expression of the corresponding format element, as you require.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0e07e-135">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="0e07e-135">Additional resources</span></span>

[<span data-ttu-id="0e07e-136">Funciones de lista</span><span class="sxs-lookup"><span data-stu-id="0e07e-136">List functions</span></span>](er-functions-category-list.md)