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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: damadipa
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-06-25
ms.openlocfilehash: dce4b6310e2f6d31a115302efa7fbc132799e48f
ms.sourcegitcommit: 4ba10abe5be8a21b95370cd970a622e954970984
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "3829294"
---
# <a name="set-up-the-mapping-for-the-sales-order-status-fields"></a><span data-ttu-id="04e02-103">Configurar la asignación para los campos de estado de pedidos de ventas</span><span class="sxs-lookup"><span data-stu-id="04e02-103">Set up the mapping for the sales order status fields</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="04e02-104">Los campos que indican el estado del pedido de ventas tienen distintos valores de enumeración en Microsoft Dynamics 365 Supply Chain Management y en Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="04e02-104">The fields that indicate sales order status have different enumeration values in Microsoft Dynamics 365 Supply Chain Management and Dynamics 365 Sales.</span></span> <span data-ttu-id="04e02-105">Se requiere una configuración adicional para asignar estos campos en doble escritura.</span><span class="sxs-lookup"><span data-stu-id="04e02-105">Additional setup is required to map these fields in dual-write.</span></span>

## <a name="fields-in-supply-chain-management"></a><span data-ttu-id="04e02-106">Campos en Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="04e02-106">Fields in Supply Chain Management</span></span>

<span data-ttu-id="04e02-107">En Supply Chain Management, dos campos reflejan el estado del pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="04e02-107">In Supply Chain Management, two fields reflect the status of the sales order.</span></span> <span data-ttu-id="04e02-108">Los campos que debe asignar son **Estado** y **Estado del documento**.</span><span class="sxs-lookup"><span data-stu-id="04e02-108">The fields that you must map are **Status** and **Document Status**.</span></span>

<span data-ttu-id="04e02-109">La enumeración **Estado** especifica el estado general del pedido.</span><span class="sxs-lookup"><span data-stu-id="04e02-109">The **Status** enumeration specifies the overall status of the order.</span></span> <span data-ttu-id="04e02-110">Este estado se muestra en el encabezado del pedido.</span><span class="sxs-lookup"><span data-stu-id="04e02-110">This status is shown on the order header.</span></span>

<span data-ttu-id="04e02-111">La enumeración **Estado** tiene los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="04e02-111">The **Status** enumeration has the following values:</span></span>

- <span data-ttu-id="04e02-112">Pedido abierto</span><span class="sxs-lookup"><span data-stu-id="04e02-112">Open Order</span></span>
- <span data-ttu-id="04e02-113">Entregado</span><span class="sxs-lookup"><span data-stu-id="04e02-113">Delivered</span></span>
- <span data-ttu-id="04e02-114">Facturado</span><span class="sxs-lookup"><span data-stu-id="04e02-114">Invoiced</span></span>
- <span data-ttu-id="04e02-115">Cancelada</span><span class="sxs-lookup"><span data-stu-id="04e02-115">Cancelled</span></span>

<span data-ttu-id="04e02-116">La enumeración **Estado del documento** especifica el documento más reciente que se generó para el pedido.</span><span class="sxs-lookup"><span data-stu-id="04e02-116">The **Document Status** enumeration specifies the most recent document that was generated for the order.</span></span> <span data-ttu-id="04e02-117">Por ejemplo, si se confirma el pedido, este documento es una confirmación de pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="04e02-117">For example, if the order is confirmed, this document is a sales order confirmation.</span></span> <span data-ttu-id="04e02-118">Si un pedido de ventas se factura parcialmente y después se confirma la línea restante, el estado del documento sigue siendo **Factura**, ya que la factura se genera posteriormente en el proceso.</span><span class="sxs-lookup"><span data-stu-id="04e02-118">If a sales order is partially invoiced, and then the remaining line is confirmed, the document status remains **Invoice**, because the invoice is generated later in the process.</span></span>

<span data-ttu-id="04e02-119">La enumeración **Estado del documento** tiene los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="04e02-119">The **Document Status** enumeration has the following values:</span></span>

- <span data-ttu-id="04e02-120">Confirmación</span><span class="sxs-lookup"><span data-stu-id="04e02-120">Confirmation</span></span>
- <span data-ttu-id="04e02-121">Lista de selección</span><span class="sxs-lookup"><span data-stu-id="04e02-121">Picking List</span></span>
- <span data-ttu-id="04e02-122">Albarán</span><span class="sxs-lookup"><span data-stu-id="04e02-122">Packing Slip</span></span>
- <span data-ttu-id="04e02-123">Factura</span><span class="sxs-lookup"><span data-stu-id="04e02-123">Invoice</span></span>

## <a name="fields-in-sales"></a><span data-ttu-id="04e02-124">Campos en Sales</span><span class="sxs-lookup"><span data-stu-id="04e02-124">Fields in Sales</span></span>

<span data-ttu-id="04e02-125">En Sales, dos campos indican el estado del pedido.</span><span class="sxs-lookup"><span data-stu-id="04e02-125">In Sales, two fields indicate the status of the order.</span></span> <span data-ttu-id="04e02-126">Los campos que debe asignar son **Estado** y **Estado de procesamiento**.</span><span class="sxs-lookup"><span data-stu-id="04e02-126">The fields that you must map are **Status** and **Processing Status**.</span></span>

<span data-ttu-id="04e02-127">La enumeración **Estado** especifica el estado general del pedido.</span><span class="sxs-lookup"><span data-stu-id="04e02-127">The **Status** enumeration specifies the overall status of the order.</span></span> <span data-ttu-id="04e02-128">Tiene los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="04e02-128">It has the following values:</span></span>

- <span data-ttu-id="04e02-129">Activa</span><span class="sxs-lookup"><span data-stu-id="04e02-129">Active</span></span>
- <span data-ttu-id="04e02-130">Emitido</span><span class="sxs-lookup"><span data-stu-id="04e02-130">Submitted</span></span>
- <span data-ttu-id="04e02-131">Cumplido</span><span class="sxs-lookup"><span data-stu-id="04e02-131">Fulfilled</span></span>
- <span data-ttu-id="04e02-132">Facturado</span><span class="sxs-lookup"><span data-stu-id="04e02-132">Invoiced</span></span>
- <span data-ttu-id="04e02-133">Cancelada</span><span class="sxs-lookup"><span data-stu-id="04e02-133">Cancelled</span></span>

<span data-ttu-id="04e02-134">Se ha incluido la enumeración **Estado de procesamiento** para que el estado se pueda asignar de forma más precisa con Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="04e02-134">The **Processing Status** enumeration was introduced so that the status can be mapped more accurately with Supply Chain Management.</span></span>

<span data-ttu-id="04e02-135">La siguiente tabla muestra la asignación de **Estado de procesamiento** en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="04e02-135">The following table shows the mapping of **Processing Status** in Supply Chain Management.</span></span>

| <span data-ttu-id="04e02-136">Estado de procesamiento</span><span class="sxs-lookup"><span data-stu-id="04e02-136">Processing Status</span></span>   | <span data-ttu-id="04e02-137">Estado en Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="04e02-137">Status in Supply Chain Management</span></span> | <span data-ttu-id="04e02-138">Estado del documento en Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="04e02-138">Document Status in Supply Chain Management</span></span> |
|---------------------|-----------------------------------|--------------------------------------------|
| <span data-ttu-id="04e02-139">Activa</span><span class="sxs-lookup"><span data-stu-id="04e02-139">Active</span></span>              | <span data-ttu-id="04e02-140">Pedido abierto</span><span class="sxs-lookup"><span data-stu-id="04e02-140">Open Order</span></span>                        | <span data-ttu-id="04e02-141">None</span><span class="sxs-lookup"><span data-stu-id="04e02-141">None</span></span>                                       |
| <span data-ttu-id="04e02-142">Confirmado</span><span class="sxs-lookup"><span data-stu-id="04e02-142">Confirmed</span></span>           | <span data-ttu-id="04e02-143">Pedido abierto</span><span class="sxs-lookup"><span data-stu-id="04e02-143">Open Order</span></span>                        | <span data-ttu-id="04e02-144">Confirmación</span><span class="sxs-lookup"><span data-stu-id="04e02-144">Confirmation</span></span>                               |
| <span data-ttu-id="04e02-145">Seleccionado</span><span class="sxs-lookup"><span data-stu-id="04e02-145">Picked</span></span>              | <span data-ttu-id="04e02-146">Pedido abierto</span><span class="sxs-lookup"><span data-stu-id="04e02-146">Open Order</span></span>                        | <span data-ttu-id="04e02-147">Lista de selección</span><span class="sxs-lookup"><span data-stu-id="04e02-147">Picking List</span></span>                               |
| <span data-ttu-id="04e02-148">Parcialmente entregado</span><span class="sxs-lookup"><span data-stu-id="04e02-148">Partially Delivered</span></span> | <span data-ttu-id="04e02-149">Pedido abierto</span><span class="sxs-lookup"><span data-stu-id="04e02-149">Open Order</span></span>                        | <span data-ttu-id="04e02-150">Albarán</span><span class="sxs-lookup"><span data-stu-id="04e02-150">Packing Slip</span></span>                               |
| <span data-ttu-id="04e02-151">Entregado</span><span class="sxs-lookup"><span data-stu-id="04e02-151">Delivered</span></span>           | <span data-ttu-id="04e02-152">Entregado</span><span class="sxs-lookup"><span data-stu-id="04e02-152">Delivered</span></span>                         | <span data-ttu-id="04e02-153">Albarán</span><span class="sxs-lookup"><span data-stu-id="04e02-153">Packing Slip</span></span>                               |
| <span data-ttu-id="04e02-154">Parcialmente facturado</span><span class="sxs-lookup"><span data-stu-id="04e02-154">Partially Invoiced</span></span>  | <span data-ttu-id="04e02-155">Entregado</span><span class="sxs-lookup"><span data-stu-id="04e02-155">Delivered</span></span>                         | <span data-ttu-id="04e02-156">Factura</span><span class="sxs-lookup"><span data-stu-id="04e02-156">Invoice</span></span>                                    |
| <span data-ttu-id="04e02-157">Facturado</span><span class="sxs-lookup"><span data-stu-id="04e02-157">Invoiced</span></span>            | <span data-ttu-id="04e02-158">Facturado</span><span class="sxs-lookup"><span data-stu-id="04e02-158">Invoiced</span></span>                          | <span data-ttu-id="04e02-159">Factura</span><span class="sxs-lookup"><span data-stu-id="04e02-159">Invoice</span></span>                                    |
| <span data-ttu-id="04e02-160">Cancelada</span><span class="sxs-lookup"><span data-stu-id="04e02-160">Cancelled</span></span>           | <span data-ttu-id="04e02-161">Cancelada</span><span class="sxs-lookup"><span data-stu-id="04e02-161">Cancelled</span></span>                         | <span data-ttu-id="04e02-162">No aplicable</span><span class="sxs-lookup"><span data-stu-id="04e02-162">Not applicable</span></span>                             |

<span data-ttu-id="04e02-163">En la tabla siguiente se muestra la asignación de **Estado de procesamiento** entre Sales y Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="04e02-163">The following table shows the mapping of **Processing Status** between Sales and Supply Chain Management.</span></span>

| <span data-ttu-id="04e02-164">Estado de procesamiento</span><span class="sxs-lookup"><span data-stu-id="04e02-164">Processing Status</span></span>   | <span data-ttu-id="04e02-165">Estado en Sales</span><span class="sxs-lookup"><span data-stu-id="04e02-165">Status in Sales</span></span> | <span data-ttu-id="04e02-166">Estado en Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="04e02-166">Status in Supply Chain Management</span></span> |
|---------------------|-----------------|-----------------------------------|
| <span data-ttu-id="04e02-167">Activa</span><span class="sxs-lookup"><span data-stu-id="04e02-167">Active</span></span>              | <span data-ttu-id="04e02-168">Activa</span><span class="sxs-lookup"><span data-stu-id="04e02-168">Active</span></span>          | <span data-ttu-id="04e02-169">Pedido abierto</span><span class="sxs-lookup"><span data-stu-id="04e02-169">Open Order</span></span>                        |
| <span data-ttu-id="04e02-170">Confirmado</span><span class="sxs-lookup"><span data-stu-id="04e02-170">Confirmed</span></span>           | <span data-ttu-id="04e02-171">Emitido</span><span class="sxs-lookup"><span data-stu-id="04e02-171">Submitted</span></span>       | <span data-ttu-id="04e02-172">Pedido abierto</span><span class="sxs-lookup"><span data-stu-id="04e02-172">Open Order</span></span>                        |
| <span data-ttu-id="04e02-173">Seleccionado</span><span class="sxs-lookup"><span data-stu-id="04e02-173">Picked</span></span>              | <span data-ttu-id="04e02-174">Emitido</span><span class="sxs-lookup"><span data-stu-id="04e02-174">Submitted</span></span>       | <span data-ttu-id="04e02-175">Pedido abierto</span><span class="sxs-lookup"><span data-stu-id="04e02-175">Open Order</span></span>                        |
| <span data-ttu-id="04e02-176">Parcialmente entregado</span><span class="sxs-lookup"><span data-stu-id="04e02-176">Partially Delivered</span></span> | <span data-ttu-id="04e02-177">Activa</span><span class="sxs-lookup"><span data-stu-id="04e02-177">Active</span></span>          | <span data-ttu-id="04e02-178">Pedido abierto</span><span class="sxs-lookup"><span data-stu-id="04e02-178">Open Order</span></span>                        |
| <span data-ttu-id="04e02-179">Parcialmente facturado</span><span class="sxs-lookup"><span data-stu-id="04e02-179">Partially Invoiced</span></span>  | <span data-ttu-id="04e02-180">Activa</span><span class="sxs-lookup"><span data-stu-id="04e02-180">Active</span></span>          | <span data-ttu-id="04e02-181">Pedido abierto</span><span class="sxs-lookup"><span data-stu-id="04e02-181">Open Order</span></span>                        |
| <span data-ttu-id="04e02-182">Parcialmente facturado</span><span class="sxs-lookup"><span data-stu-id="04e02-182">Partially Invoiced</span></span>  | <span data-ttu-id="04e02-183">Cumplido</span><span class="sxs-lookup"><span data-stu-id="04e02-183">Fulfilled</span></span>       | <span data-ttu-id="04e02-184">Entregado</span><span class="sxs-lookup"><span data-stu-id="04e02-184">Delivered</span></span>                         |
| <span data-ttu-id="04e02-185">Facturado</span><span class="sxs-lookup"><span data-stu-id="04e02-185">Invoiced</span></span>            | <span data-ttu-id="04e02-186">Facturado</span><span class="sxs-lookup"><span data-stu-id="04e02-186">Invoiced</span></span>        | <span data-ttu-id="04e02-187">Facturado</span><span class="sxs-lookup"><span data-stu-id="04e02-187">Invoiced</span></span>                          |
| <span data-ttu-id="04e02-188">Cancelada</span><span class="sxs-lookup"><span data-stu-id="04e02-188">Cancelled</span></span>           | <span data-ttu-id="04e02-189">Cancelada</span><span class="sxs-lookup"><span data-stu-id="04e02-189">Cancelled</span></span>       | <span data-ttu-id="04e02-190">Cancelada</span><span class="sxs-lookup"><span data-stu-id="04e02-190">Cancelled</span></span>                         |

## <a name="setup"></a><span data-ttu-id="04e02-191">Configurar</span><span class="sxs-lookup"><span data-stu-id="04e02-191">Setup</span></span>

<span data-ttu-id="04e02-192">Para configurar la asignación para los campos de estado del pedido de ventas, debe habilitar los atributos **IsSOPIntegrationEnabled** y **isIntegrationUser**.</span><span class="sxs-lookup"><span data-stu-id="04e02-192">To set up the mapping for the sales order status fields, you must enable the **IsSOPIntegrationEnabled** and **isIntegrationUser** attributes.</span></span>

<span data-ttu-id="04e02-193">Para habilitar el atributo **IsSOPIntegrationEnabled**, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="04e02-193">To enable the **IsSOPIntegrationEnabled** attribute, follow these steps.</span></span>

1. <span data-ttu-id="04e02-194">En un explorador, vaya a `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations`.</span><span class="sxs-lookup"><span data-stu-id="04e02-194">In a browser, go to `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations`.</span></span> <span data-ttu-id="04e02-195">Reemplace **\<test-name\>** con el enlace de su empresa en Sales.</span><span class="sxs-lookup"><span data-stu-id="04e02-195">Replace **\<test-name\>** with your company's link to Sales.</span></span>
2. <span data-ttu-id="04e02-196">En la página que se abre, busque **organizationid**y anote el valor.</span><span class="sxs-lookup"><span data-stu-id="04e02-196">On the page that is opened, find **organizationid**, and make a note of the value.</span></span>

    ![Cómo encontrar organizationid](media/sales-map-orgid.png)

3. <span data-ttu-id="04e02-198">En Sales, abra la consola del explorador y ejecute el siguiente script.</span><span class="sxs-lookup"><span data-stu-id="04e02-198">In Sales, open the browser console, and run following script.</span></span> <span data-ttu-id="04e02-199">Use el valor **organizationid** del paso 2.</span><span class="sxs-lookup"><span data-stu-id="04e02-199">Use the **organizationid** value from step 2.</span></span>

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

4. <span data-ttu-id="04e02-201">Compruebe que **IsSOPIntegrationEnabled** está establecido en **true**.</span><span class="sxs-lookup"><span data-stu-id="04e02-201">Verify that **IsSOPIntegrationEnabled** is set to **true**.</span></span> <span data-ttu-id="04e02-202">Use la dirección URL del paso 1 para comprobar el valor.</span><span class="sxs-lookup"><span data-stu-id="04e02-202">Use the URL from step 1 to check the value.</span></span>

    ![IsSOPIntegrationEnabled establecido en true.](media/sales-map-integration-enabled.png)

<span data-ttu-id="04e02-204">Para habilitar el atributo **isIntegrationUser**, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="04e02-204">To enable the **isIntegrationUser** attribute, follow these steps.</span></span>

1. <span data-ttu-id="04e02-205">En Sales, vaya a **Configuración \> Personalización \> Personaliza el sistema**, seleccione **Entidad de usuario** y abra **Formulario \> Usuario**.</span><span class="sxs-lookup"><span data-stu-id="04e02-205">In Sales, go to **Setting \> Customization \> Customize the System**, select **User entity**, and then open **Form \> User**.</span></span>

    ![Abrir el formulario de usuario](media/sales-map-user.png)

2. <span data-ttu-id="04e02-207">En el explorador de campos, busque **Modo de usuario de integración** y haga doble clic en él para agregarlo al formulario.</span><span class="sxs-lookup"><span data-stu-id="04e02-207">In Field Explorer, find **Integration user mode**, and double-click it to add it to the form.</span></span> <span data-ttu-id="04e02-208">Guarde el cambio.</span><span class="sxs-lookup"><span data-stu-id="04e02-208">Save your change.</span></span>

    ![Agregar el campo Modo de usuario de integración al formulario](media/sales-map-field-explorer.png)

3. <span data-ttu-id="04e02-210">En Sales, vaya a **Configuración \> Seguridad \> Usuarios** y cambie la vista de **Usuarios habilitados** a **Usuarios de la aplicación**.</span><span class="sxs-lookup"><span data-stu-id="04e02-210">In Sales, go to **Setting \> Security \> Users**, and change the view from **Enabled Users** to **Application Users**.</span></span>

    ![Cambiar la vista de usuarios habilitados a usuarios de aplicaciones](media/sales-map-enabled-users.png)

4. <span data-ttu-id="04e02-212">Seleccione las dos entradas para **DualWrite IntegrationUser**.</span><span class="sxs-lookup"><span data-stu-id="04e02-212">Select the two entries for **DualWrite IntegrationUser**.</span></span>

    ![Lista de usuarios de aplicación](media/sales-map-user-mode.png)

5. <span data-ttu-id="04e02-214">Cambie el valor del campo **Modo de usuario de integración** a **Sí**.</span><span class="sxs-lookup"><span data-stu-id="04e02-214">Change the value of the **Integration user mode** field to **Yes**.</span></span>

    ![Cambiar el valor del campo Modo de usuario de integración](media/sales-map-user-mode-yes.png)

<span data-ttu-id="04e02-216">Ahora los pedidos de ventas están asignados.</span><span class="sxs-lookup"><span data-stu-id="04e02-216">Your sales orders are now mapped.</span></span>
