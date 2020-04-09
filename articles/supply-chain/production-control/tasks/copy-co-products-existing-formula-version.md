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
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 93742819f492c0c169a6ca8dc2d486fe35ec4a5c
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3149352"
---
# <a name="copy-co-products-from-an-existing-formula-version"></a><span data-ttu-id="dd027-103">Copiar coproductos de una versión de fórmula existente</span><span class="sxs-lookup"><span data-stu-id="dd027-103">Copy co-products from an existing formula version</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="dd027-104">Este procedimiento muestra cómo copiar coproductos derivados de una versión de fórmula existente a otra versión de fórmula diferente para un producto liberado.</span><span class="sxs-lookup"><span data-stu-id="dd027-104">This procedure shows how to copy co-products from an existing formula version to a different formula version for a released product.</span></span> <span data-ttu-id="dd027-105">Es un requisito previo que haya al menos una versión de fórmula asociada a coproductos.</span><span class="sxs-lookup"><span data-stu-id="dd027-105">It is a prerequisite that there is at least one formula version associated with co-products.</span></span> <span data-ttu-id="dd027-106">La empresa de datos de demostración USP2 se utiliza para crear este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="dd027-106">The demo data company USP2 is used to create this procedure.</span></span>


## <a name="find-a-released-product"></a><span data-ttu-id="dd027-107">Buscar un producto liberado</span><span class="sxs-lookup"><span data-stu-id="dd027-107">Find a released product</span></span>
1. <span data-ttu-id="dd027-108">Vaya a Productos emitidos.</span><span class="sxs-lookup"><span data-stu-id="dd027-108">Go to Released products.</span></span>
2. <span data-ttu-id="dd027-109">Haga clic en Mostrar filtros.</span><span class="sxs-lookup"><span data-stu-id="dd027-109">Click Show filters.</span></span>
    * <span data-ttu-id="dd027-110">Está a punto de agregar el tipo de producción de campo en el cuadro de diálogo de filtro.</span><span class="sxs-lookup"><span data-stu-id="dd027-110">You are about to add the field Production type in the filter dialog box.</span></span>  
3. <span data-ttu-id="dd027-111">Haga clic en el campo Agregar un filtro para agregar el campo Tipo de producción.</span><span class="sxs-lookup"><span data-stu-id="dd027-111">Click Add a filter field to add the field Production type.</span></span>
    * <span data-ttu-id="dd027-112">En el siguiente paso, necesita especificar manualmente la fórmula en el campo Tipo de producción antes de seleccionar Aplicar.</span><span class="sxs-lookup"><span data-stu-id="dd027-112">In the next step, you need to manually enter Formula in the Production type field before you select Apply.</span></span> <span data-ttu-id="dd027-113">Esto establece el filtro en la lista de productos emitidos.</span><span class="sxs-lookup"><span data-stu-id="dd027-113">This sets the filter on the list of released products.</span></span>  
4. <span data-ttu-id="dd027-114">Especifique manualmente la fórmula en el campo Tipo de producción.</span><span class="sxs-lookup"><span data-stu-id="dd027-114">Manually enter Formula in the Production type field.</span></span>
5. <span data-ttu-id="dd027-115">Haga clic en Aplicar.</span><span class="sxs-lookup"><span data-stu-id="dd027-115">Click Apply.</span></span>

## <a name="select-a-released-product"></a><span data-ttu-id="dd027-116">Seleccionar un producto liberado</span><span class="sxs-lookup"><span data-stu-id="dd027-116">Select a released product</span></span>
1. <span data-ttu-id="dd027-117">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="dd027-117">In the list, find and select the desired record.</span></span>
2. <span data-ttu-id="dd027-118">Haga clic en Versiones de fórmula.</span><span class="sxs-lookup"><span data-stu-id="dd027-118">Click Formula versions.</span></span>
    * <span data-ttu-id="dd027-119">En el panel de acciones Ingeniería, haga clic en Versiones de fórmula.</span><span class="sxs-lookup"><span data-stu-id="dd027-119">On the Engineering Action Pane, click Formula versions.</span></span>  

## <a name="copy-co-products"></a><span data-ttu-id="dd027-120">Copiar coproductos</span><span class="sxs-lookup"><span data-stu-id="dd027-120">Copy co-products</span></span>
1. <span data-ttu-id="dd027-121">En el panel de acciones, haga clic en Versión de fórmula.</span><span class="sxs-lookup"><span data-stu-id="dd027-121">On the Action Pane, click Formula version.</span></span>
2. <span data-ttu-id="dd027-122">Haga clic en Productos conjuntos.</span><span class="sxs-lookup"><span data-stu-id="dd027-122">Click Co-products.</span></span>
3. <span data-ttu-id="dd027-123">Haga clic en Copiar.</span><span class="sxs-lookup"><span data-stu-id="dd027-123">Click Copy.</span></span>
4. <span data-ttu-id="dd027-124">En el campo Número de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="dd027-124">In the Item number field, enter or select a value.</span></span>
5. <span data-ttu-id="dd027-125">En el campo Versión de fórmula, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="dd027-125">In the Formula version field, enter or select a value.</span></span>
6. <span data-ttu-id="dd027-126">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="dd027-126">Click OK.</span></span>
7. <span data-ttu-id="dd027-127">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="dd027-127">Close the page.</span></span>

