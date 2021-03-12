---
title: Integrar la administración de activos con activos fijos.
description: Este tema explica cómo integrar los módulos de Administración de activos y Activos fijos, para que pueda vincular activos fijos con activos de mantenimiento.
author: kamaybac
manager: tfehr
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 879950b9aeb345fcd59dfe73d3963a44607c7ac2
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994238"
---
# <a name="integrate-asset-management-with-fixed-assets"></a><span data-ttu-id="3d1ab-103">Integrar la administración de activos con activos fijos.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-103">Integrate asset management with fixed assets</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3d1ab-104">Al integrar los módulos **Administración de activos** y **Activos fijos**, puede vincular los activos fijos con los activos de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-104">By integrating the **Asset management** and **Fixed assets** modules, you can link fixed assets with maintenance assets.</span></span> <span data-ttu-id="3d1ab-105">Los usuarios de Activos fijos pueden crear un activo de mantenimiento a partir de un activo fijo nuevo o existente, y los usuarios de Administración de activos pueden asociar un activo de mantenimiento con un activo fijo existente.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-105">Fixed assets users can then create a maintenance asset from a new or existing fixed asset, and Asset management users can associate a maintenance asset with an existing fixed asset.</span></span> <span data-ttu-id="3d1ab-106">Esta característica también facilita a los usuarios de Activos fijos ver los costos que se registraron en las órdenes de trabajo para los activos de mantenimiento relacionados.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-106">This feature also makes it easy for Fixed assets users to view the costs that were posted from work orders for related maintenance assets.</span></span>

> [!NOTE]
> <span data-ttu-id="3d1ab-107">En este tema, *activos de mantenimiento* son los activos del módulo **Administración de activos** y *Activos fijos* son los activos del módulo **Activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-107">In this topic, *maintenance assets* refer to assets from the **Asset management** module, and *fixed assets* refer to assets from the **Fixed assets** module.</span></span>

## <a name="set-a-default-location-for-new-maintenance-assets-that-are-created-from-fixed-assets-optional"></a><span data-ttu-id="3d1ab-108">Establecer una ubicación predeterminada para los nuevos activos de mantenimiento que se crean a partir de activos fijos (opcional)</span><span class="sxs-lookup"><span data-stu-id="3d1ab-108">Set a default location for new maintenance assets that are created from fixed assets (optional)</span></span>

<span data-ttu-id="3d1ab-109">Esta configuración opcional permite establecer una ubicación funcional predeterminada para los nuevos activos de mantenimiento que se crean a partir de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-109">This optional configuration lets you set a default functional location for new maintenance assets that are created from fixed assets.</span></span> <span data-ttu-id="3d1ab-110">Por lo general, completa esta configuración solo una vez, si es que la completa.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-110">You typically complete this configuration this just one time, if you complete it at all.</span></span>

<span data-ttu-id="3d1ab-111">Para completar la configuración, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-111">To complete the configuration, follow these steps.</span></span>

1. <span data-ttu-id="3d1ab-112">Vaya a **Administración de activos \> Configuración \> Parámetros de administración de activos**.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-112">Go to **Asset management \> Setup \> Asset management parameters**.</span></span>
1. <span data-ttu-id="3d1ab-113">En la ficha **Activos fijos**, en el campo **Ubicación funcional**, seleccione la ubicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-113">On the **Fixed assets** tab, in the **Functional location** field, select the default location.</span></span>
1. <span data-ttu-id="3d1ab-114">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-114">On the Action Pane, select **Save**.</span></span>

## <a name="work-with-integrated-maintenance-assets-and-fixed-assets"></a><span data-ttu-id="3d1ab-115">Trabajar con activos de mantenimiento y activos fijos</span><span class="sxs-lookup"><span data-stu-id="3d1ab-115">Work with integrated maintenance assets and fixed assets</span></span>

<span data-ttu-id="3d1ab-116">Esta sección proporciona una colección de procedimientos que muestran varias formas en que puede trabajar con las funciones integradas de Administración de activos y Activos fijos.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-116">This section provides a collection of procedures that show various ways that you can work with the integrated Asset management and Fixed assets features.</span></span>

### <a name="associate-an-existing-maintenance-asset-with-a-fixed-asset"></a><span data-ttu-id="3d1ab-117">Asociar un activo de mantenimiento existente con un activo fijo</span><span class="sxs-lookup"><span data-stu-id="3d1ab-117">Associate an existing maintenance asset with a fixed asset</span></span>

<span data-ttu-id="3d1ab-118">Para asociar un activo de mantenimiento existente con un activo fijo, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-118">To associate an existing maintenance asset with a fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="3d1ab-119">Vaya a **Administración de activos \> Activos \> Todos los activos** (o **Activos activos**).</span><span class="sxs-lookup"><span data-stu-id="3d1ab-119">Go to **Asset management \> Assets \> All assets** (or **Active assets**).</span></span>
1. <span data-ttu-id="3d1ab-120">Seleccione un activo.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-120">Select an asset.</span></span>
1. <span data-ttu-id="3d1ab-121">En la ficha desplegable **Activo fijo**, en el campo **Número de activo fijo**, seleccione un activo fijo existente.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-121">On the **Fixed asset** FastTab, in the **Fixed asset number** field, select an existing fixed asset.</span></span>
1. <span data-ttu-id="3d1ab-122">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-122">On the Action Pane, select **Save**.</span></span>

### <a name="view-the-fixed-asset-that-is-associated-with-a-selected-maintenance-asset"></a><span data-ttu-id="3d1ab-123">Ver el activo fijo asociado con un activo de mantenimiento seleccionado</span><span class="sxs-lookup"><span data-stu-id="3d1ab-123">View the fixed asset that is associated with a selected maintenance asset</span></span>

<span data-ttu-id="3d1ab-124">Para ver el activo fijo asociado con un activo de mantenimiento seleccionado, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-124">To view the fixed asset that is associated with a selected maintenance asset, follow these steps.</span></span>

1. <span data-ttu-id="3d1ab-125">Vaya a **Administración de activos \> Activos \> Todos los activos** (o **Activos activos**).</span><span class="sxs-lookup"><span data-stu-id="3d1ab-125">Go to **Asset management \> Assets \> All assets** (or **Active assets**).</span></span>
1. <span data-ttu-id="3d1ab-126">Seleccione un activo.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-126">Select an asset.</span></span>
1. <span data-ttu-id="3d1ab-127">En la ficha desplegable **Activo fijo**, en el campo **Número de activo fijo**, seleccione el vínculo.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-127">On the **Fixed asset** FastTab, in the **Fixed asset number** field, select the link.</span></span>

    <span data-ttu-id="3d1ab-128">Se abre la página **Activos fijos** para el activo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-128">The **Fixed assets** page for the selected asset is opened.</span></span> <span data-ttu-id="3d1ab-129">(Normalmente, esta página se encuentra en **Activos fijos \> Activos fijos \> Activos fijos**).</span><span class="sxs-lookup"><span data-stu-id="3d1ab-129">(Typically, this page is found at **Fixed assets \> Fixed assets \> Fixed assets**.)</span></span>

### <a name="view-the-maintenance-asset-that-is-associated-with-a-selected-fixed-asset"></a><span data-ttu-id="3d1ab-130">Ver el activo de mantenimiento asociado con un activo fijo seleccionado</span><span class="sxs-lookup"><span data-stu-id="3d1ab-130">View the maintenance asset that is associated with a selected fixed asset</span></span>

<span data-ttu-id="3d1ab-131">Para ver el activo de mantenimiento asociado con un activo fijo seleccionado, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-131">To view the maintenance asset that is associated with a selected fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="3d1ab-132">Vaya a **Activos fijos \> Activos fijos \> Activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-132">Go to **Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
1. <span data-ttu-id="3d1ab-133">Seleccione un activo.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-133">Select an asset.</span></span>
1. <span data-ttu-id="3d1ab-134">En el panel de acciones, en la ficha **Administración de activos**, en el grupo **Vista**, seleccione **Activo de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-134">On the Action Pane, on the **Asset management** tab, in the **View** group, select **Maintenance asset**.</span></span>

    <span data-ttu-id="3d1ab-135">Se abre la página **Activo de mantenimiento** para el activo asociado con el activo fijo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-135">The **Maintenance asset** page for the asset that is associated with the selected fixed asset is opened.</span></span> <span data-ttu-id="3d1ab-136">(Normalmente, esta página se encuentra en **Administración de activos \> Activos \> Todos los activos**).</span><span class="sxs-lookup"><span data-stu-id="3d1ab-136">(Typically, this page is found at **Asset management \> Assets \> All assets**.)</span></span>

### <a name="view-maintenance-costs-that-are-associated-with-a-fixed-asset"></a><span data-ttu-id="3d1ab-137">Ver los costos de mantenimiento asociados con un activo fijo</span><span class="sxs-lookup"><span data-stu-id="3d1ab-137">View maintenance costs that are associated with a fixed asset</span></span>

<span data-ttu-id="3d1ab-138">Las órdenes de trabajo de administración de activos pueden contabilizarse para activos de mantenimiento y cada una de esas órdenes de trabajo generalmente tiene un costo.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-138">Asset management work orders can be posted for maintenance assets, and each of those work orders typically has a cost.</span></span> <span data-ttu-id="3d1ab-139">Cuando un activo fijo está asociado con un activo de mantenimiento, puede ir directamente desde el activo fijo para ver los costos relacionados.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-139">When a fixed asset is associated with a maintenance asset, you can go directly from the fixed asset to view the related costs.</span></span>

<span data-ttu-id="3d1ab-140">Para ver los costos de mantenimiento asociados con un activo fijo, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-140">To view the maintenance costs that are associated with a fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="3d1ab-141">Vaya a **Activos fijos \> Activos fijos \> Activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-141">Go to **Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
1. <span data-ttu-id="3d1ab-142">Seleccione un activo.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-142">Select an asset.</span></span>
1. <span data-ttu-id="3d1ab-143">En el panel de acciones, en la ficha **Administración de activos**, en el grupo **Vista**, seleccione **Costo de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-143">On the Action Pane, on the **Asset management** tab, in the **View** group, select **Maintenance cost**.</span></span>

    <span data-ttu-id="3d1ab-144">Se abre la página **Costo de mantenimiento** y muestra los costos relacionados.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-144">The **Maintenance cost** page is opened and shows the related costs.</span></span>

### <a name="create-a-new-maintenance-asset-for-an-existing-fixed-asset"></a><a name="new-maintenance-from-fixed"></a><span data-ttu-id="3d1ab-145">Crear un activo de mantenimiento nuevo para un activo fijo existente</span><span class="sxs-lookup"><span data-stu-id="3d1ab-145">Create a new maintenance asset for an existing fixed asset</span></span>

<span data-ttu-id="3d1ab-146">Para crear un activo de mantenimiento nuevo para un activo fijo existente, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-146">To create a new maintenance asset for an existing fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="3d1ab-147">Vaya a **Activos fijos \> Activos fijos \> Activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-147">Go to **Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
1. <span data-ttu-id="3d1ab-148">Seleccione un activo.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-148">Select an asset.</span></span>
1. <span data-ttu-id="3d1ab-149">En el panel de acciones, en la ficha **Administración de activos**, en el grupo **Nuevo**, seleccione **Crear activo de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-149">On the Action Pane, on the **Asset management** tab, in the **New** group, select **Create maintenance asset**.</span></span> <span data-ttu-id="3d1ab-150">(Si esta opción no está disponible, un activo de mantenimiento ya podría estar asociado con el activo fijo seleccionado).</span><span class="sxs-lookup"><span data-stu-id="3d1ab-150">(If this option is unavailable, a maintenance asset might already be associated with the selected fixed asset.)</span></span>
1. <span data-ttu-id="3d1ab-151">Termine de crear el activo como se describe en [Crear un activo](../objects/create-an-object.md).</span><span class="sxs-lookup"><span data-stu-id="3d1ab-151">Finish creating the asset as described in [Create an asset](../objects/create-an-object.md).</span></span>

### <a name="create-a-new-fixed-asset-and-add-a-new-maintenance-asset-for-it"></a><span data-ttu-id="3d1ab-152">Crear un activo fijo nuevo y agregar un activo de mantenimiento nuevo para él</span><span class="sxs-lookup"><span data-stu-id="3d1ab-152">Create a new fixed asset and add a new maintenance asset for it</span></span>

<span data-ttu-id="3d1ab-153">Para crear un activo fijo nuevo y agregar un activo de mantenimiento nuevo para este, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-153">To create a new fixed asset and add a new maintenance asset for it, follow these steps.</span></span>

1. <span data-ttu-id="3d1ab-154">Vaya a **Activos fijos \> Activos fijos \> Activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-154">Go to **Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
1. <span data-ttu-id="3d1ab-155">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-155">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="3d1ab-156">Termine de crear el activo fijo como se describe en [Crear un activo fijo](../../../finance/fixed-assets/tasks/create-fixed-asset.md).</span><span class="sxs-lookup"><span data-stu-id="3d1ab-156">Finish creating the fixed asset as described in [Create a fixed asset](../../../finance/fixed-assets/tasks/create-fixed-asset.md).</span></span>
1. <span data-ttu-id="3d1ab-157">En el panel de acciones, en la ficha **Administración de activos**, en el grupo **Nuevo**, seleccione **Crear activo de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-157">On the Action Pane, on the **Asset management** tab, in the **New** group, select **Create maintenance asset**.</span></span>
1. <span data-ttu-id="3d1ab-158">Termine de crear el activo como se describe en [Crear un activo](../objects/create-an-object.md).</span><span class="sxs-lookup"><span data-stu-id="3d1ab-158">Finish creating the asset as described in [Create an asset](../objects/create-an-object.md).</span></span>

### <a name="remove-the-association-between-two-assets"></a><span data-ttu-id="3d1ab-159">Eliminar la asociación entre dos activos</span><span class="sxs-lookup"><span data-stu-id="3d1ab-159">Remove the association between two assets</span></span>

<span data-ttu-id="3d1ab-160">En algunos casos, es posible que deba desasociar un activo de mantenimiento de su activo fijo.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-160">In some cases, you might have to disassociate a maintenance asset from its fixed asset.</span></span> <span data-ttu-id="3d1ab-161">Por ejemplo, si quiere [crear un nuevo activo de mantenimiento](#new-maintenance-from-fixed) a partir de un activo fijo, primero debe eliminar cualquier asociación existente.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-161">For example, if you want to [create a new maintenance asset](#new-maintenance-from-fixed) from a fixed asset, you must first remove any existing association.</span></span>

<span data-ttu-id="3d1ab-162">Para eliminar una asociación existente entre un activo de mantenimiento y un activo fijo, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-162">To remove an existing association between a maintenance asset and a fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="3d1ab-163">Vaya a **Administración de activos \> Activos \> Todos los activos** (o **Activos activos**).</span><span class="sxs-lookup"><span data-stu-id="3d1ab-163">Go to **Asset management \> Assets \> All assets** (or **Active assets**).</span></span>
1. <span data-ttu-id="3d1ab-164">Busque y abra el activo fijo.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-164">Find and open the fixed asset.</span></span>
1. <span data-ttu-id="3d1ab-165">En la ficha desplegable **Activo fijo**, borre el valor del campo **Ubicación funcional**.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-165">On the **Fixed asset** FastTab, clear the value from the **Functional location** field.</span></span>
1. <span data-ttu-id="3d1ab-166">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3d1ab-166">On the Action Pane, select **Save**.</span></span>
