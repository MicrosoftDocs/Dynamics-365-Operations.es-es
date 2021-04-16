---
title: Administración de defectos
description: Este tema explica la administración de defectos en Administración de activos.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetFaultArea, EntAssetFaultDesigner, EntAssetFaultCopyFromObjectType, EntAssetFaultRemedy, EntAssetObjectFaultRelationRequestInfoPart, EntAssetObjectFaultRelationWorkOrderInfoPart, EntAssetFaultCreateCombinations, EntAssetObjectFaultSymptom, EntAssetObjectFaultSymptomListPage, EntAssetFaultType, EntAssetFaultSymptom, EntAssetFaultCause
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: c87bfa057fd2808551674f2acb9d654ad47e9a42
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5825671"
---
# <a name="fault-management"></a><span data-ttu-id="d7daf-103">Administración de defectos</span><span class="sxs-lookup"><span data-stu-id="d7daf-103">Fault management</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="d7daf-104">En Administración de activos, puede usar el diseñador de defectos para configurar síntomas de defectos, áreas de defectos y tipos de defectos en los tipos de activos.</span><span class="sxs-lookup"><span data-stu-id="d7daf-104">In Asset Management, you can use the fault designer to set up fault symptoms, fault areas, and fault types on asset types.</span></span> <span data-ttu-id="d7daf-105">De esta manera, puede administrar los defectos que se detectan en los activos.</span><span class="sxs-lookup"><span data-stu-id="d7daf-105">In this way, you can manage faults that are detected on assets.</span></span> <span data-ttu-id="d7daf-106">Además, las causas del defecto y las sugerencias para corregir defectos se pueden registrar en una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d7daf-106">Additionally, fault causes and suggestions for fixing faults can be registered on a work order.</span></span>

<span data-ttu-id="d7daf-107">El proceso para el registro y la administración de defectos consiste en estos pasos.</span><span class="sxs-lookup"><span data-stu-id="d7daf-107">The process for fault registration and management consists of these steps.</span></span>

1. <span data-ttu-id="d7daf-108">Cree una lista de síntomas del defecto, áreas del defecto y tipos de defecto que puedan aparecer en sus tipos de activo.</span><span class="sxs-lookup"><span data-stu-id="d7daf-108">Create a list of fault symptoms, fault areas, and fault types that might occur on your asset types.</span></span>
2. <span data-ttu-id="d7daf-109">En el diseñador del defectos, configure los síntomas, las áreas del defecto y los tipos del defecto.</span><span class="sxs-lookup"><span data-stu-id="d7daf-109">In the fault designer, set up symptoms, fault areas, and fault types.</span></span>

<span data-ttu-id="d7daf-110">A continuación se muestran algunos ejemplos para ayudarle a comprender la diferencia entre los síntomas del defecto, las áreas del defecto y los tipos de defecto.</span><span class="sxs-lookup"><span data-stu-id="d7daf-110">Here are some examples to help you understand the difference between fault symptoms, fault areas, and fault types.</span></span>

<span data-ttu-id="d7daf-111">**Síntomas de defecto:**</span><span class="sxs-lookup"><span data-stu-id="d7daf-111">**Fault symptoms:**</span></span>

- <span data-ttu-id="d7daf-112">Voltajes desequilibrados</span><span class="sxs-lookup"><span data-stu-id="d7daf-112">Unbalanced voltages</span></span>
- <span data-ttu-id="d7daf-113">Cortocircuito</span><span class="sxs-lookup"><span data-stu-id="d7daf-113">Short circuit</span></span>
- <span data-ttu-id="d7daf-114">Ruido</span><span class="sxs-lookup"><span data-stu-id="d7daf-114">Noise</span></span>
- <span data-ttu-id="d7daf-115">Escape</span><span class="sxs-lookup"><span data-stu-id="d7daf-115">Leak</span></span>
- <span data-ttu-id="d7daf-116">Vibraciones</span><span class="sxs-lookup"><span data-stu-id="d7daf-116">Vibrations</span></span>

<span data-ttu-id="d7daf-117">**Áreas de defecto:**</span><span class="sxs-lookup"><span data-stu-id="d7daf-117">**Fault areas:**</span></span>

- <span data-ttu-id="d7daf-118">Eléctrica</span><span class="sxs-lookup"><span data-stu-id="d7daf-118">Electrical</span></span>
- <span data-ttu-id="d7daf-119">Mecánica</span><span class="sxs-lookup"><span data-stu-id="d7daf-119">Mechanical</span></span>
- <span data-ttu-id="d7daf-120">Hidráulica</span><span class="sxs-lookup"><span data-stu-id="d7daf-120">Hydraulic</span></span>
- <span data-ttu-id="d7daf-121">Neumática</span><span class="sxs-lookup"><span data-stu-id="d7daf-121">Pneumatic</span></span>

<span data-ttu-id="d7daf-122">**Tipos de defecto:**</span><span class="sxs-lookup"><span data-stu-id="d7daf-122">**Fault types:**</span></span>

- <span data-ttu-id="d7daf-123">Bobina principal de estator defectuosa</span><span class="sxs-lookup"><span data-stu-id="d7daf-123">Faulty main stator winding</span></span>
- <span data-ttu-id="d7daf-124">Diodo defectuoso</span><span class="sxs-lookup"><span data-stu-id="d7daf-124">Faulty diode</span></span>
- <span data-ttu-id="d7daf-125">Bobinas con suciedad</span><span class="sxs-lookup"><span data-stu-id="d7daf-125">Dirty windings</span></span>
- <span data-ttu-id="d7daf-126">Generador defectuoso</span><span class="sxs-lookup"><span data-stu-id="d7daf-126">Defective generator</span></span>
- <span data-ttu-id="d7daf-127">Sensor defectuoso</span><span class="sxs-lookup"><span data-stu-id="d7daf-127">Defective sensor</span></span>

## <a name="create-fault-symptoms"></a><span data-ttu-id="d7daf-128">Crear síntomas del defecto</span><span class="sxs-lookup"><span data-stu-id="d7daf-128">Create fault symptoms</span></span>

<span data-ttu-id="d7daf-129">Siga estos pasos para crear una lista de los síntomas que se pueden utilizar en el diseñador de defectos.</span><span class="sxs-lookup"><span data-stu-id="d7daf-129">Follow these steps to create a list of symptoms that can be used in the fault designer.</span></span>

1. <span data-ttu-id="d7daf-130">Seleccione **Administración de activos** \> **Configuración** \> **Defecto** \> **Síntomas del defecto**.</span><span class="sxs-lookup"><span data-stu-id="d7daf-130">Select **Asset management** \> **Setup** \> **Fault** \> **Fault symptoms**.</span></span>
2. <span data-ttu-id="d7daf-131">Seleccione **Nuevo** para crear un registro.</span><span class="sxs-lookup"><span data-stu-id="d7daf-131">Select **New** to create a record.</span></span>
3. <span data-ttu-id="d7daf-132">En el campo **Síntoma del defecto**, especifique un nombre para el síntoma del defecto.</span><span class="sxs-lookup"><span data-stu-id="d7daf-132">In the **Fault symptom** field, enter a name for the fault symptom.</span></span>
4. <span data-ttu-id="d7daf-133">En el campo **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="d7daf-133">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="d7daf-134">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d7daf-134">Select **Save**.</span></span>

## <a name="create-fault-areas"></a><span data-ttu-id="d7daf-135">Crear áreas de defecto</span><span class="sxs-lookup"><span data-stu-id="d7daf-135">Create fault areas</span></span>

<span data-ttu-id="d7daf-136">Siga estos pasos para crear una lista de áreas o ubicaciones que se pueden utilizar en el diseñador de defectos.</span><span class="sxs-lookup"><span data-stu-id="d7daf-136">Follow these steps to create a list of areas or locations that can be used in the fault designer.</span></span>

1. <span data-ttu-id="d7daf-137">Seleccione **Administración de activos** \> **Configuración** \> **Defecto** \> **Áreas del defecto**.</span><span class="sxs-lookup"><span data-stu-id="d7daf-137">Select **Asset management** \> **Setup** \> **Fault** \> **Fault areas**.</span></span>
2. <span data-ttu-id="d7daf-138">Seleccione **Nuevo** para crear un registro.</span><span class="sxs-lookup"><span data-stu-id="d7daf-138">Select **New** to create a record.</span></span>
3. <span data-ttu-id="d7daf-139">En el campo **Área del defecto**, especifique un nombre para el área del defecto.</span><span class="sxs-lookup"><span data-stu-id="d7daf-139">In the **Fault area** field, enter a name for the fault area.</span></span>
4. <span data-ttu-id="d7daf-140">En el campo **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="d7daf-140">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="d7daf-141">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d7daf-141">Select **Save**.</span></span>

## <a name="create-fault-types"></a><span data-ttu-id="d7daf-142">Crear tipos de defecto</span><span class="sxs-lookup"><span data-stu-id="d7daf-142">Create fault types</span></span>

<span data-ttu-id="d7daf-143">Siga estos pasos para crear una lista de los tipos de defecto que se pueden utilizar en el diseñador de defectos.</span><span class="sxs-lookup"><span data-stu-id="d7daf-143">Follow these steps to create a list of fault types that can be used in the fault designer.</span></span>

1. <span data-ttu-id="d7daf-144">Seleccione **Administración de activos** \> **Configuración** \> **Defecto** \> **Tipos de defecto**.</span><span class="sxs-lookup"><span data-stu-id="d7daf-144">Select **Asset management** \> **Setup** \> **Fault** \> **Fault types**.</span></span>
2. <span data-ttu-id="d7daf-145">Seleccione **Nuevo** para crear un registro.</span><span class="sxs-lookup"><span data-stu-id="d7daf-145">Select **New** to create a record.</span></span>
3. <span data-ttu-id="d7daf-146">En el campo **Tipo de defecto**, especifique un nombre para el tipo de defecto.</span><span class="sxs-lookup"><span data-stu-id="d7daf-146">In the **Fault type** field, enter a name for the fault type.</span></span>
4. <span data-ttu-id="d7daf-147">En el campo **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="d7daf-147">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="d7daf-148">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d7daf-148">Select **Save**.</span></span>

## <a name="set-up-the-fault-designer"></a><span data-ttu-id="d7daf-149">Configurar el diseñador de defectos</span><span class="sxs-lookup"><span data-stu-id="d7daf-149">Set up the fault designer</span></span>

<span data-ttu-id="d7daf-150">En el diseñador de defectos, configure los datos del defecto en tipos de activo.</span><span class="sxs-lookup"><span data-stu-id="d7daf-150">In the fault designer, you set up fault data on asset types.</span></span>

1. <span data-ttu-id="d7daf-151">Seleccione **Administración de activos** \> **Configuración** \> **Defecto** \> **Diseñador de defectos**.</span><span class="sxs-lookup"><span data-stu-id="d7daf-151">Select **Asset management** \> **Setup** \> **Fault** \> **Fault designer**.</span></span>
2. <span data-ttu-id="d7daf-152">En el panel izquierdo, seleccione el tipo de activo para el que configurar un registro de defecto.</span><span class="sxs-lookup"><span data-stu-id="d7daf-152">In the left pane, select the type of asset to set up a fault record for.</span></span>
3. <span data-ttu-id="d7daf-153">En la ficha desplegable **Síntoma del defecto**, seleccione **Agregar línea** y, a continuación, en el campo **Síntoma del defecto**, seleccione un síntoma del defecto.</span><span class="sxs-lookup"><span data-stu-id="d7daf-153">On the **Fault symptom** FastTab, select **Add line**, and then, in the **Fault symptom** field, select a fault symptom.</span></span>
4. <span data-ttu-id="d7daf-154">En la ficha desplegable **Área del defecto**, seleccione **Agregar línea** y, a continuación, en el campo **Área del defecto**, seleccione un área del defecto.</span><span class="sxs-lookup"><span data-stu-id="d7daf-154">On the **Fault area** FastTab, select **Add line**, and then, in the **Fault area** field select a fault area.</span></span>
5. <span data-ttu-id="d7daf-155">En la ficha desplegable **Tipo del defecto**, seleccione **Agregar línea** y, a continuación, en el campo **Tipo del defecto**, seleccione un tipo del defecto.</span><span class="sxs-lookup"><span data-stu-id="d7daf-155">On the **Fault type** FastTab, select **Add line**, and then, in the **Fault type** field, select a fault type.</span></span>
6. <span data-ttu-id="d7daf-156">Para crear rápidamente combinaciones de todos los síntomas, áreas y tipos del defecto existentes para el tipo activo seleccionado, seleccione **Crear combinaciones de defectos**.</span><span class="sxs-lookup"><span data-stu-id="d7daf-156">To quickly create combinations of all existing fault symptoms, areas, and types for the selected asset type, select **Create fault combinations**.</span></span> <span data-ttu-id="d7daf-157">Esta función resulta útil si ha agregado muchos síntomas, áreas y tipos de defecto.</span><span class="sxs-lookup"><span data-stu-id="d7daf-157">This function is useful if you've added many fault symptoms, areas, and types.</span></span> <span data-ttu-id="d7daf-158">Es más fácil eliminar líneas para cualquier combinación que no sea relevante para el tipo de activo que crear nuevas líneas manualmente.</span><span class="sxs-lookup"><span data-stu-id="d7daf-158">It's easier to delete the lines for any combinations that aren't relevant to the asset type than to create new lines manually.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d7daf-159">Para copiar la configuración de los síntomas, las áreas y los tipos de defecto a partir de un tipo de activo para el tipo de activo seleccionado, seleccione **Copiar desde el tipo de activo**.</span><span class="sxs-lookup"><span data-stu-id="d7daf-159">To copy the setup of fault symptoms, areas, and types from one asset type to the selected asset type, select **Copy from asset type**.</span></span>

7. <span data-ttu-id="d7daf-160">Seleccione **Guardar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="d7daf-160">Select **Save** to save your changes.</span></span>

![Página de diseñador de defecto](media/21-setup-for-work-orders.png)

## <a name="create-fault-causes"></a><span data-ttu-id="d7daf-162">Crear causas de defecto</span><span class="sxs-lookup"><span data-stu-id="d7daf-162">Create fault causes</span></span>

<span data-ttu-id="d7daf-163">Siga estos pasos para crear una lista de causas de defecto conocidas que se pueden agregar a una orden de trabajo o a una solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="d7daf-163">Follow these steps to create a list of known fault causes that can be added to a work order or a maintenance request.</span></span>

1. <span data-ttu-id="d7daf-164">Seleccione **Administración de activos** \> **Configuración** \> **Defecto** \> **Causas de defecto**.</span><span class="sxs-lookup"><span data-stu-id="d7daf-164">Select **Asset management** \> **Setup** \> **Fault** \> **Fault causes**.</span></span>
2. <span data-ttu-id="d7daf-165">Seleccione **Nuevo** para crear un registro.</span><span class="sxs-lookup"><span data-stu-id="d7daf-165">Select **New** to create a record.</span></span>
3. <span data-ttu-id="d7daf-166">En el campo **Causa de defecto**, especifique un nombre para la causa de defecto.</span><span class="sxs-lookup"><span data-stu-id="d7daf-166">In the **Fault cause** field, enter a name for the fault cause.</span></span>
4. <span data-ttu-id="d7daf-167">En el campo **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="d7daf-167">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="d7daf-168">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d7daf-168">Select **Save**.</span></span>

## <a name="create-fault-remedies"></a><span data-ttu-id="d7daf-169">Permite soluciones a defectos</span><span class="sxs-lookup"><span data-stu-id="d7daf-169">Create fault remedies</span></span>

<span data-ttu-id="d7daf-170">Siga estos pasos para crear una lista de sugerencias de soluciones y reparaciones que se pueden agregar a una orden de trabajo o a una solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="d7daf-170">Follow these steps to create a list of suggestions for remedy and repair that can be added to a work order or a maintenance request.</span></span>

1. <span data-ttu-id="d7daf-171">Seleccione **Administración de activos** \> **Configuración** \> **Defecto** \> **Soluciones a defectos**.</span><span class="sxs-lookup"><span data-stu-id="d7daf-171">Select **Asset management** \> **Setup** \> **Fault** \> **Fault remedies**.</span></span>
2. <span data-ttu-id="d7daf-172">Seleccione **Nuevo** para crear un registro.</span><span class="sxs-lookup"><span data-stu-id="d7daf-172">Select **New** to create a record.</span></span>
3. <span data-ttu-id="d7daf-173">En el campo **Soluciones a defectos**, especifique un nombre para la solución de defectos.</span><span class="sxs-lookup"><span data-stu-id="d7daf-173">In the **Fault remedy** field, enter a name for the fault remedy.</span></span>
4. <span data-ttu-id="d7daf-174">En el campo **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="d7daf-174">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="d7daf-175">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d7daf-175">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="d7daf-176">Puede cambiar los nombres de los síntomas, áreas, tipos y causas de los defectos, así como de las soluciones según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="d7daf-176">You can change the names of your fault symptoms, areas, types, causes, and remedies as you require.</span></span> <span data-ttu-id="d7daf-177">Los cambios en el nombre se reflejan automáticamente en los registros relacionados del defecto.</span><span class="sxs-lookup"><span data-stu-id="d7daf-177">The name changes are automatically reflected in the related fault registrations.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]