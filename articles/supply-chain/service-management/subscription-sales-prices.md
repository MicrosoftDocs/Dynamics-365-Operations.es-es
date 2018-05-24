---
title: "Precios de venta de suscripción"
description: "Al crear una suscripción, el precio de ventas deriva de la configuración de precio de ventas que se creó en el formulario Precio de venta (suscripción)."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMASalespriceSubscription
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: d9d462121915ce3f800581a9540dc1ef8f6e785f
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---

# <a name="subscription-sales-prices"></a><span data-ttu-id="20fe9-103">Precios de venta de suscripción</span><span class="sxs-lookup"><span data-stu-id="20fe9-103">Subscription sales prices</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="20fe9-104">Al crear una suscripción, el precio de ventas deriva de la configuración de precio de ventas que se creó en el formulario **Precio de venta (suscripción)**.</span><span class="sxs-lookup"><span data-stu-id="20fe9-104">When you create a subscription, the sales price is derived from the sales price setup that was created in the **Sales price (subscription)** form.</span></span>

<span data-ttu-id="20fe9-105">En el formulario **Precio de venta (suscripción)**, puede crear precios de ventas para una suscripción específica o crear precios de ventas que se apliquen de manera más amplia.</span><span class="sxs-lookup"><span data-stu-id="20fe9-105">In the **Sales price (subscription)** form, you can create sales prices for a specific subscription or you can create sales prices that apply more broadly.</span></span> <span data-ttu-id="20fe9-106">Para que se aplique un precio de ventas a una suscripción, el código de período y la divisa de la suscripción deben ser idénticos al código de período y a la divisa del precio de ventas.</span><span class="sxs-lookup"><span data-stu-id="20fe9-106">For a sales price to be applied to a subscription, the period code and the currency of the subscription must be identical to the period code and the currency of the sales price.</span></span>

<span data-ttu-id="20fe9-107">Si el código de período y la divisa son idénticos tanto para la suscripción como para el precio de ventas, los precios de venta de suscripción se seleccionan basándose en las prioridades que aparecen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="20fe9-107">If the period code and currency are identical for the subscription and the sales price, subscription sales prices are selected on the basis of the priorities listed in the following table.</span></span> <span data-ttu-id="20fe9-108">Una celda en blanco en la tabla indica un campo vacío, mientras que X indica un valor igual al valor de la suscripción a partir de la cual se genera la transacción.</span><span class="sxs-lookup"><span data-stu-id="20fe9-108">A blank cell in the table indicates an empty field and an X indicates a value that is equal to the value in the subscription from which the transaction is generated.</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="20fe9-109">Prioridad</span><span class="sxs-lookup"><span data-stu-id="20fe9-109">Priority</span></span></p></th>
<th><p><span data-ttu-id="20fe9-110"><strong>Categoría</strong></span><span class="sxs-lookup"><span data-stu-id="20fe9-110"><strong>Category</strong></span></span></p></th>
<th><p><span data-ttu-id="20fe9-111"><strong>Id. de proyecto</strong></span><span class="sxs-lookup"><span data-stu-id="20fe9-111"><strong>Project ID</strong></span></span></p></th>
<th><p><span data-ttu-id="20fe9-112"><strong>Suscripción</strong></span><span class="sxs-lookup"><span data-stu-id="20fe9-112"><strong>Subscription</strong></span></span></p></th>
<th><p><span data-ttu-id="20fe9-113"><strong>Divisa de ventas</strong></span><span class="sxs-lookup"><span data-stu-id="20fe9-113"><strong>Sales currency</strong></span></span></p></th>
<th><p><span data-ttu-id="20fe9-114"><strong>Código del período</strong></span><span class="sxs-lookup"><span data-stu-id="20fe9-114"><strong>Period code</strong></span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20fe9-115">1</span><span class="sxs-lookup"><span data-stu-id="20fe9-115">1</span></span></p></td>
<td><p><span data-ttu-id="20fe9-116">X</span><span class="sxs-lookup"><span data-stu-id="20fe9-116">X</span></span></p></td>
<td><p><span data-ttu-id="20fe9-117">X</span><span class="sxs-lookup"><span data-stu-id="20fe9-117">X</span></span></p></td>
<td><p><span data-ttu-id="20fe9-118">X</span><span class="sxs-lookup"><span data-stu-id="20fe9-118">X</span></span></p></td>
<td><p><span data-ttu-id="20fe9-119">X</span><span class="sxs-lookup"><span data-stu-id="20fe9-119">X</span></span></p></td>
<td><p><span data-ttu-id="20fe9-120">X</span><span class="sxs-lookup"><span data-stu-id="20fe9-120">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20fe9-121">2</span><span class="sxs-lookup"><span data-stu-id="20fe9-121">2</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="20fe9-122">X</span><span class="sxs-lookup"><span data-stu-id="20fe9-122">X</span></span></p></td>
<td><p><span data-ttu-id="20fe9-123">X</span><span class="sxs-lookup"><span data-stu-id="20fe9-123">X</span></span></p></td>
<td><p><span data-ttu-id="20fe9-124">X</span><span class="sxs-lookup"><span data-stu-id="20fe9-124">X</span></span></p></td>
<td><p><span data-ttu-id="20fe9-125">X</span><span class="sxs-lookup"><span data-stu-id="20fe9-125">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20fe9-126">3</span><span class="sxs-lookup"><span data-stu-id="20fe9-126">3</span></span></p></td>
<td><p><span data-ttu-id="20fe9-127">X</span><span class="sxs-lookup"><span data-stu-id="20fe9-127">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="20fe9-128">X</span><span class="sxs-lookup"><span data-stu-id="20fe9-128">X</span></span></p></td>
<td><p><span data-ttu-id="20fe9-129">X</span><span class="sxs-lookup"><span data-stu-id="20fe9-129">X</span></span></p></td>
<td><p><span data-ttu-id="20fe9-130">X</span><span class="sxs-lookup"><span data-stu-id="20fe9-130">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20fe9-131">4</span><span class="sxs-lookup"><span data-stu-id="20fe9-131">4</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="20fe9-132">X</span><span class="sxs-lookup"><span data-stu-id="20fe9-132">X</span></span></p></td>
<td><p><span data-ttu-id="20fe9-133">X</span><span class="sxs-lookup"><span data-stu-id="20fe9-133">X</span></span></p></td>
<td><p><span data-ttu-id="20fe9-134">X</span><span class="sxs-lookup"><span data-stu-id="20fe9-134">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20fe9-135">5</span><span class="sxs-lookup"><span data-stu-id="20fe9-135">5</span></span></p></td>
<td><p><span data-ttu-id="20fe9-136">X</span><span class="sxs-lookup"><span data-stu-id="20fe9-136">X</span></span></p></td>
<td><p><span data-ttu-id="20fe9-137">X</span><span class="sxs-lookup"><span data-stu-id="20fe9-137">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="20fe9-138">X</span><span class="sxs-lookup"><span data-stu-id="20fe9-138">X</span></span></p></td>
<td><p><span data-ttu-id="20fe9-139">X</span><span class="sxs-lookup"><span data-stu-id="20fe9-139">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20fe9-140">6</span><span class="sxs-lookup"><span data-stu-id="20fe9-140">6</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="20fe9-141">X</span><span class="sxs-lookup"><span data-stu-id="20fe9-141">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="20fe9-142">X</span><span class="sxs-lookup"><span data-stu-id="20fe9-142">X</span></span></p></td>
<td><p><span data-ttu-id="20fe9-143">X</span><span class="sxs-lookup"><span data-stu-id="20fe9-143">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20fe9-144">7</span><span class="sxs-lookup"><span data-stu-id="20fe9-144">7</span></span></p></td>
<td><p><span data-ttu-id="20fe9-145">X</span><span class="sxs-lookup"><span data-stu-id="20fe9-145">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="20fe9-146">X</span><span class="sxs-lookup"><span data-stu-id="20fe9-146">X</span></span></p></td>
<td><p><span data-ttu-id="20fe9-147">X</span><span class="sxs-lookup"><span data-stu-id="20fe9-147">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20fe9-148">8</span><span class="sxs-lookup"><span data-stu-id="20fe9-148">8</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="20fe9-149">X</span><span class="sxs-lookup"><span data-stu-id="20fe9-149">X</span></span></p></td>
<td><p><span data-ttu-id="20fe9-150">X</span><span class="sxs-lookup"><span data-stu-id="20fe9-150">X</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="20fe9-151">Cuando se crea una cuota de suscripción, el precio de ventas con el mayor nivel de detalles (como se indica en la tabla anterior) se selecciona como precio de ventas de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="20fe9-151">When a subscription fee is created, the sales price with the greatest level of detail, as noted in the table above, is selected as the subscription sales price.</span></span>

## <a name="update-and-index-subscription-sales-prices"></a><span data-ttu-id="20fe9-152">Actualizar e indexar precios de ventas de la suscripción</span><span class="sxs-lookup"><span data-stu-id="20fe9-152">Update and index subscription sales prices</span></span>

<span data-ttu-id="20fe9-153">Puede actualizar el precio de ventas de la suscripción actualizando el precio base o el índice.</span><span class="sxs-lookup"><span data-stu-id="20fe9-153">You can update the subscription sales price by updating the base price or the index.</span></span> <span data-ttu-id="20fe9-154">Puede actualizar según un porcentaje o a un valor nuevo.</span><span class="sxs-lookup"><span data-stu-id="20fe9-154">You can update by a percentage or to a new value.</span></span>

## <a name="subscription-fee-sales-prices"></a><span data-ttu-id="20fe9-155">Precios de venta de las cuotas de suscripción</span><span class="sxs-lookup"><span data-stu-id="20fe9-155">Subscription fee sales prices</span></span>

<span data-ttu-id="20fe9-156">Al crear una cuota de suscripción, el precio de ventas se basa en la configuración de precio de ventas de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="20fe9-156">When you create a subscription fee, the sales price is based on the sales price setup of the subscription.</span></span> <span data-ttu-id="20fe9-157">Puede usar el precio de base a partir de la configuración de precio de suscripción, o bien crear precios de venta indexados.</span><span class="sxs-lookup"><span data-stu-id="20fe9-157">You can either use the base price from the subscription price setup or create indexed sales prices.</span></span>

## <a name="example"></a><span data-ttu-id="20fe9-158">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="20fe9-158">Example</span></span>

<span data-ttu-id="20fe9-159">Desea configurar precios de venta de suscripción de 500 EUR para un nuevo proyecto 9030.</span><span class="sxs-lookup"><span data-stu-id="20fe9-159">You want to set up subscription sales prices of EUR 500 for a new project 9030.</span></span> <span data-ttu-id="20fe9-160">En el formulario **Precio de venta (suscripción)**, crea una línea de precio de ventas de suscripción como se indica en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="20fe9-160">In the **Sales price (subscription)** form, you create a subscription sales price line as indicated in the following table.</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="20fe9-161">Válido desde</span><span class="sxs-lookup"><span data-stu-id="20fe9-161">Valid from</span></span></p></th>
<th><p><span data-ttu-id="20fe9-162">Categoría</span><span class="sxs-lookup"><span data-stu-id="20fe9-162">Category</span></span></p></th>
<th><p><span data-ttu-id="20fe9-163">Proyecto</span><span class="sxs-lookup"><span data-stu-id="20fe9-163">Project</span></span></p></th>
<th><p><span data-ttu-id="20fe9-164">Suscripción</span><span class="sxs-lookup"><span data-stu-id="20fe9-164">Subscription</span></span></p></th>
<th><p><span data-ttu-id="20fe9-165">Código del período</span><span class="sxs-lookup"><span data-stu-id="20fe9-165">Period code</span></span></p></th>
<th><p><span data-ttu-id="20fe9-166">Divisa de ventas</span><span class="sxs-lookup"><span data-stu-id="20fe9-166">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="20fe9-167">Precio de venta</span><span class="sxs-lookup"><span data-stu-id="20fe9-167">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20fe9-168">28-08-2006</span><span class="sxs-lookup"><span data-stu-id="20fe9-168">28-08-2006</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="20fe9-169">9030</span><span class="sxs-lookup"><span data-stu-id="20fe9-169">9030</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="20fe9-170">Mes</span><span class="sxs-lookup"><span data-stu-id="20fe9-170">Month</span></span></p></td>
<td><p><span data-ttu-id="20fe9-171">EUR</span><span class="sxs-lookup"><span data-stu-id="20fe9-171">EUR</span></span></p></td>
<td><p><span data-ttu-id="20fe9-172">500</span><span class="sxs-lookup"><span data-stu-id="20fe9-172">500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="20fe9-173">Tenga en cuenta que los campos **Categoría** y **Suscripción** están vacíos.</span><span class="sxs-lookup"><span data-stu-id="20fe9-173">Note that the **Category** and **Subscription** fields are empty.</span></span>

<span data-ttu-id="20fe9-174">A continuación, cree las siguientes suscripciones:</span><span class="sxs-lookup"><span data-stu-id="20fe9-174">You then create the following subscriptions.</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="20fe9-175">Suscripción de servicio</span><span class="sxs-lookup"><span data-stu-id="20fe9-175">Service subscription</span></span></p></th>
<th><p><span data-ttu-id="20fe9-176">Proyecto</span><span class="sxs-lookup"><span data-stu-id="20fe9-176">Project</span></span></p></th>
<th><p><span data-ttu-id="20fe9-177">Grupo de suscripciones</span><span class="sxs-lookup"><span data-stu-id="20fe9-177">Subscription group</span></span></p></th>
<th><p><span data-ttu-id="20fe9-178">Categoría</span><span class="sxs-lookup"><span data-stu-id="20fe9-178">Category</span></span></p></th>
<th><p><span data-ttu-id="20fe9-179">Divisa</span><span class="sxs-lookup"><span data-stu-id="20fe9-179">Currency</span></span></p></th>
<th><p><span data-ttu-id="20fe9-180">Código de período</span><span class="sxs-lookup"><span data-stu-id="20fe9-180">Period code</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20fe9-181">00020_135</span><span class="sxs-lookup"><span data-stu-id="20fe9-181">00020_135</span></span></p></td>
<td><p><span data-ttu-id="20fe9-182">9030</span><span class="sxs-lookup"><span data-stu-id="20fe9-182">9030</span></span></p></td>
<td><p><span data-ttu-id="20fe9-183">Sub1</span><span class="sxs-lookup"><span data-stu-id="20fe9-183">Sub1</span></span></p></td>
<td><p><span data-ttu-id="20fe9-184">SubCat1</span><span class="sxs-lookup"><span data-stu-id="20fe9-184">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="20fe9-185">EUR</span><span class="sxs-lookup"><span data-stu-id="20fe9-185">EUR</span></span></p></td>
<td><p><span data-ttu-id="20fe9-186">Mensual</span><span class="sxs-lookup"><span data-stu-id="20fe9-186">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20fe9-187">00021_135</span><span class="sxs-lookup"><span data-stu-id="20fe9-187">00021_135</span></span></p></td>
<td><p><span data-ttu-id="20fe9-188">9030</span><span class="sxs-lookup"><span data-stu-id="20fe9-188">9030</span></span></p></td>
<td><p><span data-ttu-id="20fe9-189">Sub1</span><span class="sxs-lookup"><span data-stu-id="20fe9-189">Sub1</span></span></p></td>
<td><p><span data-ttu-id="20fe9-190">SubCat2</span><span class="sxs-lookup"><span data-stu-id="20fe9-190">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="20fe9-191">EUR</span><span class="sxs-lookup"><span data-stu-id="20fe9-191">EUR</span></span></p></td>
<td><p><span data-ttu-id="20fe9-192">Mensual</span><span class="sxs-lookup"><span data-stu-id="20fe9-192">Monthly</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="20fe9-193">A continuación, cree cuotas de suscripción tanto para suscripciones como para el grupo de suscripciones Sub1:</span><span class="sxs-lookup"><span data-stu-id="20fe9-193">Now you create subscription fees for both subscriptions in the subscription group Sub1:</span></span>

1.  <span data-ttu-id="20fe9-194">Haga clic en **Gestión de servicio** \> **Configuración** \> **Suscripciones de servicio** \> **Grupos de suscripciones**.</span><span class="sxs-lookup"><span data-stu-id="20fe9-194">Click **Service management** \> **Setup** \> **Service subscriptions** \> **Subscription groups**.</span></span>

2.  <span data-ttu-id="20fe9-195">En el formulario **Grupos de suscripciones** , haga clic en **Función** \> **Crear cuota de suscripción**.</span><span class="sxs-lookup"><span data-stu-id="20fe9-195">In the **Subscription groups** form, click **Function** \> **Create subscription fee**.</span></span>

3.  <span data-ttu-id="20fe9-196">En el formulario **Crear cuota de suscripción**, especifique la información adecuada.</span><span class="sxs-lookup"><span data-stu-id="20fe9-196">In the **Create subscription fee** form, enter the appropriate information.</span></span> <span data-ttu-id="20fe9-197">Para obtener más información, vea [Crear transacciones de gastos de suscripción](create-subscription-fee-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="20fe9-197">For more information, see [Create subscription fee transactions](create-subscription-fee-transactions.md).</span></span>

<span data-ttu-id="20fe9-198">Se crean cuotas de suscripción con un precio de ventas de 500 EUR para ambas suscripciones, tal como se muestra en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="20fe9-198">Subscription fees that have a sales price of EUR 500 are created for both subscriptions, as shown in the following table.</span></span>

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="20fe9-199">Fecha del proyecto</span><span class="sxs-lookup"><span data-stu-id="20fe9-199">Project date</span></span></p></th>
<th><p><span data-ttu-id="20fe9-200">Suscripción de servicio</span><span class="sxs-lookup"><span data-stu-id="20fe9-200">Service subscription</span></span></p></th>
<th><p><span data-ttu-id="20fe9-201">Proyecto</span><span class="sxs-lookup"><span data-stu-id="20fe9-201">Project</span></span></p></th>
<th><p><span data-ttu-id="20fe9-202">Categoría</span><span class="sxs-lookup"><span data-stu-id="20fe9-202">Category</span></span></p></th>
<th><p><span data-ttu-id="20fe9-203">Fecha inicial</span><span class="sxs-lookup"><span data-stu-id="20fe9-203">Start date</span></span></p></th>
<th><p><span data-ttu-id="20fe9-204">Fecha final</span><span class="sxs-lookup"><span data-stu-id="20fe9-204">End date</span></span></p></th>
<th><p><span data-ttu-id="20fe9-205">Divisa de ventas</span><span class="sxs-lookup"><span data-stu-id="20fe9-205">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="20fe9-206">Precio de venta</span><span class="sxs-lookup"><span data-stu-id="20fe9-206">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20fe9-207">28-08-2006</span><span class="sxs-lookup"><span data-stu-id="20fe9-207">28-08-2006</span></span></p></td>
<td><p><span data-ttu-id="20fe9-208">00020_135</span><span class="sxs-lookup"><span data-stu-id="20fe9-208">00020_135</span></span></p></td>
<td><p><span data-ttu-id="20fe9-209">9030</span><span class="sxs-lookup"><span data-stu-id="20fe9-209">9030</span></span></p></td>
<td><p><span data-ttu-id="20fe9-210">SubCat1</span><span class="sxs-lookup"><span data-stu-id="20fe9-210">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="20fe9-211">01-01-2007</span><span class="sxs-lookup"><span data-stu-id="20fe9-211">01-01-2007</span></span></p></td>
<td><p><span data-ttu-id="20fe9-212">31-03-2007</span><span class="sxs-lookup"><span data-stu-id="20fe9-212">31-03-2007</span></span></p></td>
<td><p><span data-ttu-id="20fe9-213">EUR</span><span class="sxs-lookup"><span data-stu-id="20fe9-213">EUR</span></span></p></td>
<td><p><span data-ttu-id="20fe9-214">500</span><span class="sxs-lookup"><span data-stu-id="20fe9-214">500</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20fe9-215">28-08-2006</span><span class="sxs-lookup"><span data-stu-id="20fe9-215">28-08-2006</span></span></p></td>
<td><p><span data-ttu-id="20fe9-216">00021_135</span><span class="sxs-lookup"><span data-stu-id="20fe9-216">00021_135</span></span></p></td>
<td><p><span data-ttu-id="20fe9-217">9030</span><span class="sxs-lookup"><span data-stu-id="20fe9-217">9030</span></span></p></td>
<td><p><span data-ttu-id="20fe9-218">SubCat2</span><span class="sxs-lookup"><span data-stu-id="20fe9-218">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="20fe9-219">01-01-2007</span><span class="sxs-lookup"><span data-stu-id="20fe9-219">01-01-2007</span></span></p></td>
<td><p><span data-ttu-id="20fe9-220">31-03-2007</span><span class="sxs-lookup"><span data-stu-id="20fe9-220">31-03-2007</span></span></p></td>
<td><p><span data-ttu-id="20fe9-221">EUR</span><span class="sxs-lookup"><span data-stu-id="20fe9-221">EUR</span></span></p></td>
<td><p><span data-ttu-id="20fe9-222">500</span><span class="sxs-lookup"><span data-stu-id="20fe9-222">500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="20fe9-223">Más adelante, decide que desea especificar precios de venta para la categoría SubCat1 del proyecto 9030.</span><span class="sxs-lookup"><span data-stu-id="20fe9-223">Later, you decide that you want to specify sales prices for the category SubCat1 for project 9030.</span></span> <span data-ttu-id="20fe9-224">Por lo tanto, crea una nueva línea de precios de ventas con un precio de ventas de 550 EUR para la combinación del proyecto 9030 y la categoría de cuota SubCat1.</span><span class="sxs-lookup"><span data-stu-id="20fe9-224">Therefore, you create a new sales price line that has a sales price of EUR 550 for the combination of project 9030 and fee category SubCat1.</span></span> <span data-ttu-id="20fe9-225">Ahora hay dos líneas de precio de ventas de suscripción para el proyecto 9030, tal como se muestra en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="20fe9-225">There are now two subscription sales price lines for project 9030, as shown in the following table.</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="20fe9-226">Válido desde</span><span class="sxs-lookup"><span data-stu-id="20fe9-226">Valid from</span></span></p></th>
<th><p><span data-ttu-id="20fe9-227">Categoría</span><span class="sxs-lookup"><span data-stu-id="20fe9-227">Category</span></span></p></th>
<th><p><span data-ttu-id="20fe9-228">Proyecto</span><span class="sxs-lookup"><span data-stu-id="20fe9-228">Project</span></span></p></th>
<th><p><span data-ttu-id="20fe9-229">Suscripción</span><span class="sxs-lookup"><span data-stu-id="20fe9-229">Subscription</span></span></p></th>
<th><p><span data-ttu-id="20fe9-230">Código del período</span><span class="sxs-lookup"><span data-stu-id="20fe9-230">Period code</span></span></p></th>
<th><p><span data-ttu-id="20fe9-231">Divisa</span><span class="sxs-lookup"><span data-stu-id="20fe9-231">Currency</span></span></p></th>
<th><p><span data-ttu-id="20fe9-232">Precio de venta</span><span class="sxs-lookup"><span data-stu-id="20fe9-232">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20fe9-233">28-08-2007</span><span class="sxs-lookup"><span data-stu-id="20fe9-233">28-08-2007</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="20fe9-234">9030</span><span class="sxs-lookup"><span data-stu-id="20fe9-234">9030</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="20fe9-235">Mes</span><span class="sxs-lookup"><span data-stu-id="20fe9-235">Month</span></span></p></td>
<td><p><span data-ttu-id="20fe9-236">EUR</span><span class="sxs-lookup"><span data-stu-id="20fe9-236">EUR</span></span></p></td>
<td><p><span data-ttu-id="20fe9-237">500</span><span class="sxs-lookup"><span data-stu-id="20fe9-237">500</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20fe9-238">28-08-2007</span><span class="sxs-lookup"><span data-stu-id="20fe9-238">28-08-2007</span></span></p></td>
<td><p><span data-ttu-id="20fe9-239">SubCat1</span><span class="sxs-lookup"><span data-stu-id="20fe9-239">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="20fe9-240">9030</span><span class="sxs-lookup"><span data-stu-id="20fe9-240">9030</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="20fe9-241">Mes</span><span class="sxs-lookup"><span data-stu-id="20fe9-241">Month</span></span></p></td>
<td><p><span data-ttu-id="20fe9-242">EUR</span><span class="sxs-lookup"><span data-stu-id="20fe9-242">EUR</span></span></p></td>
<td><p><span data-ttu-id="20fe9-243">550</span><span class="sxs-lookup"><span data-stu-id="20fe9-243">550</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="20fe9-244">Repita el procedimiento descrito anteriormente para crear cuotas de suscripción para ambas suscripciones del grupo de suscripciones Sub1.</span><span class="sxs-lookup"><span data-stu-id="20fe9-244">You repeat the procedure described above to create subscription fees for both subscriptions in the subscription group Sub1.</span></span> <span data-ttu-id="20fe9-245">En la siguiente tabla, se muestran las transacciones que se crean para cada suscripción vinculada al grupo de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="20fe9-245">The following table shows the transactions that are created for each subscription that is attached to the subscription group.</span></span>

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="20fe9-246">Fecha del proyecto</span><span class="sxs-lookup"><span data-stu-id="20fe9-246">Project date</span></span></p></th>
<th><p><span data-ttu-id="20fe9-247">Suscripción</span><span class="sxs-lookup"><span data-stu-id="20fe9-247">Subscription</span></span></p></th>
<th><p><span data-ttu-id="20fe9-248">Proyecto</span><span class="sxs-lookup"><span data-stu-id="20fe9-248">Project</span></span></p></th>
<th><p><span data-ttu-id="20fe9-249">Categoría</span><span class="sxs-lookup"><span data-stu-id="20fe9-249">Category</span></span></p></th>
<th><p><span data-ttu-id="20fe9-250">Fecha inicial</span><span class="sxs-lookup"><span data-stu-id="20fe9-250">Start date</span></span></p></th>
<th><p><span data-ttu-id="20fe9-251">Fecha final</span><span class="sxs-lookup"><span data-stu-id="20fe9-251">End date</span></span></p></th>
<th><p><span data-ttu-id="20fe9-252">Divisa de ventas</span><span class="sxs-lookup"><span data-stu-id="20fe9-252">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="20fe9-253">Precio de venta</span><span class="sxs-lookup"><span data-stu-id="20fe9-253">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20fe9-254">28-07-2007</span><span class="sxs-lookup"><span data-stu-id="20fe9-254">28-07-2007</span></span></p></td>
<td><p><span data-ttu-id="20fe9-255">00020_135</span><span class="sxs-lookup"><span data-stu-id="20fe9-255">00020_135</span></span></p></td>
<td><p><span data-ttu-id="20fe9-256">9030</span><span class="sxs-lookup"><span data-stu-id="20fe9-256">9030</span></span></p></td>
<td><p><span data-ttu-id="20fe9-257">SubCat1</span><span class="sxs-lookup"><span data-stu-id="20fe9-257">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="20fe9-258">01-01-2008</span><span class="sxs-lookup"><span data-stu-id="20fe9-258">01-01-2008</span></span></p></td>
<td><p><span data-ttu-id="20fe9-259">31-03-2008</span><span class="sxs-lookup"><span data-stu-id="20fe9-259">31-03-2008</span></span></p></td>
<td><p><span data-ttu-id="20fe9-260">EUR</span><span class="sxs-lookup"><span data-stu-id="20fe9-260">EUR</span></span></p></td>
<td><p><span data-ttu-id="20fe9-261">550</span><span class="sxs-lookup"><span data-stu-id="20fe9-261">550</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20fe9-262">28-07-2008</span><span class="sxs-lookup"><span data-stu-id="20fe9-262">28-07-2008</span></span></p></td>
<td><p><span data-ttu-id="20fe9-263">00021_135</span><span class="sxs-lookup"><span data-stu-id="20fe9-263">00021_135</span></span></p></td>
<td><p><span data-ttu-id="20fe9-264">9030</span><span class="sxs-lookup"><span data-stu-id="20fe9-264">9030</span></span></p></td>
<td><p><span data-ttu-id="20fe9-265">SubCat2</span><span class="sxs-lookup"><span data-stu-id="20fe9-265">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="20fe9-266">01-01-2008</span><span class="sxs-lookup"><span data-stu-id="20fe9-266">01-01-2008</span></span></p></td>
<td><p><span data-ttu-id="20fe9-267">31-03-2008</span><span class="sxs-lookup"><span data-stu-id="20fe9-267">31-03-2008</span></span></p></td>
<td><p><span data-ttu-id="20fe9-268">EUR</span><span class="sxs-lookup"><span data-stu-id="20fe9-268">EUR</span></span></p></td>
<td><p><span data-ttu-id="20fe9-269">500</span><span class="sxs-lookup"><span data-stu-id="20fe9-269">500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="20fe9-270">En la primera transacción para la suscripción 00020\_135, el precio de ventas 550 EUR procede del precio de ventas de suscripción configurado para la combinación del proyecto específico y la categoría.</span><span class="sxs-lookup"><span data-stu-id="20fe9-270">In the first transaction for subscription 00020\_135, the sales price of EUR 550 derives from the subscription sales price that is set up for the combination of the specific project and category.</span></span> <span data-ttu-id="20fe9-271">En la segunda transacción para la suscripción 00021\_135, el precio de ventas 500 EUR se usa como precio de ventas de suscripción del proyecto porque no hay ningún precio configurado para la combinación de proyecto 9030 y categoría SubCat2.</span><span class="sxs-lookup"><span data-stu-id="20fe9-271">In the second transaction for subscription 00021\_135, the sales price of EUR 500 is used as the project subscription sales price because there is no price set up for the combination of project 9030 and category SubCat2.</span></span>

## <a name="see-also"></a><span data-ttu-id="20fe9-272">Consulte también</span><span class="sxs-lookup"><span data-stu-id="20fe9-272">See also</span></span>

[<span data-ttu-id="20fe9-273">Actualizar e indexar precios de ventas de la suscripción</span><span class="sxs-lookup"><span data-stu-id="20fe9-273">Update and index subscription sales prices</span></span>](update-and-index-subscription-sales-prices.md)

  



