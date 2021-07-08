---
title: No puede confirmar un envío porque los artículos no se han recogido
description: No puede confirmar un envío porque los artículos no se han recogido
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f3ebd47ffc85d4ca257b404579d60d679f7929b6
ms.sourcegitcommit: f9b145ef4a81cec81f420871b4130b05db4f4500
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301314"
---
# <a name="you-cant-confirm-a-shipment-because-items-havent-been-picked"></a><span data-ttu-id="56af5-103">No puede confirmar un envío porque los artículos no se han recogido</span><span class="sxs-lookup"><span data-stu-id="56af5-103">You can't confirm a shipment because items haven't been picked</span></span>

<span data-ttu-id="56af5-104">Código de error: LoadNotPickedAndMovedToFinalShippingLocation</span><span class="sxs-lookup"><span data-stu-id="56af5-104">Error code: LoadNotPickedAndMovedToFinalShippingLocation</span></span>

## <a name="symptoms"></a><span data-ttu-id="56af5-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="56af5-105">Symptoms</span></span>

<span data-ttu-id="56af5-106">Cuando intenta confirmar un envío, el sistema muestra el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="56af5-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="56af5-107">Algunos de los artículos necesarios para la carga %1 todavía no se han recogido y movido a la ubicación de envío final.</span><span class="sxs-lookup"><span data-stu-id="56af5-107">Some of the items that are needed for load %1 have not yet been picked and moved to the final shipping location.</span></span>

<span data-ttu-id="56af5-108">Por lo tanto, no puede confirmar el envío de la carga.</span><span class="sxs-lookup"><span data-stu-id="56af5-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="56af5-109">Causa</span><span class="sxs-lookup"><span data-stu-id="56af5-109">Cause</span></span>

<span data-ttu-id="56af5-110">La carga o el envío no se puede confirmar en su estado actual porque podría existir una de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="56af5-110">The load or shipment can't be confirmed in its current state because one of the following conditions might exist:</span></span>

- <span data-ttu-id="56af5-111">El trabajo relacionado aún no se ha seleccionado y trasladado a la ubicación de envío final.</span><span class="sxs-lookup"><span data-stu-id="56af5-111">The related work hasn't yet been picked and moved to the final shipping location.</span></span>
- <span data-ttu-id="56af5-112">La cantidad de trabajo escogido no coincide con la cantidad de trabajo creada en la línea de carga.</span><span class="sxs-lookup"><span data-stu-id="56af5-112">The picked work quantity doesn't match the created work quantity on the load line.</span></span>
- <span data-ttu-id="56af5-113">La directiva de ubicación se ha configurado con la ubicación de embalaje como la ubicación de envío final mientras se utiliza la contenedorización de plantilla Wave.</span><span class="sxs-lookup"><span data-stu-id="56af5-113">The location directive has been configured with packing location as the final shipping location while using Wave template containerization.</span></span>

## <a name="resolution"></a><span data-ttu-id="56af5-114">Resolución</span><span class="sxs-lookup"><span data-stu-id="56af5-114">Resolution</span></span>

<span data-ttu-id="56af5-115">La carga o el envío se encuentran actualmente en un estado en el que falla la confirmación del envío.</span><span class="sxs-lookup"><span data-stu-id="56af5-115">The load or shipment is currently in a state where shipment confirmation fails.</span></span> <span data-ttu-id="56af5-116">Para solucionar este problema, complete una o más de las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="56af5-116">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="56af5-117">Revise las líneas de carga y asegúrese de que todo el trabajo relacionado se haya completado en la ubicación de envío final y que las cantidades coincidan.</span><span class="sxs-lookup"><span data-stu-id="56af5-117">Review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>
- <span data-ttu-id="56af5-118">Cancele las ID de trabajo que se han creado con la ubicación de embalaje como la ubicación de envío final, reconfigure la directiva de ubicación y vuelva a liberar la carga.</span><span class="sxs-lookup"><span data-stu-id="56af5-118">Cancel the work IDs that have been created with the packing location as the final shipping location, reconfigure the location directive, and rerelease the load.</span></span>

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a><span data-ttu-id="56af5-119">Revise las líneas de carga y asegúrese de que todo el trabajo relacionado se haya completado en la ubicación de envío final y que las cantidades coincidan</span><span class="sxs-lookup"><span data-stu-id="56af5-119">Review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match</span></span>

<span data-ttu-id="56af5-120">Use el siguiente procedimiento para revisar las líneas de carga y asegúrese de que todo el trabajo relacionado se haya completado en la ubicación de envío final y que las cantidades coincidan.</span><span class="sxs-lookup"><span data-stu-id="56af5-120">Use the following procedure to review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>

1. <span data-ttu-id="56af5-121">Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.</span><span class="sxs-lookup"><span data-stu-id="56af5-121">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="56af5-122">Seleccione la carga para la que el envío no se puede confirmar.</span><span class="sxs-lookup"><span data-stu-id="56af5-122">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="56af5-123">En la ficha desplegable **Líneas de carga**, seleccione la línea de carga.</span><span class="sxs-lookup"><span data-stu-id="56af5-123">On the **Load lines** FastTab, select the load line.</span></span>
1. <span data-ttu-id="56af5-124">Anote el valor del campo **Cantidad de trabajo creado**.</span><span class="sxs-lookup"><span data-stu-id="56af5-124">Make a note of the value of the **Work created quantity** field.</span></span>
1. <span data-ttu-id="56af5-125">En el panel de acciones, en la pestaña **Cargas** del grupo **Información relacionada**, seleccione **Trabajo**.</span><span class="sxs-lookup"><span data-stu-id="56af5-125">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="56af5-126">Verifique que el trabajo se haya completado en la ubicación de envío final y que la cantidad de trabajo recogido coincida con la cantidad de trabajo creada en la línea de carga.</span><span class="sxs-lookup"><span data-stu-id="56af5-126">Verify that the work has been completed at the final shipping location, and that the picked work quantity matches the created work quantity on the load line.</span></span>
1. <span data-ttu-id="56af5-127">Repita este procedimiento para todas las líneas de carga para asegurarse de que se cumplan todos los criterios.</span><span class="sxs-lookup"><span data-stu-id="56af5-127">Repeat this procedure for all load lines to make sure that all criteria are met.</span></span>

### <a name="cancel-the-work-ids-that-have-been-created-with-the-packing-location-as-the-final-shipping-location-reconfigure-the-location-directive-and-rerelease-the-load"></a><span data-ttu-id="56af5-128">Cancele las ID de trabajo que se han creado con la ubicación de embalaje como la ubicación de envío final, reconfigure la directiva de ubicación y vuelva a liberar la carga</span><span class="sxs-lookup"><span data-stu-id="56af5-128">Cancel the work IDs that have been created with the packing location as the final shipping location, reconfigure the location directive, and rerelease the load</span></span>

<span data-ttu-id="56af5-129">Utilice el siguiente procedimiento para cancelar las ID de trabajo que tienen la ubicación de embalaje como la ubicación de colocación final con contenedorización automatizada en su lugar.</span><span class="sxs-lookup"><span data-stu-id="56af5-129">Use the following procedure to cancel the work IDs that have the packing location as the final put location with automated containerization in place.</span></span>

1. <span data-ttu-id="56af5-130">Vaya a **Gestion de almacenes \> Tareas periódicas \> Limpiar \> Cancelar trabajo**.</span><span class="sxs-lookup"><span data-stu-id="56af5-130">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="56af5-131">Se abre el cuadro de diálogo **Cancelar trabajo**.</span><span class="sxs-lookup"><span data-stu-id="56af5-131">The **Cancel work** dialog opens.</span></span> <span data-ttu-id="56af5-132">En el campo **Id. de trabajo**, especifique el id. del trabajo que desea cancelar.</span><span class="sxs-lookup"><span data-stu-id="56af5-132">In the **Work ID** field, specify the ID of the work that you want to cancel.</span></span> <span data-ttu-id="56af5-133">La identificación de trabajo seleccionada debe tener un valor **Situación laboral** de *Abierto*, *En curso*, *Cancelado*, *Combinado* o *Cerrado*.</span><span class="sxs-lookup"><span data-stu-id="56af5-133">The selected work ID must have a **Work status** value of *Open*, *In progress*, *Canceled*, *Combined*, or *Closed*.</span></span>
1. <span data-ttu-id="56af5-134">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="56af5-134">Select **OK**.</span></span>
1. <span data-ttu-id="56af5-135">Seleccione **Sí** para confirmar que desea cancelar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="56af5-135">Select **Yes** to confirm that you want to cancel the work.</span></span>
1. <span data-ttu-id="56af5-136">Repita este procedimiento para las otras ID de trabajo según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="56af5-136">Repeat this procedure for the other work IDs as needed.</span></span>

<span data-ttu-id="56af5-137">Para obtener más información, consulte [Cancelar trabajo de almacén para control de excepciones](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="56af5-137">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>

<span data-ttu-id="56af5-138">Utilice el siguiente procedimiento para reconfigurar la directiva de ubicación de modo que no utilice la ubicación de embalaje como la ubicación de envío final cuando se configure la contenedorización automatizada para la plantilla de oleada.</span><span class="sxs-lookup"><span data-stu-id="56af5-138">Use the following procedure to reconfigure the location directive so it won't use the packing location as the final shipping location when automated containerization is set up for the wave template.</span></span>

1. <span data-ttu-id="56af5-139">Vaya a **Gestión de almacenes \> Configurar \> Directivas de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="56af5-139">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="56af5-140">En el campo **Tipo de orden de trabajo**, seleccione *Pedidos de ventas*.</span><span class="sxs-lookup"><span data-stu-id="56af5-140">In the **Work order type** field, select *Sales orders*.</span></span>
1. <span data-ttu-id="56af5-141">Seleccione la directiva de ubicación que está utilizando para la contenedorización automatizada.</span><span class="sxs-lookup"><span data-stu-id="56af5-141">Select the location directive you are using for automated containerization.</span></span>
1. <span data-ttu-id="56af5-142">En la barra de herramientas de la ficha desplegable **Acciones de directiva de ubicación**, seleccione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="56af5-142">On the **Location Directive Actions** FastTab toolbar, select **Edit query**.</span></span>
1. <span data-ttu-id="56af5-143">En el cuadro de diálogo del editor de consultas, en la pestaña **Distancia**, busque la fila donde **Campo** se establece en *Perfil de ubicación* y verifique que el campo **Criterios** de esa fila no está configurado para un perfil de ubicación que tenga un **Tipo de ubicacion** de *Embalaje*.</span><span class="sxs-lookup"><span data-stu-id="56af5-143">In the query editor dialog, on the **Range** tab, find the row where **Field** is set to *Location profile*, and verify that the **Criteria** field for that row is not set to a location profile that has a **Location type** of *Packing*.</span></span> <span data-ttu-id="56af5-144">Ajuste el campo **Criterios** para corregir la ubicación de colocación final.</span><span class="sxs-lookup"><span data-stu-id="56af5-144">Adjust the **Criteria** field to correct the final put location.</span></span>

<span data-ttu-id="56af5-145">Utilice el siguiente procedimiento para liberar la carga y crear ID de trabajo con la ubicación de envío final correcta.</span><span class="sxs-lookup"><span data-stu-id="56af5-145">Use the following procedure to rerelease the load and create work IDs with the correct final shipping location.</span></span>

1. <span data-ttu-id="56af5-146">Vaya a **Gestión de almacén \> Cargas \> Área de trabajo de planificación de la carga**.</span><span class="sxs-lookup"><span data-stu-id="56af5-146">Go to **Warehouse management \> Loads \> Load planning workbench**.</span></span>
1. <span data-ttu-id="56af5-147">En la sección **Cargas**, busque la carga que necesita ser liberada.</span><span class="sxs-lookup"><span data-stu-id="56af5-147">In the **Loads** section, find the load that needs to be released.</span></span>
1. <span data-ttu-id="56af5-148">En la barra de herramientas de la sección **Cargas**, seleccione **Despachar \> Despachar al almacén** para liberar la carga seleccionada al almacén.</span><span class="sxs-lookup"><span data-stu-id="56af5-148">On the **Loads** section toolbar, select **Release \> Release to warehouse** to release the selected load to the warehouse.</span></span>
1. <span data-ttu-id="56af5-149">Repita este procedimiento para las otras cargas según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="56af5-149">Repeat this procedure for the other loads as needed.</span></span>
