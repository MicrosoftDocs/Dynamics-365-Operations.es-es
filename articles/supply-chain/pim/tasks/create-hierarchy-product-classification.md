---
title: Crear una jerarquía de clasificación de productos
description: Este procedimiento muestra cómo crear una nueva jerarquía de categoría y asignar un tipo de jerarquía de código de mercancías.
author: ShylaThompson
manager: tfehr
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResCategoryHierarchyListPage, EcoResCategoryHierarchyCreate, EcoResCategory, EcoResCategoryHierarchyRole, EcoResProductCategory, EcoResCategorySearchList, EcoResCategoryHierarchyFactbox, EcoResCategoryFriendlyName, EcoResCategoryAddProduct
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 439df63a4f8f0cc1c030554d18f80e9934c88b00
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436855"
---
# <a name="create-a-hierarchy-of-product-classification"></a><span data-ttu-id="f7aa3-103">Crear una jerarquía de clasificación de productos</span><span class="sxs-lookup"><span data-stu-id="f7aa3-103">Create a hierarchy of product classification</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f7aa3-104">Este procedimiento muestra cómo crear una nueva jerarquía de categoría y asignar un tipo de jerarquía de código de mercancías.</span><span class="sxs-lookup"><span data-stu-id="f7aa3-104">This procedure shows how to create a new category hierarchy and assign a commodity code hierarchy type.</span></span> <span data-ttu-id="f7aa3-105">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="f7aa3-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="f7aa3-106">Este procedimiento va destinado al director de categorías.</span><span class="sxs-lookup"><span data-stu-id="f7aa3-106">This procedure is intended for the category manager.</span></span>


## <a name="create-the-new-category-hierarchy"></a><span data-ttu-id="f7aa3-107">Creación de la jerarquía de categorías nueva</span><span class="sxs-lookup"><span data-stu-id="f7aa3-107">Create the new category hierarchy</span></span>
1. <span data-ttu-id="f7aa3-108">Vaya a **Panel de exploración > Módulos > Gestión de información de productos > Configuración > Categorías y atributos > Jerarquías de categorías**.</span><span class="sxs-lookup"><span data-stu-id="f7aa3-108">Go to **Navigation pane > Modules > Product information management > Setup > Categories and attributes > Category hierarchies**.</span></span>
2. <span data-ttu-id="f7aa3-109">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="f7aa3-109">Click **New**.</span></span>
3. <span data-ttu-id="f7aa3-110">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f7aa3-110">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="f7aa3-111">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f7aa3-111">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="f7aa3-112">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="f7aa3-112">Click **Create**.</span></span>

## <a name="build-the-hierarchy"></a><span data-ttu-id="f7aa3-113">Creación de la jerarquía</span><span class="sxs-lookup"><span data-stu-id="f7aa3-113">Build the hierarchy</span></span>
1. <span data-ttu-id="f7aa3-114">Haga clic en el nodo de categoría **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="f7aa3-114">Click **New** category node.</span></span>
2. <span data-ttu-id="f7aa3-115">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f7aa3-115">In the **Name** field, type a value.</span></span>
3. <span data-ttu-id="f7aa3-116">En el campo **Código**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f7aa3-116">In the **Code** field, type a value.</span></span>
4. <span data-ttu-id="f7aa3-117">En el campo **Nombre descriptivo**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f7aa3-117">In the **Friendly name** field, type a value.</span></span>
5. <span data-ttu-id="f7aa3-118">Haga clic en el nodo de categoría **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="f7aa3-118">Click **New** category node.</span></span>
6. <span data-ttu-id="f7aa3-119">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f7aa3-119">In the **Name** field, type a value.</span></span>
7. <span data-ttu-id="f7aa3-120">En el campo **Código**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f7aa3-120">In the **Code** field, type a value.</span></span>
8. <span data-ttu-id="f7aa3-121">En el campo **Nombre descriptivo**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f7aa3-121">In the **Friendly name** field, type a value.</span></span>
9. <span data-ttu-id="f7aa3-122">Haga clic en el nodo de categoría **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="f7aa3-122">Click **New** category node.</span></span>
10. <span data-ttu-id="f7aa3-123">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f7aa3-123">In the **Name** field, type a value.</span></span>
11. <span data-ttu-id="f7aa3-124">En el campo **Código**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f7aa3-124">In the **Code** field, type a value.</span></span>
12. <span data-ttu-id="f7aa3-125">En el campo **Nombre descriptivo**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f7aa3-125">In the **Friendly name** field, type a value.</span></span>
13. <span data-ttu-id="f7aa3-126">Haga clic en el nodo de categoría **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="f7aa3-126">Click **New** category node.</span></span>
14. <span data-ttu-id="f7aa3-127">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f7aa3-127">In the **Name** field, type a value.</span></span>
15. <span data-ttu-id="f7aa3-128">En el campo **Código**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f7aa3-128">In the **Code** field, type a value.</span></span>
16. <span data-ttu-id="f7aa3-129">En el campo **Nombre descriptivo**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f7aa3-129">In the **Friendly name** field, type a value.</span></span>
17. <span data-ttu-id="f7aa3-130">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f7aa3-130">Close the page.</span></span>

## <a name="classify-the-hierarchy"></a><span data-ttu-id="f7aa3-131">Clasificación de la jerarquía</span><span class="sxs-lookup"><span data-stu-id="f7aa3-131">Classify the hierarchy</span></span>
1. <span data-ttu-id="f7aa3-132">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="f7aa3-132">In the list, find and select the desired record.</span></span>
2. <span data-ttu-id="f7aa3-133">En el **Panel de acciones**, haga clic en **Jerarquía de categoría**.</span><span class="sxs-lookup"><span data-stu-id="f7aa3-133">On the **Action Pane**, click **Category hierarchy**.</span></span>
3. <span data-ttu-id="f7aa3-134">Haga clic en **Asociar tipo de jerarquía**.</span><span class="sxs-lookup"><span data-stu-id="f7aa3-134">Click **Associate hierarchy type**.</span></span>
4. <span data-ttu-id="f7aa3-135">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="f7aa3-135">Click **New**.</span></span>
5. <span data-ttu-id="f7aa3-136">En el campo **Tipo de jerarquía de categorías**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="f7aa3-136">In the **Category hierarchy type** field, select an option.</span></span> <span data-ttu-id="f7aa3-137">Seleccione **Tipo de jerarquía de categoría de código de mercancía para la clasificación del producto**.</span><span class="sxs-lookup"><span data-stu-id="f7aa3-137">Select the **Commodity code category hierarchy type for product classification**.</span></span>  
6. <span data-ttu-id="f7aa3-138">En el campo **Jerarquía de categoría**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f7aa3-138">In the **Category hierarchy** field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="f7aa3-139">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="f7aa3-139">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="f7aa3-140">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f7aa3-140">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="f7aa3-141">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f7aa3-141">Close the page.</span></span>

