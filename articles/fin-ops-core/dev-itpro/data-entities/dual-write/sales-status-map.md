---
title: Configurar la asignación de las columnas de estado del pedido de ventas
description: Este tema explica cómo configurar las columnas de estado de pedido de ventas para doble escritura.
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
ms.openlocfilehash: cc70501d231390ea15104d508a36300a1b2cd44c
ms.sourcegitcommit: 7e1be696894731e1c58074d9b5e9c5b3acf7e52a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "4744308"
---
# <a name="set-up-the-mapping-for-the-sales-order-status-columns"></a><span data-ttu-id="42bd3-103">Configurar la asignación de las columnas de estado del pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="42bd3-103">Set up the mapping for the sales order status columns</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="42bd3-104">Las columnas que indican el estado del pedido de ventas tienen distintos valores de enumeración en Microsoft Dynamics 365 Supply Chain Management y en Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="42bd3-104">The columns that indicate sales order status have different enumeration values in Microsoft Dynamics 365 Supply Chain Management and Dynamics 365 Sales.</span></span> <span data-ttu-id="42bd3-105">Se requiere una configuración adicional para asignar estas columnas en doble escritura.</span><span class="sxs-lookup"><span data-stu-id="42bd3-105">Additional setup is required to map these columns in dual-write.</span></span>

## <a name="columns-in-supply-chain-management"></a><span data-ttu-id="42bd3-106">columnas en Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="42bd3-106">columns in Supply Chain Management</span></span>

<span data-ttu-id="42bd3-107">En Supply Chain Management, dos columnas reflejan el estado del pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="42bd3-107">In Supply Chain Management, two columns reflect the status of the sales order.</span></span> <span data-ttu-id="42bd3-108">Las columnas que debe asignar son **Estado** y **Estado del documento**.</span><span class="sxs-lookup"><span data-stu-id="42bd3-108">The columns that you must map are **Status** and **Document Status**.</span></span>

<span data-ttu-id="42bd3-109">La enumeración **Estado** especifica el estado general del pedido.</span><span class="sxs-lookup"><span data-stu-id="42bd3-109">The **Status** enumeration specifies the overall status of the order.</span></span> <span data-ttu-id="42bd3-110">Este estado se muestra en el encabezado del pedido.</span><span class="sxs-lookup"><span data-stu-id="42bd3-110">This status is shown on the order header.</span></span>

<span data-ttu-id="42bd3-111">La enumeración **Estado** tiene los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="42bd3-111">The **Status** enumeration has the following values:</span></span>

- <span data-ttu-id="42bd3-112">Pedido abierto</span><span class="sxs-lookup"><span data-stu-id="42bd3-112">Open Order</span></span>
- <span data-ttu-id="42bd3-113">Entregado</span><span class="sxs-lookup"><span data-stu-id="42bd3-113">Delivered</span></span>
- <span data-ttu-id="42bd3-114">Facturado</span><span class="sxs-lookup"><span data-stu-id="42bd3-114">Invoiced</span></span>
- <span data-ttu-id="42bd3-115">Cancelada</span><span class="sxs-lookup"><span data-stu-id="42bd3-115">Cancelled</span></span>

<span data-ttu-id="42bd3-116">La enumeración **Estado del documento** especifica el documento más reciente que se generó para el pedido.</span><span class="sxs-lookup"><span data-stu-id="42bd3-116">The **Document Status** enumeration specifies the most recent document that was generated for the order.</span></span> <span data-ttu-id="42bd3-117">Por ejemplo, si se confirma el pedido, este documento es una confirmación de pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="42bd3-117">For example, if the order is confirmed, this document is a sales order confirmation.</span></span> <span data-ttu-id="42bd3-118">Si un pedido de ventas se factura parcialmente y después se confirma la línea restante, el estado del documento sigue siendo **Factura**, ya que la factura se genera posteriormente en el proceso.</span><span class="sxs-lookup"><span data-stu-id="42bd3-118">If a sales order is partially invoiced, and then the remaining line is confirmed, the document status remains **Invoice**, because the invoice is generated later in the process.</span></span>

<span data-ttu-id="42bd3-119">La enumeración **Estado del documento** tiene los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="42bd3-119">The **Document Status** enumeration has the following values:</span></span>

- <span data-ttu-id="42bd3-120">Confirmación</span><span class="sxs-lookup"><span data-stu-id="42bd3-120">Confirmation</span></span>
- <span data-ttu-id="42bd3-121">Lista de selección</span><span class="sxs-lookup"><span data-stu-id="42bd3-121">Picking List</span></span>
- <span data-ttu-id="42bd3-122">Albarán</span><span class="sxs-lookup"><span data-stu-id="42bd3-122">Packing Slip</span></span>
- <span data-ttu-id="42bd3-123">Factura</span><span class="sxs-lookup"><span data-stu-id="42bd3-123">Invoice</span></span>

## <a name="columns-in-sales"></a><span data-ttu-id="42bd3-124">columnas en Ventas</span><span class="sxs-lookup"><span data-stu-id="42bd3-124">columns in Sales</span></span>

<span data-ttu-id="42bd3-125">En Ventas, dos columnas indican el estado del pedido.</span><span class="sxs-lookup"><span data-stu-id="42bd3-125">In Sales, two columns indicate the status of the order.</span></span> <span data-ttu-id="42bd3-126">Las columnas que debe asignar son **Estado** y **Estado de procesamiento**.</span><span class="sxs-lookup"><span data-stu-id="42bd3-126">The columns that you must map are **Status** and **Processing Status**.</span></span>

<span data-ttu-id="42bd3-127">La enumeración **Estado** especifica el estado general del pedido.</span><span class="sxs-lookup"><span data-stu-id="42bd3-127">The **Status** enumeration specifies the overall status of the order.</span></span> <span data-ttu-id="42bd3-128">Tiene los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="42bd3-128">It has the following values:</span></span>

- <span data-ttu-id="42bd3-129">Activa</span><span class="sxs-lookup"><span data-stu-id="42bd3-129">Active</span></span>
- <span data-ttu-id="42bd3-130">Emitido</span><span class="sxs-lookup"><span data-stu-id="42bd3-130">Submitted</span></span>
- <span data-ttu-id="42bd3-131">Cumplido</span><span class="sxs-lookup"><span data-stu-id="42bd3-131">Fulfilled</span></span>
- <span data-ttu-id="42bd3-132">Facturado</span><span class="sxs-lookup"><span data-stu-id="42bd3-132">Invoiced</span></span>
- <span data-ttu-id="42bd3-133">Cancelada</span><span class="sxs-lookup"><span data-stu-id="42bd3-133">Cancelled</span></span>

<span data-ttu-id="42bd3-134">Se ha incluido la enumeración **Estado de procesamiento** para que el estado se pueda asignar de forma más precisa con Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="42bd3-134">The **Processing Status** enumeration was introduced so that the status can be mapped more accurately with Supply Chain Management.</span></span>

<span data-ttu-id="42bd3-135">La siguiente tabla muestra la asignación de **Estado de procesamiento** en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="42bd3-135">The following table shows the mapping of **Processing Status** in Supply Chain Management.</span></span>

| <span data-ttu-id="42bd3-136">Estado de procesamiento</span><span class="sxs-lookup"><span data-stu-id="42bd3-136">Processing Status</span></span>   | <span data-ttu-id="42bd3-137">Estado en Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="42bd3-137">Status in Supply Chain Management</span></span> | <span data-ttu-id="42bd3-138">Estado del documento en Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="42bd3-138">Document Status in Supply Chain Management</span></span> |
|---------------------|-----------------------------------|--------------------------------------------|
| <span data-ttu-id="42bd3-139">Activa</span><span class="sxs-lookup"><span data-stu-id="42bd3-139">Active</span></span>              | <span data-ttu-id="42bd3-140">Pedido abierto</span><span class="sxs-lookup"><span data-stu-id="42bd3-140">Open Order</span></span>                        | <span data-ttu-id="42bd3-141">None</span><span class="sxs-lookup"><span data-stu-id="42bd3-141">None</span></span>                                       |
| <span data-ttu-id="42bd3-142">Confirmado</span><span class="sxs-lookup"><span data-stu-id="42bd3-142">Confirmed</span></span>           | <span data-ttu-id="42bd3-143">Pedido abierto</span><span class="sxs-lookup"><span data-stu-id="42bd3-143">Open Order</span></span>                        | <span data-ttu-id="42bd3-144">Confirmación</span><span class="sxs-lookup"><span data-stu-id="42bd3-144">Confirmation</span></span>                               |
| <span data-ttu-id="42bd3-145">Seleccionado</span><span class="sxs-lookup"><span data-stu-id="42bd3-145">Picked</span></span>              | <span data-ttu-id="42bd3-146">Pedido abierto</span><span class="sxs-lookup"><span data-stu-id="42bd3-146">Open Order</span></span>                        | <span data-ttu-id="42bd3-147">Lista de selección</span><span class="sxs-lookup"><span data-stu-id="42bd3-147">Picking List</span></span>                               |
| <span data-ttu-id="42bd3-148">Parcialmente entregado</span><span class="sxs-lookup"><span data-stu-id="42bd3-148">Partially Delivered</span></span> | <span data-ttu-id="42bd3-149">Pedido abierto</span><span class="sxs-lookup"><span data-stu-id="42bd3-149">Open Order</span></span>                        | <span data-ttu-id="42bd3-150">Albarán</span><span class="sxs-lookup"><span data-stu-id="42bd3-150">Packing Slip</span></span>                               |
| <span data-ttu-id="42bd3-151">Entregado</span><span class="sxs-lookup"><span data-stu-id="42bd3-151">Delivered</span></span>           | <span data-ttu-id="42bd3-152">Entregado</span><span class="sxs-lookup"><span data-stu-id="42bd3-152">Delivered</span></span>                         | <span data-ttu-id="42bd3-153">Albarán</span><span class="sxs-lookup"><span data-stu-id="42bd3-153">Packing Slip</span></span>                               |
| <span data-ttu-id="42bd3-154">Parcialmente facturado</span><span class="sxs-lookup"><span data-stu-id="42bd3-154">Partially Invoiced</span></span>  | <span data-ttu-id="42bd3-155">Entregado</span><span class="sxs-lookup"><span data-stu-id="42bd3-155">Delivered</span></span>                         | <span data-ttu-id="42bd3-156">Factura</span><span class="sxs-lookup"><span data-stu-id="42bd3-156">Invoice</span></span>                                    |
| <span data-ttu-id="42bd3-157">Facturado</span><span class="sxs-lookup"><span data-stu-id="42bd3-157">Invoiced</span></span>            | <span data-ttu-id="42bd3-158">Facturado</span><span class="sxs-lookup"><span data-stu-id="42bd3-158">Invoiced</span></span>                          | <span data-ttu-id="42bd3-159">Factura</span><span class="sxs-lookup"><span data-stu-id="42bd3-159">Invoice</span></span>                                    |
| <span data-ttu-id="42bd3-160">Cancelada</span><span class="sxs-lookup"><span data-stu-id="42bd3-160">Cancelled</span></span>           | <span data-ttu-id="42bd3-161">Cancelada</span><span class="sxs-lookup"><span data-stu-id="42bd3-161">Cancelled</span></span>                         | <span data-ttu-id="42bd3-162">No aplicable</span><span class="sxs-lookup"><span data-stu-id="42bd3-162">Not applicable</span></span>                             |

<span data-ttu-id="42bd3-163">En la tabla siguiente se muestra la asignación de **Estado de procesamiento** entre Sales y Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="42bd3-163">The following table shows the mapping of **Processing Status** between Sales and Supply Chain Management.</span></span>

| <span data-ttu-id="42bd3-164">Estado de procesamiento</span><span class="sxs-lookup"><span data-stu-id="42bd3-164">Processing Status</span></span>   | <span data-ttu-id="42bd3-165">Estado en Sales</span><span class="sxs-lookup"><span data-stu-id="42bd3-165">Status in Sales</span></span> | <span data-ttu-id="42bd3-166">Estado en Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="42bd3-166">Status in Supply Chain Management</span></span> |
|---------------------|-----------------|-----------------------------------|
| <span data-ttu-id="42bd3-167">Activa</span><span class="sxs-lookup"><span data-stu-id="42bd3-167">Active</span></span>              | <span data-ttu-id="42bd3-168">Activa</span><span class="sxs-lookup"><span data-stu-id="42bd3-168">Active</span></span>          | <span data-ttu-id="42bd3-169">Pedido abierto</span><span class="sxs-lookup"><span data-stu-id="42bd3-169">Open Order</span></span>                        |
| <span data-ttu-id="42bd3-170">Confirmado</span><span class="sxs-lookup"><span data-stu-id="42bd3-170">Confirmed</span></span>           | <span data-ttu-id="42bd3-171">Emitido</span><span class="sxs-lookup"><span data-stu-id="42bd3-171">Submitted</span></span>       | <span data-ttu-id="42bd3-172">Pedido abierto</span><span class="sxs-lookup"><span data-stu-id="42bd3-172">Open Order</span></span>                        |
| <span data-ttu-id="42bd3-173">Seleccionado</span><span class="sxs-lookup"><span data-stu-id="42bd3-173">Picked</span></span>              | <span data-ttu-id="42bd3-174">Emitido</span><span class="sxs-lookup"><span data-stu-id="42bd3-174">Submitted</span></span>       | <span data-ttu-id="42bd3-175">Pedido abierto</span><span class="sxs-lookup"><span data-stu-id="42bd3-175">Open Order</span></span>                        |
| <span data-ttu-id="42bd3-176">Parcialmente entregado</span><span class="sxs-lookup"><span data-stu-id="42bd3-176">Partially Delivered</span></span> | <span data-ttu-id="42bd3-177">Activa</span><span class="sxs-lookup"><span data-stu-id="42bd3-177">Active</span></span>          | <span data-ttu-id="42bd3-178">Pedido abierto</span><span class="sxs-lookup"><span data-stu-id="42bd3-178">Open Order</span></span>                        |
| <span data-ttu-id="42bd3-179">Parcialmente facturado</span><span class="sxs-lookup"><span data-stu-id="42bd3-179">Partially Invoiced</span></span>  | <span data-ttu-id="42bd3-180">Activa</span><span class="sxs-lookup"><span data-stu-id="42bd3-180">Active</span></span>          | <span data-ttu-id="42bd3-181">Pedido abierto</span><span class="sxs-lookup"><span data-stu-id="42bd3-181">Open Order</span></span>                        |
| <span data-ttu-id="42bd3-182">Parcialmente facturado</span><span class="sxs-lookup"><span data-stu-id="42bd3-182">Partially Invoiced</span></span>  | <span data-ttu-id="42bd3-183">Cumplido</span><span class="sxs-lookup"><span data-stu-id="42bd3-183">Fulfilled</span></span>       | <span data-ttu-id="42bd3-184">Entregado</span><span class="sxs-lookup"><span data-stu-id="42bd3-184">Delivered</span></span>                         |
| <span data-ttu-id="42bd3-185">Facturado</span><span class="sxs-lookup"><span data-stu-id="42bd3-185">Invoiced</span></span>            | <span data-ttu-id="42bd3-186">Facturado</span><span class="sxs-lookup"><span data-stu-id="42bd3-186">Invoiced</span></span>        | <span data-ttu-id="42bd3-187">Facturado</span><span class="sxs-lookup"><span data-stu-id="42bd3-187">Invoiced</span></span>                          |
| <span data-ttu-id="42bd3-188">Cancelada</span><span class="sxs-lookup"><span data-stu-id="42bd3-188">Cancelled</span></span>           | <span data-ttu-id="42bd3-189">Cancelada</span><span class="sxs-lookup"><span data-stu-id="42bd3-189">Cancelled</span></span>       | <span data-ttu-id="42bd3-190">Cancelada</span><span class="sxs-lookup"><span data-stu-id="42bd3-190">Cancelled</span></span>                         |

## <a name="setup"></a><span data-ttu-id="42bd3-191">Configurar</span><span class="sxs-lookup"><span data-stu-id="42bd3-191">Setup</span></span>

<span data-ttu-id="42bd3-192">Para configurar la asignación para las columnas de estado del pedido de ventas, debe habilitar los atributos **IsSOPIntegrationEnabled** y **isIntegrationUser**.</span><span class="sxs-lookup"><span data-stu-id="42bd3-192">To set up the mapping for the sales order status columns, you must enable the **IsSOPIntegrationEnabled** and **isIntegrationUser** attributes.</span></span>

<span data-ttu-id="42bd3-193">Para habilitar el atributo **IsSOPIntegrationEnabled**, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="42bd3-193">To enable the **IsSOPIntegrationEnabled** attribute, follow these steps.</span></span>

1. <span data-ttu-id="42bd3-194">En un explorador, vaya a `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations`.</span><span class="sxs-lookup"><span data-stu-id="42bd3-194">In a browser, go to `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations`.</span></span> <span data-ttu-id="42bd3-195">Reemplace **\<test-name\>** con el enlace de su empresa en Sales.</span><span class="sxs-lookup"><span data-stu-id="42bd3-195">Replace **\<test-name\>** with your company's link to Sales.</span></span>
2. <span data-ttu-id="42bd3-196">En la página que se abre, busque **organizationid** y anote el valor.</span><span class="sxs-lookup"><span data-stu-id="42bd3-196">On the page that is opened, find **organizationid**, and make a note of the value.</span></span>

    ![Cómo encontrar organizationid](media/sales-map-orgid.png)

3. <span data-ttu-id="42bd3-198">En Sales, abra la consola del explorador y ejecute el siguiente script.</span><span class="sxs-lookup"><span data-stu-id="42bd3-198">In Sales, open the browser console, and run following script.</span></span> <span data-ttu-id="42bd3-199">Use el valor **organizationid** del paso 2.</span><span class="sxs-lookup"><span data-stu-id="42bd3-199">Use the **organizationid** value from step 2.</span></span>

    ```javascript
    Xrm.WebApi.updateRecord("organization",
    "d9a7c5f7-acbf-4aa9-86e8-a891c43f748c", {"issopintegrationenabled" :
    true}).then(
        function success(result) {
            console.log("Account updated");
            // perform operations on row update
        },
        function (error) {
            console.log(error.message);
            // handle error conditions
        }
    );
    ```

    ![Código JavaScript en la consola del explorador](media/sales-map-script.png)

4. <span data-ttu-id="42bd3-201">Compruebe que **IsSOPIntegrationEnabled** está establecido en **true**.</span><span class="sxs-lookup"><span data-stu-id="42bd3-201">Verify that **IsSOPIntegrationEnabled** is set to **true**.</span></span> <span data-ttu-id="42bd3-202">Use la dirección URL del paso 1 para comprobar el valor.</span><span class="sxs-lookup"><span data-stu-id="42bd3-202">Use the URL from step 1 to check the value.</span></span>

    ![IsSOPIntegrationEnabled establecido en true.](media/sales-map-integration-enabled.png)

<span data-ttu-id="42bd3-204">Para habilitar el atributo **isIntegrationUser**, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="42bd3-204">To enable the **isIntegrationUser** attribute, follow these steps.</span></span>

1. <span data-ttu-id="42bd3-205">En Sales, vaya a **Configuración \> Personalización \> Personaliza el sistema**, seleccione **Tabla de usuario** y abra **Formulario \> Usuario**.</span><span class="sxs-lookup"><span data-stu-id="42bd3-205">In Sales, go to **Setting \> Customization \> Customize the System**, select **User table**, and then open **Form \> User**.</span></span>

    ![Abrir el formulario de usuario](media/sales-map-user.png)

2. <span data-ttu-id="42bd3-207">En el explorador de campos, busque **Modo de usuario de integración** y haga doble clic en él para agregarlo al formulario.</span><span class="sxs-lookup"><span data-stu-id="42bd3-207">In Field Explorer, find **Integration user mode**, and double-click it to add it to the form.</span></span> <span data-ttu-id="42bd3-208">Guarde el cambio.</span><span class="sxs-lookup"><span data-stu-id="42bd3-208">Save your change.</span></span>

    ![Agregar la columna Modo de usuario de integración al formulario](media/sales-map-field-explorer.png)

3. <span data-ttu-id="42bd3-210">En Sales, vaya a **Configuración \> Seguridad \> Usuarios** y cambie la vista de **Usuarios habilitados** a **Usuarios de la aplicación**.</span><span class="sxs-lookup"><span data-stu-id="42bd3-210">In Sales, go to **Setting \> Security \> Users**, and change the view from **Enabled Users** to **Application Users**.</span></span>

    ![Cambiar la vista de usuarios habilitados a usuarios de aplicaciones](media/sales-map-enabled-users.png)

4. <span data-ttu-id="42bd3-212">Seleccione las dos entradas para **DualWrite IntegrationUser**.</span><span class="sxs-lookup"><span data-stu-id="42bd3-212">Select the two entries for **DualWrite IntegrationUser**.</span></span>

    ![Lista de usuarios de aplicación](media/sales-map-user-mode.png)

5. <span data-ttu-id="42bd3-214">Cambie el valor de la columna **Modo de usuario de integración** a **Sí**.</span><span class="sxs-lookup"><span data-stu-id="42bd3-214">Change the value of the **Integration user mode** column to **Yes**.</span></span>

    ![Cambiar el valor de la columna Modo de usuario de integración](media/sales-map-user-mode-yes.png)

<span data-ttu-id="42bd3-216">Ahora los pedidos de ventas están asignados.</span><span class="sxs-lookup"><span data-stu-id="42bd3-216">Your sales orders are now mapped.</span></span>
