---
title: Facturar por mantenimiento de activos del cliente
description: Este tema explica cómo crear, procesar y facturar el trabajo de mantenimiento que se realiza sobre los activos que poseen sus clientes.
author: johanhoffmann
manager: tfehr
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderProjCostInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 643e59f082949ed51ab61d79648a98b83a7f0b03
ms.sourcegitcommit: 1e615288db245f83c5d5e0cd45315400f8946beb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2021
ms.locfileid: "5131850"
---
# <a name="bill-for-maintenance-on-customer-owned-assets"></a><span data-ttu-id="c16b3-103">Facturar por mantenimiento de activos del cliente</span><span class="sxs-lookup"><span data-stu-id="c16b3-103">Bill for maintenance on customer-owned assets</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c16b3-104">La característica *Facturación de órdenes de trabajo* le permite crear, procesar y facturar el trabajo de mantenimiento que se realiza en los activos que poseen sus clientes.</span><span class="sxs-lookup"><span data-stu-id="c16b3-104">The *Work order billing* feature lets you create, process, and bill maintenance work that is done on assets that your customers own.</span></span> <span data-ttu-id="c16b3-105">Esta característica le permite realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="c16b3-105">This feature lets you perform the following tasks:</span></span>

- <span data-ttu-id="c16b3-106">Conectar a los clientes con los activos que poseen.</span><span class="sxs-lookup"><span data-stu-id="c16b3-106">Connect customers to the assets that they own.</span></span>
- <span data-ttu-id="c16b3-107">Seleccionar un cliente y ver los activos que posee cuando crea una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c16b3-107">Select a customer and view the assets that customer owns when you create a work order.</span></span>
- <span data-ttu-id="c16b3-108">Configurar un proyecto principal para cada cliente.</span><span class="sxs-lookup"><span data-stu-id="c16b3-108">Set up a parent project for each customer.</span></span>
- <span data-ttu-id="c16b3-109">Registrar horas, artículos, gastos y tarifas en la orden de trabajo y crear una propuesta de factura para el cliente más tarde.</span><span class="sxs-lookup"><span data-stu-id="c16b3-109">Register hours, items, expenses, and fees against the work order, and then create an invoice proposal for the customer later.</span></span>

<span data-ttu-id="c16b3-110">Además, la función proporciona la siguiente funcionalidad:</span><span class="sxs-lookup"><span data-stu-id="c16b3-110">In addition, the feature provides the following functionality:</span></span>

- <span data-ttu-id="c16b3-111">El contrato de proyecto del proyecto principal de un cliente se copia automáticamente en el proyecto de orden de trabajo relevante.</span><span class="sxs-lookup"><span data-stu-id="c16b3-111">The project contract from a customer's parent project is automatically copied to the relevant work order project.</span></span>
- <span data-ttu-id="c16b3-112">La administración de activos ahora puede utilizar el tipo de transacción de proyecto *tarifa* tanto en las previsiones de órdenes de trabajo como en los diarios de órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c16b3-112">Asset management can now use the *fee* project transaction type on both work order forecasts and work order journals.</span></span>

## <a name="turn-on-the-customer-billing-feature"></a><span data-ttu-id="c16b3-113">Activar la característica de facturación al cliente</span><span class="sxs-lookup"><span data-stu-id="c16b3-113">Turn on the customer billing feature</span></span>

<span data-ttu-id="c16b3-114">Antes de poder usar esta característica debe estar activada en su sistema.</span><span class="sxs-lookup"><span data-stu-id="c16b3-114">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="c16b3-115">Los administradores pueden usar la configuración de [gestión de funciones](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla.</span><span class="sxs-lookup"><span data-stu-id="c16b3-115">Admins can use the [feature management](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="c16b3-116">En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="c16b3-116">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="c16b3-117">**Módulo:** *Gestión y contabilidad de proyectos*</span><span class="sxs-lookup"><span data-stu-id="c16b3-117">**Module:** *Project management and accounting*</span></span>
- <span data-ttu-id="c16b3-118">**Nombre de la característica:** *Facturación de órdenes de trabajo*</span><span class="sxs-lookup"><span data-stu-id="c16b3-118">**Feature name:** *Work order billing*</span></span>

## <a name="example-scenario"></a><span data-ttu-id="c16b3-119">Supuesto de ejemplo</span><span class="sxs-lookup"><span data-stu-id="c16b3-119">Example scenario</span></span>

<span data-ttu-id="c16b3-120">Para aprender cómo funciona esta característica, trabaje con el siguiente escenario de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c16b3-120">To learn how this feature works, work through the following example scenario.</span></span>

<span data-ttu-id="c16b3-121">Para trabajar en este escenario mediante el uso de los registros y valores de muestra que se especifican aquí, debe estar en un sistema donde estén instalados los [datos de demostración](../../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) estándar.</span><span class="sxs-lookup"><span data-stu-id="c16b3-121">To work through this scenario by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="c16b3-122">Debe seleccionar la entidad legal **USMF** antes de comenzar.</span><span class="sxs-lookup"><span data-stu-id="c16b3-122">You must select the **USMF** legal entity before you begin.</span></span>

<span data-ttu-id="c16b3-123">También puede usar este escenario como guía para usar la característica cuando trabaje en un sistema de producción.</span><span class="sxs-lookup"><span data-stu-id="c16b3-123">You can also use this scenario as guidance for using the feature when you work on a production system.</span></span> <span data-ttu-id="c16b3-124">Sin embargo, en ese caso, debe sustituir sus propios valores y puede que le falten algunos tipos de registros necesarios que proporcionan los datos de demostración estándar.</span><span class="sxs-lookup"><span data-stu-id="c16b3-124">However, in that case, you must substitute your own values, and you might be missing some types of required records that the standard demo data provides.</span></span>

### <a name="step-1-create-a-new-project-contract-for-the-customer"></a><span data-ttu-id="c16b3-125">Paso 1: crear un nuevo contrato de proyecto para el cliente</span><span class="sxs-lookup"><span data-stu-id="c16b3-125">Step 1: Create a new project contract for the customer</span></span>

1. <span data-ttu-id="c16b3-126">Vaya a **Gestión de proyectos y contabilidad \> Proyectos \> Contratos de proyecto**.</span><span class="sxs-lookup"><span data-stu-id="c16b3-126">Go to **Project management and accounting \> Projects \> Project contracts**.</span></span>
1. <span data-ttu-id="c16b3-127">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="c16b3-127">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="c16b3-128">En el cuadro de diálogo **Nuevo contrato de proyecto**, establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="c16b3-128">In the **New project contract** dialog box, set the following values:</span></span>

    - <span data-ttu-id="c16b3-129">**Nombre:** *Pelican Wholesales*</span><span class="sxs-lookup"><span data-stu-id="c16b3-129">**Name:** *Pelican Wholesales*</span></span>
    - <span data-ttu-id="c16b3-130">**Tipo de financiación:** *Cliente*</span><span class="sxs-lookup"><span data-stu-id="c16b3-130">**Funding type:** *Customer*</span></span>
    - <span data-ttu-id="c16b3-131">**Fuente de financiación:** *US-013* (*Pelican Wholesales*)</span><span class="sxs-lookup"><span data-stu-id="c16b3-131">**Funding source:** *US-013* (*Pelican Wholesales*)</span></span>

1. <span data-ttu-id="c16b3-132">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c16b3-132">Select **OK**.</span></span>

### <a name="step-2-create-a-new-parent-project-for-the-customer"></a><span data-ttu-id="c16b3-133">Paso 2: crear un nuevo proyecto principal para el cliente</span><span class="sxs-lookup"><span data-stu-id="c16b3-133">Step 2: Create a new parent project for the customer</span></span>

<span data-ttu-id="c16b3-134">El proyecto principal que cree aquí se utilizará cuando se creen las órdenes de trabajo para el cliente.</span><span class="sxs-lookup"><span data-stu-id="c16b3-134">The parent project that you create here will be used when work orders for the customer are created.</span></span>

1. <span data-ttu-id="c16b3-135">Vaya a **Gestión de proyectos y contabilidad \> Proyectos \> Todos los proyectos**.</span><span class="sxs-lookup"><span data-stu-id="c16b3-135">Go to **Project management and accounting \> Projects \> All projects**.</span></span>
1. <span data-ttu-id="c16b3-136">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="c16b3-136">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="c16b3-137">En el cuadro de diálogo **Nuevo proyecto**, establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="c16b3-137">In the **New project** dialog box, set the following values:</span></span>

    - <span data-ttu-id="c16b3-138">**Tipo de proyecto:** *Tiempo y material*</span><span class="sxs-lookup"><span data-stu-id="c16b3-138">**Project type:** *Time and material*</span></span>
    - <span data-ttu-id="c16b3-139">**Nombre del proyecto:** *Órdenes de trabajo de Pelican Wholesales*</span><span class="sxs-lookup"><span data-stu-id="c16b3-139">**Project name:** *Pelican Wholesales work orders*</span></span>
    - <span data-ttu-id="c16b3-140">**Grupo de proyecto:** *TM*</span><span class="sxs-lookup"><span data-stu-id="c16b3-140">**Project group:** *TM*</span></span>
    - <span data-ttu-id="c16b3-141">**Id. del contrato del proyecto:** *Pelican Wholesales* (el contrato que creaste antes)</span><span class="sxs-lookup"><span data-stu-id="c16b3-141">**Project contract ID:** *Pelican Wholesales* (the contract that you created earlier)</span></span>
    - <span data-ttu-id="c16b3-142">**Fecha de inicio:** seleccione la fecha de hoy.</span><span class="sxs-lookup"><span data-stu-id="c16b3-142">**Start date:** Select today's date.</span></span>

1. <span data-ttu-id="c16b3-143">Seleccione **Crear proyecto**.</span><span class="sxs-lookup"><span data-stu-id="c16b3-143">Select **Create project**.</span></span>
1. <span data-ttu-id="c16b3-144">El nuevo proyecto está abierto.</span><span class="sxs-lookup"><span data-stu-id="c16b3-144">The new project is opened.</span></span> <span data-ttu-id="c16b3-145">Anote el valor **Id. del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="c16b3-145">Make a note of the **Project ID** value.</span></span> <span data-ttu-id="c16b3-146">Tendrá que introducirlo más tarde.</span><span class="sxs-lookup"><span data-stu-id="c16b3-146">You will have to enter it later.</span></span>

### <a name="step-3-create-a-new-work-order-type-in-asset-management"></a><span data-ttu-id="c16b3-147">Paso 3: crear un nuevo tipo de orden de trabajo en la Administración de activos</span><span class="sxs-lookup"><span data-stu-id="c16b3-147">Step 3: Create a new work order type in Asset management</span></span>

1. <span data-ttu-id="c16b3-148">Vaya a **Administración de activos \> Configuración \> Orden de trabajo \> Tipos de órdenes de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="c16b3-148">Go to **Asset management \> Setup \> Work order \> Work order types**.</span></span>
1. <span data-ttu-id="c16b3-149">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="c16b3-149">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="c16b3-150">Se agrega un nuevo registro a la lista.</span><span class="sxs-lookup"><span data-stu-id="c16b3-150">A new record is added to the list.</span></span> <span data-ttu-id="c16b3-151">Establezca los siguientes valores para este registro:</span><span class="sxs-lookup"><span data-stu-id="c16b3-151">Set the following values for it:</span></span>

    - <span data-ttu-id="c16b3-152">**Tipo de orden de trabajo:** *Servicio*</span><span class="sxs-lookup"><span data-stu-id="c16b3-152">**Work order type:** *Service*</span></span>
    - <span data-ttu-id="c16b3-153">**Nombre:** *Órdenes de trabajo de servicios*</span><span class="sxs-lookup"><span data-stu-id="c16b3-153">**Name:** *Service work orders*</span></span>
    - <span data-ttu-id="c16b3-154">**Estado del ciclo de vida de la orden de trabajo:** *Estándar*</span><span class="sxs-lookup"><span data-stu-id="c16b3-154">**Work order lifecycle state:** *Standard*</span></span>

### <a name="step-4-link-the-customer-account-to-the-parent-project"></a><span data-ttu-id="c16b3-155">Paso 4: vincular la cuenta del cliente al proyecto principal</span><span class="sxs-lookup"><span data-stu-id="c16b3-155">Step 4: Link the customer account to the parent project</span></span>

<span data-ttu-id="c16b3-156">Ahora debe vincular la cuenta del cliente al proyecto principal en la configuración del proyecto en Administración de activos.</span><span class="sxs-lookup"><span data-stu-id="c16b3-156">You must now link the customer account to the parent project in the project setup in Asset management.</span></span>

1. <span data-ttu-id="c16b3-157">Vaya a **Administración de activos \> Configuración \> Órdenes de trabajo \> Configuración del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="c16b3-157">Go to **Asset management \> Setup \> Work orders \> Project setup**.</span></span>
1. <span data-ttu-id="c16b3-158">En la pestaña **Proyecto principal**, seleccione **Agregar** para agregar una línea.</span><span class="sxs-lookup"><span data-stu-id="c16b3-158">On the **Parent project** tab, select **Add** to add a line.</span></span>
1. <span data-ttu-id="c16b3-159">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="c16b3-159">On the new line, set the following values:</span></span>

    - <span data-ttu-id="c16b3-160">**Cuenta de cliente:** *US-013* (*Pelican Wholesales*)</span><span class="sxs-lookup"><span data-stu-id="c16b3-160">**Customer account:** *US-013* (*Pelican Wholesales*)</span></span>
    - <span data-ttu-id="c16b3-161">**Id. del proyecto:** introduzca el Id. del proyecto que anotó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c16b3-161">**Project ID:** Enter the project ID that you made a note of earlier.</span></span>

### <a name="step-5-link-the-project-group-and-type-to-the-work-order-project"></a><span data-ttu-id="c16b3-162">Paso 5: vincular el grupo y tipo del proyecto al proyecto de la orden de trabajo</span><span class="sxs-lookup"><span data-stu-id="c16b3-162">Step 5: Link the project group and type to the work order project</span></span>

<span data-ttu-id="c16b3-163">Todavía debería estar en la página de **Configuración del proyecto** (**Administración de activos \> Configuración \> Órdenes de trabajo \> Configuración del proyecto**).</span><span class="sxs-lookup"><span data-stu-id="c16b3-163">You should still be on the **Project setup** page (**Asset management \> Setup \> Work orders \> Project setup**).</span></span>

1. <span data-ttu-id="c16b3-164">En la pestaña **Grupo del proyecto**, seleccione **Agregar** para agregar una línea.</span><span class="sxs-lookup"><span data-stu-id="c16b3-164">On the **Project group** tab, select **Add** to add a line.</span></span>
1. <span data-ttu-id="c16b3-165">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="c16b3-165">On the new line, set the following values:</span></span>

    - <span data-ttu-id="c16b3-166">**Tipo de orden de trabajo:** *Servicio* (el tipo de orden de trabajo que creó anteriormente)</span><span class="sxs-lookup"><span data-stu-id="c16b3-166">**Work order type:** *Service* (the work order type that you created earlier)</span></span>
    - <span data-ttu-id="c16b3-167">**Grupo de proyecto:** *TM*</span><span class="sxs-lookup"><span data-stu-id="c16b3-167">**Project group:** *TM*</span></span>

> [!NOTE]
> <span data-ttu-id="c16b3-168">El contrato del proyecto en el proyecto de la orden de trabajo siempre se hereda del proyecto principal.</span><span class="sxs-lookup"><span data-stu-id="c16b3-168">The project contract on the work order project is always inherited from the parent project.</span></span>

### <a name="step-6-link-an-asset-to-the-customer-id"></a><span data-ttu-id="c16b3-169">Paso 6: vincular un activo al Id. de cliente</span><span class="sxs-lookup"><span data-stu-id="c16b3-169">Step 6: Link an asset to the customer ID</span></span>

1. <span data-ttu-id="c16b3-170">Vaya a **Administración de activos \> Activos \> Activos activos**.</span><span class="sxs-lookup"><span data-stu-id="c16b3-170">Go to **Asset management \> Assets \> Active assets**.</span></span>
1. <span data-ttu-id="c16b3-171">En el campo **Filtrar**, introduzca *VE-102* y seleccione filtrar por **Activo**.</span><span class="sxs-lookup"><span data-stu-id="c16b3-171">In the **Filter** field, enter *VE-102*, and select to filter by **Asset**.</span></span>
1. <span data-ttu-id="c16b3-172">Seleccione el activo para abrir su configuración.</span><span class="sxs-lookup"><span data-stu-id="c16b3-172">Select the asset to open its settings.</span></span>
1. <span data-ttu-id="c16b3-173">En la ficha desplegable **Cliente**, configure el campo **Cuenta de cliente** a *US-013* (*Pelican Wholesales*).</span><span class="sxs-lookup"><span data-stu-id="c16b3-173">On the **Customer** FastTab, set the **Customer account** field to *US-013* (*Pelican Wholesales*).</span></span>

    <span data-ttu-id="c16b3-174">El campo **Nombre** se actualiza automáticamente a *Pelican Wholesales*.</span><span class="sxs-lookup"><span data-stu-id="c16b3-174">The **Name** field is automatically updated to *Pelican Wholesales*.</span></span>

### <a name="step-7-create-a-new-work-order-on-the-asset"></a><span data-ttu-id="c16b3-175">Paso 7: crear una nueva orden de trabajo sobre el activo</span><span class="sxs-lookup"><span data-stu-id="c16b3-175">Step 7: Create a new work order on the asset</span></span>

1. <span data-ttu-id="c16b3-176">Vaya a **Administración de activos \> Órdenes de trabajo \> Órdenes de trabajo activas**.</span><span class="sxs-lookup"><span data-stu-id="c16b3-176">Go to **Asset management \> Work orders \> Active work orders**.</span></span>
1. <span data-ttu-id="c16b3-177">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="c16b3-177">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="c16b3-178">En el cuadro de diálogo **Crear orden de trabajo**, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="c16b3-178">In the **Create work order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="c16b3-179">**Tipo de orden de trabajo:** *Servicio*</span><span class="sxs-lookup"><span data-stu-id="c16b3-179">**Work order type:** *Service*</span></span>
    - <span data-ttu-id="c16b3-180">**Descripción:** *Reparar camión*</span><span class="sxs-lookup"><span data-stu-id="c16b3-180">**Description:** *Repair Truck*</span></span>
    - <span data-ttu-id="c16b3-181">**Cuenta de cliente:** *US-013* (*Pelican Wholesales*)</span><span class="sxs-lookup"><span data-stu-id="c16b3-181">**Customer account:** *US-013* (*Pelican Wholesales*)</span></span>
    - <span data-ttu-id="c16b3-182">**Activo:** *VE-102*</span><span class="sxs-lookup"><span data-stu-id="c16b3-182">**Asset:** *VE-102*</span></span>

        > [!NOTE]
        > <span data-ttu-id="c16b3-183">La búsqueda muestra solo los activos que están vinculados a la cuenta de cliente seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c16b3-183">The lookup shows only assets that are linked to the selected customer account.</span></span>

    - <span data-ttu-id="c16b3-184">**Tipo de trabajo de mantenimiento:** *Reparación*</span><span class="sxs-lookup"><span data-stu-id="c16b3-184">**Maintenance job type:** *Repair*</span></span>
    - <span data-ttu-id="c16b3-185">**Comercio:** *Mecánico*</span><span class="sxs-lookup"><span data-stu-id="c16b3-185">**Trade:** *Mechanic*</span></span>
    - <span data-ttu-id="c16b3-186">**Nivel de servicio:** *4*</span><span class="sxs-lookup"><span data-stu-id="c16b3-186">**Service level:** *4*</span></span>

1. <span data-ttu-id="c16b3-187">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c16b3-187">Select **OK**.</span></span>

### <a name="step-8-review-the-work-order-and-start-to-work-on-it"></a><span data-ttu-id="c16b3-188">Paso 8: revisar la orden de trabajo y comenzar a trabajar en ella</span><span class="sxs-lookup"><span data-stu-id="c16b3-188">Step 8: Review the work order and start to work on it</span></span>

<span data-ttu-id="c16b3-189">En esta sección, trabajará en la orden de trabajo que creó en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="c16b3-189">In this section, you will work on the work order that you created in the previous section.</span></span>

1. <span data-ttu-id="c16b3-190">Siga estos pasos para verificar que el proyecto principal es el proyecto *Orden de trabajo de Pelican Wholesales*:</span><span class="sxs-lookup"><span data-stu-id="c16b3-190">Follow these steps to verify that the parent project is the *Pelican wholesales Work order* project:</span></span>

    1. <span data-ttu-id="c16b3-191">En la sección **Trabajos de mantenimiento de orden de trabajo**, seleccione una línea.</span><span class="sxs-lookup"><span data-stu-id="c16b3-191">In the **Work order maintenance jobs** section, select a line.</span></span>
    1. <span data-ttu-id="c16b3-192">En la ficha desplegable **Detalles de línea**, inspeccione el valor **Id. de proyecto**.</span><span class="sxs-lookup"><span data-stu-id="c16b3-192">On the **Line details** FastTab, inspect the **Project ID** value.</span></span> <span data-ttu-id="c16b3-193">Debe ser un número con guion de la siguiente forma *\<Parent-Project-ID\>-\<Project-ID\>*.</span><span class="sxs-lookup"><span data-stu-id="c16b3-193">It should be a hyphenated number in the form *\<Parent-Project-ID\>-\<Project-ID\>*.</span></span> <span data-ttu-id="c16b3-194">Este valor es un vínculo.</span><span class="sxs-lookup"><span data-stu-id="c16b3-194">This value is a link.</span></span>
    1. <span data-ttu-id="c16b3-195">Seleccione el vínculo del Id. del proyecto para abrir una página donde puede ver el proyecto principal y los nombres del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c16b3-195">Select the project ID link to open a page where you can view the parent project and project names.</span></span>

1. <span data-ttu-id="c16b3-196">En el panel de acciones, en la ficha **Orden de trabajo**, en el grupo **Estado de ciclo de vida**, seleccione **Actualizar el estado de la orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="c16b3-196">On the Action Pane, on the **Work order** tab, in the **Lifecycle state** group, select **Update work order state**.</span></span>
1. <span data-ttu-id="c16b3-197">En el cuadro de diálogo **Actualizar el estado de la orden de trabajo**, en la columna **Seleccionar**, seleccione la casilla de la fila donde el campo **Estado de ciclo de vida** se encuentre *En curso*.</span><span class="sxs-lookup"><span data-stu-id="c16b3-197">In the **Update work order state** dialog box, in the **Select** column, select the check box for the row where the **Lifecycle state** field is set to *In progress*.</span></span>
1. <span data-ttu-id="c16b3-198">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c16b3-198">Select **OK**.</span></span>
1. <span data-ttu-id="c16b3-199">En el cuadro de diálogo **Estado de ciclo de vida: En curso**, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c16b3-199">In the **Lifecycle state: InProgress** dialog box, select **OK**.</span></span>

### <a name="step-9-post-the-hours-that-were-spent-on-the-work-order-and-create-a-new-invoice-proposal"></a><span data-ttu-id="c16b3-200">Paso 9: publicar las horas dedicadas a la orden de trabajo y crear una nueva propuesta de factura</span><span class="sxs-lookup"><span data-stu-id="c16b3-200">Step 9: Post the hours that were spent on the work order and create a new invoice proposal</span></span>

<span data-ttu-id="c16b3-201">En esta sección, seguirá trabajando en la orden de trabajo en la que trabajó en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="c16b3-201">In this section, you will continue to work on the work order that you worked on in the previous section.</span></span>

1. <span data-ttu-id="c16b3-202">En el panel de acciones, en la ficha **Orden de trabajo**, en el grupo **Proyecto**, seleccione **Diarios**.</span><span class="sxs-lookup"><span data-stu-id="c16b3-202">On the Action Pane, on the **Work order** tab, in the **Project** group, select **Journals**.</span></span>

    <span data-ttu-id="c16b3-203">Aparecerá la página **Diarios de órdenes de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="c16b3-203">The **Work order journals** page appears.</span></span> <span data-ttu-id="c16b3-204">Aquí puede registrar el tiempo que dedicó a la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c16b3-204">Here, you can register the time that you spent on the work order.</span></span>

1. <span data-ttu-id="c16b3-205">En la ficha desplegable **Horas**, seleccione **Agregar línea**.</span><span class="sxs-lookup"><span data-stu-id="c16b3-205">On the **Hours** FastTab, select **Add line**.</span></span>
1. <span data-ttu-id="c16b3-206">En la nueva línea, establezca el campo **Horas** a *4*.</span><span class="sxs-lookup"><span data-stu-id="c16b3-206">On the new, line, set the **Hours** field to *4*.</span></span>
1. <span data-ttu-id="c16b3-207">En el panel de acciones, seleccione **Registrar diarios**.</span><span class="sxs-lookup"><span data-stu-id="c16b3-207">On the Action Pane, select **Post journals**.</span></span>
1. <span data-ttu-id="c16b3-208">Cierra la página **Diarios de órdenes de trabajo** para volver a la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c16b3-208">Close the **Work order journals** page to return to the work order.</span></span>
1. <span data-ttu-id="c16b3-209">En el panel de acciones, en la pestaña **Facturación**, seleccione **Nueva propuesta de factura**.</span><span class="sxs-lookup"><span data-stu-id="c16b3-209">On the Action Pane, on the **Invoicing** tab, select **New invoice proposal**.</span></span>
1. <span data-ttu-id="c16b3-210">En el cuadro de diálogo **Crear propuesta de factura**, en la sección **Transacciones de proyecto**, seleccione la casilla **Seleccionar** para todas las líneas que quiera facturar.</span><span class="sxs-lookup"><span data-stu-id="c16b3-210">In the **Create invoice proposal** dialog box, in the **Project transactions** section, select the **Select** check box for every line  that you want to invoice.</span></span>
1. <span data-ttu-id="c16b3-211">Seleccione **Aceptar** para cerrar el cuadro de diálogo y ver la nueva propuesta de factura.</span><span class="sxs-lookup"><span data-stu-id="c16b3-211">Select **OK** to close the dialog box and view the new invoice proposal.</span></span>
