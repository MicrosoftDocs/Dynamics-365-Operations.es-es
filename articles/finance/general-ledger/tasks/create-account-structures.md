---
title: Crear estructuras contables
description: Esta guía de tareas describe los pasos de la creación de una estructura contable.
author: aprilolson
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, DimensionCreateAccountStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8b100d5da6ec26dc386c0c6cb0793245531eb0d8
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186265"
---
# <a name="create-account-structures"></a><span data-ttu-id="8e6a7-103">Crear estructuras contables</span><span class="sxs-lookup"><span data-stu-id="8e6a7-103">Create account structures</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8e6a7-104">Esta guía de tareas describe los pasos de la creación de una estructura contable.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-104">This task guide steps through creating an account structure.</span></span> <span data-ttu-id="8e6a7-105">Los pasos usan la empresa de datos de prueba USMF.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-105">The steps use demo data company USMF.</span></span>

1. <span data-ttu-id="8e6a7-106">Vaya a **Panel de exploración > Módulos > Contabilidad general > Plan de cuentas > Estructuras > Configurar estructuras contables**.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-106">Go to **Navigation pane > Modules > General ledger > Chart of accounts > Structures > Configure account structures**.</span></span>
2. <span data-ttu-id="8e6a7-107">En el panel **Acción**, haga clic en **Nuevo** para abrir el diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-107">On the **Action pane**, click **New** to open the drop dialog.</span></span>
3. <span data-ttu-id="8e6a7-108">En el campo **Estructura contable**, escriba un nombre para describir el propósito de la estructura contable.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-108">In the **Account structure** field, type a name to describe the purpose of the account structure.</span></span>
4. <span data-ttu-id="8e6a7-109">En el campo **Descripción**, escriba una descripción para especificar el propósito de la estructura contable.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-109">In the **Description** field, type a description to specify the purpose of the account structure.</span></span>
5. <span data-ttu-id="8e6a7-110">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-110">Click **Create**.</span></span>
6. <span data-ttu-id="8e6a7-111">En **Segmentos y valores permitidos**, haga clic en **Agregar segmento**.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-111">In the **Segments and allowed values**, click **Add segment**.</span></span>
7. <span data-ttu-id="8e6a7-112">En la lista de dimensiones, seleccione la dimensión que se agregará a la estructura contable.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-112">In the dimensions list, select the dimension to add to the account structure.</span></span>
8. <span data-ttu-id="8e6a7-113">Al final de la lista, haga clic en **Agregar segmento**.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-113">At the end of the list, click **Add segment**.</span></span>
9. <span data-ttu-id="8e6a7-114">Repita del paso 6 al 9 según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-114">Repeat step 6 to 9 as needed.</span></span>
10. <span data-ttu-id="8e6a7-115">En la sección **Detalles de valores permitidos**, seleccione el segmento para editar los valores permitidos.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-115">In the **Allowed value details** section, select the segment to edit the allowed values.</span></span>
    <span data-ttu-id="8e6a7-116">Por ejemplo, haga clic en **Cuenta principal**.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-116">For example, click the **Main Account** field.</span></span>  
11. <span data-ttu-id="8e6a7-117">En el campo **Operador**, seleccione una opción, como está entre e incluye.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-117">In the **Operator** field, select an option, such as is between and includes.</span></span>
12. <span data-ttu-id="8e6a7-118">En el campo **Valor**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-118">In the **Value** field, type a value.</span></span> <span data-ttu-id="8e6a7-119">Por ejemplo, 600000.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-119">For example, 600000.</span></span>  
13. <span data-ttu-id="8e6a7-120">En el campo **hasta**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-120">In the **through** field, type a value.</span></span> <span data-ttu-id="8e6a7-121">Por ejemplo, 699999.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-121">For example, 699999.</span></span>  
14. <span data-ttu-id="8e6a7-122">En la sección **Detalles de valores permitidos** , haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-122">In the **Allowed value details** section, click **Apply**.</span></span>
15. <span data-ttu-id="8e6a7-123">Repita del paso 10 al 15 según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-123">Repeat step 10 to 15 as needed.</span></span>  
16. <span data-ttu-id="8e6a7-124">En la sección **Detalles de valores permitidos** , haga clic en **Agregar nuevo criterio**.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-124">In the **Allowed value details** section, click **Add new criteria**.</span></span>
17. <span data-ttu-id="8e6a7-125">En el campo Operador, seleccione una opción, como está entre e incluye.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-125">In the Operator field, select an option, such as is between and includes.</span></span>
18. <span data-ttu-id="8e6a7-126">En el campo **Valor**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-126">In the **Value** field, type a value.</span></span> <span data-ttu-id="8e6a7-127">Por ejemplo, 033.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-127">For example, 033.</span></span>  
19. <span data-ttu-id="8e6a7-128">En el campo **hasta**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-128">In the **through** field, type a value.</span></span> <span data-ttu-id="8e6a7-129">Por ejemplo, 034.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-129">For example, 034.</span></span>  
20. <span data-ttu-id="8e6a7-130">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-130">Click **Apply**.</span></span>
21. <span data-ttu-id="8e6a7-131">En la cuadrícula, seleccione el segmento para editar los valores permitidos.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-131">In the grid, select the segment to edit the allowed values.</span></span> <span data-ttu-id="8e6a7-132">Por ejemplo, Centro de coste.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-132">For example, Cost Center.</span></span>  
22. <span data-ttu-id="8e6a7-133">En el campo **CostCenter**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-133">In the **CostCenter field**, type a value.</span></span> <span data-ttu-id="8e6a7-134">Por ejemplo, 007..021.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-134">For example, 007..021.</span></span>  
23. <span data-ttu-id="8e6a7-135">En **Segmentos y valores permitidos**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-135">In the **Segments and allowed values**, click **Add**.</span></span>
24. <span data-ttu-id="8e6a7-136">En el campo **MainAccount**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-136">In the **MainAccount** field, type a value.</span></span> <span data-ttu-id="8e6a7-137">Por ejemplo, 600000..699999</span><span class="sxs-lookup"><span data-stu-id="8e6a7-137">For example, 600000..699999</span></span>  
25. <span data-ttu-id="8e6a7-138">En la cuadrícula, seleccione el segmento para editar los valores permitidos.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-138">In the grid, select the segment to edit the allowed values.</span></span> <span data-ttu-id="8e6a7-139">Por ejemplo, Departamento.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-139">For example, Department.</span></span>  
26. <span data-ttu-id="8e6a7-140">En el campo Departamento, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-140">In the Department field, type a value.</span></span> <span data-ttu-id="8e6a7-141">Por ejemplo, 032.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-141">For example, 032.</span></span>  
27. <span data-ttu-id="8e6a7-142">En el campo CostCenter, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-142">In the CostCenter field, type a value.</span></span> <span data-ttu-id="8e6a7-143">Por ejemplo, 086.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-143">For example, 086.</span></span>  
28. <span data-ttu-id="8e6a7-144">En el panel **Acciones**, haga clic en **Validar**.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-144">On the **Action pane**, click **Validate**.</span></span>
29. <span data-ttu-id="8e6a7-145">En el panel de **Acción**, haga clic en **Activar**.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-145">On the **Action pane**, click **Activate**.</span></span>
30. <span data-ttu-id="8e6a7-146">Haga clic en **Activar**.</span><span class="sxs-lookup"><span data-stu-id="8e6a7-146">Click **Activate**.</span></span>
