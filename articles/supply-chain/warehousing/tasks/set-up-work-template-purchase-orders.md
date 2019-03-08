---
title: Configurar una plantilla de trabajo para pedidos de compra
description: Este procedimiento se centra en la configuración de una plantilla de trabajo simple que se debe usar al ubicar los artículos recibidos.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkTemplateTable, SysQueryForm
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d737f9dfd1888602266a87853e54407618ae2781
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "318037"
---
# <a name="set-up-a-work-template-for-purchase-orders"></a><span data-ttu-id="622d4-103">Configurar una plantilla de trabajo para pedidos de compra</span><span class="sxs-lookup"><span data-stu-id="622d4-103">Set up a work template for purchase orders</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="622d4-104">Este procedimiento se centra en la configuración de una plantilla de trabajo simple que se debe usar al ubicar los artículos recibidos.</span><span class="sxs-lookup"><span data-stu-id="622d4-104">This procedure focuses on the set up of a simple work template to be used when putting away received items.</span></span> <span data-ttu-id="622d4-105">Las plantillas de trabajo determinan el sistema de instrucciones presentadas al trabajador del almacén en un dispositivo móvil al mover artículos desde el área de recepción.</span><span class="sxs-lookup"><span data-stu-id="622d4-105">Work templates determine the set of instructions presented to the warehouse worker on a mobile device when moving items from the receiving area.</span></span> <span data-ttu-id="622d4-106">Puede utilizar este procedimiento con los datos mencionados en la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="622d4-106">You can use this procedure with the data mentioned in demo data company USMF.</span></span> <span data-ttu-id="622d4-107">Antes de comenzar esta guía, cree un id. de grupo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="622d4-107">Before you start this guide, create a work pool ID.</span></span> <span data-ttu-id="622d4-108">En este ejemplo, se usa un id. grupo de trabajo denominado Entrada.</span><span class="sxs-lookup"><span data-stu-id="622d4-108">In this example, a work pool ID called in Inbound is used.</span></span> <span data-ttu-id="622d4-109">Este procedimiento va destinado al encargado de almacén.</span><span class="sxs-lookup"><span data-stu-id="622d4-109">This procedure is intended for the warehouse manager.</span></span>

1. <span data-ttu-id="622d4-110">Vaya a Gestión de almacenes > Configurar > Trabajo > Plantillas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="622d4-110">Go to Warehouse management > Setup > Work > Work templates.</span></span>
2. <span data-ttu-id="622d4-111">En el campo Tipo de pedido de trabajo, seleccione Pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="622d4-111">In the Work order type field, select 'Purchase orders'.</span></span>

## <a name="create-a-work-template-header"></a><span data-ttu-id="622d4-112">Crear un encabezado de plantilla de trabajo</span><span class="sxs-lookup"><span data-stu-id="622d4-112">Create a work template header</span></span>
1. <span data-ttu-id="622d4-113">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="622d4-113">Click New.</span></span>
2. <span data-ttu-id="622d4-114">En el campo Número de secuencia, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="622d4-114">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="622d4-115">Esta es la secuencia en la que se evalúan las plantillas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="622d4-115">This is the sequence in which the work templates are evaluated.</span></span> <span data-ttu-id="622d4-116">Si fuera necesario, puede modificar la secuencia.</span><span class="sxs-lookup"><span data-stu-id="622d4-116">You can modify the sequence, if needed.</span></span>  
3. <span data-ttu-id="622d4-117">En el campo Plantilla de trabajo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="622d4-117">In the Work template field, type a value.</span></span>
    * <span data-ttu-id="622d4-118">Este es el identificador único para esta plantilla.</span><span class="sxs-lookup"><span data-stu-id="622d4-118">This is the unique identifier for this template.</span></span>  
4. <span data-ttu-id="622d4-119">En el campo Descripción de la plantilla de trabajo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="622d4-119">In the Work template description field, type a value.</span></span>
    * <span data-ttu-id="622d4-120">La opción Válido no se activará hasta que haya completado toda la información que necesita la plantilla y haya hecho clic después en Guardar.</span><span class="sxs-lookup"><span data-stu-id="622d4-120">The Valid option will not be checked until you’ve completed all the information that's needed by the template and have then clicked Save.</span></span>  
    * <span data-ttu-id="622d4-121">Un pedido de trabajo del tipo Pedido de compra no se puede procesar automáticamente, por tanto, deje la opción Procesar automáticamente establecida en No.</span><span class="sxs-lookup"><span data-stu-id="622d4-121">A work order of type Purchase order cannot be automatically processed, so leave the  Automatically process option set to No.</span></span>  
5. <span data-ttu-id="622d4-122">En el campo Id. del grupo de trabajo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="622d4-122">In the Work pool ID field, type a value.</span></span>
    * <span data-ttu-id="622d4-123">Los id. del grupo de trabajo le permiten organizar el trabajo en grupos.</span><span class="sxs-lookup"><span data-stu-id="622d4-123">Work pool IDs allow you to organize work into groups.</span></span> <span data-ttu-id="622d4-124">El valor que se establece aquí será el valor predeterminado para cualquier trabajo que se crea usando esta plantilla.</span><span class="sxs-lookup"><span data-stu-id="622d4-124">The value that you set here will be the default value for any work that’s created using this template.</span></span>  
6. <span data-ttu-id="622d4-125">En el campo Prioridad de trabajo, escriba "1".</span><span class="sxs-lookup"><span data-stu-id="622d4-125">In the Work priority field, enter '1'.</span></span>
    * <span data-ttu-id="622d4-126">Esto indica la importancia del trabajo y el valor que se establece aquí será el predeterminado para los trabajos creados con esta plantilla.</span><span class="sxs-lookup"><span data-stu-id="622d4-126">This indicates the importance of the work, and the value that you set here will be the default for any work created using this template.</span></span>  
7. <span data-ttu-id="622d4-127">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="622d4-127">Click Save.</span></span>
    * <span data-ttu-id="622d4-128">Debe guardar el encabezado de la plantilla de trabajo antes de que el botón Editar consulta se vuelva disponible.</span><span class="sxs-lookup"><span data-stu-id="622d4-128">You must save the work template header before the Edit Query button becomes available.</span></span>  

## <a name="set-up-the-query-for-the-work-template"></a><span data-ttu-id="622d4-129">Configurar la consulta para la plantilla de trabajo</span><span class="sxs-lookup"><span data-stu-id="622d4-129">Set up the query for the work template</span></span>
1. <span data-ttu-id="622d4-130">Haga clic en Editar consulta.</span><span class="sxs-lookup"><span data-stu-id="622d4-130">Click Edit query.</span></span>
    * <span data-ttu-id="622d4-131">Estableceremos una limitación de que la plantilla solo se puede usar dentro de un almacén específico.</span><span class="sxs-lookup"><span data-stu-id="622d4-131">We’ll set a limitation that the template can only be used within a specific warehouse.</span></span>  
2. <span data-ttu-id="622d4-132">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="622d4-132">Click Add.</span></span>
3. <span data-ttu-id="622d4-133">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="622d4-133">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="622d4-134">En el campo Almacén, escriba "almacén".</span><span class="sxs-lookup"><span data-stu-id="622d4-134">In the Field field, type 'warehouse'.</span></span>
5. <span data-ttu-id="622d4-135">En el campo Criterios, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="622d4-135">In the Criteria field, type a value.</span></span>
6. <span data-ttu-id="622d4-136">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="622d4-136">Click OK.</span></span>
7. <span data-ttu-id="622d4-137">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="622d4-137">Click Yes.</span></span>

## <a name="set-work-template-details"></a><span data-ttu-id="622d4-138">Establecer detalles de plantilla de trabajo</span><span class="sxs-lookup"><span data-stu-id="622d4-138">Set work template details</span></span>
1. <span data-ttu-id="622d4-139">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="622d4-139">Click New.</span></span>
2. <span data-ttu-id="622d4-140">En el campo Tipo de trabajo, seleccione "Seleccionar".</span><span class="sxs-lookup"><span data-stu-id="622d4-140">In the Work type field, select 'Pick'.</span></span>
3. <span data-ttu-id="622d4-141">En el campo Identificador de la clase de trabajo, escriba "compra".</span><span class="sxs-lookup"><span data-stu-id="622d4-141">In the Work class ID field, type 'purchase'.</span></span>
    * <span data-ttu-id="622d4-142">La clase de trabajo que establece aquí será el valor predeterminado en todas las líneas de trabajo de tipo Seleccionar que se crean con esta plantilla.</span><span class="sxs-lookup"><span data-stu-id="622d4-142">The work class that you set here will be the default on all work lines of type Pick that are created using this template.</span></span> <span data-ttu-id="622d4-143">La clase de trabajo no se puede anular de las líneas de pedido de trabajo.</span><span class="sxs-lookup"><span data-stu-id="622d4-143">The work class cannot be overridden from the work order lines.</span></span> <span data-ttu-id="622d4-144">Las clases de trabajo se usan para dirigir y/o para limitar el tipo de líneas de pedido de trabajo que un trabajador de almacén puede procesar en un dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="622d4-144">Work classes are used to direct and/or limit the type of work order lines a warehouse worker can process on a mobile device.</span></span>  
4. <span data-ttu-id="622d4-145">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="622d4-145">Click New.</span></span>
5. <span data-ttu-id="622d4-146">En el campo Tipo de trabajo, seleccione Colocar.</span><span class="sxs-lookup"><span data-stu-id="622d4-146">In the Work type field, select 'Put'.</span></span>
6. <span data-ttu-id="622d4-147">En el campo Identificador de la clase de trabajo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="622d4-147">In the Work class ID field, type a value.</span></span>
    * <span data-ttu-id="622d4-148">Las instrucciones seleccionar y colocar son un conjunto.</span><span class="sxs-lookup"><span data-stu-id="622d4-148">The pick and put instructions are a set.</span></span> <span data-ttu-id="622d4-149">Cada conjunto de selección y colocación deben tener la misma clase de trabajo.</span><span class="sxs-lookup"><span data-stu-id="622d4-149">Each pick/put set must have the same work class.</span></span> <span data-ttu-id="622d4-150">Use la misma clase de trabajo que se ha proporcionado para la instrucción seleccionar.</span><span class="sxs-lookup"><span data-stu-id="622d4-150">Use the same work class that you provided for the pick instruction.</span></span>  
7. <span data-ttu-id="622d4-151">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="622d4-151">Click Save.</span></span>
    * <span data-ttu-id="622d4-152">Tenga en cuenta que la casilla Válido está ahora activada.</span><span class="sxs-lookup"><span data-stu-id="622d4-152">Note that the Valid checkbox is now checked.</span></span>  

