--- 
title: "Usar el diario de existencias de seguridad para actualizar la cobertura mínima"
description: "Este procedimiento muestra cómo calcular las propuestas de cobertura mínima basadas en transacciones históricas y, a continuación, actualizar la cobertura del artículo con las propuestas."
author: ChristianRytt
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqItemJournalName, ReqItemJournalSafetyStock, EcoResProductInformationDialog, EcoResProductDetailsExtended, ReqItemTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 5199d5270a6ec709f76ddb05fda3d98d3df02384
ms.contentlocale: es-es
ms.lasthandoff: 09/11/2018

---
# <a name="use-the-safety-stock-journal-to-update-minimum-coverage"></a><span data-ttu-id="534d6-103">Usar el diario de existencias de seguridad para actualizar la cobertura mínima</span><span class="sxs-lookup"><span data-stu-id="534d6-103">Use the safety stock journal to update minimum coverage</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="534d6-104">Este procedimiento muestra cómo calcular las propuestas de cobertura mínima basadas en transacciones históricas y, a continuación, actualizar la cobertura del artículo con las propuestas.</span><span class="sxs-lookup"><span data-stu-id="534d6-104">This procedure shows how to calculate minimum coverage proposals based on historical transactions and then update the item coverage with the proposals.</span></span> <span data-ttu-id="534d6-105">Esto se hace usando el diario de existencias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="534d6-105">This is done using the safety stock journal.</span></span> <span data-ttu-id="534d6-106">La empresa de datos de prueba utilizada para crear esta tarea es USMF.</span><span class="sxs-lookup"><span data-stu-id="534d6-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="534d6-107">Esta tarea está pensada para el planificador de producción, para ayudar a mantener una cobertura mínima.</span><span class="sxs-lookup"><span data-stu-id="534d6-107">This task is intended for the production planner, to help maintain minimum coverage.</span></span>


## <a name="create-a-new-safety-stock-journal-name"></a><span data-ttu-id="534d6-108">Puede crear un nuevo nombre de diario de existencias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="534d6-108">Create a new safety stock journal name</span></span>
1. <span data-ttu-id="534d6-109">Vaya a Nombres de diario de existencias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="534d6-109">Go to Safety stock journal names.</span></span>
2. <span data-ttu-id="534d6-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="534d6-110">Click New.</span></span>
3. <span data-ttu-id="534d6-111">En el campo Nombre, escriba "Material".</span><span class="sxs-lookup"><span data-stu-id="534d6-111">In the Name field, type 'Material'.</span></span>
4. <span data-ttu-id="534d6-112">En el campo Descripción, escriba "Material".</span><span class="sxs-lookup"><span data-stu-id="534d6-112">In the Description field, type 'Material'.</span></span>
5. <span data-ttu-id="534d6-113">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="534d6-113">Close the page.</span></span>

## <a name="create-a-safety-stock-journal"></a><span data-ttu-id="534d6-114">Crear un diario de existencias de seguridad</span><span class="sxs-lookup"><span data-stu-id="534d6-114">Create a safety stock journal</span></span>
1. <span data-ttu-id="534d6-115">Vaya a Cálculo de existencias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="534d6-115">Go to Safety stock calculation.</span></span>
2. <span data-ttu-id="534d6-116">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="534d6-116">Click New.</span></span>
3. <span data-ttu-id="534d6-117">En el campo Nombre, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="534d6-117">In the Name field, enter or select a value.</span></span>
    * <span data-ttu-id="534d6-118">Seleccione el nombre del diario de las existencias de seguridad que ha creado, por ejemplo, Material.</span><span class="sxs-lookup"><span data-stu-id="534d6-118">Select the safety stock journal name that you created, for example, Material.</span></span>  
4. <span data-ttu-id="534d6-119">Haga clic en Crear líneas.</span><span class="sxs-lookup"><span data-stu-id="534d6-119">Click Create lines.</span></span>
5. <span data-ttu-id="534d6-120">En el campo Fecha inicial, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="534d6-120">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="534d6-121">Establezca la fecha en "02-01-2015".</span><span class="sxs-lookup"><span data-stu-id="534d6-121">Set the date to '2015-01-02'.</span></span>  
6. <span data-ttu-id="534d6-122">Especifique una fecha en el campo Fecha final.</span><span class="sxs-lookup"><span data-stu-id="534d6-122">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="534d6-123">Establezca la fecha en "30-12-2015".</span><span class="sxs-lookup"><span data-stu-id="534d6-123">Set the date to '2015-12-30'.</span></span>  
7. <span data-ttu-id="534d6-124">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="534d6-124">Click OK.</span></span>
    * <span data-ttu-id="534d6-125">Esto creará líneas para las dimensiones que tienen transacciones de inventario.</span><span class="sxs-lookup"><span data-stu-id="534d6-125">This will create lines for the dimensions that have inventory transactions.</span></span>  

## <a name="calculate-proposal"></a><span data-ttu-id="534d6-126">Calcular propuesta</span><span class="sxs-lookup"><span data-stu-id="534d6-126">Calculate proposal</span></span>
1. <span data-ttu-id="534d6-127">Haga clic en Calcular propuesta.</span><span class="sxs-lookup"><span data-stu-id="534d6-127">Click Calculate proposal.</span></span>
2. <span data-ttu-id="534d6-128">Seleccione la opción Usar el promedio de emisión durante el plazo.</span><span class="sxs-lookup"><span data-stu-id="534d6-128">Select the Use average issue during lead time option.</span></span>
3. <span data-ttu-id="534d6-129">Establezca el factor de multiplicación en "10".</span><span class="sxs-lookup"><span data-stu-id="534d6-129">Set Multiplication factor to '10'.</span></span>
    * <span data-ttu-id="534d6-130">El factor Multiplicar se utiliza para ajustar la propuesta.</span><span class="sxs-lookup"><span data-stu-id="534d6-130">The Multiply factor is used to adjust the proposal.</span></span> <span data-ttu-id="534d6-131">Dado que los datos de demostración solo tienen algunas transacciones, deberá establecer el factor para conseguir una propuesta realista.</span><span class="sxs-lookup"><span data-stu-id="534d6-131">Because demo data only has a few transactions, you will need to set the factor to get a realistic proposal.</span></span>  
4. <span data-ttu-id="534d6-132">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="534d6-132">Click OK.</span></span>
    * <span data-ttu-id="534d6-133">Desplácese hacia abajo para encontrar M0002 y M0003.</span><span class="sxs-lookup"><span data-stu-id="534d6-133">Scroll down to find M0002 and M0003.</span></span> <span data-ttu-id="534d6-134">Vea la columna Cantidad mínima calculada.</span><span class="sxs-lookup"><span data-stu-id="534d6-134">View the Calculated minimum quantity column.</span></span>   

## <a name="update-minimum-quantity"></a><span data-ttu-id="534d6-135">Actualizar cantidad mínima</span><span class="sxs-lookup"><span data-stu-id="534d6-135">Update minimum quantity</span></span>
1. <span data-ttu-id="534d6-136">En el campo Nueva cantidad mínima, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="534d6-136">In the New minimum quantity field, enter a number.</span></span>
    * <span data-ttu-id="534d6-137">Actualice la Nueva cantidad mínima para que coincida con el valor de la Cantidad mínima calculada.</span><span class="sxs-lookup"><span data-stu-id="534d6-137">Update the New minimum quantity to match the value in the Calculated minimum quantity.</span></span> <span data-ttu-id="534d6-138">Si el mínimo calculado es cero, puede escribir el valor futuro deseado.</span><span class="sxs-lookup"><span data-stu-id="534d6-138">If the Calculated minimum is zero,  you can enter the desired future value.</span></span> <span data-ttu-id="534d6-139">Por ejemplo, usted puede especificar la Cantidad mínima calculada en este campo para M0002 que tiene el almacén 12.</span><span class="sxs-lookup"><span data-stu-id="534d6-139">For example, you can enter the Calculated minimum quantity in this field for M0002 that has warehouse 12.</span></span>  
2. <span data-ttu-id="534d6-140">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="534d6-140">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="534d6-141">Por ejemplo, puede seleccionar M0002 que tiene el almacén 12.</span><span class="sxs-lookup"><span data-stu-id="534d6-141">For example, you can select M0002 that has warehouse 12.</span></span>  
3. <span data-ttu-id="534d6-142">En el campo Nueva cantidad mínima, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="534d6-142">In the New minimum quantity field, enter a number.</span></span>
    * <span data-ttu-id="534d6-143">Actualice la Nueva cantidad mínima para que coincida con el valor de la Cantidad mínima calculada.</span><span class="sxs-lookup"><span data-stu-id="534d6-143">Update the New minimum quantity to match the value in the Calculated minimum quantity.</span></span> <span data-ttu-id="534d6-144">Si el mínimo calculado es cero, puede escribir el valor futuro deseado.</span><span class="sxs-lookup"><span data-stu-id="534d6-144">If the Calculated minimum is zero you can enter the desired future value.</span></span>  

## <a name="post-the-new-minimum-quantity-and-validate-the-result"></a><span data-ttu-id="534d6-145">Publicar la nueva cantidad mínima y validar el resultado</span><span class="sxs-lookup"><span data-stu-id="534d6-145">Post the new minimum quantity and validate the result</span></span>
1. <span data-ttu-id="534d6-146">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="534d6-146">Click Post.</span></span>
2. <span data-ttu-id="534d6-147">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="534d6-147">Click OK.</span></span>
3. <span data-ttu-id="534d6-148">Haga clic para seguir el vínculo en el campo Número de artículo.</span><span class="sxs-lookup"><span data-stu-id="534d6-148">Click to follow the link in the Item number field.</span></span>
4. <span data-ttu-id="534d6-149">Haga clic para seguir el vínculo en el campo Número de artículo.</span><span class="sxs-lookup"><span data-stu-id="534d6-149">Click to follow the link in the Item number field.</span></span>
5. <span data-ttu-id="534d6-150">En el panel de acciones, haga clic en Plan.</span><span class="sxs-lookup"><span data-stu-id="534d6-150">On the Action Pane, click Plan.</span></span>
6. <span data-ttu-id="534d6-151">Haga clic en Cobertura de artículos.</span><span class="sxs-lookup"><span data-stu-id="534d6-151">Click Item coverage.</span></span>
    * <span data-ttu-id="534d6-152">Observe que se ha actualizado la Cantidad mínima con la nueva cantidad mínima del diario de existencias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="534d6-152">Notice that the Minimum quantity has been updated with the new minimum quantity from the safety stock journal.</span></span>  


