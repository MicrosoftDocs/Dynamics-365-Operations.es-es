--- 
title: Configurar los derechos de acceso para un controlador de objeto de coste
description: Use este procedimiento para configurar los derechos de acceso para el controlador de objeto de coste.
author: YuyuScheller
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 533d592191ba639c9345d23f4daf5bafb6db2766
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---
# <a name="configure-access-rights-for-a-cost-object-controller"></a><span data-ttu-id="4ca1d-103">Configurar los derechos de acceso para un controlador de objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4ca1d-103">Configure access rights for a cost object controller</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4ca1d-104">Use este procedimiento para configurar los derechos de acceso para el controlador de objeto de coste.</span><span class="sxs-lookup"><span data-stu-id="4ca1d-104">Use this procedure to configure access rights for a cost object controller.</span></span> <span data-ttu-id="4ca1d-105">Este registro usa la empresa USP2 con los datos para demostración.</span><span class="sxs-lookup"><span data-stu-id="4ca1d-105">This recording uses the USP2 demo data company.</span></span>


## <a name="assign-the-cost-object-controller-role"></a><span data-ttu-id="4ca1d-106">Asignar el rol del controlador del objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4ca1d-106">Assign the cost object controller role</span></span>
1. <span data-ttu-id="4ca1d-107">Vaya a Administración del sistema > Usuarios > Usuarios.</span><span class="sxs-lookup"><span data-stu-id="4ca1d-107">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="4ca1d-108">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="4ca1d-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="4ca1d-109">Por ejemplo, filtre según el campo Nombre de usuario con un valor de “alicia”.</span><span class="sxs-lookup"><span data-stu-id="4ca1d-109">For example, filter on the User name field with a value of 'alicia'.</span></span>
3. <span data-ttu-id="4ca1d-110">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4ca1d-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="4ca1d-111">Haga clic en Asignar roles.</span><span class="sxs-lookup"><span data-stu-id="4ca1d-111">Click Assign roles.</span></span>
5. <span data-ttu-id="4ca1d-112">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="4ca1d-112">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="4ca1d-113">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="4ca1d-113">Click OK.</span></span>

## <a name="enable-access-list-security"></a><span data-ttu-id="4ca1d-114">Habilitar la seguridad de lista de acceso</span><span class="sxs-lookup"><span data-stu-id="4ca1d-114">Enable access list security</span></span>
1. <span data-ttu-id="4ca1d-115">Vaya a Contabilidad de costes > Dimensiones > Jerarquías de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="4ca1d-115">Go to Cost accounting > Dimensions > Dimension hierarchies.</span></span>
2. <span data-ttu-id="4ca1d-116">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="4ca1d-116">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="4ca1d-117">Seleccione Organización.</span><span class="sxs-lookup"><span data-stu-id="4ca1d-117">Select Organization.</span></span>  
3. <span data-ttu-id="4ca1d-118">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="4ca1d-118">Click Edit.</span></span>
4. <span data-ttu-id="4ca1d-119">Seleccione Sí en el campo de la jerarquía de la lista de acceso.</span><span class="sxs-lookup"><span data-stu-id="4ca1d-119">Select Yes in the Access list hierarchy field.</span></span>
5. <span data-ttu-id="4ca1d-120">Haga clic en Ver jerarquía.</span><span class="sxs-lookup"><span data-stu-id="4ca1d-120">Click View hierarchy.</span></span>

## <a name="assign-access-rights-to-user"></a><span data-ttu-id="4ca1d-121">Asignar derechos de acceso al usuario</span><span class="sxs-lookup"><span data-stu-id="4ca1d-121">Assign access rights to user</span></span>
1. <span data-ttu-id="4ca1d-122">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="4ca1d-122">Click New.</span></span>
2. <span data-ttu-id="4ca1d-123">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4ca1d-123">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="4ca1d-124">En el campo Id. de usuario, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="4ca1d-124">In the User ID field, enter or select a value.</span></span>
    * <span data-ttu-id="4ca1d-125">Seleccione Administración.</span><span class="sxs-lookup"><span data-stu-id="4ca1d-125">Select Admin.</span></span>  
4. <span data-ttu-id="4ca1d-126">En el árbol, seleccione "Organización\Director general\Director financiero\FIM".</span><span class="sxs-lookup"><span data-stu-id="4ca1d-126">In the tree, select 'Organization\CEO\CFO\FIM'.</span></span>
5. <span data-ttu-id="4ca1d-127">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="4ca1d-127">Click New.</span></span>
6. <span data-ttu-id="4ca1d-128">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4ca1d-128">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="4ca1d-129">En el campo Id. de usuario, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="4ca1d-129">In the User ID field, enter or select a value.</span></span>
    * <span data-ttu-id="4ca1d-130">Seleccione Alicia.</span><span class="sxs-lookup"><span data-stu-id="4ca1d-130">Select Alicia.</span></span>  
8. <span data-ttu-id="4ca1d-131">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="4ca1d-131">Click Save.</span></span>

## <a name="enable-access-rights-in-cost-accounting"></a><span data-ttu-id="4ca1d-132">Habilitar derechos de acceso en la contabilidad de costes</span><span class="sxs-lookup"><span data-stu-id="4ca1d-132">Enable access rights in Cost accounting</span></span>
1. <span data-ttu-id="4ca1d-133">Vaya a Contabilidad de costes > Configuración > Parámetros.</span><span class="sxs-lookup"><span data-stu-id="4ca1d-133">Go to Cost accounting > Setup > Parameters.</span></span>
2. <span data-ttu-id="4ca1d-134">Haga clic en la pestaña General.</span><span class="sxs-lookup"><span data-stu-id="4ca1d-134">Click the General tab.</span></span>
3. <span data-ttu-id="4ca1d-135">Seleccione Sí en el parámetro Habilitar acceso de visualización para el campo de miembros de dimensión de objeto de coste.</span><span class="sxs-lookup"><span data-stu-id="4ca1d-135">Select Yes in the Enable view access for cost object dimension members field.</span></span>
4. <span data-ttu-id="4ca1d-136">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="4ca1d-136">Click Save.</span></span>
5. <span data-ttu-id="4ca1d-137">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="4ca1d-137">Close the page.</span></span>
6. <span data-ttu-id="4ca1d-138">Vaya a Contabilidad de costes > Configuración > Configuración del espacio de trabajo de control de costes.</span><span class="sxs-lookup"><span data-stu-id="4ca1d-138">Go to Cost accounting > Setup > Cost control workspace configuration.</span></span>
7. <span data-ttu-id="4ca1d-139">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="4ca1d-139">Click Edit.</span></span>
8. <span data-ttu-id="4ca1d-140">Seleccione Sí en el campo Publicado.</span><span class="sxs-lookup"><span data-stu-id="4ca1d-140">Select Yes in the Published field.</span></span>
    * <span data-ttu-id="4ca1d-141">Si selecciona Sí, un usuario al que se asigna uno de los cuatro roles siguientes puede ver los informes del área de trabajo de control de costes: administrador de contabilidad de costes, contable de costes, funcionario contable de costes y controlador de objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="4ca1d-141">If you select Yes, a user who is assigned one of the following four roles can see the reports in the Cost control workspace: cost accounting manager, cost accountant, cost accountant clerk, and cost object controller.</span></span> <span data-ttu-id="4ca1d-142">Si selecciona No, solo un usuario al que se asigna uno de los cuatro roles siguientes puede ver los informes del área de trabajo de control de costes: administrador de contabilidad de costes, contable de costes y funcionario contable de costes.</span><span class="sxs-lookup"><span data-stu-id="4ca1d-142">If you select No, only a user who is assigned one of the following roles can see the reports: cost accounting manager, cost accountant, and cost accountant clerk.</span></span>    
9. <span data-ttu-id="4ca1d-143">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="4ca1d-143">Click Save.</span></span>


