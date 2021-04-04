---
title: Usar el diario de existencias de seguridad para actualizar la cobertura mínima
description: Este procedimiento muestra cómo calcular las propuestas de cobertura mínima basadas en transacciones históricas y, a continuación, actualizar la cobertura del artículo con las propuestas.
author: ChristianRytt
manager: tfehr
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqItemJournalName, ReqItemJournalSafetyStock, EcoResProductInformationDialog, EcoResProductDetailsExtended, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 95dec1dba97923e58cfb603434a01cab6f66a3de
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5252807"
---
# <a name="use-the-safety-stock-journal-to-update-minimum-coverage"></a><span data-ttu-id="00776-103">Usar el diario de existencias de seguridad para actualizar la cobertura mínima</span><span class="sxs-lookup"><span data-stu-id="00776-103">Use the safety stock journal to update minimum coverage</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="00776-104">Este procedimiento muestra cómo calcular las propuestas de cobertura mínima basadas en transacciones históricas y, a continuación, actualizar la cobertura del artículo con las propuestas.</span><span class="sxs-lookup"><span data-stu-id="00776-104">This procedure shows how to calculate minimum coverage proposals based on historical transactions and then update the item coverage with the proposals.</span></span> <span data-ttu-id="00776-105">Esto se hace usando el diario de existencias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="00776-105">This is done using the safety stock journal.</span></span> <span data-ttu-id="00776-106">La empresa de datos de prueba utilizada para crear esta tarea es USMF.</span><span class="sxs-lookup"><span data-stu-id="00776-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="00776-107">Esta tarea está pensada para el planificador de producción, para ayudar a mantener una cobertura mínima.</span><span class="sxs-lookup"><span data-stu-id="00776-107">This task is intended for the production planner, to help maintain minimum coverage.</span></span>


## <a name="create-a-new-safety-stock-journal-name"></a><span data-ttu-id="00776-108">Puede crear un nuevo nombre de diario de existencias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="00776-108">Create a new safety stock journal name</span></span>
1. <span data-ttu-id="00776-109">En el **Panel de exploración**, vaya a **Planificación maestra > Configuración > Nombres de diario de existencias de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="00776-109">In the **Navigation pane**, go to **Master planning > Setup > Safety stock journal names**.</span></span>
2. <span data-ttu-id="00776-110">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="00776-110">Click **New**.</span></span>
3. <span data-ttu-id="00776-111">En el campo **Nombre**, escriba "Material".</span><span class="sxs-lookup"><span data-stu-id="00776-111">In the **Name** field, type 'Material'.</span></span>
4. <span data-ttu-id="00776-112">En el campo **Descripción**, escriba "Material".</span><span class="sxs-lookup"><span data-stu-id="00776-112">In the **Description** field, type 'Material'.</span></span>
5. <span data-ttu-id="00776-113">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="00776-113">Close the page.</span></span>

## <a name="create-a-safety-stock-journal"></a><span data-ttu-id="00776-114">Crear un diario de existencias de seguridad</span><span class="sxs-lookup"><span data-stu-id="00776-114">Create a safety stock journal</span></span>
1. <span data-ttu-id="00776-115">En el **Panel de exploración**, vaya a **Planificación maestra > Planificación maestra > Ejecutar > Cálculo de existencias de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="00776-115">In the **Navigation pane**, go to **Master planning > Master planning > Run > Safety stock calculation**.</span></span>
2. <span data-ttu-id="00776-116">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="00776-116">Click **New**.</span></span>
3. <span data-ttu-id="00776-117">En el campo **Nombre**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="00776-117">In the **Name** field, enter or select a value.</span></span> <span data-ttu-id="00776-118">Seleccione el nombre del diario de las existencias de seguridad que ha creado, por ejemplo, Material.</span><span class="sxs-lookup"><span data-stu-id="00776-118">Select the safety stock journal name that you created, for example, Material.</span></span>  
4. <span data-ttu-id="00776-119">Haga clic en **Crear líneas**.</span><span class="sxs-lookup"><span data-stu-id="00776-119">Click **Create lines**.</span></span>
5. <span data-ttu-id="00776-120">En el campo **Fecha inicial**, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="00776-120">In the **From date** field, enter a date.</span></span>  
6. <span data-ttu-id="00776-121">En el campo **Fecha final**, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="00776-121">In the **To date** field, enter a date.</span></span>
7. <span data-ttu-id="00776-122">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="00776-122">Click **OK**.</span></span> <span data-ttu-id="00776-123">Esto creará líneas para las dimensiones que tienen transacciones de inventario.</span><span class="sxs-lookup"><span data-stu-id="00776-123">This will create lines for the dimensions that have inventory transactions.</span></span>  

## <a name="calculate-proposal"></a><span data-ttu-id="00776-124">Calcular propuesta</span><span class="sxs-lookup"><span data-stu-id="00776-124">Calculate proposal</span></span>
1. <span data-ttu-id="00776-125">Haga clic en **Calcular propuesta**.</span><span class="sxs-lookup"><span data-stu-id="00776-125">Click **Calculate proposal**.</span></span>
2. <span data-ttu-id="00776-126">Seleccione la opción **Usar el promedio de emisión durante el plazo**.</span><span class="sxs-lookup"><span data-stu-id="00776-126">Select the **Use average issue during lead time** option.</span></span>
3. <span data-ttu-id="00776-127">Establezca **Factor de multiplicación** en "10".</span><span class="sxs-lookup"><span data-stu-id="00776-127">Set **Multiplication factor** to '10'.</span></span> <span data-ttu-id="00776-128">El factor Multiplicar se utiliza para ajustar la propuesta.</span><span class="sxs-lookup"><span data-stu-id="00776-128">The Multiply factor is used to adjust the proposal.</span></span> <span data-ttu-id="00776-129">Dado que los datos de demostración solo tienen algunas transacciones, deberá establecer el factor para conseguir una propuesta realista.</span><span class="sxs-lookup"><span data-stu-id="00776-129">Because demo data only has a few transactions, you will need to set the factor to get a realistic proposal.</span></span>  
4. <span data-ttu-id="00776-130">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="00776-130">Click **OK**.</span></span> <span data-ttu-id="00776-131">Desplácese hacia abajo para encontrar M0002 y M0003.</span><span class="sxs-lookup"><span data-stu-id="00776-131">Scroll down to find M0002 and M0003.</span></span> <span data-ttu-id="00776-132">Vea la columna **Cantidad mínima calculada**.</span><span class="sxs-lookup"><span data-stu-id="00776-132">View the **Calculated minimum** quantity column.</span></span>   

## <a name="update-minimum-quantity"></a><span data-ttu-id="00776-133">Actualizar cantidad mínima</span><span class="sxs-lookup"><span data-stu-id="00776-133">Update minimum quantity</span></span>
1. <span data-ttu-id="00776-134">En el campo **Nueva cantidad mínima**, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="00776-134">In the **New minimum quantity** field, enter a number.</span></span> <span data-ttu-id="00776-135">Actualice la Nueva cantidad mínima para que coincida con el valor de la Cantidad mínima calculada.</span><span class="sxs-lookup"><span data-stu-id="00776-135">Update the New minimum quantity to match the value in the Calculated minimum quantity.</span></span> <span data-ttu-id="00776-136">Si el mínimo calculado es cero, puede escribir el valor futuro deseado.</span><span class="sxs-lookup"><span data-stu-id="00776-136">If the Calculated minimum is zero,  you can enter the desired future value.</span></span> <span data-ttu-id="00776-137">Por ejemplo, usted puede especificar la Cantidad mínima calculada en este campo para M0002 que tiene el almacén 12.</span><span class="sxs-lookup"><span data-stu-id="00776-137">For example, you can enter the Calculated minimum quantity in this field for M0002 that has warehouse 12.</span></span>  
2. <span data-ttu-id="00776-138">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="00776-138">In the list, find and select the desired record.</span></span> <span data-ttu-id="00776-139">Por ejemplo, puede seleccionar M0002 que tiene el almacén 12.</span><span class="sxs-lookup"><span data-stu-id="00776-139">For example, you can select M0002 that has warehouse 12.</span></span>  
3. <span data-ttu-id="00776-140">En el campo **Nueva cantidad mínima**, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="00776-140">In the **New minimum quantity** field, enter a number.</span></span> <span data-ttu-id="00776-141">Actualice la Nueva cantidad mínima para que coincida con el valor de la Cantidad mínima calculada.</span><span class="sxs-lookup"><span data-stu-id="00776-141">Update the New minimum quantity to match the value in the Calculated minimum quantity.</span></span> <span data-ttu-id="00776-142">Si el mínimo calculado es cero, puede escribir el valor futuro deseado.</span><span class="sxs-lookup"><span data-stu-id="00776-142">If the Calculated minimum is zero you can enter the desired future value.</span></span>  

## <a name="post-the-new-minimum-quantity-and-validate-the-result"></a><span data-ttu-id="00776-143">Publicar la nueva cantidad mínima y validar el resultado</span><span class="sxs-lookup"><span data-stu-id="00776-143">Post the new minimum quantity and validate the result</span></span>
1. <span data-ttu-id="00776-144">Haga clic en **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="00776-144">Click **Post**.</span></span>
2. <span data-ttu-id="00776-145">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="00776-145">Click **OK**.</span></span>
3. <span data-ttu-id="00776-146">Haga clic para seguir el vínculo en el campo **Número de artículo**.</span><span class="sxs-lookup"><span data-stu-id="00776-146">Click to follow the link in the **Item number** field.</span></span>
4. <span data-ttu-id="00776-147">Haga clic para seguir el vínculo en el campo **Número de artículo**.</span><span class="sxs-lookup"><span data-stu-id="00776-147">Click to follow the link in the **Item number** field.</span></span>
5. <span data-ttu-id="00776-148">En el **panel acciones**, haga clic en Plan.</span><span class="sxs-lookup"><span data-stu-id="00776-148">On the **Action Pane**, click Plan.</span></span>
6. <span data-ttu-id="00776-149">Haga clic en **Cobertura de artículos**.</span><span class="sxs-lookup"><span data-stu-id="00776-149">Click **Item coverage**.</span></span> <span data-ttu-id="00776-150">Observe que se ha actualizado la **Cantidad mínima** con la nueva cantidad mínima del diario de existencias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="00776-150">Notice that the **Minimum quantity** has been updated with the new minimum quantity from the safety stock journal.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]