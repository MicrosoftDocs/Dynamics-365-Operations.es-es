---
title: Activos de varios niveles
description: Este tema explica cómo crear y eliminar activos de varios niveles.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fd4da57c3849095909226db53c23b3c25301acdc
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021331"
---
# <a name="multi-level-assets"></a><span data-ttu-id="51594-103">Activos de varios niveles</span><span class="sxs-lookup"><span data-stu-id="51594-103">Multi-level assets</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="51594-104">Este tema explica cómo crear y eliminar activos de varios niveles.</span><span class="sxs-lookup"><span data-stu-id="51594-104">This topic explains how to create and delete multi-level assets.</span></span> <span data-ttu-id="51594-105">Puede crear activos y subactivos relacionados en una estructura en árbol jerárquica.</span><span class="sxs-lookup"><span data-stu-id="51594-105">You can create assets and related sub-assets in a hierarchical tree structure.</span></span> <span data-ttu-id="51594-106">De esta manera, puede mostrar las relaciones y dependencias entre los activos.</span><span class="sxs-lookup"><span data-stu-id="51594-106">In this way, you can show relations and dependencies among assets.</span></span> <span data-ttu-id="51594-107">Los trabajos de mantenimiento pueden estar relacionadas con todos los niveles de la estructura de árbol.</span><span class="sxs-lookup"><span data-stu-id="51594-107">Maintenance jobs can be related to all levels of the tree structure.</span></span> <span data-ttu-id="51594-108">También se pueden crear estadísticas para un nivel individual o como suma de todos los niveles de subactivos.</span><span class="sxs-lookup"><span data-stu-id="51594-108">Statistics can also be created for an individual level or as a sum of all sub-asset levels.</span></span>

<span data-ttu-id="51594-109">En la página de lista **Todos los activos** (**Administración de activos** \> **Común** \> **Activos** \> **Todos los activos**), la columna **Activo** muestra los activos por orden jerárquico.</span><span class="sxs-lookup"><span data-stu-id="51594-109">On the **All Assets** list page (**Asset management** \> **Common** \> **Assets** \> **All assets**), the **Asset** column lists assets in hierarchical order.</span></span> <span data-ttu-id="51594-110">La columna **Principal** muestra el elemento principal relacionado.</span><span class="sxs-lookup"><span data-stu-id="51594-110">The **Parent** column shows the related parent.</span></span> <span data-ttu-id="51594-111">Además, si los activos y los subactivos ya se han creado, la sección **Árbol de activos** en el panel **Información relacionada** se muestra los activos en una estructura de árbol.</span><span class="sxs-lookup"><span data-stu-id="51594-111">Additionally, if assets and sub-assets have already been created, the **Asset tree** section in the **Related information** pane shows the assets in a tree structure.</span></span>

<span data-ttu-id="51594-112">Para obtener información sobre cómo crear un activo, consulte [Crear un activo](../objects/create-an-object.md).</span><span class="sxs-lookup"><span data-stu-id="51594-112">For information about how to create an asset, see [Create an asset](../objects/create-an-object.md).</span></span> <span data-ttu-id="51594-113">Para crear un subactivo, seleccione el activo principal en el campo **Principal** del FastTab **General**.</span><span class="sxs-lookup"><span data-stu-id="51594-113">To create a sub-asset, select the parent asset in the **Parent** field on the **General** FastTab.</span></span>

## <a name="copy-an-asset-or-asset-structure"></a><span data-ttu-id="51594-114">Copiar un activo o una estructura de activos</span><span class="sxs-lookup"><span data-stu-id="51594-114">Copy an asset or asset structure</span></span>

<span data-ttu-id="51594-115">Si su empresa tiene varias estructuras de activos similares, puede usar la función Copiar de Administración de activos para crearlas rápidamente.</span><span class="sxs-lookup"><span data-stu-id="51594-115">If your company has several similar asset structures, you can use the Copy function in Asset Management to quickly create them.</span></span>

1. <span data-ttu-id="51594-116">Seleccione **Administración de activos** \> **Común** \> **Activos** \> **Todos los activos**.</span><span class="sxs-lookup"><span data-stu-id="51594-116">Select **Asset management** \> **Common** \> **Assets** \> **All assets**.</span></span>
2. <span data-ttu-id="51594-117">En la página de lista **Todos los activos**, seleccione el activo para copiar.</span><span class="sxs-lookup"><span data-stu-id="51594-117">On the **All assets** list page, select the asset to copy.</span></span> <span data-ttu-id="51594-118">Por ejemplo, si desea copiar la estructura de activos completa, incluidos los subactivos, seleccione un activo principal.</span><span class="sxs-lookup"><span data-stu-id="51594-118">For example, if you want to copy the whole asset structure, including sub-assets, select a parent asset.</span></span>
3. <span data-ttu-id="51594-119">Seleccione **Copiar activo**.</span><span class="sxs-lookup"><span data-stu-id="51594-119">Select **Copy asset**.</span></span> <span data-ttu-id="51594-120">En la sección **Copiar de**, el campo **Activo** está configurado con el activo que seleccionó en la página de lista.</span><span class="sxs-lookup"><span data-stu-id="51594-120">In the **Copy from** section, the **Asset** field is set to the asset that you selected on the list page.</span></span>
4. <span data-ttu-id="51594-121">En la sección **Copiar a**, en el campo **Activo**, escriba el nombre del nuevo activo.</span><span class="sxs-lookup"><span data-stu-id="51594-121">In the **Copy to** section, in the **Asset** field, enter the name of the new asset.</span></span>
5. <span data-ttu-id="51594-122">Si el activo que está creando si es parte de una estructura de activos existente, en la sección **Activo principal**, en el campo **Activo**, seleccione un identificador principal.</span><span class="sxs-lookup"><span data-stu-id="51594-122">If the asset that you're creating should be part of an existing asset structure, in the **Parent asset** section, in the **Asset** field, select a parent ID.</span></span>
6. <span data-ttu-id="51594-123">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="51594-123">Select **OK**.</span></span> <span data-ttu-id="51594-124">La nueva estructura de activos se muestra en la página de lista **Todos los activos**.</span><span class="sxs-lookup"><span data-stu-id="51594-124">The new asset structure is shown on the **All assets** list page.</span></span> <span data-ttu-id="51594-125">Todos los atributos de activo, planes de mantenimiento y rondas de mantenimiento relacionadas con el activo que ha copiado se transfieren al nuevo activo o estructura de activos.</span><span class="sxs-lookup"><span data-stu-id="51594-125">All asset attributes, maintenance plans, and maintenance rounds that are related to the asset that you copied are transferred to the new asset or asset structure.</span></span>

<span data-ttu-id="51594-126">Al copiar una estructura de activos, los subactivos de la nueva estructura tienen el mismo nombre que los subactivos que ha copiado.</span><span class="sxs-lookup"><span data-stu-id="51594-126">When you copy an asset structure, the sub-assets in the new structure have the same name as the sub-assets that you copied.</span></span> <span data-ttu-id="51594-127">Una vez que el procedimiento de copia se complete, puede cambiar fácilmente el nombre y otros parámetros del activo.</span><span class="sxs-lookup"><span data-stu-id="51594-127">After the copy procedure is completed, you can easily change the name and other settings for an asset.</span></span> <span data-ttu-id="51594-128">Seleccione el activo en la página de lista **Todos los activos** y seleccione el botón **Editar**.</span><span class="sxs-lookup"><span data-stu-id="51594-128">Select the asset on the **All assets** list page, and then select the **Edit** button.</span></span>

> [!NOTE]
> <span data-ttu-id="51594-129">Al copiar un activo o una estructura de activos, se restablece el estado de ciclo de vida de los nuevos activos en el estado definido como estado de ciclo de vida inicial de los activos.</span><span class="sxs-lookup"><span data-stu-id="51594-129">When you copy an asset or asset structure, the lifecycle state of the new assets is reset to whatever state you defined as the initial lifecycle state for assets.</span></span> <span data-ttu-id="51594-130">La ubicación funcional se restablece a la ubicación funcional predeterminada.</span><span class="sxs-lookup"><span data-stu-id="51594-130">The functional location is reset to the default functional location.</span></span>

## <a name="delete-an-asset-or-asset-structure"></a><span data-ttu-id="51594-131">Eliminar un activo o una estructura de activos</span><span class="sxs-lookup"><span data-stu-id="51594-131">Delete an asset or asset structure</span></span>

<span data-ttu-id="51594-132">Si un activo tiene subactivos relacionados, puede eliminarlo solo si no hay solicitudes de mantenimiento, trabajos de órdenes de trabajo, registros de errores o evaluaciones de estado registrados en ninguno de los activos.</span><span class="sxs-lookup"><span data-stu-id="51594-132">If an asset has related sub-assets, you can delete it only if no maintenance requests, work order jobs, fault registrations, or condition assessments are registered on any of the assets.</span></span>

1. <span data-ttu-id="51594-133">En la página de lista **Todos los activos**, seleccione el activo para eliminar.</span><span class="sxs-lookup"><span data-stu-id="51594-133">On the **All assets** list page, select the asset to delete.</span></span>
2. <span data-ttu-id="51594-134">Seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="51594-134">Select **Delete**.</span></span>

> [!NOTE]
> <span data-ttu-id="51594-135">Si no puede eliminar un activo mediante este procedimiento, otro modo de gestionar la eliminación es configurar un estado de ciclo de vida del activo con este propósito.</span><span class="sxs-lookup"><span data-stu-id="51594-135">If you can't delete an asset by using this procedure, another way to handle deletion is to set up an asset lifecycle state for this purpose.</span></span> <span data-ttu-id="51594-136">Por ejemplo, puede configurar un estado de ciclo de vida **Desechado** o **Eliminado** en la página **Estados del ciclo de vida de activo**.</span><span class="sxs-lookup"><span data-stu-id="51594-136">For example, you can set up a **Scrapped** or **Deleted** lifecycle state on the **Asset lifecycle states** page.</span></span>
