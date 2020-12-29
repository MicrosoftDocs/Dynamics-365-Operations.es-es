---
title: Configurar la asignación para los campos de estado de pedidos de ventas
description: Este tema explica cómo configurar los campos de estado de pedido de ventas para doble escritura.
author: dasani-madipalli
manager: tonyafehr
ms.date: 06/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: damadipa
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-06-25
ms.openlocfilehash: 5855581100606003c1faf6b88a0ab234ae378893
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4457001"
---
# <a name="set-up-the-mapping-for-the-sales-order-status-fields"></a><span data-ttu-id="d223f-103">Configurar la asignación para los campos de estado de pedidos de ventas</span><span class="sxs-lookup"><span data-stu-id="d223f-103">Set up the mapping for the sales order status fields</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d223f-104">Los campos que indican el estado del pedido de ventas tienen distintos valores de enumeración en Microsoft Dynamics 365 Supply Chain Management y en Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="d223f-104">The fields that indicate sales order status have different enumeration values in Microsoft Dynamics 365 Supply Chain Management and Dynamics 365 Sales.</span></span> <span data-ttu-id="d223f-105">Se requiere una configuración adicional para asignar estos campos en doble escritura.</span><span class="sxs-lookup"><span data-stu-id="d223f-105">Additional setup is required to map these fields in dual-write.</span></span>

## <a name="fields-in-supply-chain-management"></a><span data-ttu-id="d223f-106">Campos en Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="d223f-106">Fields in Supply Chain Management</span></span>

<span data-ttu-id="d223f-107">En Supply Chain Management, dos campos reflejan el estado del pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="d223f-107">In Supply Chain Management, two fields reflect the status of the sales order.</span></span> <span data-ttu-id="d223f-108">Los campos que debe asignar son **Estado** y **Estado del documento**.</span><span class="sxs-lookup"><span data-stu-id="d223f-108">The fields that you must map are **Status** and **Document Status**.</span></span>

<span data-ttu-id="d223f-109">La enumeración **Estado** especifica el estado general del pedido.</span><span class="sxs-lookup"><span data-stu-id="d223f-109">The **Status** enumeration specifies the overall status of the order.</span></span> <span data-ttu-id="d223f-110">Este estado se muestra en el encabezado del pedido.</span><span class="sxs-lookup"><span data-stu-id="d223f-110">This status is shown on the order header.</span></span>

<span data-ttu-id="d223f-111">La enumeración **Estado** tiene los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="d223f-111">The **Status** enumeration has the following values:</span></span>

- <span data-ttu-id="d223f-112">Pedido abierto</span><span class="sxs-lookup"><span data-stu-id="d223f-112">Open Order</span></span>
- <span data-ttu-id="d223f-113">Entregado</span><span class="sxs-lookup"><span data-stu-id="d223f-113">Delivered</span></span>
- <span data-ttu-id="d223f-114">Facturado</span><span class="sxs-lookup"><span data-stu-id="d223f-114">Invoiced</span></span>
- <span data-ttu-id="d223f-115">Cancelada</span><span class="sxs-lookup"><span data-stu-id="d223f-115">Cancelled</span></span>

<span data-ttu-id="d223f-116">La enumeración **Estado del documento** especifica el documento más reciente que se generó para el pedido.</span><span class="sxs-lookup"><span data-stu-id="d223f-116">The **Document Status** enumeration specifies the most recent document that was generated for the order.</span></span> <span data-ttu-id="d223f-117">Por ejemplo, si se confirma el pedido, este documento es una confirmación de pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="d223f-117">For example, if the order is confirmed, this document is a sales order confirmation.</span></span> <span data-ttu-id="d223f-118">Si un pedido de ventas se factura parcialmente y después se confirma la línea restante, el estado del documento sigue siendo **Factura**, ya que la factura se genera posteriormente en el proceso.</span><span class="sxs-lookup"><span data-stu-id="d223f-118">If a sales order is partially invoiced, and then the remaining line is confirmed, the document status remains **Invoice**, because the invoice is generated later in the process.</span></span>

<span data-ttu-id="d223f-119">La enumeración **Estado del documento** tiene los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="d223f-119">The **Document Status** enumeration has the following values:</span></span>

- <span data-ttu-id="d223f-120">Confirmación</span><span class="sxs-lookup"><span data-stu-id="d223f-120">Confirmation</span></span>
- <span data-ttu-id="d223f-121">Lista de selección</span><span class="sxs-lookup"><span data-stu-id="d223f-121">Picking List</span></span>
- <span data-ttu-id="d223f-122">Albarán</span><span class="sxs-lookup"><span data-stu-id="d223f-122">Packing Slip</span></span>
- <span data-ttu-id="d223f-123">Factura</span><span class="sxs-lookup"><span data-stu-id="d223f-123">Invoice</span></span>

## <a name="fields-in-sales"></a><span data-ttu-id="d223f-124">Campos en Sales</span><span class="sxs-lookup"><span data-stu-id="d223f-124">Fields in Sales</span></span>

<span data-ttu-id="d223f-125">En Sales, dos campos indican el estado del pedido.</span><span class="sxs-lookup"><span data-stu-id="d223f-125">In Sales, two fields indicate the status of the order.</span></span> <span data-ttu-id="d223f-126">Los campos que debe asignar son **Estado** y **Estado de procesamiento**.</span><span class="sxs-lookup"><span data-stu-id="d223f-126">The fields that you must map are **Status** and **Processing Status**.</span></span>

<span data-ttu-id="d223f-127">La enumeración **Estado** especifica el estado general del pedido.</span><span class="sxs-lookup"><span data-stu-id="d223f-127">The **Status** enumeration specifies the overall status of the order.</span></span> <span data-ttu-id="d223f-128">Tiene los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="d223f-128">It has the following values:</span></span>

- <span data-ttu-id="d223f-129">Activa</span><span class="sxs-lookup"><span data-stu-id="d223f-129">Active</span></span>
- <span data-ttu-id="d223f-130">Emitido</span><span class="sxs-lookup"><span data-stu-id="d223f-130">Submitted</span></span>
- <span data-ttu-id="d223f-131">Cumplido</span><span class="sxs-lookup"><span data-stu-id="d223f-131">Fulfilled</span></span>
- <span data-ttu-id="d223f-132">Facturado</span><span class="sxs-lookup"><span data-stu-id="d223f-132">Invoiced</span></span>
- <span data-ttu-id="d223f-133">Cancelada</span><span class="sxs-lookup"><span data-stu-id="d223f-133">Cancelled</span></span>

<span data-ttu-id="d223f-134">Se ha incluido la enumeración **Estado de procesamiento** para que el estado se pueda asignar de forma más precisa con Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d223f-134">The **Processing Status** enumeration was introduced so that the status can be mapped more accurately with Supply Chain Management.</span></span>

<span data-ttu-id="d223f-135">La siguiente tabla muestra la asignación de **Estado de procesamiento** en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d223f-135">The following table shows the mapping of **Processing Status** in Supply Chain Management.</span></span>

| <span data-ttu-id="d223f-136">Estado de procesamiento</span><span class="sxs-lookup"><span data-stu-id="d223f-136">Processing Status</span></span>   | <span data-ttu-id="d223f-137">Estado en Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="d223f-137">Status in Supply Chain Management</span></span> | <span data-ttu-id="d223f-138">Estado del documento en Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="d223f-138">Document Status in Supply Chain Management</span></span> |
|---------------------|-----------------------------------|--------------------------------------------|
| <span data-ttu-id="d223f-139">Activa</span><span class="sxs-lookup"><span data-stu-id="d223f-139">Active</span></span>              | <span data-ttu-id="d223f-140">Pedido abierto</span><span class="sxs-lookup"><span data-stu-id="d223f-140">Open Order</span></span>                        | <span data-ttu-id="d223f-141">None</span><span class="sxs-lookup"><span data-stu-id="d223f-141">None</span></span>                                       |
| <span data-ttu-id="d223f-142">Confirmado</span><span class="sxs-lookup"><span data-stu-id="d223f-142">Confirmed</span></span>           | <span data-ttu-id="d223f-143">Pedido abierto</span><span class="sxs-lookup"><span data-stu-id="d223f-143">Open Order</span></span>                        | <span data-ttu-id="d223f-144">Confirmación</span><span class="sxs-lookup"><span data-stu-id="d223f-144">Confirmation</span></span>                               |
| <span data-ttu-id="d223f-145">Seleccionado</span><span class="sxs-lookup"><span data-stu-id="d223f-145">Picked</span></span>              | <span data-ttu-id="d223f-146">Pedido abierto</span><span class="sxs-lookup"><span data-stu-id="d223f-146">Open Order</span></span>                        | <span data-ttu-id="d223f-147">Lista de selección</span><span class="sxs-lookup"><span data-stu-id="d223f-147">Picking List</span></span>                               |
| <span data-ttu-id="d223f-148">Parcialmente entregado</span><span class="sxs-lookup"><span data-stu-id="d223f-148">Partially Delivered</span></span> | <span data-ttu-id="d223f-149">Pedido abierto</span><span class="sxs-lookup"><span data-stu-id="d223f-149">Open Order</span></span>                        | <span data-ttu-id="d223f-150">Albarán</span><span class="sxs-lookup"><span data-stu-id="d223f-150">Packing Slip</span></span>                               |
| <span data-ttu-id="d223f-151">Entregado</span><span class="sxs-lookup"><span data-stu-id="d223f-151">Delivered</span></span>           | <span data-ttu-id="d223f-152">Entregado</span><span class="sxs-lookup"><span data-stu-id="d223f-152">Delivered</span></span>                         | <span data-ttu-id="d223f-153">Albarán</span><span class="sxs-lookup"><span data-stu-id="d223f-153">Packing Slip</span></span>                               |
| <span data-ttu-id="d223f-154">Parcialmente facturado</span><span class="sxs-lookup"><span data-stu-id="d223f-154">Partially Invoiced</span></span>  | <span data-ttu-id="d223f-155">Entregado</span><span class="sxs-lookup"><span data-stu-id="d223f-155">Delivered</span></span>                         | <span data-ttu-id="d223f-156">Factura</span><span class="sxs-lookup"><span data-stu-id="d223f-156">Invoice</span></span>                                    |
| <span data-ttu-id="d223f-157">Facturado</span><span class="sxs-lookup"><span data-stu-id="d223f-157">Invoiced</span></span>            | <span data-ttu-id="d223f-158">Facturado</span><span class="sxs-lookup"><span data-stu-id="d223f-158">Invoiced</span></span>                          | <span data-ttu-id="d223f-159">Factura</span><span class="sxs-lookup"><span data-stu-id="d223f-159">Invoice</span></span>                                    |
| <span data-ttu-id="d223f-160">Cancelada</span><span class="sxs-lookup"><span data-stu-id="d223f-160">Cancelled</span></span>           | <span data-ttu-id="d223f-161">Cancelada</span><span class="sxs-lookup"><span data-stu-id="d223f-161">Cancelled</span></span>                         | <span data-ttu-id="d223f-162">No aplicable</span><span class="sxs-lookup"><span data-stu-id="d223f-162">Not applicable</span></span>                             |

<span data-ttu-id="d223f-163">En la tabla siguiente se muestra la asignación de **Estado de procesamiento** entre Sales y Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d223f-163">The following table shows the mapping of **Processing Status** between Sales and Supply Chain Management.</span></span>

| <span data-ttu-id="d223f-164">Estado de procesamiento</span><span class="sxs-lookup"><span data-stu-id="d223f-164">Processing Status</span></span>   | <span data-ttu-id="d223f-165">Estado en Sales</span><span class="sxs-lookup"><span data-stu-id="d223f-165">Status in Sales</span></span> | <span data-ttu-id="d223f-166">Estado en Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="d223f-166">Status in Supply Chain Management</span></span> |
|---------------------|-----------------|-----------------------------------|
| <span data-ttu-id="d223f-167">Activa</span><span class="sxs-lookup"><span data-stu-id="d223f-167">Active</span></span>              | <span data-ttu-id="d223f-168">Activa</span><span class="sxs-lookup"><span data-stu-id="d223f-168">Active</span></span>          | <span data-ttu-id="d223f-169">Pedido abierto</span><span class="sxs-lookup"><span data-stu-id="d223f-169">Open Order</span></span>                        |
| <span data-ttu-id="d223f-170">Confirmado</span><span class="sxs-lookup"><span data-stu-id="d223f-170">Confirmed</span></span>           | <span data-ttu-id="d223f-171">Emitido</span><span class="sxs-lookup"><span data-stu-id="d223f-171">Submitted</span></span>       | <span data-ttu-id="d223f-172">Pedido abierto</span><span class="sxs-lookup"><span data-stu-id="d223f-172">Open Order</span></span>                        |
| <span data-ttu-id="d223f-173">Seleccionado</span><span class="sxs-lookup"><span data-stu-id="d223f-173">Picked</span></span>              | <span data-ttu-id="d223f-174">Emitido</span><span class="sxs-lookup"><span data-stu-id="d223f-174">Submitted</span></span>       | <span data-ttu-id="d223f-175">Pedido abierto</span><span class="sxs-lookup"><span data-stu-id="d223f-175">Open Order</span></span>                        |
| <span data-ttu-id="d223f-176">Parcialmente entregado</span><span class="sxs-lookup"><span data-stu-id="d223f-176">Partially Delivered</span></span> | <span data-ttu-id="d223f-177">Activa</span><span class="sxs-lookup"><span data-stu-id="d223f-177">Active</span></span>          | <span data-ttu-id="d223f-178">Pedido abierto</span><span class="sxs-lookup"><span data-stu-id="d223f-178">Open Order</span></span>                        |
| <span data-ttu-id="d223f-179">Parcialmente facturado</span><span class="sxs-lookup"><span data-stu-id="d223f-179">Partially Invoiced</span></span>  | <span data-ttu-id="d223f-180">Activa</span><span class="sxs-lookup"><span data-stu-id="d223f-180">Active</span></span>          | <span data-ttu-id="d223f-181">Pedido abierto</span><span class="sxs-lookup"><span data-stu-id="d223f-181">Open Order</span></span>                        |
| <span data-ttu-id="d223f-182">Parcialmente facturado</span><span class="sxs-lookup"><span data-stu-id="d223f-182">Partially Invoiced</span></span>  | <span data-ttu-id="d223f-183">Cumplido</span><span class="sxs-lookup"><span data-stu-id="d223f-183">Fulfilled</span></span>       | <span data-ttu-id="d223f-184">Entregado</span><span class="sxs-lookup"><span data-stu-id="d223f-184">Delivered</span></span>                         |
| <span data-ttu-id="d223f-185">Facturado</span><span class="sxs-lookup"><span data-stu-id="d223f-185">Invoiced</span></span>            | <span data-ttu-id="d223f-186">Facturado</span><span class="sxs-lookup"><span data-stu-id="d223f-186">Invoiced</span></span>        | <span data-ttu-id="d223f-187">Facturado</span><span class="sxs-lookup"><span data-stu-id="d223f-187">Invoiced</span></span>                          |
| <span data-ttu-id="d223f-188">Cancelada</span><span class="sxs-lookup"><span data-stu-id="d223f-188">Cancelled</span></span>           | <span data-ttu-id="d223f-189">Cancelada</span><span class="sxs-lookup"><span data-stu-id="d223f-189">Cancelled</span></span>       | <span data-ttu-id="d223f-190">Cancelada</span><span class="sxs-lookup"><span data-stu-id="d223f-190">Cancelled</span></span>                         |

## <a name="setup"></a><span data-ttu-id="d223f-191">Configurar</span><span class="sxs-lookup"><span data-stu-id="d223f-191">Setup</span></span>

<span data-ttu-id="d223f-192">Para configurar la asignación para los campos de estado del pedido de ventas, debe habilitar los atributos **IsSOPIntegrationEnabled** y **isIntegrationUser**.</span><span class="sxs-lookup"><span data-stu-id="d223f-192">To set up the mapping for the sales order status fields, you must enable the **IsSOPIntegrationEnabled** and **isIntegrationUser** attributes.</span></span>

<span data-ttu-id="d223f-193">Para habilitar el atributo **IsSOPIntegrationEnabled**, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="d223f-193">To enable the **IsSOPIntegrationEnabled** attribute, follow these steps.</span></span>

1. <span data-ttu-id="d223f-194">En un explorador, vaya a `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations`.</span><span class="sxs-lookup"><span data-stu-id="d223f-194">In a browser, go to `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations`.</span></span> <span data-ttu-id="d223f-195">Reemplace **\<test-name\>** con el enlace de su empresa en Sales.</span><span class="sxs-lookup"><span data-stu-id="d223f-195">Replace **\<test-name\>** with your company's link to Sales.</span></span>
2. <span data-ttu-id="d223f-196">En la página que se abre, busque **organizationid** y anote el valor.</span><span class="sxs-lookup"><span data-stu-id="d223f-196">On the page that is opened, find **organizationid**, and make a note of the value.</span></span>

    ![Cómo encontrar organizationid](media/sales-map-orgid.png)

3. <span data-ttu-id="d223f-198">En Sales, abra la consola del explorador y ejecute el siguiente script.</span><span class="sxs-lookup"><span data-stu-id="d223f-198">In Sales, open the browser console, and run following script.</span></span> <span data-ttu-id="d223f-199">Use el valor **organizationid** del paso 2.</span><span class="sxs-lookup"><span data-stu-id="d223f-199">Use the **organizationid** value from step 2.</span></span>

    ```javascript
    Xrm.WebApi.updateRecord("organization",
    "d9a7c5f7-acbf-4aa9-86e8-a891c43f748c", {"issopintegrationenabled" :
    true}).then(
        function success(result) {
            console.log("Account updated");
            // perform operations on record update
        },
        function (error) {
            console.log(error.message);
            // handle error conditions
        }
    );
    ```

    ![Código JavaScript en la consola del explorador](media/sales-map-script.png)

4. <span data-ttu-id="d223f-201">Compruebe que **IsSOPIntegrationEnabled** está establecido en **true**.</span><span class="sxs-lookup"><span data-stu-id="d223f-201">Verify that **IsSOPIntegrationEnabled** is set to **true**.</span></span> <span data-ttu-id="d223f-202">Use la dirección URL del paso 1 para comprobar el valor.</span><span class="sxs-lookup"><span data-stu-id="d223f-202">Use the URL from step 1 to check the value.</span></span>

    ![IsSOPIntegrationEnabled establecido en true.](media/sales-map-integration-enabled.png)

<span data-ttu-id="d223f-204">Para habilitar el atributo **isIntegrationUser**, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="d223f-204">To enable the **isIntegrationUser** attribute, follow these steps.</span></span>

1. <span data-ttu-id="d223f-205">En Sales, vaya a **Configuración \> Personalización \> Personaliza el sistema**, seleccione **Entidad de usuario** y abra **Formulario \> Usuario**.</span><span class="sxs-lookup"><span data-stu-id="d223f-205">In Sales, go to **Setting \> Customization \> Customize the System**, select **User entity**, and then open **Form \> User**.</span></span>

    ![Abrir el formulario de usuario](media/sales-map-user.png)

2. <span data-ttu-id="d223f-207">En el explorador de campos, busque **Modo de usuario de integración** y haga doble clic en él para agregarlo al formulario.</span><span class="sxs-lookup"><span data-stu-id="d223f-207">In Field Explorer, find **Integration user mode**, and double-click it to add it to the form.</span></span> <span data-ttu-id="d223f-208">Guarde el cambio.</span><span class="sxs-lookup"><span data-stu-id="d223f-208">Save your change.</span></span>

    ![Agregar el campo Modo de usuario de integración al formulario](media/sales-map-field-explorer.png)

3. <span data-ttu-id="d223f-210">En Sales, vaya a **Configuración \> Seguridad \> Usuarios** y cambie la vista de **Usuarios habilitados** a **Usuarios de la aplicación**.</span><span class="sxs-lookup"><span data-stu-id="d223f-210">In Sales, go to **Setting \> Security \> Users**, and change the view from **Enabled Users** to **Application Users**.</span></span>

    ![Cambiar la vista de usuarios habilitados a usuarios de aplicaciones](media/sales-map-enabled-users.png)

4. <span data-ttu-id="d223f-212">Seleccione las dos entradas para **DualWrite IntegrationUser**.</span><span class="sxs-lookup"><span data-stu-id="d223f-212">Select the two entries for **DualWrite IntegrationUser**.</span></span>

    ![Lista de usuarios de aplicación](media/sales-map-user-mode.png)

5. <span data-ttu-id="d223f-214">Cambie el valor del campo **Modo de usuario de integración** a **Sí**.</span><span class="sxs-lookup"><span data-stu-id="d223f-214">Change the value of the **Integration user mode** field to **Yes**.</span></span>

    ![Cambiar el valor del campo Modo de usuario de integración](media/sales-map-user-mode-yes.png)

<span data-ttu-id="d223f-216">Ahora los pedidos de ventas están asignados.</span><span class="sxs-lookup"><span data-stu-id="d223f-216">Your sales orders are now mapped.</span></span>
