---
title: Administración de defectos
description: Este tema explica la administración de defectos en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 48c90a8b776cc16804de8e20ada7d8ca347fa5b9
ms.sourcegitcommit: 802dbf0a744d70f9e546632d419415b0993331ab
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "1874748"
---
# <a name="fault-management"></a><span data-ttu-id="9cc30-103">Administración de defectos</span><span class="sxs-lookup"><span data-stu-id="9cc30-103">Fault management</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="9cc30-104">En Administración de activos, puede usar el diseñador de defectos para configurar síntomas de defectos, áreas de defectos y tipos de defectos en los tipos de activos.</span><span class="sxs-lookup"><span data-stu-id="9cc30-104">In Asset Management, you can use the fault designer to set up fault symptoms, fault areas, and fault types on asset types.</span></span> <span data-ttu-id="9cc30-105">De esta manera, puede administrar los defectos que se detectan en los activos.</span><span class="sxs-lookup"><span data-stu-id="9cc30-105">In this way, you can manage faults that are detected on assets.</span></span> <span data-ttu-id="9cc30-106">Además, las causas del defecto y las sugerencias para corregir defectos se pueden registrar en una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9cc30-106">Additionally, fault causes and suggestions for fixing faults can be registered on a work order.</span></span>

<span data-ttu-id="9cc30-107">El proceso para el registro y la administración de defectos consiste en estos pasos.</span><span class="sxs-lookup"><span data-stu-id="9cc30-107">The process for fault registration and management consists of these steps.</span></span>

1. <span data-ttu-id="9cc30-108">Cree una lista de síntomas del defecto, áreas del defecto y tipos de defecto que puedan aparecer en sus tipos de activo.</span><span class="sxs-lookup"><span data-stu-id="9cc30-108">Create a list of fault symptoms, fault areas, and fault types that might occur on your asset types.</span></span>
2. <span data-ttu-id="9cc30-109">En el diseñador del defectos, configure los síntomas, las áreas del defecto y los tipos del defecto.</span><span class="sxs-lookup"><span data-stu-id="9cc30-109">In the fault designer, set up symptoms, fault areas, and fault types.</span></span>

<span data-ttu-id="9cc30-110">A continuación se muestran algunos ejemplos para ayudarle a comprender la diferencia entre los síntomas del defecto, las áreas del defecto y los tipos de defecto.</span><span class="sxs-lookup"><span data-stu-id="9cc30-110">Here are some examples to help you understand the difference between fault symptoms, fault areas, and fault types.</span></span>

<span data-ttu-id="9cc30-111">**Síntomas de defecto:**</span><span class="sxs-lookup"><span data-stu-id="9cc30-111">**Fault symptoms:**</span></span>

- <span data-ttu-id="9cc30-112">Voltajes desequilibrados</span><span class="sxs-lookup"><span data-stu-id="9cc30-112">Unbalanced voltages</span></span>
- <span data-ttu-id="9cc30-113">Cortocircuito</span><span class="sxs-lookup"><span data-stu-id="9cc30-113">Short circuit</span></span>
- <span data-ttu-id="9cc30-114">Ruido</span><span class="sxs-lookup"><span data-stu-id="9cc30-114">Noise</span></span>
- <span data-ttu-id="9cc30-115">Escape</span><span class="sxs-lookup"><span data-stu-id="9cc30-115">Leak</span></span>
- <span data-ttu-id="9cc30-116">Vibraciones</span><span class="sxs-lookup"><span data-stu-id="9cc30-116">Vibrations</span></span>

<span data-ttu-id="9cc30-117">**Áreas de defecto:**</span><span class="sxs-lookup"><span data-stu-id="9cc30-117">**Fault areas:**</span></span>

- <span data-ttu-id="9cc30-118">Eléctrica</span><span class="sxs-lookup"><span data-stu-id="9cc30-118">Electrical</span></span>
- <span data-ttu-id="9cc30-119">Mecánica</span><span class="sxs-lookup"><span data-stu-id="9cc30-119">Mechanical</span></span>
- <span data-ttu-id="9cc30-120">Hidráulica</span><span class="sxs-lookup"><span data-stu-id="9cc30-120">Hydraulic</span></span>
- <span data-ttu-id="9cc30-121">Neumática</span><span class="sxs-lookup"><span data-stu-id="9cc30-121">Pneumatic</span></span>

<span data-ttu-id="9cc30-122">**Tipos de defecto:**</span><span class="sxs-lookup"><span data-stu-id="9cc30-122">**Fault types:**</span></span>

- <span data-ttu-id="9cc30-123">Bobina principal de estator defectuosa</span><span class="sxs-lookup"><span data-stu-id="9cc30-123">Faulty main stator winding</span></span>
- <span data-ttu-id="9cc30-124">Diodo defectuoso</span><span class="sxs-lookup"><span data-stu-id="9cc30-124">Faulty diode</span></span>
- <span data-ttu-id="9cc30-125">Bobinas con suciedad</span><span class="sxs-lookup"><span data-stu-id="9cc30-125">Dirty windings</span></span>
- <span data-ttu-id="9cc30-126">Generador defectuoso</span><span class="sxs-lookup"><span data-stu-id="9cc30-126">Defective generator</span></span>
- <span data-ttu-id="9cc30-127">Sensor defectuoso</span><span class="sxs-lookup"><span data-stu-id="9cc30-127">Defective sensor</span></span>

## <a name="create-fault-symptoms"></a><span data-ttu-id="9cc30-128">Crear síntomas del defecto</span><span class="sxs-lookup"><span data-stu-id="9cc30-128">Create fault symptoms</span></span>

<span data-ttu-id="9cc30-129">Siga estos pasos para crear una lista de los síntomas que se pueden utilizar en el diseñador de defectos.</span><span class="sxs-lookup"><span data-stu-id="9cc30-129">Follow these steps to create a list of symptoms that can be used in the fault designer.</span></span>

1. <span data-ttu-id="9cc30-130">Seleccione **Administración de activos** \> **Configuración** \> **Defecto** \> **Síntomas del defecto**.</span><span class="sxs-lookup"><span data-stu-id="9cc30-130">Select **Asset management** \> **Setup** \> **Fault** \> **Fault symptoms**.</span></span>
2. <span data-ttu-id="9cc30-131">Seleccione **Nuevo** para crear un registro.</span><span class="sxs-lookup"><span data-stu-id="9cc30-131">Select **New** to create a record.</span></span>
3. <span data-ttu-id="9cc30-132">En el campo **Síntoma del defecto**, especifique un nombre para el síntoma del defecto.</span><span class="sxs-lookup"><span data-stu-id="9cc30-132">In the **Fault symptom** field, enter a name for the fault symptom.</span></span>
4. <span data-ttu-id="9cc30-133">En el campo **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="9cc30-133">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="9cc30-134">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9cc30-134">Select **Save**.</span></span>

## <a name="create-fault-areas"></a><span data-ttu-id="9cc30-135">Crear áreas de defecto</span><span class="sxs-lookup"><span data-stu-id="9cc30-135">Create fault areas</span></span>

<span data-ttu-id="9cc30-136">Siga estos pasos para crear una lista de áreas o ubicaciones que se pueden utilizar en el diseñador de defectos.</span><span class="sxs-lookup"><span data-stu-id="9cc30-136">Follow these steps to create a list of areas or locations that can be used in the fault designer.</span></span>

1. <span data-ttu-id="9cc30-137">Seleccione **Administración de activos** \> **Configuración** \> **Defecto** \> **Áreas del defecto**.</span><span class="sxs-lookup"><span data-stu-id="9cc30-137">Select **Asset management** \> **Setup** \> **Fault** \> **Fault areas**.</span></span>
2. <span data-ttu-id="9cc30-138">Seleccione **Nuevo** para crear un registro.</span><span class="sxs-lookup"><span data-stu-id="9cc30-138">Select **New** to create a record.</span></span>
3. <span data-ttu-id="9cc30-139">En el campo **Área del defecto**, especifique un nombre para el área del defecto.</span><span class="sxs-lookup"><span data-stu-id="9cc30-139">In the **Fault area** field, enter a name for the fault area.</span></span>
4. <span data-ttu-id="9cc30-140">En el campo **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="9cc30-140">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="9cc30-141">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9cc30-141">Select **Save**.</span></span>

## <a name="create-fault-types"></a><span data-ttu-id="9cc30-142">Crear tipos de defecto</span><span class="sxs-lookup"><span data-stu-id="9cc30-142">Create fault types</span></span>

<span data-ttu-id="9cc30-143">Siga estos pasos para crear una lista de los tipos de defecto que se pueden utilizar en el diseñador de defectos.</span><span class="sxs-lookup"><span data-stu-id="9cc30-143">Follow these steps to create a list of fault types that can be used in the fault designer.</span></span>

1. <span data-ttu-id="9cc30-144">Seleccione **Administración de activos** \> **Configuración** \> **Defecto** \> **Tipos de defecto**.</span><span class="sxs-lookup"><span data-stu-id="9cc30-144">Select **Asset management** \> **Setup** \> **Fault** \> **Fault types**.</span></span>
2. <span data-ttu-id="9cc30-145">Seleccione **Nuevo** para crear un registro.</span><span class="sxs-lookup"><span data-stu-id="9cc30-145">Select **New** to create a record.</span></span>
3. <span data-ttu-id="9cc30-146">En el campo **Tipo de defecto**, especifique un nombre para el tipo de defecto.</span><span class="sxs-lookup"><span data-stu-id="9cc30-146">In the **Fault type** field, enter a name for the fault type.</span></span>
4. <span data-ttu-id="9cc30-147">En el campo **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="9cc30-147">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="9cc30-148">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9cc30-148">Select **Save**.</span></span>

## <a name="set-up-the-fault-designer"></a><span data-ttu-id="9cc30-149">Configurar el diseñador de defectos</span><span class="sxs-lookup"><span data-stu-id="9cc30-149">Set up the fault designer</span></span>

<span data-ttu-id="9cc30-150">En el diseñador de defectos, configure los datos del defecto en tipos de activo.</span><span class="sxs-lookup"><span data-stu-id="9cc30-150">In the fault designer, you set up fault data on asset types.</span></span>

1. <span data-ttu-id="9cc30-151">Seleccione **Administración de activos** \> **Configuración** \> **Defecto** \> **Diseñador de defectos**.</span><span class="sxs-lookup"><span data-stu-id="9cc30-151">Select **Asset management** \> **Setup** \> **Fault** \> **Fault designer**.</span></span>
2. <span data-ttu-id="9cc30-152">En el panel izquierdo, seleccione el tipo de activo para el que configurar un registro de defecto.</span><span class="sxs-lookup"><span data-stu-id="9cc30-152">In the left pane, select the type of asset to set up a fault record for.</span></span>
3. <span data-ttu-id="9cc30-153">En la ficha desplegable **Síntoma del defecto**, seleccione **Agregar línea** y, a continuación, en el campo **Síntoma del defecto**, seleccione un síntoma del defecto.</span><span class="sxs-lookup"><span data-stu-id="9cc30-153">On the **Fault symptom** FastTab, select **Add line**, and then, in the **Fault symptom** field, select a fault symptom.</span></span>
4. <span data-ttu-id="9cc30-154">En la ficha desplegable **Área del defecto**, seleccione **Agregar línea** y, a continuación, en el campo **Área del defecto**, seleccione un área del defecto.</span><span class="sxs-lookup"><span data-stu-id="9cc30-154">On the **Fault area** FastTab, select **Add line**, and then, in the **Fault area** field select a fault area.</span></span>
5. <span data-ttu-id="9cc30-155">En la ficha desplegable **Tipo del defecto**, seleccione **Agregar línea** y, a continuación, en el campo **Tipo del defecto**, seleccione un tipo del defecto.</span><span class="sxs-lookup"><span data-stu-id="9cc30-155">On the **Fault type** FastTab, select **Add line**, and then, in the **Fault type** field, select a fault type.</span></span>
6. <span data-ttu-id="9cc30-156">Para crear rápidamente combinaciones de todos los síntomas, áreas y tipos del defecto existentes para el tipo activo seleccionado, seleccione **Crear combinaciones de defectos**.</span><span class="sxs-lookup"><span data-stu-id="9cc30-156">To quickly create combinations of all existing fault symptoms, areas, and types for the selected asset type, select **Create fault combinations**.</span></span> <span data-ttu-id="9cc30-157">Esta función resulta útil si ha añadido muchos síntomas, áreas y tipos de defecto.</span><span class="sxs-lookup"><span data-stu-id="9cc30-157">This function is useful if you've added many fault symptoms, areas, and types.</span></span> <span data-ttu-id="9cc30-158">Es más fácil eliminar líneas para cualquier combinación que no sea relevante para el tipo de activo que crear nuevas líneas manualmente.</span><span class="sxs-lookup"><span data-stu-id="9cc30-158">It's easier to delete the lines for any combinations that aren't relevant to the asset type than to create new lines manually.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9cc30-159">Para copiar la configuración de los síntomas, las áreas y los tipos de defecto a partir de un tipo de activo para el tipo de activo seleccionado, seleccione **Copiar desde el tipo de activo**.</span><span class="sxs-lookup"><span data-stu-id="9cc30-159">To copy the setup of fault symptoms, areas, and types from one asset type to the selected asset type, select **Copy from asset type**.</span></span>

7. <span data-ttu-id="9cc30-160">Seleccione **Guardar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="9cc30-160">Select **Save** to save your changes.</span></span>

![Figura 1](media/21-setup-for-work-orders.png)

## <a name="create-fault-causes"></a><span data-ttu-id="9cc30-162">Crear causas de defecto</span><span class="sxs-lookup"><span data-stu-id="9cc30-162">Create fault causes</span></span>

<span data-ttu-id="9cc30-163">Siga estos pasos para crear una lista de causas de defecto conocidas que se pueden agregar a una orden de trabajo o a una solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="9cc30-163">Follow these steps to create a list of known fault causes that can be added to a work order or a maintenance request.</span></span>

1. <span data-ttu-id="9cc30-164">Seleccione **Administración de activos** \> **Configuración** \> **Defecto** \> **Causas de defecto**.</span><span class="sxs-lookup"><span data-stu-id="9cc30-164">Select **Asset management** \> **Setup** \> **Fault** \> **Fault causes**.</span></span>
2. <span data-ttu-id="9cc30-165">Seleccione **Nuevo** para crear un registro.</span><span class="sxs-lookup"><span data-stu-id="9cc30-165">Select **New** to create a record.</span></span>
3. <span data-ttu-id="9cc30-166">En el campo **Causa de defecto**, especifique un nombre para la causa de defecto.</span><span class="sxs-lookup"><span data-stu-id="9cc30-166">In the **Fault cause** field, enter a name for the fault cause.</span></span>
4. <span data-ttu-id="9cc30-167">En el campo **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="9cc30-167">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="9cc30-168">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9cc30-168">Select **Save**.</span></span>

## <a name="create-fault-remedies"></a><span data-ttu-id="9cc30-169">Permite soluciones a defectos</span><span class="sxs-lookup"><span data-stu-id="9cc30-169">Create fault remedies</span></span>

<span data-ttu-id="9cc30-170">Siga estos pasos para crear una lista de sugerencias de soluciones y reparaciones que se pueden agregar a una orden de trabajo o a una solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="9cc30-170">Follow these steps to create a list of suggestions for remedy and repair that can be added to a work order or a maintenance request.</span></span>

1. <span data-ttu-id="9cc30-171">Seleccione **Administración de activos** \> **Configuración** \> **Defecto** \> **Soluciones a defectos**.</span><span class="sxs-lookup"><span data-stu-id="9cc30-171">Select **Asset management** \> **Setup** \> **Fault** \> **Fault remedies**.</span></span>
2. <span data-ttu-id="9cc30-172">Seleccione **Nuevo** para crear un registro.</span><span class="sxs-lookup"><span data-stu-id="9cc30-172">Select **New** to create a record.</span></span>
3. <span data-ttu-id="9cc30-173">En el campo **Soluciones a defectos**, especifique un nombre para la solución de defectos.</span><span class="sxs-lookup"><span data-stu-id="9cc30-173">In the **Fault remedy** field, enter a name for the fault remedy.</span></span>
4. <span data-ttu-id="9cc30-174">En el campo **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="9cc30-174">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="9cc30-175">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9cc30-175">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="9cc30-176">Puede cambiar los nombres de los síntomas, áreas, tipos y causas de los defectos, así como de las soluciones según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="9cc30-176">You can change the names of your fault symptoms, areas, types, causes, and remedies as you require.</span></span> <span data-ttu-id="9cc30-177">Los cambios en el nombre se reflejan automáticamente en los registros relacionados del defecto.</span><span class="sxs-lookup"><span data-stu-id="9cc30-177">The name changes are automatically reflected in the related fault registrations.</span></span>
