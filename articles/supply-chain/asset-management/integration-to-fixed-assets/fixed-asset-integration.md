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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: cdda44d361011706fe0ba170309908533aa0c2f7
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "3276961"
---
# <a name="integrate-asset-management-with-fixed-assets"></a><span data-ttu-id="0aa7c-103">Integrar la administración de activos con activos fijos.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-103">Integrate asset management with fixed assets</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0aa7c-104">Al integrar los módulos **Administración de activos** y **Activos fijos**, puede vincular los activos fijos con los activos de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-104">By integrating the **Asset management** and **Fixed assets** modules, you can link fixed assets with maintenance assets.</span></span> <span data-ttu-id="0aa7c-105">Los usuarios de Activos fijos pueden crear un activo de mantenimiento a partir de un activo fijo nuevo o existente, y los usuarios de Administración de activos pueden asociar un activo de mantenimiento con un activo fijo existente.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-105">Fixed assets users can then create a maintenance asset from a new or existing fixed asset, and Asset management users can associate a maintenance asset with an existing fixed asset.</span></span> <span data-ttu-id="0aa7c-106">Esta característica también facilita a los usuarios de Activos fijos ver los costos que se registraron en las órdenes de trabajo para los activos de mantenimiento relacionados.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-106">This feature also makes it easy for Fixed assets users to view the costs that were posted from work orders for related maintenance assets.</span></span>

> [!NOTE]
> <span data-ttu-id="0aa7c-107">En este tema, *activos de mantenimiento* son los activos del módulo **Administración de activos** y *Activos fijos* son los activos del módulo **Activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-107">In this topic, *maintenance assets* refer to assets from the **Asset management** module, and *fixed assets* refer to assets from the **Fixed assets** module.</span></span>

## <a name="set-a-default-location-for-new-maintenance-assets-that-are-created-from-fixed-assets-optional"></a><span data-ttu-id="0aa7c-108">Establecer una ubicación predeterminada para los nuevos activos de mantenimiento que se crean a partir de activos fijos (opcional)</span><span class="sxs-lookup"><span data-stu-id="0aa7c-108">Set a default location for new maintenance assets that are created from fixed assets (optional)</span></span>

<span data-ttu-id="0aa7c-109">Esta configuración opcional permite establecer una ubicación funcional predeterminada para los nuevos activos de mantenimiento que se crean a partir de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-109">This optional configuration lets you set a default functional location for new maintenance assets that are created from fixed assets.</span></span> <span data-ttu-id="0aa7c-110">Por lo general, completa esta configuración solo una vez, si es que la completa.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-110">You typically complete this configuration this just one time, if you complete it at all.</span></span>

<span data-ttu-id="0aa7c-111">Para completar la configuración, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-111">To complete the configuration, follow these steps.</span></span>

1. <span data-ttu-id="0aa7c-112">Vaya a **Administración de activos \> Configuración \> Parámetros de administración de activos**.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-112">Go to **Asset management \> Setup \> Asset management parameters**.</span></span>
1. <span data-ttu-id="0aa7c-113">En la ficha **Activos fijos**, en el campo **Ubicación funcional**, seleccione la ubicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-113">On the **Fixed assets** tab, in the **Functional location** field, select the default location.</span></span>
1. <span data-ttu-id="0aa7c-114">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-114">On the Action Pane, select **Save**.</span></span>

## <a name="work-with-integrated-maintenance-assets-and-fixed-assets"></a><span data-ttu-id="0aa7c-115">Trabajar con activos de mantenimiento y activos fijos</span><span class="sxs-lookup"><span data-stu-id="0aa7c-115">Work with integrated maintenance assets and fixed assets</span></span>

<span data-ttu-id="0aa7c-116">Esta sección proporciona una colección de procedimientos que muestran varias formas en que puede trabajar con las funciones integradas de Administración de activos y Activos fijos.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-116">This section provides a collection of procedures that show various ways that you can work with the integrated Asset management and Fixed assets features.</span></span>

### <a name="associate-an-existing-maintenance-asset-with-a-fixed-asset"></a><span data-ttu-id="0aa7c-117">Asociar un activo de mantenimiento existente con un activo fijo</span><span class="sxs-lookup"><span data-stu-id="0aa7c-117">Associate an existing maintenance asset with a fixed asset</span></span>

<span data-ttu-id="0aa7c-118">Para asociar un activo de mantenimiento existente con un activo fijo, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-118">To associate an existing maintenance asset with a fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="0aa7c-119">Vaya a **Administración de activos \> Activos \> Todos los activos** (o **Activos activos**).</span><span class="sxs-lookup"><span data-stu-id="0aa7c-119">Go to **Asset management \> Assets \> All assets** (or **Active assets**).</span></span>
1. <span data-ttu-id="0aa7c-120">Seleccione un activo.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-120">Select an asset.</span></span>
1. <span data-ttu-id="0aa7c-121">En la ficha desplegable **Activo fijo**, en el campo **Número de activo fijo**, seleccione un activo fijo existente.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-121">On the **Fixed asset** FastTab, in the **Fixed asset number** field, select an existing fixed asset.</span></span>
1. <span data-ttu-id="0aa7c-122">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-122">On the Action Pane, select **Save**.</span></span>

### <a name="view-the-fixed-asset-that-is-associated-with-a-selected-maintenance-asset"></a><span data-ttu-id="0aa7c-123">Ver el activo fijo asociado con un activo de mantenimiento seleccionado</span><span class="sxs-lookup"><span data-stu-id="0aa7c-123">View the fixed asset that is associated with a selected maintenance asset</span></span>

<span data-ttu-id="0aa7c-124">Para ver el activo fijo asociado con un activo de mantenimiento seleccionado, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-124">To view the fixed asset that is associated with a selected maintenance asset, follow these steps.</span></span>

1. <span data-ttu-id="0aa7c-125">Vaya a **Administración de activos \> Activos \> Todos los activos** (o **Activos activos**).</span><span class="sxs-lookup"><span data-stu-id="0aa7c-125">Go to **Asset management \> Assets \> All assets** (or **Active assets**).</span></span>
1. <span data-ttu-id="0aa7c-126">Seleccione un activo.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-126">Select an asset.</span></span>
1. <span data-ttu-id="0aa7c-127">En la ficha desplegable **Activo fijo**, en el campo **Número de activo fijo**, seleccione el vínculo.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-127">On the **Fixed asset** FastTab, in the **Fixed asset number** field, select the link.</span></span>

    <span data-ttu-id="0aa7c-128">Se abre la página **Activos fijos** para el activo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-128">The **Fixed assets** page for the selected asset is opened.</span></span> <span data-ttu-id="0aa7c-129">(Normalmente, esta página se encuentra en **Activos fijos \> Activos fijos \> Activos fijos**).</span><span class="sxs-lookup"><span data-stu-id="0aa7c-129">(Typically, this page is found at **Fixed assets \> Fixed assets \> Fixed assets**.)</span></span>

### <a name="view-the-maintenance-asset-that-is-associated-with-a-selected-fixed-asset"></a><span data-ttu-id="0aa7c-130">Ver el activo de mantenimiento asociado con un activo fijo seleccionado</span><span class="sxs-lookup"><span data-stu-id="0aa7c-130">View the maintenance asset that is associated with a selected fixed asset</span></span>

<span data-ttu-id="0aa7c-131">Para ver el activo de mantenimiento asociado con un activo fijo seleccionado, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-131">To view the maintenance asset that is associated with a selected fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="0aa7c-132">Vaya a **Activos fijos \> Activos fijos \> Activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-132">Go to **Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
1. <span data-ttu-id="0aa7c-133">Seleccione un activo.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-133">Select an asset.</span></span>
1. <span data-ttu-id="0aa7c-134">En el panel de acciones, en la ficha **Administración de activos**, en el grupo **Vista**, seleccione **Activo de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-134">On the Action Pane, on the **Asset management** tab, in the **View** group, select **Maintenance asset**.</span></span>

    <span data-ttu-id="0aa7c-135">Se abre la página **Activo de mantenimiento** para el activo asociado con el activo fijo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-135">The **Maintenance asset** page for the asset that is associated with the selected fixed asset is opened.</span></span> <span data-ttu-id="0aa7c-136">(Normalmente, esta página se encuentra en **Administración de activos \> Activos \> Todos los activos**).</span><span class="sxs-lookup"><span data-stu-id="0aa7c-136">(Typically, this page is found at **Asset management \> Assets \> All assets**.)</span></span>

### <a name="view-maintenance-costs-that-are-associated-with-a-fixed-asset"></a><span data-ttu-id="0aa7c-137">Ver los costos de mantenimiento asociados con un activo fijo</span><span class="sxs-lookup"><span data-stu-id="0aa7c-137">View maintenance costs that are associated with a fixed asset</span></span>

<span data-ttu-id="0aa7c-138">Las órdenes de trabajo de administración de activos pueden contabilizarse para activos de mantenimiento y cada una de esas órdenes de trabajo generalmente tiene un costo.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-138">Asset management work orders can be posted for maintenance assets, and each of those work orders typically has a cost.</span></span> <span data-ttu-id="0aa7c-139">Cuando un activo fijo está asociado con un activo de mantenimiento, puede ir directamente desde el activo fijo para ver los costos relacionados.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-139">When a fixed asset is associated with a maintenance asset, you can go directly from the fixed asset to view the related costs.</span></span>

<span data-ttu-id="0aa7c-140">Para ver los costos de mantenimiento asociados con un activo fijo, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-140">To view the maintenance costs that are associated with a fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="0aa7c-141">Vaya a **Activos fijos \> Activos fijos \> Activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-141">Go to **Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
1. <span data-ttu-id="0aa7c-142">Seleccione un activo.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-142">Select an asset.</span></span>
1. <span data-ttu-id="0aa7c-143">En el panel de acciones, en la ficha **Administración de activos**, en el grupo **Vista**, seleccione **Costo de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-143">On the Action Pane, on the **Asset management** tab, in the **View** group, select **Maintenance cost**.</span></span>

    <span data-ttu-id="0aa7c-144">Se abre la página **Costo de mantenimiento** y muestra los costos relacionados.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-144">The **Maintenance cost** page is opened and shows the related costs.</span></span>

### <a name="create-a-new-maintenance-asset-for-an-existing-fixed-asset"></a><a name="new-maintenance-from-fixed"></a><span data-ttu-id="0aa7c-145">Crear un activo de mantenimiento nuevo para un activo fijo existente</span><span class="sxs-lookup"><span data-stu-id="0aa7c-145">Create a new maintenance asset for an existing fixed asset</span></span>

<span data-ttu-id="0aa7c-146">Para crear un activo de mantenimiento nuevo para un activo fijo existente, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-146">To create a new maintenance asset for an existing fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="0aa7c-147">Vaya a **Activos fijos \> Activos fijos \> Activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-147">Go to **Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
1. <span data-ttu-id="0aa7c-148">Seleccione un activo.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-148">Select an asset.</span></span>
1. <span data-ttu-id="0aa7c-149">En el panel de acciones, en la ficha **Administración de activos**, en el grupo **Nuevo**, seleccione **Crear activo de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-149">On the Action Pane, on the **Asset management** tab, in the **New** group, select **Create maintenance asset**.</span></span> <span data-ttu-id="0aa7c-150">(Si esta opción no está disponible, un activo de mantenimiento ya podría estar asociado con el activo fijo seleccionado).</span><span class="sxs-lookup"><span data-stu-id="0aa7c-150">(If this option is unavailable, a maintenance asset might already be associated with the selected fixed asset.)</span></span>
1. <span data-ttu-id="0aa7c-151">Termine de crear el activo como se describe en [Crear un activo](../objects/create-an-object.md).</span><span class="sxs-lookup"><span data-stu-id="0aa7c-151">Finish creating the asset as described in [Create an asset](../objects/create-an-object.md).</span></span>

### <a name="create-a-new-fixed-asset-and-add-a-new-maintenance-asset-for-it"></a><span data-ttu-id="0aa7c-152">Crear un activo fijo nuevo y agregar un activo de mantenimiento nuevo para él</span><span class="sxs-lookup"><span data-stu-id="0aa7c-152">Create a new fixed asset and add a new maintenance asset for it</span></span>

<span data-ttu-id="0aa7c-153">Para crear un activo fijo nuevo y agregar un activo de mantenimiento nuevo para este, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-153">To create a new fixed asset and add a new maintenance asset for it, follow these steps.</span></span>

1. <span data-ttu-id="0aa7c-154">Vaya a **Activos fijos \> Activos fijos \> Activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-154">Go to **Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
1. <span data-ttu-id="0aa7c-155">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-155">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="0aa7c-156">Termine de crear el activo fijo como se describe en [Crear un activo fijo](../../../finance/fixed-assets/tasks/create-fixed-asset.md).</span><span class="sxs-lookup"><span data-stu-id="0aa7c-156">Finish creating the fixed asset as described in [Create a fixed asset](../../../finance/fixed-assets/tasks/create-fixed-asset.md).</span></span>
1. <span data-ttu-id="0aa7c-157">En el panel de acciones, en la ficha **Administración de activos**, en el grupo **Nuevo**, seleccione **Crear activo de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-157">On the Action Pane, on the **Asset management** tab, in the **New** group, select **Create maintenance asset**.</span></span>
1. <span data-ttu-id="0aa7c-158">Termine de crear el activo como se describe en [Crear un activo](../objects/create-an-object.md).</span><span class="sxs-lookup"><span data-stu-id="0aa7c-158">Finish creating the asset as described in [Create an asset](../objects/create-an-object.md).</span></span>

### <a name="remove-the-association-between-two-assets"></a><span data-ttu-id="0aa7c-159">Eliminar la asociación entre dos activos</span><span class="sxs-lookup"><span data-stu-id="0aa7c-159">Remove the association between two assets</span></span>

<span data-ttu-id="0aa7c-160">En algunos casos, es posible que deba desasociar un activo de mantenimiento de su activo fijo.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-160">In some cases, you might have to disassociate a maintenance asset from its fixed asset.</span></span> <span data-ttu-id="0aa7c-161">Por ejemplo, si quiere [crear un nuevo activo de mantenimiento](#new-maintenance-from-fixed) a partir de un activo fijo, primero debe eliminar cualquier asociación existente.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-161">For example, if you want to [create a new maintenance asset](#new-maintenance-from-fixed) from a fixed asset, you must first remove any existing association.</span></span>

<span data-ttu-id="0aa7c-162">Para eliminar una asociación existente entre un activo de mantenimiento y un activo fijo, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-162">To remove an existing association between a maintenance asset and a fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="0aa7c-163">Vaya a **Administración de activos \> Activos \> Todos los activos** (o **Activos activos**).</span><span class="sxs-lookup"><span data-stu-id="0aa7c-163">Go to **Asset management \> Assets \> All assets** (or **Active assets**).</span></span>
1. <span data-ttu-id="0aa7c-164">Busque y abra el activo fijo.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-164">Find and open the fixed asset.</span></span>
1. <span data-ttu-id="0aa7c-165">En la ficha desplegable **Activo fijo**, borre el valor del campo **Ubicación funcional**.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-165">On the **Fixed asset** FastTab, clear the value from the **Functional location** field.</span></span>
1. <span data-ttu-id="0aa7c-166">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0aa7c-166">On the Action Pane, select **Save**.</span></span>
