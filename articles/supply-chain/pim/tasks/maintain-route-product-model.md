--- 
title: Mantener una ruta para un modelo de producto
description: "La ejecución de este procedimiento requiere que existe un modelo de configuración de producto."
author: YuyuScheller
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: 637614a17513ec68c0a180f46606ac8430c00133
ms.contentlocale: es-es
ms.lasthandoff: 01/17/2018

---
# <a name="maintain-a-route-for-a-product-model"></a><span data-ttu-id="00636-103">Mantener una ruta para un modelo de producto</span><span class="sxs-lookup"><span data-stu-id="00636-103">Maintain a route for a product model</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="00636-104">La ejecución de este procedimiento requiere que existe un modelo de configuración de producto.</span><span class="sxs-lookup"><span data-stu-id="00636-104">Running this procedure requires that a product configuration model exists.</span></span> <span data-ttu-id="00636-105">Este procedimiento usa el modelo Altavoz superior en la empresa de demostración de datos USMF para guiarle por el proceso.</span><span class="sxs-lookup"><span data-stu-id="00636-105">This procedure uses the High end speaker model in the demo company USMF to walk you through the process.</span></span>


## <a name="add-a-route-operation"></a><span data-ttu-id="00636-106">Agregar un nodo de ruta</span><span class="sxs-lookup"><span data-stu-id="00636-106">Add a route operation</span></span>
1. <span data-ttu-id="00636-107">Haga clic en Definición de modelo de variante del producto.</span><span class="sxs-lookup"><span data-stu-id="00636-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="00636-108">Haga clic en Modelos de configuración del producto.</span><span class="sxs-lookup"><span data-stu-id="00636-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="00636-109">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="00636-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="00636-110">Seleccione el modelo Altavoz superior para este ejercicio.</span><span class="sxs-lookup"><span data-stu-id="00636-110">Select the High end speaker model for this exercise.</span></span>  
4. <span data-ttu-id="00636-111">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="00636-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="00636-112">Expanda la sección Operaciones de ruta.</span><span class="sxs-lookup"><span data-stu-id="00636-112">Expand the Route operations section.</span></span>
6. <span data-ttu-id="00636-113">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="00636-113">Click Add.</span></span>
7. <span data-ttu-id="00636-114">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="00636-114">In the Name field, type a value.</span></span>
8. <span data-ttu-id="00636-115">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="00636-115">In the Description field, type a value.</span></span>
9. <span data-ttu-id="00636-116">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="00636-116">Click Save.</span></span>

## <a name="enter-route-operation-details"></a><span data-ttu-id="00636-117">Especificar detalles de operación de ruta</span><span class="sxs-lookup"><span data-stu-id="00636-117">Enter route operation details</span></span>
1. <span data-ttu-id="00636-118">Haga clic en Detalles de operación de ruta.</span><span class="sxs-lookup"><span data-stu-id="00636-118">Click Route operation details.</span></span>
2. <span data-ttu-id="00636-119">En el campo Operación, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="00636-119">In the Operation field, enter or select a value.</span></span>
3. <span data-ttu-id="00636-120">El campo Nº de oper.</span><span class="sxs-lookup"><span data-stu-id="00636-120">In the Oper.</span></span> <span data-ttu-id="00636-121">N. º</span><span class="sxs-lookup"><span data-stu-id="00636-121">No.</span></span> <span data-ttu-id="00636-122">especifique un número.</span><span class="sxs-lookup"><span data-stu-id="00636-122">field, enter a number.</span></span>
    * <span data-ttu-id="00636-123">Los números de operación determinan la secuencia de ruta.</span><span class="sxs-lookup"><span data-stu-id="00636-123">Operation numbers determine the route sequence.</span></span>  
    * <span data-ttu-id="00636-124">Cada propiedad de una operación de ruta puede obtener un valor estático o se puede asignar a un atributo.</span><span class="sxs-lookup"><span data-stu-id="00636-124">Each property on a route operation can get a static value or be mapped to an attribute.</span></span> <span data-ttu-id="00636-125">La asignación a un atributo dará lugar al valor que se está estableciendo como parte de la configuración.</span><span class="sxs-lookup"><span data-stu-id="00636-125">Mapping to an attribute will result in the value being set as part of the configuration.</span></span>  
4. <span data-ttu-id="00636-126">En el campo Grupo de rutas, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="00636-126">In the Route group field, enter or select a value.</span></span>
    * <span data-ttu-id="00636-127">El grupo de rutas determina el comportamiento esencial de la gestión de costes, el consumo y la configuración.</span><span class="sxs-lookup"><span data-stu-id="00636-127">The route group determines essential behavior for costing, consumption, and setup.</span></span>  
5. <span data-ttu-id="00636-128">Haga clic en la pestaña Configurar.</span><span class="sxs-lookup"><span data-stu-id="00636-128">Click the Setup tab.</span></span>
6. <span data-ttu-id="00636-129">Haga clic en la ficha Tiempos.</span><span class="sxs-lookup"><span data-stu-id="00636-129">Click the Times tab.</span></span>
7. <span data-ttu-id="00636-130">En el campo Cantidad de proceso, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="00636-130">In the Process qty. field, enter a number.</span></span>
    * <span data-ttu-id="00636-131">Determine cuántos se procesarán durante una operación.</span><span class="sxs-lookup"><span data-stu-id="00636-131">Determine how many will be processed during one operation.</span></span>  
8. <span data-ttu-id="00636-132">En el campo Horas/tiempo, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="00636-132">In the Hours/time field, enter a number.</span></span>
    * <span data-ttu-id="00636-133">Escriba el coeficiente de tiempo.</span><span class="sxs-lookup"><span data-stu-id="00636-133">Enter the time ratio.</span></span>  
9. <span data-ttu-id="00636-134">Active la casilla Establecer.</span><span class="sxs-lookup"><span data-stu-id="00636-134">Select the Set check box.</span></span>
10. <span data-ttu-id="00636-135">En el campo Tiempo de ejecución, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="00636-135">In the Run time field, enter a number.</span></span>
    * <span data-ttu-id="00636-136">Determine el tiempo de procesamiento para la cantidad que ha especificado.</span><span class="sxs-lookup"><span data-stu-id="00636-136">Determine the processing time for the quantity that you have specified.</span></span>  
11. <span data-ttu-id="00636-137">Haga clic en la ficha Requisitos de recursos.</span><span class="sxs-lookup"><span data-stu-id="00636-137">Click the Resource requirements tab.</span></span>
12. <span data-ttu-id="00636-138">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="00636-138">Click Add.</span></span>
13. <span data-ttu-id="00636-139">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="00636-139">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="00636-140">En el campo Tipo de requisito, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="00636-140">In the Requirement type field, select an option.</span></span>
    * <span data-ttu-id="00636-141">Decida si desea especificar recursos o capacidades específicos que debe poseer.</span><span class="sxs-lookup"><span data-stu-id="00636-141">Decide if you want to specify specific resources or capabilities that they must possess.</span></span>  
15. <span data-ttu-id="00636-142">En el campo Requisito, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="00636-142">In the Requirement field, enter or select a value.</span></span>
16. <span data-ttu-id="00636-143">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="00636-143">Click OK.</span></span>


