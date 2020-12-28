---
title: Mover, reemplazar e instalar activos
description: En este tema se explica cómo mover, reemplazar e instalar activos en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectReplace, EntAssetObjectInstallLookup, EntAssetObjectMove, EntAssetObjectTableEditSubObjects
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ec150adb35eb0600844245b14cbec9e9632ab337
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436910"
---
# <a name="move-replace-and-install-assets"></a><span data-ttu-id="011b5-103">Mover, reemplazar e instalar activos</span><span class="sxs-lookup"><span data-stu-id="011b5-103">Move, replace, and install assets</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="011b5-104">En este tema se explica cómo mover, reemplazar e instalar activos en Administración de activos.</span><span class="sxs-lookup"><span data-stu-id="011b5-104">This topic explains how to move, replace, and install assets in Asset Management.</span></span> <span data-ttu-id="011b5-105">Puede crear activos individuales que no tienen ninguna relación con otros activos o puede crear una estructura de activos que incluya un activo (activo principal de nivel superior) y activos secundarios relacionados (subactivos).</span><span class="sxs-lookup"><span data-stu-id="011b5-105">You can create individual assets that have no relations to other assets, or you can create an asset structure that includes a parent asset (top-level asset) and related child assets (sub-assets).</span></span> <span data-ttu-id="011b5-106">En Admnistración de activos, hay tres enfoques para mover y cambiar la ubicación de un activo:</span><span class="sxs-lookup"><span data-stu-id="011b5-106">In Asset Management, there are three approaches to moving and changing the location of an asset:</span></span>

- <span data-ttu-id="011b5-107">**Mover** para mover un activo a otra estructura de activos o a otra ubicación de la misma estructura de activos.</span><span class="sxs-lookup"><span data-stu-id="011b5-107">**Move** – Move an asset either to another asset structure or to another location in the same asset structure.</span></span>
- <span data-ttu-id="011b5-108">**Reemplazar** para quitar temporalmente un activo de la estructura de activos de modo que pueda repararse o restaurarse y luego agregar el activo restaurado de nuevo a la estructura de activos.</span><span class="sxs-lookup"><span data-stu-id="011b5-108">**Replace** – Temporarily remove an asset from an asset structure so that it can be repaired or refurbished, and then add the refurbished asset back to the asset structure later.</span></span> <span data-ttu-id="011b5-109">Como alternativa, se puede reemplazar permanentemente un activo utilizado con un nuevo activo.</span><span class="sxs-lookup"><span data-stu-id="011b5-109">Alternatively, permanently replace a used asset with a new asset.</span></span>
- <span data-ttu-id="011b5-110">**Instalar** para instalar un activo principal y cualquier activo secundario relacionado en una ubicación funcional.</span><span class="sxs-lookup"><span data-stu-id="011b5-110">**Install** – Install a parent asset and any related child assets on a functional location.</span></span>

> [!NOTE]
> <span data-ttu-id="011b5-111">El activo que se mueve, reemplaza o instala puede estar relacionado con otra ubicación funcional.</span><span class="sxs-lookup"><span data-stu-id="011b5-111">The asset that you move, replace, or install might be related to another functional location.</span></span> <span data-ttu-id="011b5-112">En ese caso, el activo puede usar dimensiones financieras de la ubicación funcional.</span><span class="sxs-lookup"><span data-stu-id="011b5-112">In that case, the asset might use financial dimensions of the functional location.</span></span> <span data-ttu-id="011b5-113">En la página **Tipos de ubicaciones funcionales**, configure el control de las dimensiones financieras en las ubicaciones funcionales.</span><span class="sxs-lookup"><span data-stu-id="011b5-113">On the **Functional location types** page, you set up the handling of financial dimensions on functional locations.</span></span>

## <a name="move-asset"></a><span data-ttu-id="011b5-114">Mover activo</span><span class="sxs-lookup"><span data-stu-id="011b5-114">Move asset</span></span>

<span data-ttu-id="011b5-115">Utilice la función **Mover activo** para mover un activo a otra estructura de activos o a otra ubicación de la misma estructura de activos.</span><span class="sxs-lookup"><span data-stu-id="011b5-115">Use the **Move asset** function to move an asset either to another asset structure or to another location in the same asset structure.</span></span> <span data-ttu-id="011b5-116">También puede mover un activo de una estructura de activos de modo que se convierta en un activo independiente que no tenga ninguna relación de estructura.</span><span class="sxs-lookup"><span data-stu-id="011b5-116">You can also move an asset out of an asset structure so that it becomes a standalone asset that has no structure relations.</span></span>

> [!NOTE]
> <span data-ttu-id="011b5-117">No use esta función si se están reparando o se están reemplazando temporalmente los activos.</span><span class="sxs-lookup"><span data-stu-id="011b5-117">Don't use this function if assets are being repaired or temporarily replaced.</span></span> <span data-ttu-id="011b5-118">En tal caso, use la funcionalidad **Reemplazar activo** que se describe más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="011b5-118">Instead, use the **Replace asset** functionality that is described later in this topic.</span></span>

1. <span data-ttu-id="011b5-119">Seleccione **Administración de activos** \> **Común** \> **Activos** \> **Todos los activos** o **Activos activos**.</span><span class="sxs-lookup"><span data-stu-id="011b5-119">Select **Asset management** \> **Common** \> **Assets** \> **All assets** or **Active assets**.</span></span>
2. <span data-ttu-id="011b5-120">En la lista, seleccione el activo que desea mover.</span><span class="sxs-lookup"><span data-stu-id="011b5-120">In the list, select the asset to move.</span></span> <span data-ttu-id="011b5-121">Si el activo tiene activos secundarios, también mueve dichos activos.</span><span class="sxs-lookup"><span data-stu-id="011b5-121">If the asset has child assets, you also move those assets.</span></span>
3. <span data-ttu-id="011b5-122">Seleccione **Mover activo**.</span><span class="sxs-lookup"><span data-stu-id="011b5-122">Select **Move asset**.</span></span>
4. <span data-ttu-id="011b5-123">Para mover el activo de modo que se convierta en parte de una estructura de activos, seleccione el nuevo activo principal en el campo **Activo principal**.</span><span class="sxs-lookup"><span data-stu-id="011b5-123">To move the asset so that it becomes part of an asset structure, select the new parent asset in the **Parent asset** field.</span></span> <span data-ttu-id="011b5-124">Si está moviendo un activo secundario y desea que sea un activo independiente sin ninguna relación de estructura, deje en blanco del campo **Activo principal**.</span><span class="sxs-lookup"><span data-stu-id="011b5-124">If you're moving a child asset, and you want to make it a standalone asset that has no structure relations, leave the **Parent asset** field blank.</span></span>
5. <span data-ttu-id="011b5-125">De manera predeterminada, el campo **Vigencia** se establece automáticamente en la fecha y la hora actuales.</span><span class="sxs-lookup"><span data-stu-id="011b5-125">By default, the **Effective** field is set to the current date and time.</span></span> <span data-ttu-id="011b5-126">Sin embargo, puede seleccionar otra fecha y hora a partir de las cuales sea válido el movimiento.</span><span class="sxs-lookup"><span data-stu-id="011b5-126">However, you can select a different date and time that the asset move is valid from.</span></span>
6. <span data-ttu-id="011b5-127">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="011b5-127">Select **OK**.</span></span>

## <a name="replace-asset"></a><span data-ttu-id="011b5-128">Reemplazar activo</span><span class="sxs-lookup"><span data-stu-id="011b5-128">Replace asset</span></span>

<span data-ttu-id="011b5-129">Use la función **Reemplazar activo** en relación con reparaciones, restauraciones o sustitucioens permanentes de un activo por otro nuevo.</span><span class="sxs-lookup"><span data-stu-id="011b5-129">Use the **Replace asset** function in connection with repairs, refurbishment, or permanent replacement of a worn-out asset by a new asset.</span></span> <span data-ttu-id="011b5-130">Esta función se usa para reemplazar activos secundarios en una estructura de activos.</span><span class="sxs-lookup"><span data-stu-id="011b5-130">This function is used to replace child assets in an asset structure.</span></span> <span data-ttu-id="011b5-131">Para los activos principales (es decir, activos fijos que no tienen actualmente un activo principal), esta sustitución se realiza en una ubicación funcional.</span><span class="sxs-lookup"><span data-stu-id="011b5-131">For parent assets (that is, assets that don't currently have a parent asset), this replacement is done on a functional location.</span></span> <span data-ttu-id="011b5-132">Para obtener más información sobre cómo reemplazar activos principales en una ubicación funcional, consulte [Instalar activos en ubicaciones funcionales](../functional-locations/install-objects-on-functional-locations.md).</span><span class="sxs-lookup"><span data-stu-id="011b5-132">For more information about how to replace parent assets on a functional location, see [Install assets on functional locations](../functional-locations/install-objects-on-functional-locations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="011b5-133">Si hay un taller de reparación relacionado con el departamento de producción, puede crear ubicaciones funcionales como **Reparación**, **Residuos** y **Almacenamiento** para gestionar la reparación y la sustitución de activos.</span><span class="sxs-lookup"><span data-stu-id="011b5-133">If a repair shop is related to your production department, you can create functional locations such as **Repair**, **Scrap**, and **Storage** to handle the repair and replacement of assets.</span></span>

1. <span data-ttu-id="011b5-134">Seleccione **Administración de activos** \> **Común** \> **Activos** \> **Todos los activos** o **Activos activos**.</span><span class="sxs-lookup"><span data-stu-id="011b5-134">Select **Asset management** \> **Common** \> **Assets** \> **All assets** or **Active assets**.</span></span>
2. <span data-ttu-id="011b5-135">En la lista, seleccione el activo secundario que se vaya a reemplazar.</span><span class="sxs-lookup"><span data-stu-id="011b5-135">In the list, select the child asset to replace.</span></span> <span data-ttu-id="011b5-136">Si el activo tiene activos secundarios, también reemplaza dichos activos.</span><span class="sxs-lookup"><span data-stu-id="011b5-136">If the asset has child assets, you also replace those assets.</span></span>
3. <span data-ttu-id="011b5-137">Seleccione **Reemplazar activo**.</span><span class="sxs-lookup"><span data-stu-id="011b5-137">Select **Replace asset**.</span></span>

    <span data-ttu-id="011b5-138">El campo **Cambio de estructura** muestra la fecha y la hora en las que el activo seleccionado y los activos secundarios relacionados se movieron por última vez en la estructura de activos.</span><span class="sxs-lookup"><span data-stu-id="011b5-138">The **Structure change** field shows the last date and time that the selected asset and related child assets were moved in the asset structure.</span></span>

4. <span data-ttu-id="011b5-139">En la sección **Activo seleccionado**, en el campo **Ubicación funcional de destino**, seleccione la ubicación funcional a la que se moverá el activo.</span><span class="sxs-lookup"><span data-stu-id="011b5-139">In the **Selected asset** section, in the **Target functional location** field, select the functional location to move the asset to.</span></span> <span data-ttu-id="011b5-140">Por ejemplo, seleccione la ubicación **Reparación** o **Residuos**.</span><span class="sxs-lookup"><span data-stu-id="011b5-140">For example, select the **Repair** or **Scrap** location.</span></span>

    <span data-ttu-id="011b5-141">En la sección **Activo principal**, el campo **Vigencia** muestra la fecha y la hora en las cuales el activo principal y los activos secundarios relacionados se instalaron o movieron por última vez en la ubicación funcional actual.</span><span class="sxs-lookup"><span data-stu-id="011b5-141">In the **Parent asset** section, the **Effective** field shows the last date and time that the parent asset and related child assets were installed or moved on the current functional location.</span></span>

5. <span data-ttu-id="011b5-142">En la sección **Nuevo activo**, en el campo **Activo**, seleccione el activo para insertar como sustitución temporal o permanente del activo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="011b5-142">In the **New asset** section, in the **Asset** field, select the asset to insert as a temporary or permanent replacement for the selected asset.</span></span> <span data-ttu-id="011b5-143">Este activo se puede encontrar actualmente en otra ubicación funcional, como **Almacenamiento**.</span><span class="sxs-lookup"><span data-stu-id="011b5-143">This asset might currently be located on another functional location, such as **Storage**.</span></span>
7. <span data-ttu-id="011b5-144">En la sección **Vigente desde**, el campo **Vigencia** se establece automáticamente en la fecha y la hora actuales de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="011b5-144">In the **Effective from** section, the **Effective** field is set to the current date and time by default.</span></span> <span data-ttu-id="011b5-145">Sin embargo, puede seleccionar otra fecha y hora a partir de las cuales sea válido el reemplazo.</span><span class="sxs-lookup"><span data-stu-id="011b5-145">However, you can select a different date and time that the asset replacement is valid from.</span></span>
8. <span data-ttu-id="011b5-146">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="011b5-146">Select **OK**.</span></span>

## <a name="install-asset"></a><span data-ttu-id="011b5-147">Instalar activo</span><span class="sxs-lookup"><span data-stu-id="011b5-147">Install asset</span></span>

<span data-ttu-id="011b5-148">Use la función **Instalar activo** para instalar una estructura de activos en una ubicación funcional.</span><span class="sxs-lookup"><span data-stu-id="011b5-148">Use the **Install asset** function to install an asset structure on a functional location.</span></span>

> [!NOTE]
> <span data-ttu-id="011b5-149">Seleccione siempre un activo principal.</span><span class="sxs-lookup"><span data-stu-id="011b5-149">Always select a parent asset.</span></span> <span data-ttu-id="011b5-150">El activo principal y los activos secundarios relacionados se mueven a la ubicación funcional seleccionada.</span><span class="sxs-lookup"><span data-stu-id="011b5-150">The parent asset and related child assets will be moved to the selected functional location.</span></span>

1. <span data-ttu-id="011b5-151">Seleccione **Administración de activos** \> **Común** \> **Activos** \> **Todos los activos** o **Activos activos**.</span><span class="sxs-lookup"><span data-stu-id="011b5-151">Select **Asset management** \> **Common** \> **Assets** \> **All assets** or **Active assets**.</span></span>
2. <span data-ttu-id="011b5-152">En la lista, seleccione el activo principal para instalar en otra ubicación funcional.</span><span class="sxs-lookup"><span data-stu-id="011b5-152">In the list, select the parent asset to install on another functional location.</span></span>
3. <span data-ttu-id="011b5-153">Seleccione **Instalar activo**.</span><span class="sxs-lookup"><span data-stu-id="011b5-153">Select **Install asset**.</span></span>

    <span data-ttu-id="011b5-154">La sección **Atributos** muestra los atributos de activos que se configuran en el activo principal.</span><span class="sxs-lookup"><span data-stu-id="011b5-154">The **Attributes** section shows the asset attributes that are set up on the parent asset.</span></span>

4. <span data-ttu-id="011b5-155">Seleccione la nueva ubicación en el campo **Ubicación funcional**.</span><span class="sxs-lookup"><span data-stu-id="011b5-155">In the **Functional location** field, select the new location.</span></span>
5. <span data-ttu-id="011b5-156">De manera predeterminada, el campo **Vigencia** se establece automáticamente en la fecha y la hora actuales.</span><span class="sxs-lookup"><span data-stu-id="011b5-156">By default, the **Effective** field is set to the current date and time.</span></span> <span data-ttu-id="011b5-157">Sin embargo, puede seleccionar otra fecha y hora a partir de las cuales sea válida la instalación en la estructura de activos.</span><span class="sxs-lookup"><span data-stu-id="011b5-157">However, you can select a different date and time that the installation on the asset structure is valid from.</span></span>
6. <span data-ttu-id="011b5-158">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="011b5-158">Select **OK**.</span></span>
