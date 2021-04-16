---
title: Crear una jerarquía de clasificación de productos
description: Este procedimiento muestra cómo crear una nueva jerarquía de categoría y asignar un tipo de jerarquía de código de mercancías.
author: ShylaThompson
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResCategoryHierarchyListPage, EcoResCategoryHierarchyCreate, EcoResCategory, EcoResCategoryHierarchyRole, EcoResProductCategory, EcoResCategorySearchList, EcoResCategoryHierarchyFactbox, EcoResCategoryFriendlyName, EcoResCategoryAddProduct
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d4e2fdc62d7faa73efa78092d7754d3fa1213a94
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809383"
---
# <a name="create-a-hierarchy-of-product-classification"></a><span data-ttu-id="2d673-103">Crear una jerarquía de clasificación de productos</span><span class="sxs-lookup"><span data-stu-id="2d673-103">Create a hierarchy of product classification</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2d673-104">Este procedimiento muestra cómo crear una nueva jerarquía de categoría y asignar un tipo de jerarquía de código de mercancías.</span><span class="sxs-lookup"><span data-stu-id="2d673-104">This procedure shows how to create a new category hierarchy and assign a commodity code hierarchy type.</span></span> <span data-ttu-id="2d673-105">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="2d673-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="2d673-106">Este procedimiento va destinado al director de categorías.</span><span class="sxs-lookup"><span data-stu-id="2d673-106">This procedure is intended for the category manager.</span></span>


## <a name="create-the-new-category-hierarchy"></a><span data-ttu-id="2d673-107">Creación de la jerarquía de categorías nueva</span><span class="sxs-lookup"><span data-stu-id="2d673-107">Create the new category hierarchy</span></span>
1. <span data-ttu-id="2d673-108">Vaya a **Panel de exploración > Módulos > Gestión de información de productos > Configuración > Categorías y atributos > Jerarquías de categorías**.</span><span class="sxs-lookup"><span data-stu-id="2d673-108">Go to **Navigation pane > Modules > Product information management > Setup > Categories and attributes > Category hierarchies**.</span></span>
2. <span data-ttu-id="2d673-109">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="2d673-109">Click **New**.</span></span>
3. <span data-ttu-id="2d673-110">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="2d673-110">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="2d673-111">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="2d673-111">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="2d673-112">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="2d673-112">Click **Create**.</span></span>

## <a name="build-the-hierarchy"></a><span data-ttu-id="2d673-113">Creación de la jerarquía</span><span class="sxs-lookup"><span data-stu-id="2d673-113">Build the hierarchy</span></span>
1. <span data-ttu-id="2d673-114">Haga clic en el nodo de categoría **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="2d673-114">Click **New** category node.</span></span>
2. <span data-ttu-id="2d673-115">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="2d673-115">In the **Name** field, type a value.</span></span>
3. <span data-ttu-id="2d673-116">En el campo **Código**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="2d673-116">In the **Code** field, type a value.</span></span>
4. <span data-ttu-id="2d673-117">En el campo **Nombre descriptivo**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="2d673-117">In the **Friendly name** field, type a value.</span></span>
5. <span data-ttu-id="2d673-118">Haga clic en el nodo de categoría **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="2d673-118">Click **New** category node.</span></span>
6. <span data-ttu-id="2d673-119">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="2d673-119">In the **Name** field, type a value.</span></span>
7. <span data-ttu-id="2d673-120">En el campo **Código**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="2d673-120">In the **Code** field, type a value.</span></span>
8. <span data-ttu-id="2d673-121">En el campo **Nombre descriptivo**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="2d673-121">In the **Friendly name** field, type a value.</span></span>
9. <span data-ttu-id="2d673-122">Haga clic en el nodo de categoría **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="2d673-122">Click **New** category node.</span></span>
10. <span data-ttu-id="2d673-123">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="2d673-123">In the **Name** field, type a value.</span></span>
11. <span data-ttu-id="2d673-124">En el campo **Código**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="2d673-124">In the **Code** field, type a value.</span></span>
12. <span data-ttu-id="2d673-125">En el campo **Nombre descriptivo**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="2d673-125">In the **Friendly name** field, type a value.</span></span>
13. <span data-ttu-id="2d673-126">Haga clic en el nodo de categoría **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="2d673-126">Click **New** category node.</span></span>
14. <span data-ttu-id="2d673-127">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="2d673-127">In the **Name** field, type a value.</span></span>
15. <span data-ttu-id="2d673-128">En el campo **Código**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="2d673-128">In the **Code** field, type a value.</span></span>
16. <span data-ttu-id="2d673-129">En el campo **Nombre descriptivo**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="2d673-129">In the **Friendly name** field, type a value.</span></span>
17. <span data-ttu-id="2d673-130">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="2d673-130">Close the page.</span></span>

## <a name="classify-the-hierarchy"></a><span data-ttu-id="2d673-131">Clasificación de la jerarquía</span><span class="sxs-lookup"><span data-stu-id="2d673-131">Classify the hierarchy</span></span>
1. <span data-ttu-id="2d673-132">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="2d673-132">In the list, find and select the desired record.</span></span>
2. <span data-ttu-id="2d673-133">En el **Panel de acciones**, haga clic en **Jerarquía de categoría**.</span><span class="sxs-lookup"><span data-stu-id="2d673-133">On the **Action Pane**, click **Category hierarchy**.</span></span>
3. <span data-ttu-id="2d673-134">Haga clic en **Asociar tipo de jerarquía**.</span><span class="sxs-lookup"><span data-stu-id="2d673-134">Click **Associate hierarchy type**.</span></span>
4. <span data-ttu-id="2d673-135">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="2d673-135">Click **New**.</span></span>
5. <span data-ttu-id="2d673-136">En el campo **Tipo de jerarquía de categorías**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="2d673-136">In the **Category hierarchy type** field, select an option.</span></span> <span data-ttu-id="2d673-137">Seleccione **Tipo de jerarquía de categoría de código de mercancía para la clasificación del producto**.</span><span class="sxs-lookup"><span data-stu-id="2d673-137">Select the **Commodity code category hierarchy type for product classification**.</span></span>  
6. <span data-ttu-id="2d673-138">En el campo **Jerarquía de categoría**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="2d673-138">In the **Category hierarchy** field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="2d673-139">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="2d673-139">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="2d673-140">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="2d673-140">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="2d673-141">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="2d673-141">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]