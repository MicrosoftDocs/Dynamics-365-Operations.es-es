---
title: Asignar iconos y títulos de paso para la aplicación móvil Warehouse Management
description: Este tema describe cómo asignar títulos e iconos de paso para flujos de tareas nuevos o personalizados para la aplicación móvil Warehouse Management.
author: MarkusFogelberg
ms.date: 05/17/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2021-05-17
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 9523492d766669e6c38579fba7b5ddd6b3d282fc
ms.sourcegitcommit: c53de2c09b9296b41653e739178edf29f79e0679
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049373"
---
# <a name="assign-step-icons-and-titles-for-the-warehouse-management-mobile-app"></a><span data-ttu-id="b0f6b-103">Asignar iconos y títulos de paso para la aplicación móvil Warehouse Management</span><span class="sxs-lookup"><span data-stu-id="b0f6b-103">Assign step icons and titles for the Warehouse Management mobile app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b0f6b-104">Este tema describe cómo asignar títulos de paso e iconos de paso para flujos de tareas nuevos o personalizados para la aplicación móvil Warehouse Management.</span><span class="sxs-lookup"><span data-stu-id="b0f6b-104">This topic describes how to assign step icons and step titles for new or customized task flows for the Warehouse Management mobile app.</span></span>

<span data-ttu-id="b0f6b-105">Las siguientes ilustraciones muestran cómo aparecen los títulos e iconos de pasos en la aplicación móvil Warehouse Management.</span><span class="sxs-lookup"><span data-stu-id="b0f6b-105">The following illustrations shows how step icons and titles appear in the Warehouse Management mobile app.</span></span>

<span data-ttu-id="b0f6b-106">![Ejemplo de un icono de paso y un título de paso en la aplicación móvil Warehouse Management](media/step-icon-example.png "Ejemplo de un icono de paso y un título de paso en la aplicación móvil Warehouse Management")</span><span class="sxs-lookup"><span data-stu-id="b0f6b-106">![Example of a step icon and a step title in the Warehouse Management mobile app](media/step-icon-example.png "Example of a step icon and a step title in the Warehouse Management mobile app")</span></span>

## <a name="turn-on-this-feature-in-your-system"></a><span data-ttu-id="b0f6b-107">Activar esta función en el sistema</span><span class="sxs-lookup"><span data-stu-id="b0f6b-107">Turn on this feature in your system</span></span>

<span data-ttu-id="b0f6b-108">Antes de poder usar esta característica debe estar activada en su sistema.</span><span class="sxs-lookup"><span data-stu-id="b0f6b-108">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="b0f6b-109">Los administradores pueden usar la configuración de [gestión de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y activarla.</span><span class="sxs-lookup"><span data-stu-id="b0f6b-109">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="b0f6b-110">En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="b0f6b-110">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="b0f6b-111">**Módulo:** *Gestión de almacén*</span><span class="sxs-lookup"><span data-stu-id="b0f6b-111">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="b0f6b-112">**Nombre de la función:** *Configuración de usuario, iconos y títulos de pasos para la nueva aplicación de almacén*</span><span class="sxs-lookup"><span data-stu-id="b0f6b-112">**Feature name:** *User settings, icons, and step titles for the new warehouse app*</span></span>

## <a name="standard-step-ids-classes-and-icons"></a><span data-ttu-id="b0f6b-113">Íconos, clases e ID de pasos estándar</span><span class="sxs-lookup"><span data-stu-id="b0f6b-113">Standard step IDs, classes, and icons</span></span>

<span data-ttu-id="b0f6b-114">Cada paso en un flujo de tareas se identifica mediante un ID de paso, y cada ID de paso tiene una clase de paso correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b0f6b-114">Each step in a task flow is identified by a step ID, and each step ID has a corresponding step class.</span></span> <span data-ttu-id="b0f6b-115">El icono y el título del paso se especifican en cada clase de paso.</span><span class="sxs-lookup"><span data-stu-id="b0f6b-115">The step icon and title are specified in each step class.</span></span>

### <a name="step-ids-and-step-classes"></a><a name="step-ids-classes"></a><span data-ttu-id="b0f6b-116">ID de pasos y clases de pasos</span><span class="sxs-lookup"><span data-stu-id="b0f6b-116">Step IDs and step classes</span></span>

<span data-ttu-id="b0f6b-117">La siguiente tabla enumera cada ID de paso que está disponible actualmente y su clase de paso correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b0f6b-117">The following table lists every step ID that is currently available, and its corresponding step class.</span></span> <span data-ttu-id="b0f6b-118">El nombre de control del campo de entrada principal se utiliza como ID de paso.</span><span class="sxs-lookup"><span data-stu-id="b0f6b-118">The control name of the primary input field is used as the step ID.</span></span>

<span data-ttu-id="b0f6b-119">Para ver un ejemplo que muestra cómo se utilizan estas clases y ID de pasos, consulte la implementación del método `WHSMobileAppStepInfoBuilder.stepId()` en la sección [Ejemplo: asignar iconos y títulos de paso para un flujo personalizado](#example) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="b0f6b-119">For an example that shows how these step IDs and classes are used, see the implementation of the `WHSMobileAppStepInfoBuilder.stepId()` method in the [Example: Assign step icons and titles for a custom flow](#example) section later in this topic.</span></span>

| <span data-ttu-id="b0f6b-120">Id. del paso</span><span class="sxs-lookup"><span data-stu-id="b0f6b-120">Step ID</span></span> | <span data-ttu-id="b0f6b-121">Clase de paso</span><span class="sxs-lookup"><span data-stu-id="b0f6b-121">Step Class</span></span> |
|-|-|
| <span data-ttu-id="b0f6b-122">BatchDisposition</span><span class="sxs-lookup"><span data-stu-id="b0f6b-122">BatchDisposition</span></span> | <span data-ttu-id="b0f6b-123">WHSMobileAppStepBatchDisposition</span><span class="sxs-lookup"><span data-stu-id="b0f6b-123">WHSMobileAppStepBatchDisposition</span></span> |
| <span data-ttu-id="b0f6b-124">Transportista</span><span class="sxs-lookup"><span data-stu-id="b0f6b-124">Carrier</span></span> | <span data-ttu-id="b0f6b-125">WHSMobileAppStepCarrier</span><span class="sxs-lookup"><span data-stu-id="b0f6b-125">WHSMobileAppStepCarrier</span></span> |
| <span data-ttu-id="b0f6b-126">CatchWeight</span><span class="sxs-lookup"><span data-stu-id="b0f6b-126">CatchWeight</span></span> | <span data-ttu-id="b0f6b-127">WHSMobileAppStepCatchWeight</span><span class="sxs-lookup"><span data-stu-id="b0f6b-127">WHSMobileAppStepCatchWeight</span></span> |
| <span data-ttu-id="b0f6b-128">CatchWeightQtyOutboundWeight</span><span class="sxs-lookup"><span data-stu-id="b0f6b-128">CatchWeightQtyOutboundWeight</span></span> | <span data-ttu-id="b0f6b-129">WHSMobileAppStepCatchWeight</span><span class="sxs-lookup"><span data-stu-id="b0f6b-129">WHSMobileAppStepCatchWeight</span></span> |
| <span data-ttu-id="b0f6b-130">CatchWeightTag</span><span class="sxs-lookup"><span data-stu-id="b0f6b-130">CatchWeightTag</span></span> | <span data-ttu-id="b0f6b-131">WHSMobileAppStepCatchWeightTag</span><span class="sxs-lookup"><span data-stu-id="b0f6b-131">WHSMobileAppStepCatchWeightTag</span></span> |
| <span data-ttu-id="b0f6b-132">CatchWeightTagWeight</span><span class="sxs-lookup"><span data-stu-id="b0f6b-132">CatchWeightTagWeight</span></span> | <span data-ttu-id="b0f6b-133">WHSMobileAppStepCatchWeightTagWeight</span><span class="sxs-lookup"><span data-stu-id="b0f6b-133">WHSMobileAppStepCatchWeightTagWeight</span></span> |
| <span data-ttu-id="b0f6b-134">ChangeWarehouseSuccess</span><span class="sxs-lookup"><span data-stu-id="b0f6b-134">ChangeWarehouseSuccess</span></span> | <span data-ttu-id="b0f6b-135">WHSMobileAppStepChangeWarehouseSuccess</span><span class="sxs-lookup"><span data-stu-id="b0f6b-135">WHSMobileAppStepChangeWarehouseSuccess</span></span> |
| <span data-ttu-id="b0f6b-136">CheckDigit</span><span class="sxs-lookup"><span data-stu-id="b0f6b-136">CheckDigit</span></span> | <span data-ttu-id="b0f6b-137">WHSMobileAppStepCheckDigit</span><span class="sxs-lookup"><span data-stu-id="b0f6b-137">WHSMobileAppStepCheckDigit</span></span> |
| <span data-ttu-id="b0f6b-138">ClusterId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-138">ClusterId</span></span> | <span data-ttu-id="b0f6b-139">WHSMobileAppStepClusterId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-139">WHSMobileAppStepClusterId</span></span> |
| <span data-ttu-id="b0f6b-140">ClusterPickQtyVerification</span><span class="sxs-lookup"><span data-stu-id="b0f6b-140">ClusterPickQtyVerification</span></span> | <span data-ttu-id="b0f6b-141">WHSMobileAppStepQtyVerification</span><span class="sxs-lookup"><span data-stu-id="b0f6b-141">WHSMobileAppStepQtyVerification</span></span> |
| <span data-ttu-id="b0f6b-142">ClusterPosition</span><span class="sxs-lookup"><span data-stu-id="b0f6b-142">ClusterPosition</span></span> | <span data-ttu-id="b0f6b-143">WHSMobileAppStepClusterPosition</span><span class="sxs-lookup"><span data-stu-id="b0f6b-143">WHSMobileAppStepClusterPosition</span></span> |
| <span data-ttu-id="b0f6b-144">ConfigId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-144">ConfigId</span></span> | <span data-ttu-id="b0f6b-145">WHSMobileAppStepConfigId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-145">WHSMobileAppStepConfigId</span></span> |
| <span data-ttu-id="b0f6b-146">Confirmación</span><span class="sxs-lookup"><span data-stu-id="b0f6b-146">Confirmation</span></span> | <span data-ttu-id="b0f6b-147">WHSMobileAppStepConfirmation</span><span class="sxs-lookup"><span data-stu-id="b0f6b-147">WHSMobileAppStepConfirmation</span></span> |
| <span data-ttu-id="b0f6b-148">ConsolidateFromLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-148">ConsolidateFromLicensePlateId</span></span> | <span data-ttu-id="b0f6b-149">WHSMobileAppStepConsolidateFromLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-149">WHSMobileAppStepConsolidateFromLicensePlateId</span></span> |
| <span data-ttu-id="b0f6b-150">ConsolidateLPConfirmation</span><span class="sxs-lookup"><span data-stu-id="b0f6b-150">ConsolidateLPConfirmation</span></span> | <span data-ttu-id="b0f6b-151">WHSMobileAppStepConsolidateLPConfirmation</span><span class="sxs-lookup"><span data-stu-id="b0f6b-151">WHSMobileAppStepConsolidateLPConfirmation</span></span> |
| <span data-ttu-id="b0f6b-152">ConsolidateToLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-152">ConsolidateToLicensePlateId</span></span> | <span data-ttu-id="b0f6b-153">WHSMobileAppStepConsolidateToLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-153">WHSMobileAppStepConsolidateToLicensePlateId</span></span> |
| <span data-ttu-id="b0f6b-154">ContainerType</span><span class="sxs-lookup"><span data-stu-id="b0f6b-154">ContainerType</span></span> | <span data-ttu-id="b0f6b-155">WHSMobileAppStepContainerType</span><span class="sxs-lookup"><span data-stu-id="b0f6b-155">WHSMobileAppStepContainerType</span></span> |
| <span data-ttu-id="b0f6b-156">CountingReasonCode</span><span class="sxs-lookup"><span data-stu-id="b0f6b-156">CountingReasonCode</span></span> | <span data-ttu-id="b0f6b-157">WHSMobileAppStepCountingReasonCode</span><span class="sxs-lookup"><span data-stu-id="b0f6b-157">WHSMobileAppStepCountingReasonCode</span></span> |
| <span data-ttu-id="b0f6b-158">CycleCountingAddLPOrFinish</span><span class="sxs-lookup"><span data-stu-id="b0f6b-158">CycleCountingAddLPOrFinish</span></span> | <span data-ttu-id="b0f6b-159">WHSMobileAppStepCycleCountingAddLPOrFinish</span><span class="sxs-lookup"><span data-stu-id="b0f6b-159">WHSMobileAppStepCycleCountingAddLPOrFinish</span></span> |
| <span data-ttu-id="b0f6b-160">CycleCountQty1</span><span class="sxs-lookup"><span data-stu-id="b0f6b-160">CycleCountQty1</span></span> | <span data-ttu-id="b0f6b-161">WHSMobileAppStepCycleCountQty</span><span class="sxs-lookup"><span data-stu-id="b0f6b-161">WHSMobileAppStepCycleCountQty</span></span> |
| <span data-ttu-id="b0f6b-162">CycleCountQty2</span><span class="sxs-lookup"><span data-stu-id="b0f6b-162">CycleCountQty2</span></span> | <span data-ttu-id="b0f6b-163">WHSMobileAppStepCycleCountQty</span><span class="sxs-lookup"><span data-stu-id="b0f6b-163">WHSMobileAppStepCycleCountQty</span></span> |
| <span data-ttu-id="b0f6b-164">CycleCountQty3</span><span class="sxs-lookup"><span data-stu-id="b0f6b-164">CycleCountQty3</span></span> | <span data-ttu-id="b0f6b-165">WHSMobileAppStepCycleCountQty</span><span class="sxs-lookup"><span data-stu-id="b0f6b-165">WHSMobileAppStepCycleCountQty</span></span> |
| <span data-ttu-id="b0f6b-166">CycleCountQty4</span><span class="sxs-lookup"><span data-stu-id="b0f6b-166">CycleCountQty4</span></span> | <span data-ttu-id="b0f6b-167">WHSMobileAppStepCycleCountQty</span><span class="sxs-lookup"><span data-stu-id="b0f6b-167">WHSMobileAppStepCycleCountQty</span></span> |
| <span data-ttu-id="b0f6b-168">Disposición</span><span class="sxs-lookup"><span data-stu-id="b0f6b-168">Disposition</span></span> | <span data-ttu-id="b0f6b-169">WHSMobileAppStepDisposition</span><span class="sxs-lookup"><span data-stu-id="b0f6b-169">WHSMobileAppStepDisposition</span></span> |
| <span data-ttu-id="b0f6b-170">DriverCheckInConfirmation</span><span class="sxs-lookup"><span data-stu-id="b0f6b-170">DriverCheckInConfirmation</span></span> | <span data-ttu-id="b0f6b-171">WHSMobileAppStepDriverCheckInConfirmation</span><span class="sxs-lookup"><span data-stu-id="b0f6b-171">WHSMobileAppStepDriverCheckInConfirmation</span></span> |
| <span data-ttu-id="b0f6b-172">DriverCheckInId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-172">DriverCheckInId</span></span> | <span data-ttu-id="b0f6b-173">WHSMobileAppStepDriverCheckInId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-173">WHSMobileAppStepDriverCheckInId</span></span> |
| <span data-ttu-id="b0f6b-174">DriverCheckOutConfirmation</span><span class="sxs-lookup"><span data-stu-id="b0f6b-174">DriverCheckOutConfirmation</span></span> | <span data-ttu-id="b0f6b-175">WHSMobileAppStepDriverCheckOutConfirmation</span><span class="sxs-lookup"><span data-stu-id="b0f6b-175">WHSMobileAppStepDriverCheckOutConfirmation</span></span> |
| <span data-ttu-id="b0f6b-176">DriverCheckOutId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-176">DriverCheckOutId</span></span> | <span data-ttu-id="b0f6b-177">WHSMobileAppStepDriverCheckOutId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-177">WHSMobileAppStepDriverCheckOutId</span></span> |
| <span data-ttu-id="b0f6b-178">ExpDate</span><span class="sxs-lookup"><span data-stu-id="b0f6b-178">ExpDate</span></span> | <span data-ttu-id="b0f6b-179">WHSMobileAppStepExpDate</span><span class="sxs-lookup"><span data-stu-id="b0f6b-179">WHSMobileAppStepExpDate</span></span> |
| <span data-ttu-id="b0f6b-180">FromBatchDisposition</span><span class="sxs-lookup"><span data-stu-id="b0f6b-180">FromBatchDisposition</span></span> | <span data-ttu-id="b0f6b-181">WHSMobileAppStepFromBatchDisposition</span><span class="sxs-lookup"><span data-stu-id="b0f6b-181">WHSMobileAppStepFromBatchDisposition</span></span> |
| <span data-ttu-id="b0f6b-182">FromInventoryStatus</span><span class="sxs-lookup"><span data-stu-id="b0f6b-182">FromInventoryStatus</span></span> | <span data-ttu-id="b0f6b-183">WHSMobileAppStepInventoryStatusFrom</span><span class="sxs-lookup"><span data-stu-id="b0f6b-183">WHSMobileAppStepInventoryStatusFrom</span></span> |
| <span data-ttu-id="b0f6b-184">FullQty</span><span class="sxs-lookup"><span data-stu-id="b0f6b-184">FullQty</span></span> | <span data-ttu-id="b0f6b-185">WHSMobileAppStepFullQty</span><span class="sxs-lookup"><span data-stu-id="b0f6b-185">WHSMobileAppStepFullQty</span></span> |
| <span data-ttu-id="b0f6b-186">InboundPut</span><span class="sxs-lookup"><span data-stu-id="b0f6b-186">InboundPut</span></span> | <span data-ttu-id="b0f6b-187">WHSMobileAppStepInboundPut</span><span class="sxs-lookup"><span data-stu-id="b0f6b-187">WHSMobileAppStepInboundPut</span></span> |
| <span data-ttu-id="b0f6b-188">InventBatchId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-188">InventBatchId</span></span> | <span data-ttu-id="b0f6b-189">WHSMobileAppStepBatch</span><span class="sxs-lookup"><span data-stu-id="b0f6b-189">WHSMobileAppStepBatch</span></span> |
| <span data-ttu-id="b0f6b-190">InventColorId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-190">InventColorId</span></span> | <span data-ttu-id="b0f6b-191">WHSMobileAppStepInventColorId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-191">WHSMobileAppStepInventColorId</span></span> |
| <span data-ttu-id="b0f6b-192">InventLocation</span><span class="sxs-lookup"><span data-stu-id="b0f6b-192">InventLocation</span></span> | <span data-ttu-id="b0f6b-193">WHSMobileAppStepInventLocation</span><span class="sxs-lookup"><span data-stu-id="b0f6b-193">WHSMobileAppStepInventLocation</span></span> |
| <span data-ttu-id="b0f6b-194">InventLocationId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-194">InventLocationId</span></span> | <span data-ttu-id="b0f6b-195">WHSMobileAppStepWarehouse</span><span class="sxs-lookup"><span data-stu-id="b0f6b-195">WHSMobileAppStepWarehouse</span></span> |
| <span data-ttu-id="b0f6b-196">InventSerialId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-196">InventSerialId</span></span> | <span data-ttu-id="b0f6b-197">WHSMobileAppStepInventSerialId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-197">WHSMobileAppStepInventSerialId</span></span> |
| <span data-ttu-id="b0f6b-198">InventSizeId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-198">InventSizeId</span></span> | <span data-ttu-id="b0f6b-199">WHSMobileAppStepInventSizeId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-199">WHSMobileAppStepInventSizeId</span></span> |
| <span data-ttu-id="b0f6b-200">InventStatusId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-200">InventStatusId</span></span> | <span data-ttu-id="b0f6b-201">WHSMobileAppStepInventStatus</span><span class="sxs-lookup"><span data-stu-id="b0f6b-201">WHSMobileAppStepInventStatus</span></span> |
| <span data-ttu-id="b0f6b-202">InventStyleId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-202">InventStyleId</span></span> | <span data-ttu-id="b0f6b-203">WHSMobileAppStepInventStyleId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-203">WHSMobileAppStepInventStyleId</span></span> |
| <span data-ttu-id="b0f6b-204">InventVersionId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-204">InventVersionId</span></span> | <span data-ttu-id="b0f6b-205">WHSMobileAppStepInventVersionId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-205">WHSMobileAppStepInventVersionId</span></span> |
| <span data-ttu-id="b0f6b-206">ItemId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-206">ItemId</span></span> | <span data-ttu-id="b0f6b-207">WHSMobileAppStepItem</span><span class="sxs-lookup"><span data-stu-id="b0f6b-207">WHSMobileAppStepItem</span></span> |
| <span data-ttu-id="b0f6b-208">ITMContainerID</span><span class="sxs-lookup"><span data-stu-id="b0f6b-208">ITMContainerID</span></span> | <span data-ttu-id="b0f6b-209">ITMMobileAppStepContainerId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-209">ITMMobileAppStepContainerId</span></span> |
| <span data-ttu-id="b0f6b-210">ITMShipmentID</span><span class="sxs-lookup"><span data-stu-id="b0f6b-210">ITMShipmentID</span></span> | <span data-ttu-id="b0f6b-211">ITMMobileAppStepShipmentId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-211">ITMMobileAppStepShipmentId</span></span> |
| <span data-ttu-id="b0f6b-212">KanbanCardId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-212">KanbanCardId</span></span> | <span data-ttu-id="b0f6b-213">WHSMobileAppStepKanbanCard</span><span class="sxs-lookup"><span data-stu-id="b0f6b-213">WHSMobileAppStepKanbanCard</span></span> |
| <span data-ttu-id="b0f6b-214">KanbanCardToEmpty</span><span class="sxs-lookup"><span data-stu-id="b0f6b-214">KanbanCardToEmpty</span></span> | <span data-ttu-id="b0f6b-215">WHSMobileAppStepKanbanCardToEmpty</span><span class="sxs-lookup"><span data-stu-id="b0f6b-215">WHSMobileAppStepKanbanCardToEmpty</span></span> |
| <span data-ttu-id="b0f6b-216">KanbanOrCardId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-216">KanbanOrCardId</span></span> | <span data-ttu-id="b0f6b-217">WHSMobileAppStepKanbanCard</span><span class="sxs-lookup"><span data-stu-id="b0f6b-217">WHSMobileAppStepKanbanCard</span></span> |
| <span data-ttu-id="b0f6b-218">LicensePlateId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-218">LicensePlateId</span></span> | <span data-ttu-id="b0f6b-219">WHSMobileAppStepLicensePlate</span><span class="sxs-lookup"><span data-stu-id="b0f6b-219">WHSMobileAppStepLicensePlate</span></span> |
| <span data-ttu-id="b0f6b-220">LoadId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-220">LoadId</span></span> | <span data-ttu-id="b0f6b-221">WHSMobileAppStepLoadId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-221">WHSMobileAppStepLoadId</span></span> |
| <span data-ttu-id="b0f6b-222">LocationLicensePlatePosition</span><span class="sxs-lookup"><span data-stu-id="b0f6b-222">LocationLicensePlatePosition</span></span> | <span data-ttu-id="b0f6b-223">WHSMobileAppStepLocationLicensePlatePosition</span><span class="sxs-lookup"><span data-stu-id="b0f6b-223">WHSMobileAppStepLocationLicensePlatePosition</span></span> |
| <span data-ttu-id="b0f6b-224">LocOrLP</span><span class="sxs-lookup"><span data-stu-id="b0f6b-224">LocOrLP</span></span> | <span data-ttu-id="b0f6b-225">WHSMobileAppStepLocOrLP</span><span class="sxs-lookup"><span data-stu-id="b0f6b-225">WHSMobileAppStepLocOrLP</span></span> |
| <span data-ttu-id="b0f6b-226">LocOrLP_From</span><span class="sxs-lookup"><span data-stu-id="b0f6b-226">LocOrLP_From</span></span> | <span data-ttu-id="b0f6b-227">WHSMobileAppStepLocOrLPFrom</span><span class="sxs-lookup"><span data-stu-id="b0f6b-227">WHSMobileAppStepLocOrLPFrom</span></span> |
| <span data-ttu-id="b0f6b-228">LocOrLP_To</span><span class="sxs-lookup"><span data-stu-id="b0f6b-228">LocOrLP_To</span></span> | <span data-ttu-id="b0f6b-229">WHSMobileAppStepLocOrLPTo</span><span class="sxs-lookup"><span data-stu-id="b0f6b-229">WHSMobileAppStepLocOrLPTo</span></span> |
| <span data-ttu-id="b0f6b-230">LocOrLPCheck</span><span class="sxs-lookup"><span data-stu-id="b0f6b-230">LocOrLPCheck</span></span> | <span data-ttu-id="b0f6b-231">WHSMobileAppStepLocOrLPCheck</span><span class="sxs-lookup"><span data-stu-id="b0f6b-231">WHSMobileAppStepLocOrLPCheck</span></span> |
| <span data-ttu-id="b0f6b-232">LocVerification</span><span class="sxs-lookup"><span data-stu-id="b0f6b-232">LocVerification</span></span> | <span data-ttu-id="b0f6b-233">WHSMobileAppStepLocVerification</span><span class="sxs-lookup"><span data-stu-id="b0f6b-233">WHSMobileAppStepLocVerification</span></span> |
| <span data-ttu-id="b0f6b-234">LPAdjustIn</span><span class="sxs-lookup"><span data-stu-id="b0f6b-234">LPAdjustIn</span></span> | <span data-ttu-id="b0f6b-235">WHSMobileAppStepLPAdjustIn</span><span class="sxs-lookup"><span data-stu-id="b0f6b-235">WHSMobileAppStepLPAdjustIn</span></span> |
| <span data-ttu-id="b0f6b-236">LPBreakChildLP</span><span class="sxs-lookup"><span data-stu-id="b0f6b-236">LPBreakChildLP</span></span> | <span data-ttu-id="b0f6b-237">WHSMobileAppStepLPBreakChildLP</span><span class="sxs-lookup"><span data-stu-id="b0f6b-237">WHSMobileAppStepLPBreakChildLP</span></span> |
| <span data-ttu-id="b0f6b-238">LPBreakParentLP</span><span class="sxs-lookup"><span data-stu-id="b0f6b-238">LPBreakParentLP</span></span> | <span data-ttu-id="b0f6b-239">WHSMobileAppStepLPBreakParentLP</span><span class="sxs-lookup"><span data-stu-id="b0f6b-239">WHSMobileAppStepLPBreakParentLP</span></span> |
| <span data-ttu-id="b0f6b-240">LPBuildChildLP</span><span class="sxs-lookup"><span data-stu-id="b0f6b-240">LPBuildChildLP</span></span> | <span data-ttu-id="b0f6b-241">WHSMobileAppStepLPBuildChildLP</span><span class="sxs-lookup"><span data-stu-id="b0f6b-241">WHSMobileAppStepLPBuildChildLP</span></span> |
| <span data-ttu-id="b0f6b-242">LPBuildParentLP</span><span class="sxs-lookup"><span data-stu-id="b0f6b-242">LPBuildParentLP</span></span> | <span data-ttu-id="b0f6b-243">WHSMobileAppStepLPBuildParentLP</span><span class="sxs-lookup"><span data-stu-id="b0f6b-243">WHSMobileAppStepLPBuildParentLP</span></span> |
| <span data-ttu-id="b0f6b-244">LPVerification</span><span class="sxs-lookup"><span data-stu-id="b0f6b-244">LPVerification</span></span> | <span data-ttu-id="b0f6b-245">WHSMobileAppStepLPVerification</span><span class="sxs-lookup"><span data-stu-id="b0f6b-245">WHSMobileAppStepLPVerification</span></span> |
| <span data-ttu-id="b0f6b-246">MergeContainerId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-246">MergeContainerId</span></span> | <span data-ttu-id="b0f6b-247">WHSMobileAppStepMergeContainerId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-247">WHSMobileAppStepMergeContainerId</span></span> |
| <span data-ttu-id="b0f6b-248">MixedLPLineNum</span><span class="sxs-lookup"><span data-stu-id="b0f6b-248">MixedLPLineNum</span></span> | <span data-ttu-id="b0f6b-249">WHSMobileAppStepMixedLPLineNum</span><span class="sxs-lookup"><span data-stu-id="b0f6b-249">WHSMobileAppStepMixedLPLineNum</span></span> |
| <span data-ttu-id="b0f6b-250">MobileDeviceQueueMessageCollectionIdentifierId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-250">MobileDeviceQueueMessageCollectionIdentifierId</span></span> | <span data-ttu-id="b0f6b-251">WHSMobileAppStepSelectOrder</span><span class="sxs-lookup"><span data-stu-id="b0f6b-251">WHSMobileAppStepSelectOrder</span></span> |
| <span data-ttu-id="b0f6b-252">MovementConfirmCancel</span><span class="sxs-lookup"><span data-stu-id="b0f6b-252">MovementConfirmCancel</span></span> | <span data-ttu-id="b0f6b-253">WHSMobileAppStepMovementConfirmCancel</span><span class="sxs-lookup"><span data-stu-id="b0f6b-253">WHSMobileAppStepMovementConfirmCancel</span></span> |
| <span data-ttu-id="b0f6b-254">NewCaptureWeight</span><span class="sxs-lookup"><span data-stu-id="b0f6b-254">NewCaptureWeight</span></span> | <span data-ttu-id="b0f6b-255">WHSMobileAppStepCatchWeight</span><span class="sxs-lookup"><span data-stu-id="b0f6b-255">WHSMobileAppStepCatchWeight</span></span> |
| <span data-ttu-id="b0f6b-256">NewQty</span><span class="sxs-lookup"><span data-stu-id="b0f6b-256">NewQty</span></span> | <span data-ttu-id="b0f6b-257">WHSMobileAppStepNewQty</span><span class="sxs-lookup"><span data-stu-id="b0f6b-257">WHSMobileAppStepNewQty</span></span> |
| <span data-ttu-id="b0f6b-258">OutboundCatchWeightTag</span><span class="sxs-lookup"><span data-stu-id="b0f6b-258">OutboundCatchWeightTag</span></span> | <span data-ttu-id="b0f6b-259">WHSMobileAppStepCatchWeightTag</span><span class="sxs-lookup"><span data-stu-id="b0f6b-259">WHSMobileAppStepCatchWeightTag</span></span> |
| <span data-ttu-id="b0f6b-260">OutboundPut</span><span class="sxs-lookup"><span data-stu-id="b0f6b-260">OutboundPut</span></span> | <span data-ttu-id="b0f6b-261">WHSMobileAppStepOutboundPut</span><span class="sxs-lookup"><span data-stu-id="b0f6b-261">WHSMobileAppStepOutboundPut</span></span> |
| <span data-ttu-id="b0f6b-262">OutboundWeight</span><span class="sxs-lookup"><span data-stu-id="b0f6b-262">OutboundWeight</span></span> | <span data-ttu-id="b0f6b-263">WHSMobileAppStepCatchWeight</span><span class="sxs-lookup"><span data-stu-id="b0f6b-263">WHSMobileAppStepCatchWeight</span></span> |
| <span data-ttu-id="b0f6b-264">OverridePutNewLocation</span><span class="sxs-lookup"><span data-stu-id="b0f6b-264">OverridePutNewLocation</span></span> | <span data-ttu-id="b0f6b-265">WHSMobileAppStepOverridePutNewLocation</span><span class="sxs-lookup"><span data-stu-id="b0f6b-265">WHSMobileAppStepOverridePutNewLocation</span></span> |
| <span data-ttu-id="b0f6b-266">PieceByPieceConfirmation</span><span class="sxs-lookup"><span data-stu-id="b0f6b-266">PieceByPieceConfirmation</span></span> | <span data-ttu-id="b0f6b-267">WHSMobileAppStepQtyVerification</span><span class="sxs-lookup"><span data-stu-id="b0f6b-267">WHSMobileAppStepQtyVerification</span></span> |
| <span data-ttu-id="b0f6b-268">POLineNum</span><span class="sxs-lookup"><span data-stu-id="b0f6b-268">POLineNum</span></span> | <span data-ttu-id="b0f6b-269">WHSMobileAppStepPOLineNum</span><span class="sxs-lookup"><span data-stu-id="b0f6b-269">WHSMobileAppStepPOLineNum</span></span> |
| <span data-ttu-id="b0f6b-270">NúmPC</span><span class="sxs-lookup"><span data-stu-id="b0f6b-270">PONum</span></span> | <span data-ttu-id="b0f6b-271">WHSMobileAppStepPONum</span><span class="sxs-lookup"><span data-stu-id="b0f6b-271">WHSMobileAppStepPONum</span></span> |
| <span data-ttu-id="b0f6b-272">PositionFull</span><span class="sxs-lookup"><span data-stu-id="b0f6b-272">PositionFull</span></span> | <span data-ttu-id="b0f6b-273">WHSMobileAppStepPositionFull</span><span class="sxs-lookup"><span data-stu-id="b0f6b-273">WHSMobileAppStepPositionFull</span></span> |
| <span data-ttu-id="b0f6b-274">PositionFullQty</span><span class="sxs-lookup"><span data-stu-id="b0f6b-274">PositionFullQty</span></span> | <span data-ttu-id="b0f6b-275">WHSMobileAppStepPositionFullQty</span><span class="sxs-lookup"><span data-stu-id="b0f6b-275">WHSMobileAppStepPositionFullQty</span></span> |
| <span data-ttu-id="b0f6b-276">Potencia</span><span class="sxs-lookup"><span data-stu-id="b0f6b-276">Potency</span></span> | <span data-ttu-id="b0f6b-277">WHSMobileAppStepPotency</span><span class="sxs-lookup"><span data-stu-id="b0f6b-277">WHSMobileAppStepPotency</span></span> |
| <span data-ttu-id="b0f6b-278">PrinterName</span><span class="sxs-lookup"><span data-stu-id="b0f6b-278">PrinterName</span></span> | <span data-ttu-id="b0f6b-279">WHSMobileAppStepPrinterName</span><span class="sxs-lookup"><span data-stu-id="b0f6b-279">WHSMobileAppStepPrinterName</span></span> |
| <span data-ttu-id="b0f6b-280">ProdId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-280">ProdId</span></span> | <span data-ttu-id="b0f6b-281">WHSMobileAppStepProdId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-281">WHSMobileAppStepProdId</span></span> |
| <span data-ttu-id="b0f6b-282">ProdLastPalletConfirmation</span><span class="sxs-lookup"><span data-stu-id="b0f6b-282">ProdLastPalletConfirmation</span></span> | <span data-ttu-id="b0f6b-283">WHSMobileAppStepProdLastPalletConfirmation</span><span class="sxs-lookup"><span data-stu-id="b0f6b-283">WHSMobileAppStepProdLastPalletConfirmation</span></span> |
| <span data-ttu-id="b0f6b-284">ProductConfirmation</span><span class="sxs-lookup"><span data-stu-id="b0f6b-284">ProductConfirmation</span></span> | <span data-ttu-id="b0f6b-285">WHSMobileAppStepProductConfirmation</span><span class="sxs-lookup"><span data-stu-id="b0f6b-285">WHSMobileAppStepProductConfirmation</span></span> |
| <span data-ttu-id="b0f6b-286">ProductionScrapConfirmation</span><span class="sxs-lookup"><span data-stu-id="b0f6b-286">ProductionScrapConfirmation</span></span> | <span data-ttu-id="b0f6b-287">WHSMobileAppStepProductionScrapConfirmation</span><span class="sxs-lookup"><span data-stu-id="b0f6b-287">WHSMobileAppStepProductionScrapConfirmation</span></span> |
| <span data-ttu-id="b0f6b-288">Colocar</span><span class="sxs-lookup"><span data-stu-id="b0f6b-288">Put</span></span> | <span data-ttu-id="b0f6b-289">WHSMobileAppStepPut</span><span class="sxs-lookup"><span data-stu-id="b0f6b-289">WHSMobileAppStepPut</span></span> |
| <span data-ttu-id="b0f6b-290">PutawayClusterId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-290">PutawayClusterId</span></span> | <span data-ttu-id="b0f6b-291">WHSMobileAppStepPutawayClusterId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-291">WHSMobileAppStepPutawayClusterId</span></span> |
| <span data-ttu-id="b0f6b-292">Cant.</span><span class="sxs-lookup"><span data-stu-id="b0f6b-292">Qty</span></span> | <span data-ttu-id="b0f6b-293">WHSMobileAppStepQty</span><span class="sxs-lookup"><span data-stu-id="b0f6b-293">WHSMobileAppStepQty</span></span> |
| <span data-ttu-id="b0f6b-294">QtyAdjust</span><span class="sxs-lookup"><span data-stu-id="b0f6b-294">QtyAdjust</span></span> | <span data-ttu-id="b0f6b-295">WHSMobileAppStepQtyAdjust</span><span class="sxs-lookup"><span data-stu-id="b0f6b-295">WHSMobileAppStepQtyAdjust</span></span> |
| <span data-ttu-id="b0f6b-296">QtyShort</span><span class="sxs-lookup"><span data-stu-id="b0f6b-296">QtyShort</span></span> | <span data-ttu-id="b0f6b-297">WHSMobileAppStepQtyShort</span><span class="sxs-lookup"><span data-stu-id="b0f6b-297">WHSMobileAppStepQtyShort</span></span> |
| <span data-ttu-id="b0f6b-298">QtyToConsume</span><span class="sxs-lookup"><span data-stu-id="b0f6b-298">QtyToConsume</span></span> | <span data-ttu-id="b0f6b-299">WHSMobileAppStepQtyToConsume</span><span class="sxs-lookup"><span data-stu-id="b0f6b-299">WHSMobileAppStepQtyToConsume</span></span> |
| <span data-ttu-id="b0f6b-300">QtyToPick</span><span class="sxs-lookup"><span data-stu-id="b0f6b-300">QtyToPick</span></span> | <span data-ttu-id="b0f6b-301">WHSMobileAppStepQtyToPick</span><span class="sxs-lookup"><span data-stu-id="b0f6b-301">WHSMobileAppStepQtyToPick</span></span> |
| <span data-ttu-id="b0f6b-302">QtyToPut</span><span class="sxs-lookup"><span data-stu-id="b0f6b-302">QtyToPut</span></span> | <span data-ttu-id="b0f6b-303">WHSMobileAppStepQtyToPut</span><span class="sxs-lookup"><span data-stu-id="b0f6b-303">WHSMobileAppStepQtyToPut</span></span> |
| <span data-ttu-id="b0f6b-304">QtyToScrap</span><span class="sxs-lookup"><span data-stu-id="b0f6b-304">QtyToScrap</span></span> | <span data-ttu-id="b0f6b-305">WHSMobileAppStepQtyToScrap</span><span class="sxs-lookup"><span data-stu-id="b0f6b-305">WHSMobileAppStepQtyToScrap</span></span> |
| <span data-ttu-id="b0f6b-306">QtyVerification</span><span class="sxs-lookup"><span data-stu-id="b0f6b-306">QtyVerification</span></span> | <span data-ttu-id="b0f6b-307">WHSMobileAppStepQtyVerification</span><span class="sxs-lookup"><span data-stu-id="b0f6b-307">WHSMobileAppStepQtyVerification</span></span> |
| <span data-ttu-id="b0f6b-308">QtyWithScanningLimit</span><span class="sxs-lookup"><span data-stu-id="b0f6b-308">QtyWithScanningLimit</span></span> | <span data-ttu-id="b0f6b-309">WHSMobileAppStepQtyAdjust</span><span class="sxs-lookup"><span data-stu-id="b0f6b-309">WHSMobileAppStepQtyAdjust</span></span> |
| <span data-ttu-id="b0f6b-310">ReasonString</span><span class="sxs-lookup"><span data-stu-id="b0f6b-310">ReasonString</span></span> | <span data-ttu-id="b0f6b-311">WHSMobileAppStepReasonString</span><span class="sxs-lookup"><span data-stu-id="b0f6b-311">WHSMobileAppStepReasonString</span></span> |
| <span data-ttu-id="b0f6b-312">RecvLocationId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-312">RecvLocationId</span></span> | <span data-ttu-id="b0f6b-313">WHSMobileAppStepRecvLocationId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-313">WHSMobileAppStepRecvLocationId</span></span> |
| <span data-ttu-id="b0f6b-314">RemoveContainerId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-314">RemoveContainerId</span></span> | <span data-ttu-id="b0f6b-315">WHSMobileAppStepRemoveContainerId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-315">WHSMobileAppStepRemoveContainerId</span></span> |
| <span data-ttu-id="b0f6b-316">ReprintLabelConfirmation</span><span class="sxs-lookup"><span data-stu-id="b0f6b-316">ReprintLabelConfirmation</span></span> | <span data-ttu-id="b0f6b-317">WHSMobileAppStepReprintLabelConfirmation</span><span class="sxs-lookup"><span data-stu-id="b0f6b-317">WHSMobileAppStepReprintLabelConfirmation</span></span> |
| <span data-ttu-id="b0f6b-318">RMANum</span><span class="sxs-lookup"><span data-stu-id="b0f6b-318">RMANum</span></span> | <span data-ttu-id="b0f6b-319">WHSMobileAppStepRMANum</span><span class="sxs-lookup"><span data-stu-id="b0f6b-319">WHSMobileAppStepRMANum</span></span> |
| <span data-ttu-id="b0f6b-320">ShortPickReason</span><span class="sxs-lookup"><span data-stu-id="b0f6b-320">ShortPickReason</span></span> | <span data-ttu-id="b0f6b-321">WHSMobileAppStepShortPickReason</span><span class="sxs-lookup"><span data-stu-id="b0f6b-321">WHSMobileAppStepShortPickReason</span></span> |
| <span data-ttu-id="b0f6b-322">SortConOrLP</span><span class="sxs-lookup"><span data-stu-id="b0f6b-322">SortConOrLP</span></span> | <span data-ttu-id="b0f6b-323">WHSMobileAppStepSortConOrLP</span><span class="sxs-lookup"><span data-stu-id="b0f6b-323">WHSMobileAppStepSortConOrLP</span></span> |
| <span data-ttu-id="b0f6b-324">SortLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-324">SortLicensePlateId</span></span> | <span data-ttu-id="b0f6b-325">WHSMobileAppStepSortLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-325">WHSMobileAppStepSortLicensePlateId</span></span> |
| <span data-ttu-id="b0f6b-326">SortPositionId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-326">SortPositionId</span></span> | <span data-ttu-id="b0f6b-327">WHSMobileAppStepSortPositionId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-327">WHSMobileAppStepSortPositionId</span></span> |
| <span data-ttu-id="b0f6b-328">SortVerification</span><span class="sxs-lookup"><span data-stu-id="b0f6b-328">SortVerification</span></span> | <span data-ttu-id="b0f6b-329">WHSMobileAppStepSortVerification</span><span class="sxs-lookup"><span data-stu-id="b0f6b-329">WHSMobileAppStepSortVerification</span></span> |
| <span data-ttu-id="b0f6b-330">StartLocationId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-330">StartLocationId</span></span> | <span data-ttu-id="b0f6b-331">WHSMobileAppStepStartLocationId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-331">WHSMobileAppStepStartLocationId</span></span> |
| <span data-ttu-id="b0f6b-332">StartProdOrderConfirmation</span><span class="sxs-lookup"><span data-stu-id="b0f6b-332">StartProdOrderConfirmation</span></span> | <span data-ttu-id="b0f6b-333">WHSMobileAppStepStartProdOrderConfirmation</span><span class="sxs-lookup"><span data-stu-id="b0f6b-333">WHSMobileAppStepStartProdOrderConfirmation</span></span> |
| <span data-ttu-id="b0f6b-334">TargetLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-334">TargetLicensePlateId</span></span> | <span data-ttu-id="b0f6b-335">WHSMobileAppStepTargetLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-335">WHSMobileAppStepTargetLicensePlateId</span></span> |
| <span data-ttu-id="b0f6b-336">TOLineNum</span><span class="sxs-lookup"><span data-stu-id="b0f6b-336">TOLineNum</span></span> | <span data-ttu-id="b0f6b-337">WHSMobileAppStepTOLineNum</span><span class="sxs-lookup"><span data-stu-id="b0f6b-337">WHSMobileAppStepTOLineNum</span></span> |
| <span data-ttu-id="b0f6b-338">ToLocation</span><span class="sxs-lookup"><span data-stu-id="b0f6b-338">ToLocation</span></span> | <span data-ttu-id="b0f6b-339">WHSMobileAppStepToLocation</span><span class="sxs-lookup"><span data-stu-id="b0f6b-339">WHSMobileAppStepToLocation</span></span> |
| <span data-ttu-id="b0f6b-340">TONum</span><span class="sxs-lookup"><span data-stu-id="b0f6b-340">TONum</span></span> | <span data-ttu-id="b0f6b-341">WHSMobileAppStepTONum</span><span class="sxs-lookup"><span data-stu-id="b0f6b-341">WHSMobileAppStepTONum</span></span> |
| <span data-ttu-id="b0f6b-342">ToWarehouse</span><span class="sxs-lookup"><span data-stu-id="b0f6b-342">ToWarehouse</span></span> | <span data-ttu-id="b0f6b-343">WHSMobileAppStepWarehouseTo</span><span class="sxs-lookup"><span data-stu-id="b0f6b-343">WHSMobileAppStepWarehouseTo</span></span> |
| <span data-ttu-id="b0f6b-344">TransportLoadId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-344">TransportLoadId</span></span> | <span data-ttu-id="b0f6b-345">WHSMobileAppStepTransportLoadId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-345">WHSMobileAppStepTransportLoadId</span></span> |
| <span data-ttu-id="b0f6b-346">WaveLabelId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-346">WaveLabelId</span></span> | <span data-ttu-id="b0f6b-347">WHSMobileAppStepWaveLabelId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-347">WHSMobileAppStepWaveLabelId</span></span> |
| <span data-ttu-id="b0f6b-348">WaveLblQty</span><span class="sxs-lookup"><span data-stu-id="b0f6b-348">WaveLblQty</span></span> | <span data-ttu-id="b0f6b-349">WHSMobileAppStepWaveLblQty</span><span class="sxs-lookup"><span data-stu-id="b0f6b-349">WHSMobileAppStepWaveLblQty</span></span> |
| <span data-ttu-id="b0f6b-350">Importancia</span><span class="sxs-lookup"><span data-stu-id="b0f6b-350">Weight</span></span> | <span data-ttu-id="b0f6b-351">WHSMobileAppStepWeight</span><span class="sxs-lookup"><span data-stu-id="b0f6b-351">WHSMobileAppStepWeight</span></span> |
| <span data-ttu-id="b0f6b-352">WeightToConsume</span><span class="sxs-lookup"><span data-stu-id="b0f6b-352">WeightToConsume</span></span> | <span data-ttu-id="b0f6b-353">WHSMobileAppStepWeightToConsume</span><span class="sxs-lookup"><span data-stu-id="b0f6b-353">WHSMobileAppStepWeightToConsume</span></span> |
| <span data-ttu-id="b0f6b-354">WHSAdjustmentType</span><span class="sxs-lookup"><span data-stu-id="b0f6b-354">WHSAdjustmentType</span></span> | <span data-ttu-id="b0f6b-355">WHSMobileAppStepWHSAdjustmentType</span><span class="sxs-lookup"><span data-stu-id="b0f6b-355">WHSMobileAppStepWHSAdjustmentType</span></span> |
| <span data-ttu-id="b0f6b-356">WHSReceivingException</span><span class="sxs-lookup"><span data-stu-id="b0f6b-356">WHSReceivingException</span></span> | <span data-ttu-id="b0f6b-357">WHSMobileAppStepWHSReceivingException</span><span class="sxs-lookup"><span data-stu-id="b0f6b-357">WHSMobileAppStepWHSReceivingException</span></span> |
| <span data-ttu-id="b0f6b-358">WHSWorkException</span><span class="sxs-lookup"><span data-stu-id="b0f6b-358">WHSWorkException</span></span> | <span data-ttu-id="b0f6b-359">WHSMobileAppStepWHSWorkException</span><span class="sxs-lookup"><span data-stu-id="b0f6b-359">WHSMobileAppStepWHSWorkException</span></span> |
| <span data-ttu-id="b0f6b-360">WHSWorkLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-360">WHSWorkLicensePlateId</span></span> | <span data-ttu-id="b0f6b-361">WHSMobileAppStepWorkLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-361">WHSMobileAppStepWorkLicensePlateId</span></span> |
| <span data-ttu-id="b0f6b-362">WMSLocationId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-362">WMSLocationId</span></span> | <span data-ttu-id="b0f6b-363">WHSMobileAppStepLocation</span><span class="sxs-lookup"><span data-stu-id="b0f6b-363">WHSMobileAppStepLocation</span></span> |
| <span data-ttu-id="b0f6b-364">WorkId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-364">WorkId</span></span> | <span data-ttu-id="b0f6b-365">WHSMobileAppStepWorkId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-365">WHSMobileAppStepWorkId</span></span> |
| <span data-ttu-id="b0f6b-366">WorkIdToCancel</span><span class="sxs-lookup"><span data-stu-id="b0f6b-366">WorkIdToCancel</span></span> | <span data-ttu-id="b0f6b-367">WHSMobileAppStepWorkIdToCancel</span><span class="sxs-lookup"><span data-stu-id="b0f6b-367">WHSMobileAppStepWorkIdToCancel</span></span> |
| <span data-ttu-id="b0f6b-368">WorkLPIdPutawayCluster</span><span class="sxs-lookup"><span data-stu-id="b0f6b-368">WorkLPIdPutawayCluster</span></span> | <span data-ttu-id="b0f6b-369">WHSMobileAppStepWorkLPIdPutawayCluster</span><span class="sxs-lookup"><span data-stu-id="b0f6b-369">WHSMobileAppStepWorkLPIdPutawayCluster</span></span> |
| <span data-ttu-id="b0f6b-370">WorkPoolId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-370">WorkPoolId</span></span> | <span data-ttu-id="b0f6b-371">WHSMobileAppStepWorkPoolId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-371">WHSMobileAppStepWorkPoolId</span></span> |
| <span data-ttu-id="b0f6b-372">ZoneId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-372">ZoneId</span></span> | <span data-ttu-id="b0f6b-373">WHSMobileAppStepZoneId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-373">WHSMobileAppStepZoneId</span></span> |

### <a name="available-step-icons"></a><a name="step-icons"></a><span data-ttu-id="b0f6b-374">Iconos de pasos disponibles</span><span class="sxs-lookup"><span data-stu-id="b0f6b-374">Available step icons</span></span>

<span data-ttu-id="b0f6b-375">El sistema incluye una colección de iconos de pasos estándar que también puede utilizar para sus pasos personalizados.</span><span class="sxs-lookup"><span data-stu-id="b0f6b-375">The system includes a collection of standard step icons that you can also use for your custom steps.</span></span> <span data-ttu-id="b0f6b-376">Actualmente, no puede cargar iconos de pasos personalizados.</span><span class="sxs-lookup"><span data-stu-id="b0f6b-376">You can't currently upload custom step icons.</span></span> <span data-ttu-id="b0f6b-377">Por lo tanto, siempre debe seleccionar uno de los iconos de pasos estándar.</span><span class="sxs-lookup"><span data-stu-id="b0f6b-377">Therefore, you must always select one of the standard step icons.</span></span>

<span data-ttu-id="b0f6b-378">La siguiente tabla muestra cada icono de paso estándar que está disponible actualmente y su nombre.</span><span class="sxs-lookup"><span data-stu-id="b0f6b-378">The following table shows every standard step icon that is currently available, and its name.</span></span>

<table>
<tbody>
<tr>
<td><img src="media/step-icons-about.png" alt="About step icon" title="Acerca del icono de paso"><br><span data-ttu-id="b0f6b-380">Acerca de</span><span class="sxs-lookup"><span data-stu-id="b0f6b-380">About</span></span></td>
<td><img src="media/step-icons-add-lp.png" alt="Add license plate or item step icon" title="Agregar matrícula de entidad o icono de paso de artículo"><br><span data-ttu-id="b0f6b-382">AddLpOrItem</span><span class="sxs-lookup"><span data-stu-id="b0f6b-382">AddLpOrItem</span></span></td>
<td><img src="media/step-icons-batch-disposition.png" alt="Batch disposition step icon" title="Icono de paso de disposición de lote"><br><span data-ttu-id="b0f6b-384">BatchDisposition</span><span class="sxs-lookup"><span data-stu-id="b0f6b-384">BatchDisposition</span></span></td>
<td><img src="media/step-icons-carrier.png" alt="Carrier step icon" title="Icono de paso del operador"><br><span data-ttu-id="b0f6b-386">Transportista</span><span class="sxs-lookup"><span data-stu-id="b0f6b-386">Carrier</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-cw-tag.png" alt="Catch weight tag step icon" title="Icono de paso de etiqueta de peso de captura"><br><span data-ttu-id="b0f6b-388">CatchWeightTag</span><span class="sxs-lookup"><span data-stu-id="b0f6b-388">CatchWeightTag</span></span></td>
<td><img src="media/step-icons-cw-tag-weight.png" alt="Catch weight tag weight step icon" title="Icono de peso de paso de etiqueta de peso de captura"><br><span data-ttu-id="b0f6b-390">CatchWeightTagWeight</span><span class="sxs-lookup"><span data-stu-id="b0f6b-390">CatchWeightTagWeight</span></span></td>
<td><img src="media/step-icons-check-digit.png" alt="Check digit step icon" title="Icono de comprobar dígito de paso"><br><span data-ttu-id="b0f6b-392">CheckDigit</span><span class="sxs-lookup"><span data-stu-id="b0f6b-392">CheckDigit</span></span></td>
<td><img src="media/step-icons-check-in-out.png" alt="Check in or out ID step icon" title="Icono de paso de identificación de entrada o salida"><br><span data-ttu-id="b0f6b-394">CheckInOutId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-394">CheckInOutId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-child-lp.png" alt="Child license plate step icon" title="Icono de paso de matrícula infantil"><br><span data-ttu-id="b0f6b-396">ChildLP</span><span class="sxs-lookup"><span data-stu-id="b0f6b-396">ChildLP</span></span></td>
<td><img src="media/step-icons-cluster-id.png" alt="Cluster ID step icon" title="Icono de paso de ID de clúster"><br><span data-ttu-id="b0f6b-398">ClusterId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-398">ClusterId</span></span></td>
<td><img src="media/step-icons-cluster-position.png" alt="Cluster position step icon" title="Icono de paso de posición de clúster"><br><span data-ttu-id="b0f6b-400">ClusterPosition</span><span class="sxs-lookup"><span data-stu-id="b0f6b-400">ClusterPosition</span></span></td>
<td><img src="media/step-icons-config-id.png" alt="Config ID step icon" title="Icono de paso de ID de configuración"><br><span data-ttu-id="b0f6b-402">ConfigId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-402">ConfigId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-configured-field.png" alt="Configured field step icon" title="Icono de paso de campo configurado"><br><span data-ttu-id="b0f6b-404">ConfiguredField</span><span class="sxs-lookup"><span data-stu-id="b0f6b-404">ConfiguredField</span></span></td>
<td><img src="media/step-icons-con-lp.png" alt="Con or LP step icon" title="Icono de paso con o LP"><br><span data-ttu-id="b0f6b-406">ConOrLP</span><span class="sxs-lookup"><span data-stu-id="b0f6b-406">ConOrLP</span></span></td>
<td><img src="media/step-icons-consolidate-from-LP.png" alt="Consolidate from license plate ID step icon" title="Icono de paso consolidar desde identificador de matrícula de entidad"><br><span data-ttu-id="b0f6b-408">ConsolidateFromLicensePlateID</span><span class="sxs-lookup"><span data-stu-id="b0f6b-408">ConsolidateFromLicensePlateID</span></span></td>
<td><img src="media/step-icons-consolidate-to-LP.png" alt="Consolidate to license plate ID step icon" title="Icono de paso consolidar a identificador de matrícula de entidad"><br><span data-ttu-id="b0f6b-410">ConsolidateToLicensePlateID</span><span class="sxs-lookup"><span data-stu-id="b0f6b-410">ConsolidateToLicensePlateID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-container-type.png" alt="Container type step icon" title="Icono de paso de tipo de contenedor"><br><span data-ttu-id="b0f6b-412">ContainerType</span><span class="sxs-lookup"><span data-stu-id="b0f6b-412">ContainerType</span></span></td>
<td><img src="media/step-icons-counting.png" alt="Counting step icon" title="Icono de paso contando"><br><span data-ttu-id="b0f6b-414">Recuento</span><span class="sxs-lookup"><span data-stu-id="b0f6b-414">Counting</span></span></td>
<td><img src="media/step-icons-counting-reason.png" alt="Counting reason code step icon" title="Icono de paso contando código de razón"><br><span data-ttu-id="b0f6b-416">CountingReasonCode</span><span class="sxs-lookup"><span data-stu-id="b0f6b-416">CountingReasonCode</span></span></td>
<td><img src="media/step-icons-country-origin.png" alt="Country of origin code step icon" title="Icono de paso de código de país de origen"><br><span data-ttu-id="b0f6b-418">CountryOfOrigin</span><span class="sxs-lookup"><span data-stu-id="b0f6b-418">CountryOfOrigin</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-disposition.png" alt="Disposition step icon" title="Icono de paso de disposición"><br><span data-ttu-id="b0f6b-420">Disposición</span><span class="sxs-lookup"><span data-stu-id="b0f6b-420">Disposition</span></span></td>
<td><img src="media/step-icons-done.png" alt="Done step icon" title="Icono de paso hecho"><br><span data-ttu-id="b0f6b-422">Hecho</span><span class="sxs-lookup"><span data-stu-id="b0f6b-422">Done</span></span></td>
<td><img src="media/step-icons-driver-check-in-confirmation.png" alt="Driver check in confirmation step icon" title="Icono de paso de confirmación de registro de conductor"><br><span data-ttu-id="b0f6b-424">DriverCheckInConfirmation</span><span class="sxs-lookup"><span data-stu-id="b0f6b-424">DriverCheckInConfirmation</span></span></td>
<td><img src="media/step-icons-driver-check-in-id.png" alt="Driver check in ID step icon" title="Icono de paso de identificación de registro de conductor"><br><span data-ttu-id="b0f6b-426">DriverCheckInId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-426">DriverCheckInId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-driver-check-out-id.png" alt="Driver check out ID step icon" title="Icono de paso de identificación de registro de salida de conductor"><br><span data-ttu-id="b0f6b-428">DriverCheckOutId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-428">DriverCheckOutId</span></span></td>
<td><img src="media/step-icons-exp-date.png" alt="Expiration date step icon" title="Icono de paso de fecha de vencimiento"><br><span data-ttu-id="b0f6b-430">ExpDate</span><span class="sxs-lookup"><span data-stu-id="b0f6b-430">ExpDate</span></span></td>
<td><img src="media/step-icons-field.png" alt="Field step icon" title="Icono de paso de campo"><br><span data-ttu-id="b0f6b-432">Campo</span><span class="sxs-lookup"><span data-stu-id="b0f6b-432">Field</span></span></td>
<td><img src="media/step-icons-from-batch.png" alt="From batch disposition step icon" title="Icono de paso de desde disposición de lote"><br><span data-ttu-id="b0f6b-434">FromBatchDisposition</span><span class="sxs-lookup"><span data-stu-id="b0f6b-434">FromBatchDisposition</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-from-inventory-status.png" alt="From inventory status step icon" title="Icono de paso desde estado de inventario"><br><span data-ttu-id="b0f6b-436">FromInventoryStatus</span><span class="sxs-lookup"><span data-stu-id="b0f6b-436">FromInventoryStatus</span></span></td>
<td><img src="media/step-icons-id-attribute.png" alt="ID attribute step icon" title="Icono de paso de ID de atributo"><br><span data-ttu-id="b0f6b-438">IdAttribute</span><span class="sxs-lookup"><span data-stu-id="b0f6b-438">IdAttribute</span></span></td>
<td><img src="media/step-icons-invent-batch-id.png" alt="Inventory batch ID step icon" title="Icono de paso de ID de lote de inventario"><br><span data-ttu-id="b0f6b-440">InventBatchID</span><span class="sxs-lookup"><span data-stu-id="b0f6b-440">InventBatchID</span></span></td>
<td><img src="media/step-icons-invent-color-id.png" alt="Inventory color ID step icon" title="Icono de paso de ID de color de inventario"><br><span data-ttu-id="b0f6b-442">InventColorID</span><span class="sxs-lookup"><span data-stu-id="b0f6b-442">InventColorID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-invent-location.png" alt="Inventory location step icon" title="Icono de paso de ID de ubicación de inventario"><br><span data-ttu-id="b0f6b-444">InventLocation</span><span class="sxs-lookup"><span data-stu-id="b0f6b-444">InventLocation</span></span></td>
<td><img src="media/step-icons-invent-serial-id.png" alt="Inventory serial ID step icon" title="Icono de paso de ID de serie de inventario"><br><span data-ttu-id="b0f6b-446">InventSerialID</span><span class="sxs-lookup"><span data-stu-id="b0f6b-446">InventSerialID</span></span></td>
<td><img src="media/step-icons-invent-size-id.png" alt="Inventory size ID step icon" title="Icono de paso de ID de tamaño de inventario"><br><span data-ttu-id="b0f6b-448">InventSizeID</span><span class="sxs-lookup"><span data-stu-id="b0f6b-448">InventSizeID</span></span></td>
<td><img src="media/step-icons-invent-status-id.png" alt="Inventory status ID step icon" title="Icono de paso de ID de estado de inventario"><br><span data-ttu-id="b0f6b-450">InventStatusID</span><span class="sxs-lookup"><span data-stu-id="b0f6b-450">InventStatusID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-invent-style-id.png" alt="Inventory style ID step icon" title="Icono de paso de ID de estilo de inventario"><br><span data-ttu-id="b0f6b-452">InventStyleID</span><span class="sxs-lookup"><span data-stu-id="b0f6b-452">InventStyleID</span></span></td>
<td><img src="media/step-icons-invent-version-id.png" alt="Inventory version ID step icon" title="Icono de paso de ID de versión de inventario"><br><span data-ttu-id="b0f6b-454">InventVersionID</span><span class="sxs-lookup"><span data-stu-id="b0f6b-454">InventVersionID</span></span></td>
<td><img src="media/step-icons-item-id.png" alt="Item ID step icon" title="Icono de paso de ID de artículo"><br><span data-ttu-id="b0f6b-456">ItemID</span><span class="sxs-lookup"><span data-stu-id="b0f6b-456">ItemID</span></span></td>
<td><img src="media/step-icons-itm-contianer-id.png" alt="ITM container ID step icon" title="Icono de paso de ID de contenedor ITM"><br><span data-ttu-id="b0f6b-458">ITMContainerID</span><span class="sxs-lookup"><span data-stu-id="b0f6b-458">ITMContainerID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-itm-shipment-id.png" alt="ITM shipment ID step icon" title="Ícono de paso de ID de envío de ITM"><br><span data-ttu-id="b0f6b-460">ITMShipmentID</span><span class="sxs-lookup"><span data-stu-id="b0f6b-460">ITMShipmentID</span></span></td>
<td><img src="media/step-icons-kanban-card-id.png" alt="Kanban card ID step icon" title="Icono de paso de ID de tarjeta Kanban"><br><span data-ttu-id="b0f6b-462">KanbanCardID</span><span class="sxs-lookup"><span data-stu-id="b0f6b-462">KanbanCardID</span></span></td>
<td><img src="media/step-icons-kanban-or-card-id.png" alt="Kanban or card ID step icon" title="Icono de paso de ID de tarjeta o Kanban"><br><span data-ttu-id="b0f6b-464">KanbanOrCardID</span><span class="sxs-lookup"><span data-stu-id="b0f6b-464">KanbanOrCardID</span></span></td>
<td><img src="media/step-icons-license-plate-id.png" alt="License plate ID step icon" title="Icono de paso de matrícula de entidad"><br><span data-ttu-id="b0f6b-466">LicensePlateID</span><span class="sxs-lookup"><span data-stu-id="b0f6b-466">LicensePlateID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-load-id.png" alt="Load ID step icon" title="Icono de paso de ID de carga"><br><span data-ttu-id="b0f6b-468">LoadId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-468">LoadId</span></span></td>
<td><img src="media/step-icons-location-lp-pos.png" alt="Location license plate position step icon" title="Icono de paso de posición de ubicación de matrícula de entidad"><br><span data-ttu-id="b0f6b-470">LocationLicensePlatePosition</span><span class="sxs-lookup"><span data-stu-id="b0f6b-470">LocationLicensePlatePosition</span></span></td>
<td><img src="media/step-icons-location-or-lp.png" alt="Location or license plate step icon" title="Icono de paso de ubicación o matrícula de entidad"><br><span data-ttu-id="b0f6b-472">LocOrLP</span><span class="sxs-lookup"><span data-stu-id="b0f6b-472">LocOrLP</span></span></td>
<td><img src="media/step-icons-location-or-lp-check.png" alt="Location or license plate check step icon" title="Icono de paso de comprobación de ubicación o matrícula de entidad"><br><span data-ttu-id="b0f6b-474">LocOrLPCheck</span><span class="sxs-lookup"><span data-stu-id="b0f6b-474">LocOrLPCheck</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-location-or-lp-from.png" alt="Location or license plate from step icon" title="Icono de paso de desde ubicación o matrícula de entidad"><br><span data-ttu-id="b0f6b-476">LocOrLPFrom</span><span class="sxs-lookup"><span data-stu-id="b0f6b-476">LocOrLPFrom</span></span></td>
<td><img src="media/step-icons-location-or-lp-to.png" alt="Location or license plate to step icon" title="Icono de paso de para ubicación o matrícula de entidad"><br><span data-ttu-id="b0f6b-478">LocOrLPTo</span><span class="sxs-lookup"><span data-stu-id="b0f6b-478">LocOrLPTo</span></span></td>
<td><img src="media/step-icons-long-process-complete.png" alt="Long process completed step icon" title="Icono de paso de proceso largo completado"><br><span data-ttu-id="b0f6b-480">LongProcessCompleted</span><span class="sxs-lookup"><span data-stu-id="b0f6b-480">LongProcessCompleted</span></span></td>
<td><img src="media/step-icons-lp-break-parent.png" alt="LP break parent LP step icon" title="Icono de paso LP romper LP primario"><br><span data-ttu-id="b0f6b-482">LPBreakParentLP</span><span class="sxs-lookup"><span data-stu-id="b0f6b-482">LPBreakParentLP</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-merge-container.png" alt="Merge container ID step icon" title="Icono de paso de ID de combinar contenedor"><br><span data-ttu-id="b0f6b-484">MergeContainerId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-484">MergeContainerId</span></span></td>
<td><img src="media/step-icons-mixed-lp-line.png" alt="Mixed license plate line number step icon" title="Icono de paso de línea de número de matrícula de entidad mixta"><br><span data-ttu-id="b0f6b-486">MixedLPLineNum</span><span class="sxs-lookup"><span data-stu-id="b0f6b-486">MixedLPLineNum</span></span></td>
<td><img src="media/step-icons-outbound-weight.png" alt="Outbound weight step icon" title="Icono de paso de peso saliente"><br><span data-ttu-id="b0f6b-488">OutboundWeight</span><span class="sxs-lookup"><span data-stu-id="b0f6b-488">OutboundWeight</span></span></td>
<td><img src="media/step-icons-owner.png" alt="Owner step icon" title="Icono de paso de propietario"><br><span data-ttu-id="b0f6b-490">Propietario</span><span class="sxs-lookup"><span data-stu-id="b0f6b-490">Owner</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-parent-lp.png" alt="Parent license plate step icon" title="Icono de paso de matrícula primaria"><br><span data-ttu-id="b0f6b-492">ParentLP</span><span class="sxs-lookup"><span data-stu-id="b0f6b-492">ParentLP</span></span></td>
<td><img src="media/step-icons-please-confirm.png" alt="Please confirm step icon" title="Icono de paso de por favor confirme"><br><span data-ttu-id="b0f6b-494">PleaseConfirm</span><span class="sxs-lookup"><span data-stu-id="b0f6b-494">PleaseConfirm</span></span></td>
<td><img src="media/step-icons-po-line-num.png" alt="Purchase order line number step icon" title="Icono de paso del número de línea de pedido de compra"><br><span data-ttu-id="b0f6b-496">POLineNum</span><span class="sxs-lookup"><span data-stu-id="b0f6b-496">POLineNum</span></span></td>
<td><img src="media/step-icons-po-num.png" alt="Purchase order number step icon" title="Icono de paso del número de pedido de compra"><br><span data-ttu-id="b0f6b-498">NúmPC</span><span class="sxs-lookup"><span data-stu-id="b0f6b-498">PONum</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-position-full.png" alt="Position full step icon" title="Icono de paso de posición completa"><br><span data-ttu-id="b0f6b-500">PositionFull</span><span class="sxs-lookup"><span data-stu-id="b0f6b-500">PositionFull</span></span></td>
<td><img src="media/step-icons-potency.png" alt="Potency step icon" title="Icono de paso de potencia"><br><span data-ttu-id="b0f6b-502">Potencia</span><span class="sxs-lookup"><span data-stu-id="b0f6b-502">Potency</span></span></td>
<td><img src="media/step-icons-printer-name.png" alt="Printer name step icon" title="Icono de paso del nombre de la impresora"><br><span data-ttu-id="b0f6b-504">PrinterName</span><span class="sxs-lookup"><span data-stu-id="b0f6b-504">PrinterName</span></span></td>
<td><img src="media/step-icons-prod-id.png" alt="Prod ID step icon" title="Icono de paso de ID de prod"><br><span data-ttu-id="b0f6b-506">ProdId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-506">ProdId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-product-confirm.png" alt="Product confirmation step icon" title="Icono de paso de confirmación del producto"><br><span data-ttu-id="b0f6b-508">ProductConfirmation</span><span class="sxs-lookup"><span data-stu-id="b0f6b-508">ProductConfirmation</span></span></td>
<td><img src="media/step-icons-put.png" alt="Put step icon" title="Icono de paso de colocar"><br><span data-ttu-id="b0f6b-510">Colocar</span><span class="sxs-lookup"><span data-stu-id="b0f6b-510">Put</span></span></td>
<td><img src="media/step-icons-putaway-cluster-id.png" alt="Putaway cluster ID step icon" title="Icono de paso de ID de ubicación de clúster"><br><span data-ttu-id="b0f6b-512">PutawayClusterId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-512">PutawayClusterId</span></span></td>
<td><img src="media/step-icons-qty.png" alt="Quantity step icon" title="Icono de paso de cantidad"><br><span data-ttu-id="b0f6b-514">Cant.</span><span class="sxs-lookup"><span data-stu-id="b0f6b-514">Qty</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-qty-adjust-in.png" alt="Quantity adjust in step icon" title="Icono de paso de ajustar cantidad en"><br><span data-ttu-id="b0f6b-516">QtyAdjustIn</span><span class="sxs-lookup"><span data-stu-id="b0f6b-516">QtyAdjustIn</span></span></td>
<td><img src="media/step-icons-qty-short.png" alt="Quantity short step icon" title="Icono de paso de cantidad corta"><br><span data-ttu-id="b0f6b-518">QtyShort</span><span class="sxs-lookup"><span data-stu-id="b0f6b-518">QtyShort</span></span></td>
<td><img src="media/step-icons-qty-to-consume.png" alt="Quantity to consume step icon" title="Icono de paso de cantidad a consumir"><br><span data-ttu-id="b0f6b-520">QtyToConsume</span><span class="sxs-lookup"><span data-stu-id="b0f6b-520">QtyToConsume</span></span></td>
<td><img src="media/step-icons-qty-to-put.png" alt="Quantity to put step icon" title="Icono de paso de cantidad a colocar"><br><span data-ttu-id="b0f6b-522">QtyToPut</span><span class="sxs-lookup"><span data-stu-id="b0f6b-522">QtyToPut</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-qty-to-scrap.png" alt="Quantity to scrap step icon" title="Icono de paso de cantidad para dar de baja"><br><span data-ttu-id="b0f6b-524">QtyToScrap</span><span class="sxs-lookup"><span data-stu-id="b0f6b-524">QtyToScrap</span></span></td>
<td><img src="media/step-icons-qty-confirmation.png" alt="Quantity confirmation step icon" title="Icono de paso de confirmación de cantidad"><br><span data-ttu-id="b0f6b-526">QuantityConfirmation</span><span class="sxs-lookup"><span data-stu-id="b0f6b-526">QuantityConfirmation</span></span></td>
<td><img src="media/step-icons-raf-end-job.png" alt="Report as finished end job step icon" title="Icono de paso Informar como trabajo finalizado"><br><span data-ttu-id="b0f6b-528">RAFEndJob</span><span class="sxs-lookup"><span data-stu-id="b0f6b-528">RAFEndJob</span></span></td>
<td><img src="media/step-icons-recv-loc-id.png" alt="Receive location ID step icon" title="Icono de paso recibir ID de ubicación"><br><span data-ttu-id="b0f6b-530">RecvLocationID</span><span class="sxs-lookup"><span data-stu-id="b0f6b-530">RecvLocationID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-remove-container-id.png" alt="Remove container ID step icon" title="Icono de paso de eliminar ID de contenedor"><br><span data-ttu-id="b0f6b-532">RemoveContainerID</span><span class="sxs-lookup"><span data-stu-id="b0f6b-532">RemoveContainerID</span></span></td>
<td><img src="media/step-icons-rma-no.png" alt="RMA number step icon" title="Icono de paso de número de RMA"><br><span data-ttu-id="b0f6b-534">RMANum</span><span class="sxs-lookup"><span data-stu-id="b0f6b-534">RMANum</span></span></td>
<td><img src="media/step-icons-select-order.png" alt="Select order step icon" title="Icono de paso de seleccionar pedido"><br><span data-ttu-id="b0f6b-536">SelectOrder</span><span class="sxs-lookup"><span data-stu-id="b0f6b-536">SelectOrder</span></span></td>
<td><img src="media/step-icons-short-pick-reason.png" alt="Short pick reason step icon" title="Icono de paso de motivo de selección breve"><br><span data-ttu-id="b0f6b-538">ShortPickReason</span><span class="sxs-lookup"><span data-stu-id="b0f6b-538">ShortPickReason</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-sort-position-id.png" alt="Sort position ID step icon" title="Icono de paso de ID de ordenar posición"><br><span data-ttu-id="b0f6b-540">SortPositionId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-540">SortPositionId</span></span></td>
<td><img src="media/step-icons-target-lp-id.png" alt="Target license plate ID step icon" title="Icono de paso de matrícula de entidad de destino"><br><span data-ttu-id="b0f6b-542">TargetLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-542">TargetLicensePlateId</span></span></td>
<td><img src="media/step-icons-to-line-no.png" alt="To line number step icon" title="Icono de paso al número de línea"><br><span data-ttu-id="b0f6b-544">ToLineNum</span><span class="sxs-lookup"><span data-stu-id="b0f6b-544">ToLineNum</span></span></td>
<td><img src="media/step-icons-to-location.png" alt="To location step icon" title="Icono de paso a ubicación"><br><span data-ttu-id="b0f6b-546">ToLocation</span><span class="sxs-lookup"><span data-stu-id="b0f6b-546">ToLocation</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-to-number.png" alt="To number step icon" title="Icono de paso a número"><br><span data-ttu-id="b0f6b-548">ToNum</span><span class="sxs-lookup"><span data-stu-id="b0f6b-548">ToNum</span></span></td>
<td><img src="media/step-icons-to-warehouse.png" alt="To warehouse step icon" title="Icono de paso a almacén"><br><span data-ttu-id="b0f6b-550">ToWarehouse</span><span class="sxs-lookup"><span data-stu-id="b0f6b-550">ToWarehouse</span></span></td>
<td><img src="media/step-icons-tranport-load-id.png" alt="Transport load ID step icon" title="Icono de paso de ID de transporte carga"><br><span data-ttu-id="b0f6b-552">TransportLoadId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-552">TransportLoadId</span></span></td>
<td><img src="media/step-icons-vendor-batch-id.png" alt="Vendor batch ID step icon" title="Icono de paso de ID de lote de proveedor"><br><span data-ttu-id="b0f6b-554">VendBatchId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-554">VendBatchId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-wave-label-id.png" alt="Wave label ID step icon" title="Icono de paso de ID de etiqueta de oleada"><br><span data-ttu-id="b0f6b-556">WaveLabelId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-556">WaveLabelId</span></span></td>
<td><img src="media/step-icons-wave-label-qty.png" alt="Wave label quantity step icon" title="Icono de paso de cantidad de etiqueta de oleada"><br><span data-ttu-id="b0f6b-558">WaveLblQty</span><span class="sxs-lookup"><span data-stu-id="b0f6b-558">WaveLblQty</span></span></td>
<td><img src="media/step-icons-weight.png" alt="Weight step icon" title="Icono de paso de peso"><br><span data-ttu-id="b0f6b-560">Importancia</span><span class="sxs-lookup"><span data-stu-id="b0f6b-560">Weight</span></span></td>
<td><img src="media/step-icons-weight-to-consume.png" alt="Weight to consume step icon" title="Icono de paso de peso a consumir"><br><span data-ttu-id="b0f6b-562">WeightToConsume</span><span class="sxs-lookup"><span data-stu-id="b0f6b-562">WeightToConsume</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-whs-adjustment-type.png" alt="WHS adjustment type step icon" title="Icono de paso de tipo de ajuste WHS"><br><span data-ttu-id="b0f6b-564">WHSAdjustmentType</span><span class="sxs-lookup"><span data-stu-id="b0f6b-564">WHSAdjustmentType</span></span></td>
<td><img src="media/step-icons-whs-receiving-exception.png" alt="WHS receiving exception step icon" title="Icono de paso de excepción de recepción WHS"><br><span data-ttu-id="b0f6b-566">WHSReceivingException</span><span class="sxs-lookup"><span data-stu-id="b0f6b-566">WHSReceivingException</span></span></td>
<td><img src="media/step-icons-wms-location-id.png" alt="WMS location ID step icon" title="Icono de paso de ubicación WMS"><br><span data-ttu-id="b0f6b-568">WMSLocationID</span><span class="sxs-lookup"><span data-stu-id="b0f6b-568">WMSLocationID</span></span></td>
<td><img src="media/step-icons-work-id.png" alt="Work ID step icon" title="Icono de paso de ID de trabajo"><br><span data-ttu-id="b0f6b-570">WorkId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-570">WorkId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-work-id-to-cancel.png" alt="Work ID to cancel step icon" title="Icono de paso de ID de trabajo a cancelar"><br><span data-ttu-id="b0f6b-572">WorkIdToCancel</span><span class="sxs-lookup"><span data-stu-id="b0f6b-572">WorkIdToCancel</span></span></td>
<td><img src="media/step-icons-work-lp-id.png" alt="Work license plate ID step icon" title="Icono de paso de matrícula de entidad de trabajo"><br><span data-ttu-id="b0f6b-574">WorkLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="b0f6b-574">WorkLicensePlateId</span></span></td>
<td><img src="media/step-icons-work-lp-putaway-cluster.png" alt="Work license plate ID putaway cluster step icon" title="Icono de paso de ID de matrícula de entidad de trabajo de ubicación de clúster"><br><span data-ttu-id="b0f6b-576">WorkLPIDPutawayCluster</span><span class="sxs-lookup"><span data-stu-id="b0f6b-576">WorkLPIDPutawayCluster</span></span></td>
<td><img src="media/step-icons-work-pool-id.png" alt="Work pool ID step icon" title="Icono de paso de ID de grupo de trabajo"><br><span data-ttu-id="b0f6b-578">WorkPoolID</span><span class="sxs-lookup"><span data-stu-id="b0f6b-578">WorkPoolID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-zone-pool-id.png" alt="Zone ID step icon" title="Icono de paso de ID de zona"><br><span data-ttu-id="b0f6b-580">ZoneID</span><span class="sxs-lookup"><span data-stu-id="b0f6b-580">ZoneID</span></span></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

## <a name="example-assign-step-icons-and-titles-for-a-custom-flow"></a><a name="example"></a><span data-ttu-id="b0f6b-581">Ejemplo: asignar iconos y títulos de paso para un flujo personalizado</span><span class="sxs-lookup"><span data-stu-id="b0f6b-581">Example: Assign step icons and titles for a custom flow</span></span>

<span data-ttu-id="b0f6b-582">Este ejemplo explica cómo configurar los iconos y los títulos de los pasos para un flujo de tareas personalizado.</span><span class="sxs-lookup"><span data-stu-id="b0f6b-582">This example explains how to set up step icons and titles for a custom task flow.</span></span> <span data-ttu-id="b0f6b-583">El escenario se basa en un ejemplo de un flujo de tareas personalizado que se presenta y explora con más detalle en la siguiente publicación del blog: [Personalización de la aplicación móvil de almacenamiento](https://cloudblogs.microsoft.com/dynamics365/it/2017/07/06/customizing-the-warehousing-mobile-app).</span><span class="sxs-lookup"><span data-stu-id="b0f6b-583">The scenario is built on an example of a custom task flow that is presented and explored in more detail in the following blog post: [Customizing the Warehousing Mobile App](https://cloudblogs.microsoft.com/dynamics365/it/2017/07/06/customizing-the-warehousing-mobile-app).</span></span> <span data-ttu-id="b0f6b-584">El flujo de tareas funciona de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="b0f6b-584">The task flow works in the following way:</span></span>

1. <span data-ttu-id="b0f6b-585">La aplicación muestra una página que solicita al trabajador que proporcione una identificación de contenedor (por ejemplo, escaneando un código de barras).</span><span class="sxs-lookup"><span data-stu-id="b0f6b-585">The app shows a page that prompts the worker to provide a container ID (for example, by scanning a bar code).</span></span>
1. <span data-ttu-id="b0f6b-586">Si el ID del contenedor es válido, la aplicación abre una nueva página que solicita al trabajador el peso.</span><span class="sxs-lookup"><span data-stu-id="b0f6b-586">If the container ID is valid, the app opens a new page that prompts the worker for the weight.</span></span> <span data-ttu-id="b0f6b-587">(Si el ID del contenedor no es válido, el trabajador vuelve a la primera página).</span><span class="sxs-lookup"><span data-stu-id="b0f6b-587">(If the container ID isn't valid, the worker is returned to the first page.)</span></span>
1. <span data-ttu-id="b0f6b-588">Cuando el trabajador introduce un peso válido, el sistema almacena el peso y devuelve al trabajador a la primera página.</span><span class="sxs-lookup"><span data-stu-id="b0f6b-588">When the worker enters a valid weight, the system stores the weight and returns the worker to the first page.</span></span>

<span data-ttu-id="b0f6b-589">En la ilustración siguiente se muestra el flujo de la tarea.</span><span class="sxs-lookup"><span data-stu-id="b0f6b-589">The following illustration shows this task flow.</span></span>

<span data-ttu-id="b0f6b-590">![Diagrama de flujo de tarea](media/step-icons-example-task-flow.png "Diagrama de flujo de tarea")</span><span class="sxs-lookup"><span data-stu-id="b0f6b-590">![Task flow diagram](media/step-icons-example-task-flow.png "Task flow diagram")</span></span>

### <a name="create-a-step-class-for-the-container-input-page"></a><span data-ttu-id="b0f6b-591">Cree una clase de paso para la página de entrada del contenedor</span><span class="sxs-lookup"><span data-stu-id="b0f6b-591">Create a step class for the container input page</span></span>

<span data-ttu-id="b0f6b-592">La página de entrada del contenedor permite al trabajador escanear o introducir una ID de contenedor.</span><span class="sxs-lookup"><span data-stu-id="b0f6b-592">The container input page lets the worker scan or enter a container ID.</span></span>

<span data-ttu-id="b0f6b-593">![Página de entrada del contenedor](media/step-icons-example-container-input.png "Página de entrada del contenedor")</span><span class="sxs-lookup"><span data-stu-id="b0f6b-593">![Container input page](media/step-icons-example-container-input.png "Container input page")</span></span>

<span data-ttu-id="b0f6b-594">En la página de entrada del contenedor, el nombre de control del campo de entrada es `ContainerId`.</span><span class="sxs-lookup"><span data-stu-id="b0f6b-594">On the container input page, the control name of the input field is `ContainerId`.</span></span> <span data-ttu-id="b0f6b-595">Debido a que este nombre de control no está en la [lista de ID de pasos](#step-ids-classes), no encontrará un paso existente que se base en él.</span><span class="sxs-lookup"><span data-stu-id="b0f6b-595">Because this control name isn't in the [list of step IDs](#step-ids-classes), you won't find an existing step that is based on it.</span></span> <span data-ttu-id="b0f6b-596">Por lo tanto, debe crear una clase de paso que represente el paso.</span><span class="sxs-lookup"><span data-stu-id="b0f6b-596">Therefore, you must create a step class that represents the step.</span></span> <span data-ttu-id="b0f6b-597">He aquí un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b0f6b-597">Here is an example.</span></span>

```xpp
[WHSMobileAppStepId('ContainerId')]
final internal class WHSMobileAppStepContainerId extends WHSMobileAppStep
{
    private const WHSMobileAppStepIcon PopulationIcon = 'InventBatchID';
    private const WHSMobileAppStepTitle InputNotFilledTitle = "@WAX:WHSMobileAppStepContainerID_InputNotFilled"; //Scan a container
    protected void initValues()
    {
        defaultStepIcon = PopulationIcon;
        defaultStepTitle = InputNotFilledTitle;
    }
}
```

<span data-ttu-id="b0f6b-598">El identificador del icono de paso se almacena en el miembro de la clase `defaultStepIcon` y el título del paso se almacena en el miembro de la clase `defaultStepTitle`.</span><span class="sxs-lookup"><span data-stu-id="b0f6b-598">The identifier of the step icon is stored in the `defaultStepIcon` class member, and the step title is stored in the `defaultStepTitle` class member.</span></span>

<span data-ttu-id="b0f6b-599">Para asignar un icono de paso, configure `defaultStepIcon` a uno de los ID de icono que se enumeran en la sección [Iconos de pasos disponibles](#step-icons) anterior en este tema.</span><span class="sxs-lookup"><span data-stu-id="b0f6b-599">To assign a step icon, set `defaultStepIcon` to one of the icon IDs that are listed in the [Available step icons](#step-icons) section earlier in this topic.</span></span>

### <a name="use-a-standard-or-custom-step-icon-and-title-for-the-weight-input"></a><span data-ttu-id="b0f6b-600">Use un icono de paso estándar o personalizado y un título para la entrada de peso</span><span class="sxs-lookup"><span data-stu-id="b0f6b-600">Use a standard or custom step icon and title for the weight input</span></span>

<span data-ttu-id="b0f6b-601">La página de entrada de peso le permite al trabajador introducir un peso.</span><span class="sxs-lookup"><span data-stu-id="b0f6b-601">The weight input page lets the worker enter a weight.</span></span>

<span data-ttu-id="b0f6b-602">![Página de entrada de peso](media/step-icons-example-weight-input.png "Página de entrada de peso")</span><span class="sxs-lookup"><span data-stu-id="b0f6b-602">![Weight input page](media/step-icons-example-weight-input.png "Weight input page")</span></span>

<span data-ttu-id="b0f6b-603">En la página de entrada de peso, el nombre de control del campo de entrada es `Weight`, que está en la [lista de ID de pasos](#step-ids-classes).</span><span class="sxs-lookup"><span data-stu-id="b0f6b-603">On the weight input page, the control name of the input field is `Weight`, which is in the [list of step IDs](#step-ids-classes).</span></span> <span data-ttu-id="b0f6b-604">Por lo tanto, si el icono de paso y el título que se definen en la clase `WHSMobileAppStepWeight` son aceptables para usted, no tiene que cambiar nada para este paso.</span><span class="sxs-lookup"><span data-stu-id="b0f6b-604">Therefore, if the step icon and title that are defined in the `WHSMobileAppStepWeight` class are acceptable to you, you don't have to change anything for this step.</span></span>

<span data-ttu-id="b0f6b-605">Sin embargo, si prefiere utilizar un icono o título diferente para este paso, puede anular el método `stepId()` o el método `stepInfo()` en la clase de constructor.</span><span class="sxs-lookup"><span data-stu-id="b0f6b-605">However, if you prefer to use a different icon or title for this step, you can override either the `stepId()` method or the `stepInfo()` method in the builder class.</span></span> <span data-ttu-id="b0f6b-606">Cada flujo de tareas tiene su propio generador de información de pasos.</span><span class="sxs-lookup"><span data-stu-id="b0f6b-606">Each task flow has its own step info builder.</span></span>

#### <a name="override-the-stepid-method"></a><span data-ttu-id="b0f6b-607">Anular el método stepId()</span><span class="sxs-lookup"><span data-stu-id="b0f6b-607">Override the stepId() method</span></span>

<span data-ttu-id="b0f6b-608">El siguiente ejemplo muestra una forma en la que puede modificar una clase de constructor anulando el método `stepId()`.</span><span class="sxs-lookup"><span data-stu-id="b0f6b-608">The following example shows one way that you can modify a builder class by overriding the `stepId()` method.</span></span>

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode:: WeighContainer)]
public class WHSMobileAppStepInfoBuilderWeighContainer extends WHSMobileAppStepInfoBuilder
{
    protected WHSMobileAppStepId stepId()
    {
        WHSMobileAppStepId stepIdLocal = super();
        if (stepIdLocal == 'Weight')
        {
            return 'NewWeight';
        }
        return stepIdLocal;
    }
}
```

<span data-ttu-id="b0f6b-609">Luego cree una clase de pasos para el paso `NewWeight`.</span><span class="sxs-lookup"><span data-stu-id="b0f6b-609">You then create a step class for the `NewWeight` step.</span></span> <span data-ttu-id="b0f6b-610">El código debe parecerse al código del ejemplo `ContainerId` que se mostró anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="b0f6b-610">The code should resemble the code for the `ContainerId` example that was shown earlier in this topic.</span></span>

#### <a name="override-the-stepinfo-method"></a><span data-ttu-id="b0f6b-611">Anular el método stepInfo()</span><span class="sxs-lookup"><span data-stu-id="b0f6b-611">Override the stepInfo() method</span></span>

<span data-ttu-id="b0f6b-612">El siguiente ejemplo muestra una forma en la que puede modificar una clase de constructor anulando el método `stepInfo()`.</span><span class="sxs-lookup"><span data-stu-id="b0f6b-612">The following example shows one way that you can modify a builder class by overriding the `stepInfo()` method.</span></span>

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode:: WeighContainer)]
public class WHSMobileAppStepInfoBuilderWeighContainer extends WHSMobileAppStepInfoBuilder
{
    protected WHSMobileAppStepInfo stepInfo()
    {
        if (stepId != 'Weight')
        {
            return super();
        }
        WHSMobileAppStepInfo stepInfo = WHSMobileAppStepInfo::construct();
        stepInfo.parmStepIcon('NewIcon');
        stepInfo.parmStepTitle('NewTitle');
        return stepInfo;
    }
}
```

<span data-ttu-id="b0f6b-613">Luego construye un objeto `WHSMobileAppStepInfo` y establezca el icono y/o título directamente.</span><span class="sxs-lookup"><span data-stu-id="b0f6b-613">You then construct a `WHSMobileAppStepInfo` object, and set the icon and/or title directly.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b0f6b-614">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="b0f6b-614">Additional resources</span></span>

- [<span data-ttu-id="b0f6b-615">Instalar y conectar la aplicación móvil Gestión de almacenes</span><span class="sxs-lookup"><span data-stu-id="b0f6b-615">Install and connect the Warehouse Management mobile app</span></span>](install-configure-warehouse-management-app.md)
- [<span data-ttu-id="b0f6b-616">Configuración de usuario del dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="b0f6b-616">Mobile device user settings</span></span>](mobile-device-user-settings.md)
