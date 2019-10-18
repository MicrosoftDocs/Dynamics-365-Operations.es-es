---
title: Configurar los parámetros del espacio de trabajo de control de costes
description: Use este procedimiento para configurar el espacio de trabajo de control de costes de modo que los administradores de varios niveles de una organización puedan obtener información detallada sobre los objetos de coste, como los centros de coste y los grupos de productos.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 867bfd2f2d1ff486e683cb11c38906dd0efe8c14
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2187875"
---
# <a name="configure-cost-control-workspace-parameters"></a><span data-ttu-id="00ce3-103">Configurar los parámetros del espacio de trabajo de control de costes</span><span class="sxs-lookup"><span data-stu-id="00ce3-103">Configure cost control workspace parameters</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="00ce3-104">Use este procedimiento para configurar el espacio de trabajo de control de costes de modo que los administradores de varios niveles de una organización puedan obtener información detallada sobre los objetos de coste, como los centros de coste y los grupos de productos.</span><span class="sxs-lookup"><span data-stu-id="00ce3-104">Use this procedure to configure the Cost control workspace so that managers at various levels in an organization can gain insight into their cost objects, such as cost centers and product groups.</span></span> <span data-ttu-id="00ce3-105">La empresa de demostración USP2 se usó para crear este registro.</span><span class="sxs-lookup"><span data-stu-id="00ce3-105">The USP2 demo company was used to create this recording.</span></span>

1. <span data-ttu-id="00ce3-106">Vaya a Contabilidad de costes > Configuración > Configuración del espacio de trabajo de control de costes.</span><span class="sxs-lookup"><span data-stu-id="00ce3-106">Go to Cost accounting > Setup > Cost control workspace configuration.</span></span>
2. <span data-ttu-id="00ce3-107">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="00ce3-107">Click New.</span></span>
3. <span data-ttu-id="00ce3-108">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="00ce3-108">In the Name field, type a value.</span></span>
4. <span data-ttu-id="00ce3-109">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="00ce3-109">In the Description field, type a value.</span></span>
5. <span data-ttu-id="00ce3-110">Seleccione Sí en el campo Publicado.</span><span class="sxs-lookup"><span data-stu-id="00ce3-110">Select Yes in the Published field.</span></span>
    * <span data-ttu-id="00ce3-111">Si establece esta opción en Sí, los usuarios a los que se asignen uno de estos roles podrán ver los informes del área de trabajo de control de costes: administrador de contabilidad de costes, contable de costes, funcionario contable de costes o controlador de objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="00ce3-111">If you set this option to Yes, users who are assigned one of these roles can see the report in the Cost control workspace: cost accounting manager, cost accountant, cost accountant clerk, or cost object controller.</span></span> <span data-ttu-id="00ce3-112">Si establece esta opción en No, solo los usuarios a los que se asignen uno de estos roles podrán ver los informes del área de trabajo de control de costes: administrador de contabilidad de costes, contable de costes, funcionario contable de costes o funcionario contable de costes.</span><span class="sxs-lookup"><span data-stu-id="00ce3-112">If you set this option to No, only users who are assigned one of these roles can see the report in the Cost control workspace: cost accounting manager, cost accountant, or cost accountant clerk.</span></span>  
6. <span data-ttu-id="00ce3-113">Expanda la sección de filtrado de datos.</span><span class="sxs-lookup"><span data-stu-id="00ce3-113">Expand the Data filtering section.</span></span>
7. <span data-ttu-id="00ce3-114">En el campo Unidad de control de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="00ce3-114">In the Cost control unit field, enter or select a value.</span></span>
8. <span data-ttu-id="00ce3-115">En el campo de versión original de presupuesto, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="00ce3-115">In the Budget original version field, enter or select a value.</span></span>
9. <span data-ttu-id="00ce3-116">En el campo Jerarquía de dimensión de elementos de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="00ce3-116">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
10. <span data-ttu-id="00ce3-117">En el campo Jerarquía de dimensión de objetos de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="00ce3-117">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
11. <span data-ttu-id="00ce3-118">Expanda la sección de los registros de cálculo de asignación.</span><span class="sxs-lookup"><span data-stu-id="00ce3-118">Expand the Assign calculation records section.</span></span>
12. <span data-ttu-id="00ce3-119">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="00ce3-119">Click New.</span></span>
13. <span data-ttu-id="00ce3-120">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="00ce3-120">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="00ce3-121">En el campo Periodo de calendario fiscal, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="00ce3-121">In the Fiscal calendar period field, enter or select a value.</span></span>
15. <span data-ttu-id="00ce3-122">En el campo Versión actual, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="00ce3-122">In the Actual version field, enter or select a value.</span></span>
16. <span data-ttu-id="00ce3-123">Amplíe los Períodos fiscales por sección de columna.</span><span class="sxs-lookup"><span data-stu-id="00ce3-123">Expand the Fiscal periods per column section.</span></span>
17. <span data-ttu-id="00ce3-124">Seleccione Sí en el campo Periodo actual.</span><span class="sxs-lookup"><span data-stu-id="00ce3-124">Select Yes in the Current period field.</span></span>
18. <span data-ttu-id="00ce3-125">Expanda las columnas a mostrar para la sección de costes.</span><span class="sxs-lookup"><span data-stu-id="00ce3-125">Expand the Columns to display for costs section.</span></span>
19. <span data-ttu-id="00ce3-126">Seleccione Sí en el campo Coste fijo.</span><span class="sxs-lookup"><span data-stu-id="00ce3-126">Select Yes in the Fixed cost field.</span></span>
20. <span data-ttu-id="00ce3-127">Seleccione Sí en el campo Coste variable.</span><span class="sxs-lookup"><span data-stu-id="00ce3-127">Select Yes in the Variable cost field.</span></span>
21. <span data-ttu-id="00ce3-128">Seleccione Sí en el campo Coste total.</span><span class="sxs-lookup"><span data-stu-id="00ce3-128">Select Yes in the Total cost field.</span></span>
22. <span data-ttu-id="00ce3-129">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="00ce3-129">Click Save.</span></span>
23. <span data-ttu-id="00ce3-130">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="00ce3-130">Close the page.</span></span>
24. <span data-ttu-id="00ce3-131">Vaya a Contabilidad de costes > Espacios de trabajo > Control de costes.</span><span class="sxs-lookup"><span data-stu-id="00ce3-131">Go to Cost accounting > Workspaces > Cost control.</span></span>
25. <span data-ttu-id="00ce3-132">Seleccione un extracto para ver los costes fijos, variables, totales y sin clasificar para los períodos fiscales seleccionados.</span><span class="sxs-lookup"><span data-stu-id="00ce3-132">Select a statement to see fixed, variable, total, and unclassified costs for the selected fiscal periods.</span></span>
26. <span data-ttu-id="00ce3-133">En el campo Periodo de calendario fiscal, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="00ce3-133">In the Fiscal calendar period field, enter or select a value.</span></span>
27. <span data-ttu-id="00ce3-134">En el campo Nodo de jerarquía de dimensión de objetos de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="00ce3-134">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="00ce3-135">Una vez haya seleccionado una jerarquía de dimensión de objetos de coste, expanda la jerarquía de dimensión de elementos de coste para ver los valores de coste deseados.</span><span class="sxs-lookup"><span data-stu-id="00ce3-135">After you've selected a Cost object dimension hierarchy, expand the Cost element dimension hierarchy to see the desired cost values.</span></span> <span data-ttu-id="00ce3-136">Por ejemplo, puede expandir la jerarquía a los gastos generales de fabricación para ver el valor.</span><span class="sxs-lookup"><span data-stu-id="00ce3-136">For example, you can expand the hierarchy to Manufacturing overhead to see the value.</span></span>  

