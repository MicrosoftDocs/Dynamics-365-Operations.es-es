---
title: Integrar Dynamics 365 Supply Chain Management (Administración de activos) con Dynamics 365 Guides
description: Este tema explica cómo integrar el módulo Administración de activos en Microsoft Dynamics 365 Supply Chain Management con Dynamics 365 Guides para aprovechar las guías de realidad mixta en sus flujos de trabajo diarios de servicio y mantenimiento.
author: kamaybac
manager: tfehr
ms.date: 04/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2020-04-28
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: f9ee7f1af8e88f56589c84bfaa063ea005aa353a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436682"
---
# <a name="integrate-dynamics-365-supply-chain-management-asset-management-with-dynamics-365-guides"></a><span data-ttu-id="8c71c-103">Integrar Dynamics 365 Supply Chain Management (Administración de activos) con Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="8c71c-103">Integrate Dynamics 365 Supply Chain Management (Asset management) with Dynamics 365 Guides</span></span>

<span data-ttu-id="8c71c-104">Puede integrar el módulo **Administración de activos** en Microsoft Dynamics 365 Supply Chain Management con Dynamics 365 Guides para aprovechar las guías de realidad mixta en sus flujos de trabajo diarios de servicio y mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="8c71c-104">You can integrate the **Asset management** module in Microsoft Dynamics 365 Supply Chain Management with Dynamics 365 Guides to take advantage of mixed-reality guides in your day-to-day service and maintenance workflows.</span></span> <span data-ttu-id="8c71c-105">Si una guía está asociada con una orden de trabajo de Administración de activos, un trabajador que abra la lista de comprobación de mantenimiento de órdenes de trabajo en la aplicación móvil Supply Chain Management (Dynamics 365) verá que hay una guía disponible.</span><span class="sxs-lookup"><span data-stu-id="8c71c-105">If a guide is associated with an Asset Management work order, a worker who opens the work order's maintenance checklist in the Supply Chain Management (Dynamics 365) mobile app sees that a guide is available.</span></span> <span data-ttu-id="8c71c-106">El trabajador puede encontrar y abrir la guía en la aplicación Dynamics 365 Guides HoloLens.</span><span class="sxs-lookup"><span data-stu-id="8c71c-106">The worker can then find and open the guide in the Dynamics 365 Guides HoloLens app.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8c71c-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8c71c-107">Prerequisites</span></span>

<span data-ttu-id="8c71c-108">Antes de poder adjuntar guías a las órdenes de trabajo de gestión de activos, debe completar estos requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="8c71c-108">Before you can attach guides to Asset management work orders, you must complete these prerequisites:</span></span>

- <span data-ttu-id="8c71c-109">[Configurar Dynamics 365 Supply Chain Management](../../fin-ops-core/fin-ops/index.md), versión 10.0.9 o posterior.</span><span class="sxs-lookup"><span data-stu-id="8c71c-109">[Set up Dynamics 365 Supply Chain Management](../../fin-ops-core/fin-ops/index.md) version 10.0.9 or later.</span></span>
- <span data-ttu-id="8c71c-110">[Activar la escritura dual para las aplicaciones de Supply Chain Management](../../fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write.md).</span><span class="sxs-lookup"><span data-stu-id="8c71c-110">[Turn on dual-write for Supply Chain Management apps](../../fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write.md).</span></span>
- <span data-ttu-id="8c71c-111">[Activar transacción](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md#features-flighted-in-data-management-and-enabling-flighted-features) para la función **MRGuidesFeature**.</span><span class="sxs-lookup"><span data-stu-id="8c71c-111">[Turn on flight](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md#features-flighted-in-data-management-and-enabling-flighted-features) for the **MRGuidesFeature** feature.</span></span> <span data-ttu-id="8c71c-112">(Para entornos de producción, primero debe enviar un ticket de soporte para que su inquilino se agregue al grupo de transacciones).</span><span class="sxs-lookup"><span data-stu-id="8c71c-112">(For production environments, you must first submit a support ticket to have your tenant added to the flighting group.)</span></span>
- <span data-ttu-id="8c71c-113">[Activar las siguientes teclas de configuración](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/license-code-and-configuration-key-reference) en la página **Configuración de la licencia**:</span><span class="sxs-lookup"><span data-stu-id="8c71c-113">[Turn on the following configuration keys](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/license-code-and-configuration-key-reference) on the **License configuration** page:</span></span>

    - <span data-ttu-id="8c71c-114">Gestión de activos \> Gestión de activos de realidad mixta</span><span class="sxs-lookup"><span data-stu-id="8c71c-114">Asset management \> Asset management mixed reality</span></span>
    - <span data-ttu-id="8c71c-115">Realidad mixta \> Guía de realidad mixta</span><span class="sxs-lookup"><span data-stu-id="8c71c-115">Mixed reality \> Mixed reality guide</span></span>

- <span data-ttu-id="8c71c-116">[Configurar Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution), versión 200.0.0.96 o posterior.</span><span class="sxs-lookup"><span data-stu-id="8c71c-116">[Set up Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) version 200.0.0.96 or later.</span></span>

## <a name="use-dynamics-365-guides-with-asset-management"></a><span data-ttu-id="8c71c-117">Usar Dynamics 365 Guides con Administración de activos</span><span class="sxs-lookup"><span data-stu-id="8c71c-117">Use Dynamics 365 Guides with Asset management</span></span>

<span data-ttu-id="8c71c-118">Para asociar una guía, utiliza una línea de lista de comprobación de mantenimiento en Administración de activos.</span><span class="sxs-lookup"><span data-stu-id="8c71c-118">To associate a guide, you use a maintenance checklist line in Asset management.</span></span> <span data-ttu-id="8c71c-119">Puede crear la asociación a través de una plantilla de lista de comprobación de mantenimiento, un tipo de trabajo de mantenimiento o una orden de trabajo, porque las tres contienen líneas de lista de comprobación de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="8c71c-119">You can create the association through a maintenance checklist template, a maintenance job type, or a work order, because all three contain maintenance checklist lines.</span></span> <span data-ttu-id="8c71c-120">Puede ahorrar tiempo utilizando una plantilla, ya que una plantilla se puede asociar con todos los tipos de trabajos de mantenimiento que la utilizan.</span><span class="sxs-lookup"><span data-stu-id="8c71c-120">You can save time by using a template, because a template can be associated with all the maintenance job types that use it.</span></span> <span data-ttu-id="8c71c-121">Por ejemplo, una guía asociada con un tipo de trabajo de mantenimiento se asocia automáticamente con todas las órdenes de trabajo que especifican ese tipo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8c71c-121">For example, a guide that is associated with a maintenance job type is automatically associated with all work orders that specify that job type.</span></span> <span data-ttu-id="8c71c-122">Por otro lado, una guía que está asociada directamente con una orden de trabajo existe solo para esa orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8c71c-122">On the other hand, a guide that is associated directly with a work order exists only for that work order.</span></span>

### <a name="associate-a-guide-with-a-maintenance-checklist-template"></a><span data-ttu-id="8c71c-123">Asociar una guía con una plantilla de lista de verificación de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="8c71c-123">Associate a guide with a maintenance checklist template</span></span>

<span data-ttu-id="8c71c-124">Para asociar una guía con una plantilla de lista de verificación de mantenimiento, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="8c71c-124">To associate a guide with a maintenance checklist template, follow these steps.</span></span>

1. <span data-ttu-id="8c71c-125">Cree una guía utilizando las aplicaciones Dynamics 365 Guides PC y HoloLens.</span><span class="sxs-lookup"><span data-stu-id="8c71c-125">Create a guide by using the Dynamics 365 Guides PC and HoloLens apps.</span></span> <span data-ttu-id="8c71c-126">Los temas siguientes contienen información sobre cómo crear una guía:</span><span class="sxs-lookup"><span data-stu-id="8c71c-126">For information about how to create a guide, see the following topics:</span></span>

    - [<span data-ttu-id="8c71c-127">Usar la aplicación para PC para crear una guía</span><span class="sxs-lookup"><span data-stu-id="8c71c-127">Use the PC app to create a guide</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/pc-app-overview)
    - [<span data-ttu-id="8c71c-128">Utilizar la aplicación HoloLens para colocar los hologramas</span><span class="sxs-lookup"><span data-stu-id="8c71c-128">Use the HoloLens app to place your holograms</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-overview)

1. <span data-ttu-id="8c71c-129">En Supply Chain Management, [creae una plantilla de lista de verificación de mantenimiento](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-checklist-template).</span><span class="sxs-lookup"><span data-stu-id="8c71c-129">In Supply Chain Management, [create a maintenance checklist template](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-checklist-template).</span></span>
1. <span data-ttu-id="8c71c-130">Asocie la guía que creó con una línea de lista de verificación de mantenimiento en la nueva plantilla de lista de verificación de mantenimiento:</span><span class="sxs-lookup"><span data-stu-id="8c71c-130">Associate the guide that you created with a maintenance checklist line in the new maintenance checklist template:</span></span>

    1. <span data-ttu-id="8c71c-131">En la ficha desplegable **Líneas de control de mantenimiento**, seleccione la línea con la que desea asociar la guía.</span><span class="sxs-lookup"><span data-stu-id="8c71c-131">On the **Maintenance checklist lines** FastTab, select the line that you want to associate the guide with.</span></span>
    1. <span data-ttu-id="8c71c-132">En la ficha desplegable **Guías asociadas**, seleccione **Agregar guía**.</span><span class="sxs-lookup"><span data-stu-id="8c71c-132">On the **Associated guides** FastTab, select **Add Guide**.</span></span>

        <span data-ttu-id="8c71c-133">![Asociar una guía con una línea de lista de verificación de mantenimiento](media/am-guides-integration-add-guide.png "Asociar una guía con una línea de lista de verificación de mantenimiento")</span><span class="sxs-lookup"><span data-stu-id="8c71c-133">![Associate a guide with a maintenance checklist line](media/am-guides-integration-add-guide.png "Associate a guide with a maintenance checklist line")</span></span>

    1. <span data-ttu-id="8c71c-134">En el campo **Nombre**, seleccione una guía y luego seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8c71c-134">In the **Name** field, select a guide, and then select **Save**.</span></span>

        <span data-ttu-id="8c71c-135">![Seleccione una guía en el campo Nombre](media/am-guides-integration-select-guide.png "Seleccione una guía en el campo Nombre")</span><span class="sxs-lookup"><span data-stu-id="8c71c-135">![Select a guide in the Name field](media/am-guides-integration-select-guide.png "Select a guide in the Name field")</span></span>

1. <span data-ttu-id="8c71c-136">Asocie la plantilla de lista de verificación de mantenimiento con un tipo de trabajo:</span><span class="sxs-lookup"><span data-stu-id="8c71c-136">Associate the maintenance checklist template with a job type:</span></span>

    1. <span data-ttu-id="8c71c-137">[Cree un tipo de trabajo de mantenimiento](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-job-type) o seleccione un tipo de trabajo de mantenimiento existente.</span><span class="sxs-lookup"><span data-stu-id="8c71c-137">[Create a maintenance job type](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-job-type), or select an existing maintenance job type.</span></span>
    1. <span data-ttu-id="8c71c-138">En el Panel Acciones, seleccione **Tipos de trabajo de mantenimiento predeterminados**.</span><span class="sxs-lookup"><span data-stu-id="8c71c-138">On the Action Pane, select **Maintenance job type defaults**.</span></span>

        <span data-ttu-id="8c71c-139">![Botón de tipos predeterminados de trabajo de mantenimiento](media/am-guides-integration-job-defaults.png "Botón de tipos predeterminados de trabajo de mantenimiento")</span><span class="sxs-lookup"><span data-stu-id="8c71c-139">![Maintenance job type defaults button](media/am-guides-integration-job-defaults.png "Maintenance job type defaults button")</span></span>

    1. <span data-ttu-id="8c71c-140">Cree una línea y luego seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8c71c-140">Create a line, and then select **Save**.</span></span>

        <span data-ttu-id="8c71c-141">![Crear una línea](media/am-guides-integration-add-line.png "Crear una línea")</span><span class="sxs-lookup"><span data-stu-id="8c71c-141">![Create a line](media/am-guides-integration-add-line.png "Create a line")</span></span>

    1. <span data-ttu-id="8c71c-142">En el panel Acciones, seleccione **Lista de comprobación de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="8c71c-142">On the Action Pane, select **Maintenance checklist**.</span></span>

        <span data-ttu-id="8c71c-143">![Botón de lista de comprobación de mantenimiento](media/am-guides-integration-maintenance-checklist.png "Botón de lista de comprobación de mantenimiento")</span><span class="sxs-lookup"><span data-stu-id="8c71c-143">![Maintenance checklist button](media/am-guides-integration-maintenance-checklist.png "Maintenance checklist button")</span></span>

    1. <span data-ttu-id="8c71c-144">En la ficha desplegable **Líneas de control de mantenimiento**, agregue una línea y luego cambie el valor del campo **Tipo** a **Plantilla**.</span><span class="sxs-lookup"><span data-stu-id="8c71c-144">On the **Maintenance checklist lines** FastTab, add a line, and then change the value of the **Type** field to **Template**.</span></span>

        <span data-ttu-id="8c71c-145">![Cambiar el valor de Tipo](media/am-guides-integration-checklist-lines.png "Cambiar el valor de Tipo")</span><span class="sxs-lookup"><span data-stu-id="8c71c-145">![Change the Type value](media/am-guides-integration-checklist-lines.png "Change the Type value")</span></span>

    1. <span data-ttu-id="8c71c-146">En la ficha desplegable **Detalles de línea**, en el campo **Modelo**,seleccione la plantilla con la que asoció la guía y luego seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8c71c-146">On the **Line details** FastTab, in the **Template** field, select the template that you associated the guide with, and then select **Save**.</span></span>

        <span data-ttu-id="8c71c-147">![Seleccione la plantilla](media/am-guides-integration-checklist-line-details.png "Seleccionar la plantilla")</span><span class="sxs-lookup"><span data-stu-id="8c71c-147">![Select the template](media/am-guides-integration-checklist-line-details.png "Select the template")</span></span>

1. <span data-ttu-id="8c71c-148">[Cree una orden de trabajo](work-orders/manually-created-workorders.md#create-work-order) y luego seleccione el tipo de trabajo de mantenimiento que utiliza la plantilla de la lista de verificación de mantenimiento con la que asoció la guía.</span><span class="sxs-lookup"><span data-stu-id="8c71c-148">[Create a work order](work-orders/manually-created-workorders.md#create-work-order), and then select the maintenance job type that uses the maintenance checklist template that you associated the guide with.</span></span> <span data-ttu-id="8c71c-149">La guía se asocia automáticamente con la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8c71c-149">The guide is automatically associated with the work order.</span></span>

    <span data-ttu-id="8c71c-150">![Seleccionar un tipo de trabajo de mantenimiento](media/am-guides-integration-create-work-order.png "Seleccionar un tipo de trabajo de mantenimiento")</span><span class="sxs-lookup"><span data-stu-id="8c71c-150">![Select a maintenance job type](media/am-guides-integration-create-work-order.png "Select a maintenance job type")</span></span>

1. <span data-ttu-id="8c71c-151">Vea la guía asociada a la orden de trabajo y trabajadores:</span><span class="sxs-lookup"><span data-stu-id="8c71c-151">View the guide that is associated with the work order and workers:</span></span>

    1. <span data-ttu-id="8c71c-152">Abra el [Espacio de trabajo móvil de gestión de activos](asset-management-mobile-workspace.md) para acceder a la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8c71c-152">Open the [Asset management mobile workspace](asset-management-mobile-workspace.md) to access the work order.</span></span>
    1. <span data-ttu-id="8c71c-153">[Abra la lista de verificación de mantenimiento](asset-management-mobile-workspace.md#view-maintenance-checklist-on-a-work-order-job) para la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8c71c-153">[Open the maintenance checklist](asset-management-mobile-workspace.md#view-maintenance-checklist-on-a-work-order-job) for the work order.</span></span>
    1. <span data-ttu-id="8c71c-154">Seleccione una línea de lista de verificación para ver la guía asociada.</span><span class="sxs-lookup"><span data-stu-id="8c71c-154">Select a checklist line to see the associated guide.</span></span>

        <span data-ttu-id="8c71c-155">![Guía asociada con una línea de lista de verificación](media/am-guides-integration-show-guide.png "Guía asociada con una línea de lista de verificación")</span><span class="sxs-lookup"><span data-stu-id="8c71c-155">![Guide associated with a checklist line](media/am-guides-integration-show-guide.png "Guide associated with a checklist line")</span></span>

    1. <span data-ttu-id="8c71c-156">Abra la guía en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="8c71c-156">Open the guide on HoloLens.</span></span>

        <span data-ttu-id="8c71c-157">![Abrir la guía en HoloLens](media/am-guides-integration-hololens-select.png "Abrir la guía en HoloLens")</span><span class="sxs-lookup"><span data-stu-id="8c71c-157">![Open the guide on HoloLens](media/am-guides-integration-hololens-select.png "Open the guide on HoloLens")</span></span>

> [!NOTE]
> <span data-ttu-id="8c71c-158">También puede asociar una guía directamente en la lista de verificación de mantenimiento de una orden de trabajo o un tipo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8c71c-158">You can also associate a guide directly in the maintenance checklist of a work order or a job type.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8c71c-159">Existe un problema conocido en el que, cuando se asocia una plantilla de lista de verificación de mantenimiento con un tipo de trabajo de mantenimiento predeterminado, la guía que está vinculada a la plantilla no aparece en la ficha desplegable **Guías asociadas** de la página **Tipo de trabajo de mantenimiento predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="8c71c-159">There is a known issue where, when you associate a maintenance checklist template with a default maintenance job type, the guide that is linked to the template doesn't appear on the **Associated guides** FastTab of the **Maintenance job type defaults** page.</span></span> <span data-ttu-id="8c71c-160">Sin embargo, la guía aparecerá después de que ese tipo de trabajo se aplique a una orden de trabajo en la ficha desplegable **Guías asociadas**.</span><span class="sxs-lookup"><span data-stu-id="8c71c-160">However, the guide will appear after that job type is applied to a work order on the **Associated guides** FastTab.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c71c-161">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8c71c-161">See also</span></span>

- [<span data-ttu-id="8c71c-162">Visión general de doble escritura</span><span class="sxs-lookup"><span data-stu-id="8c71c-162">Dual-write overview</span></span>](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview.md)
- [<span data-ttu-id="8c71c-163">Visión general de la administración de activos</span><span class="sxs-lookup"><span data-stu-id="8c71c-163">Asset management overview</span></span>](index.md)
