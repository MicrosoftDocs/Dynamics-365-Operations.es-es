---
title: Buscar variantes de producto obsoletas
description: Este procedimiento muestra cómo encontrar los productos liberados obsoletos o las variantes de producto y cómo asociar un estado de ciclo de vida del producto a los productos obsoletos.
author: cvocph
manager: AnnBe
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dcd0f67bae1042cb1e81423898eacd20f921e0e2
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3147601"
---
# <a name="find-obsolete-product-variants"></a><span data-ttu-id="8ebe4-103">Buscar variantes de producto obsoletas</span><span class="sxs-lookup"><span data-stu-id="8ebe4-103">Find obsolete product variants</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8ebe4-104">Este procedimiento muestra cómo encontrar los productos liberados obsoletos o las variantes de producto y cómo asociar un estado de ciclo de vida del producto a los productos obsoletos.</span><span class="sxs-lookup"><span data-stu-id="8ebe4-104">This procedure shows how to find obsolete released products or product variants and how to associate a product lifecycle state to the obsolete products.</span></span> <span data-ttu-id="8ebe4-105">Requisito previo: Es necesario definir el menos un estado de ciclo de vida del producto que esté inactivo para realizar la planificación antes de que se pueda reproducir esta guía de la tarea.</span><span class="sxs-lookup"><span data-stu-id="8ebe4-105">Prerequisite: You need to define at least one product lifecycle state that is inactive for planning before you can play this task guide.</span></span>


## <a name="run-a-simulation"></a><span data-ttu-id="8ebe4-106">Ejecutar una simulación</span><span class="sxs-lookup"><span data-stu-id="8ebe4-106">Run a simulation</span></span>
1. <span data-ttu-id="8ebe4-107">Vaya a Gestión de información de productos > Tareas periódicas > Cambiar estado de ciclo de vida para productos obsoletos.</span><span class="sxs-lookup"><span data-stu-id="8ebe4-107">Go to Product information management > Periodic tasks > Change lifecycle state for obsolete products.</span></span>
2. <span data-ttu-id="8ebe4-108">En el campo Nuevo estado de ciclo de vida de producto, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8ebe4-108">In the New product lifecycle state field, enter or select a value.</span></span>
3. <span data-ttu-id="8ebe4-109">Seleccione Sí en el campo Ejecutar simulación sin actualizar datos de producto.</span><span class="sxs-lookup"><span data-stu-id="8ebe4-109">Select Yes in the Run simulation without updating product data field.</span></span>
4. <span data-ttu-id="8ebe4-110">En el campo Excluir productos creados dentro de este número de días, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="8ebe4-110">In the Exclude products created within this number of days field, enter a number.</span></span>
5. <span data-ttu-id="8ebe4-111">En el campo Excluir productos usados en transacciones (en número de días), escriba un número.</span><span class="sxs-lookup"><span data-stu-id="8ebe4-111">In the Exclude products used in transactions (in number of days) field, enter a number.</span></span>
6. <span data-ttu-id="8ebe4-112">Expanda la sección Registros que incluir.</span><span class="sxs-lookup"><span data-stu-id="8ebe4-112">Expand the Records to include section.</span></span>
7. <span data-ttu-id="8ebe4-113">Haga clic en Filtro.</span><span class="sxs-lookup"><span data-stu-id="8ebe4-113">Click Filter.</span></span>
8. <span data-ttu-id="8ebe4-114">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8ebe4-114">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="8ebe4-115">En el campo Criterios, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="8ebe4-115">In the Criteria field, type a value.</span></span>
10. <span data-ttu-id="8ebe4-116">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="8ebe4-116">Click OK.</span></span>
11. <span data-ttu-id="8ebe4-117">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="8ebe4-117">Click OK.</span></span>

> [!NOTE]
> <span data-ttu-id="8ebe4-118">Se recomienda ejecutar la simulación en lotes si espera buscar un gran número de productos.</span><span class="sxs-lookup"><span data-stu-id="8ebe4-118">It is recommended to run the simulation in batch if you expect to search a large number of products.</span></span> <span data-ttu-id="8ebe4-119">Además, asegúrese de que la simulación no se ejecute durante el período laborable más activo de la empresa.</span><span class="sxs-lookup"><span data-stu-id="8ebe4-119">Also, make sure that the simulation is not run during the most active working time of the company.</span></span>  

## <a name="review-the-simulation-results"></a><span data-ttu-id="8ebe4-120">Revise los resultados de simulación</span><span class="sxs-lookup"><span data-stu-id="8ebe4-120">Review the simulation results</span></span>
1. <span data-ttu-id="8ebe4-121">Vaya a Gestión de información de productos > Consultas e informes > Historial de mantenimiento de estado del ciclo de vida del producto.</span><span class="sxs-lookup"><span data-stu-id="8ebe4-121">Go to Product information management > Inquiries and reports > Product lifecycle state maintenance history.</span></span>
   
> [!NOTE]
> <span data-ttu-id="8ebe4-122">En esta página puede revisar los resultados de simulación y evaluar la cantidad de productos y variantes de producto que se asociarán a un estado del ciclo de vida del nuevo producto al ejecutar la actualización sin la simulación.</span><span class="sxs-lookup"><span data-stu-id="8ebe4-122">On this page, you can review the simulation results and make an assessment of how many products and product variants will be associated with a new product lifecycle state when running the update without simulation.</span></span>  

## <a name="run-the-update-of-the-product-lifecycle-state-for-obsolete-products"></a><span data-ttu-id="8ebe4-123">Ejecute la actualización del estado del ciclo de vida de producto para los productos obsoletos</span><span class="sxs-lookup"><span data-stu-id="8ebe4-123">Run the update of the Product lifecycle state for obsolete products</span></span>
1. <span data-ttu-id="8ebe4-124">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="8ebe4-124">Close the page.</span></span>
2. <span data-ttu-id="8ebe4-125">Vaya a Gestión de información de productos > Tareas periódicas > Cambiar estado de ciclo de vida para productos obsoletos.</span><span class="sxs-lookup"><span data-stu-id="8ebe4-125">Go to Product information management > Periodic tasks > Change lifecycle state for obsolete products.</span></span>
3. <span data-ttu-id="8ebe4-126">Expanda la sección Registros que incluir.</span><span class="sxs-lookup"><span data-stu-id="8ebe4-126">Expand the Records to include section.</span></span>

> [!NOTE]
> <span data-ttu-id="8ebe4-127">Observe que se ha guardado la última selección.</span><span class="sxs-lookup"><span data-stu-id="8ebe4-127">Note that the last selection has been saved.</span></span>  

4. <span data-ttu-id="8ebe4-128">Seleccione No en el campo Ejecutar simulación sin actualizar datos de producto.</span><span class="sxs-lookup"><span data-stu-id="8ebe4-128">Select No in the Run simulation without updating product data field.</span></span>
5. <span data-ttu-id="8ebe4-129">Expanda la sección Ejecutar en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="8ebe4-129">Expand the Run in the background section.</span></span>

> [!NOTE]
> <span data-ttu-id="8ebe4-130">En función de la cantidad de productos y variantes de producto se vean afectadas, considere ejecutar este trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="8ebe4-130">Depending on how many products and product variants are affected, consider running this job in batch.</span></span> <span data-ttu-id="8ebe4-131">Compruebe que no se ejecuta un trabajo de actualización grande durante el horario laboral más activo de la empresa.</span><span class="sxs-lookup"><span data-stu-id="8ebe4-131">Make sure that you are not running a large update job during the most active working hours in the company.</span></span>  

6. <span data-ttu-id="8ebe4-132">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="8ebe4-132">Click OK.</span></span>
7. <span data-ttu-id="8ebe4-133">Vaya a Gestión de información de productos > Consultas e informes > Historial de mantenimiento de estado del ciclo de vida del producto.</span><span class="sxs-lookup"><span data-stu-id="8ebe4-133">Go to Product information management > Inquiries and reports > Product lifecycle state maintenance history.</span></span>

> [!NOTE]
> <span data-ttu-id="8ebe4-134">Revise los productos emitidos y las variantes de producto cambiados.</span><span class="sxs-lookup"><span data-stu-id="8ebe4-134">Review the changed released products and product variants.</span></span>  

8. <span data-ttu-id="8ebe4-135">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="8ebe4-135">In the list, find and select the desired record.</span></span>

