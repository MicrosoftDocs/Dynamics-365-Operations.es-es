---
title: Copiar coproductos de una versión de fórmula existente
description: Este procedimiento muestra cómo copiar coproductos derivados de una versión de fórmula existente a otra versión de fórmula diferente para un producto liberado.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, BOMConsistOf, PmfFormulaCoBy, BOMRouteCopyDialog
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 179c12da0c2ddc7b5e2f2fdddd21168eac121811
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1557811"
---
# <a name="copy-co-products-from-an-existing-formula-version"></a><span data-ttu-id="f16d0-103">Copiar coproductos de una versión de fórmula existente</span><span class="sxs-lookup"><span data-stu-id="f16d0-103">Copy co-products from an existing formula version</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f16d0-104">Este procedimiento muestra cómo copiar coproductos derivados de una versión de fórmula existente a otra versión de fórmula diferente para un producto liberado.</span><span class="sxs-lookup"><span data-stu-id="f16d0-104">This procedure shows how to copy co-products from an existing formula version to a different formula version for a released product.</span></span> <span data-ttu-id="f16d0-105">Es un requisito previo que haya al menos una versión de fórmula asociada a coproductos.</span><span class="sxs-lookup"><span data-stu-id="f16d0-105">It is a prerequisite that there is at least one formula version associated with co-products.</span></span> <span data-ttu-id="f16d0-106">La empresa de datos de demostración USP2 se utiliza para crear este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f16d0-106">The demo data company USP2 is used to create this procedure.</span></span>


## <a name="find-a-released-product"></a><span data-ttu-id="f16d0-107">Buscar un producto liberado</span><span class="sxs-lookup"><span data-stu-id="f16d0-107">Find a released product</span></span>
1. <span data-ttu-id="f16d0-108">Vaya a Productos emitidos.</span><span class="sxs-lookup"><span data-stu-id="f16d0-108">Go to Released products.</span></span>
2. <span data-ttu-id="f16d0-109">Haga clic en Mostrar filtros.</span><span class="sxs-lookup"><span data-stu-id="f16d0-109">Click Show filters.</span></span>
    * <span data-ttu-id="f16d0-110">Está a punto de agregar el tipo de producción de campo en el cuadro de diálogo de filtro.</span><span class="sxs-lookup"><span data-stu-id="f16d0-110">You are about to add the field Production type in the filter dialog box.</span></span>  
3. <span data-ttu-id="f16d0-111">Haga clic en el campo Agregar un filtro para agregar el campo Tipo de producción.</span><span class="sxs-lookup"><span data-stu-id="f16d0-111">Click Add a filter field to add the field Production type.</span></span>
    * <span data-ttu-id="f16d0-112">En el siguiente paso, necesita especificar manualmente la fórmula en el campo Tipo de producción antes de seleccionar Aplicar.</span><span class="sxs-lookup"><span data-stu-id="f16d0-112">In the next step, you need to manually enter Formula in the Production type field before you select Apply.</span></span> <span data-ttu-id="f16d0-113">Esto establece el filtro en la lista de productos emitidos.</span><span class="sxs-lookup"><span data-stu-id="f16d0-113">This sets the filter on the list of released products.</span></span>  
4. <span data-ttu-id="f16d0-114">Especifique manualmente la fórmula en el campo Tipo de producción.</span><span class="sxs-lookup"><span data-stu-id="f16d0-114">Manually enter Formula in the Production type field.</span></span>
5. <span data-ttu-id="f16d0-115">Haga clic en Aplicar.</span><span class="sxs-lookup"><span data-stu-id="f16d0-115">Click Apply.</span></span>

## <a name="select-a-released-product"></a><span data-ttu-id="f16d0-116">Seleccionar un producto liberado</span><span class="sxs-lookup"><span data-stu-id="f16d0-116">Select a released product</span></span>
1. <span data-ttu-id="f16d0-117">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="f16d0-117">In the list, find and select the desired record.</span></span>
2. <span data-ttu-id="f16d0-118">Haga clic en Versiones de fórmula.</span><span class="sxs-lookup"><span data-stu-id="f16d0-118">Click Formula versions.</span></span>
    * <span data-ttu-id="f16d0-119">En el panel de acciones Ingeniería, haga clic en Versiones de fórmula.</span><span class="sxs-lookup"><span data-stu-id="f16d0-119">On the Engineering Action Pane, click Formula versions.</span></span>  

## <a name="copy-co-products"></a><span data-ttu-id="f16d0-120">Copiar coproductos</span><span class="sxs-lookup"><span data-stu-id="f16d0-120">Copy co-products</span></span>
1. <span data-ttu-id="f16d0-121">En el panel de acciones, haga clic en Versión de fórmula.</span><span class="sxs-lookup"><span data-stu-id="f16d0-121">On the Action Pane, click Formula version.</span></span>
2. <span data-ttu-id="f16d0-122">Haga clic en Productos conjuntos.</span><span class="sxs-lookup"><span data-stu-id="f16d0-122">Click Co-products.</span></span>
3. <span data-ttu-id="f16d0-123">Haga clic en Copiar.</span><span class="sxs-lookup"><span data-stu-id="f16d0-123">Click Copy.</span></span>
4. <span data-ttu-id="f16d0-124">En el campo Número de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f16d0-124">In the Item number field, enter or select a value.</span></span>
5. <span data-ttu-id="f16d0-125">En el campo Versión de fórmula, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f16d0-125">In the Formula version field, enter or select a value.</span></span>
6. <span data-ttu-id="f16d0-126">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="f16d0-126">Click OK.</span></span>
7. <span data-ttu-id="f16d0-127">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f16d0-127">Close the page.</span></span>

