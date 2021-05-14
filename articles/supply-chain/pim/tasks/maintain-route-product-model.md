---
title: Mantener ruta para un modelo de producto
description: La ejecución de este procedimiento requiere que existe un modelo de configuración de producto.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCRouteOperationDetails, WrkCtrCapabilityLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 45c6b1e6e75645bb17ce4defa0bca0e6d2131b6e
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921274"
---
# <a name="maintain-route-for-a-product-model"></a><span data-ttu-id="be708-103">Mantener ruta para un modelo de producto</span><span class="sxs-lookup"><span data-stu-id="be708-103">Maintain route for a product model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="be708-104">La ejecución de este procedimiento requiere que existe un modelo de configuración de producto.</span><span class="sxs-lookup"><span data-stu-id="be708-104">Running this procedure requires that a product configuration model exists.</span></span> <span data-ttu-id="be708-105">Este procedimiento usa el modelo Altavoz superior en la empresa de demostración de datos USMF para guiarle por el proceso.</span><span class="sxs-lookup"><span data-stu-id="be708-105">This procedure uses the High end speaker model in the demo company USMF to walk you through the process.</span></span>

## <a name="add-a-route-operation"></a><span data-ttu-id="be708-106">Agregar un nodo de ruta</span><span class="sxs-lookup"><span data-stu-id="be708-106">Add a route operation</span></span>

1. <span data-ttu-id="be708-107">Vaya a **Gestión de información de productos \> Productos \> Modelos de configuración del producto**.</span><span class="sxs-lookup"><span data-stu-id="be708-107">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="be708-108">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="be708-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="be708-109">Seleccione el modelo Altavoz superior para este ejercicio.</span><span class="sxs-lookup"><span data-stu-id="be708-109">Select the High end speaker model for this exercise.</span></span>  
1. <span data-ttu-id="be708-110">En la lista, seleccione el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="be708-110">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="be708-111">Expanda la sección **Operaciones de ruta**.</span><span class="sxs-lookup"><span data-stu-id="be708-111">Expand the **Route operations** section.</span></span>
1. <span data-ttu-id="be708-112">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="be708-112">Select **Add**.</span></span>
1. <span data-ttu-id="be708-113">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="be708-113">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="be708-114">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="be708-114">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="be708-115">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="be708-115">Select **Save**.</span></span>

## <a name="enter-route-operation-details"></a><span data-ttu-id="be708-116">Especificar detalles de operación de ruta</span><span class="sxs-lookup"><span data-stu-id="be708-116">Enter route operation details</span></span>

1. <span data-ttu-id="be708-117">Seleccione **Detalles de operación de ruta**.</span><span class="sxs-lookup"><span data-stu-id="be708-117">Select **Route operation details**.</span></span>
1. <span data-ttu-id="be708-118">En el campo **Operación**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="be708-118">In the **Operation** field, enter or select a value.</span></span>
1. <span data-ttu-id="be708-119">En el campo **N.º oper.**</span><span class="sxs-lookup"><span data-stu-id="be708-119">In the **Oper. No.**</span></span> <span data-ttu-id="be708-120">especifique un número.</span><span class="sxs-lookup"><span data-stu-id="be708-120">field, enter a number.</span></span>
    * <span data-ttu-id="be708-121">Los números de operación determinan la secuencia de ruta.</span><span class="sxs-lookup"><span data-stu-id="be708-121">Operation numbers determine the route sequence.</span></span>  
    * <span data-ttu-id="be708-122">Cada propiedad de una operación de ruta puede obtener un valor estático o se puede asignar a un atributo.</span><span class="sxs-lookup"><span data-stu-id="be708-122">Each property on a route operation can get a static value or be mapped to an attribute.</span></span> <span data-ttu-id="be708-123">La asignación a un atributo dará lugar al valor que se está estableciendo como parte de la configuración.</span><span class="sxs-lookup"><span data-stu-id="be708-123">Mapping to an attribute will result in the value being set as part of the configuration.</span></span>  
1. <span data-ttu-id="be708-124">En el campo **Grupo de rutas**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="be708-124">In the **Route group** field, enter or select a value.</span></span>
    * <span data-ttu-id="be708-125">El grupo de rutas determina el comportamiento esencial de la gestión de costes, el consumo y la configuración.</span><span class="sxs-lookup"><span data-stu-id="be708-125">The route group determines essential behavior for costing, consumption, and setup.</span></span>  
1. <span data-ttu-id="be708-126">Seleccione la pestaña **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="be708-126">Select the **Setup** tab.</span></span>
1. <span data-ttu-id="be708-127">Seleccione la pestaña **Veces**.</span><span class="sxs-lookup"><span data-stu-id="be708-127">Select the **Times** tab.</span></span>
1. <span data-ttu-id="be708-128">En el campo **Cantidad de proceso**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="be708-128">In the **Process qty.** field, enter a number.</span></span>
    * <span data-ttu-id="be708-129">Determine cuántos se procesarán durante una operación.</span><span class="sxs-lookup"><span data-stu-id="be708-129">Determine how many will be processed during one operation.</span></span>  
1. <span data-ttu-id="be708-130">En el campo **Horas/tiempo**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="be708-130">In the **Hours/time** field, enter a number.</span></span>
    * <span data-ttu-id="be708-131">Escriba el coeficiente de tiempo.</span><span class="sxs-lookup"><span data-stu-id="be708-131">Enter the time ratio.</span></span>  
1. <span data-ttu-id="be708-132">Seleccione la casilla **Establecer**.</span><span class="sxs-lookup"><span data-stu-id="be708-132">Select the **Set** check box.</span></span>
1. <span data-ttu-id="be708-133">En el campo **Tiempo de ejecución**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="be708-133">In the **Run time** field, enter a number.</span></span>
    * <span data-ttu-id="be708-134">Determine el tiempo de procesamiento para la cantidad que ha especificado.</span><span class="sxs-lookup"><span data-stu-id="be708-134">Determine the processing time for the quantity that you have specified.</span></span>  
1. <span data-ttu-id="be708-135">Seleccione la ficha **Requisitos de recursos**.</span><span class="sxs-lookup"><span data-stu-id="be708-135">Select the **Resource requirements** tab.</span></span>
1. <span data-ttu-id="be708-136">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="be708-136">Select **Add**.</span></span>
1. <span data-ttu-id="be708-137">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="be708-137">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="be708-138">En el campo **Tipo de requisito**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="be708-138">In the **Requirement type** field, select an option.</span></span>
    * <span data-ttu-id="be708-139">Decida si desea especificar recursos o capacidades específicos que debe poseer.</span><span class="sxs-lookup"><span data-stu-id="be708-139">Decide if you want to specify specific resources or capabilities that they must possess.</span></span>  
1. <span data-ttu-id="be708-140">En el campo **Requisito**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="be708-140">In the **Requirement** field, enter or select a value.</span></span>
1. <span data-ttu-id="be708-141">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="be708-141">Select **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]