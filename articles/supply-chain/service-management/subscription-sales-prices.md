---
title: Precios de venta de suscripción
description: Al crear una suscripción, el precio de ventas deriva de la configuración de precio de ventas que se creó en el formulario Precio de venta (suscripción).
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMASalespriceSubscription
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2ed8329e9da08fbe24d9b3982eee562974f0fb3b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5242310"
---
# <a name="subscription-sales-prices"></a><span data-ttu-id="e1b91-103">Precios de venta de suscripción</span><span class="sxs-lookup"><span data-stu-id="e1b91-103">Subscription sales prices</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="e1b91-104">Al crear una suscripción, el precio de ventas deriva de la configuración de precio de ventas que se creó en el formulario **Precio de venta (suscripción)**.</span><span class="sxs-lookup"><span data-stu-id="e1b91-104">When you create a subscription, the sales price is derived from the sales price setup that was created in the **Sales price (subscription)** form.</span></span>

<span data-ttu-id="e1b91-105">En el formulario **Precio de venta (suscripción)**, puede crear precios de ventas para una suscripción específica o crear precios de ventas que se apliquen de manera más amplia.</span><span class="sxs-lookup"><span data-stu-id="e1b91-105">In the **Sales price (subscription)** form, you can create sales prices for a specific subscription or you can create sales prices that apply more broadly.</span></span> <span data-ttu-id="e1b91-106">Para que se aplique un precio de ventas a una suscripción, el código de período y la divisa de la suscripción deben ser idénticos al código de período y a la divisa del precio de ventas.</span><span class="sxs-lookup"><span data-stu-id="e1b91-106">For a sales price to be applied to a subscription, the period code and the currency of the subscription must be identical to the period code and the currency of the sales price.</span></span>

<span data-ttu-id="e1b91-107">Si el código de período y la divisa son idénticos tanto para la suscripción como para el precio de ventas, los precios de venta de suscripción se seleccionan basándose en las prioridades que aparecen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e1b91-107">If the period code and currency are identical for the subscription and the sales price, subscription sales prices are selected on the basis of the priorities listed in the following table.</span></span> <span data-ttu-id="e1b91-108">Una celda en blanco en la tabla indica un campo vacío, mientras que X indica un valor igual al valor de la suscripción a partir de la cual se genera la transacción.</span><span class="sxs-lookup"><span data-stu-id="e1b91-108">A blank cell in the table indicates an empty field and an X indicates a value that is equal to the value in the subscription from which the transaction is generated.</span></span>

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
<th><p><span data-ttu-id="e1b91-109">Prioridad</span><span class="sxs-lookup"><span data-stu-id="e1b91-109">Priority</span></span></p></th>
<th><p><span data-ttu-id="e1b91-110"><strong>Categoría</strong></span><span class="sxs-lookup"><span data-stu-id="e1b91-110"><strong>Category</strong></span></span></p></th>
<th><p><span data-ttu-id="e1b91-111"><strong>Id. de proyecto</strong></span><span class="sxs-lookup"><span data-stu-id="e1b91-111"><strong>Project ID</strong></span></span></p></th>
<th><p><span data-ttu-id="e1b91-112"><strong>Suscripción</strong></span><span class="sxs-lookup"><span data-stu-id="e1b91-112"><strong>Subscription</strong></span></span></p></th>
<th><p><span data-ttu-id="e1b91-113"><strong>Divisa de ventas</strong></span><span class="sxs-lookup"><span data-stu-id="e1b91-113"><strong>Sales currency</strong></span></span></p></th>
<th><p><span data-ttu-id="e1b91-114"><strong>Código del período</strong></span><span class="sxs-lookup"><span data-stu-id="e1b91-114"><strong>Period code</strong></span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e1b91-115">1</span><span class="sxs-lookup"><span data-stu-id="e1b91-115">1</span></span></p></td>
<td><p><span data-ttu-id="e1b91-116">X</span><span class="sxs-lookup"><span data-stu-id="e1b91-116">X</span></span></p></td>
<td><p><span data-ttu-id="e1b91-117">X</span><span class="sxs-lookup"><span data-stu-id="e1b91-117">X</span></span></p></td>
<td><p><span data-ttu-id="e1b91-118">X</span><span class="sxs-lookup"><span data-stu-id="e1b91-118">X</span></span></p></td>
<td><p><span data-ttu-id="e1b91-119">X</span><span class="sxs-lookup"><span data-stu-id="e1b91-119">X</span></span></p></td>
<td><p><span data-ttu-id="e1b91-120">X</span><span class="sxs-lookup"><span data-stu-id="e1b91-120">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1b91-121">2</span><span class="sxs-lookup"><span data-stu-id="e1b91-121">2</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="e1b91-122">X</span><span class="sxs-lookup"><span data-stu-id="e1b91-122">X</span></span></p></td>
<td><p><span data-ttu-id="e1b91-123">X</span><span class="sxs-lookup"><span data-stu-id="e1b91-123">X</span></span></p></td>
<td><p><span data-ttu-id="e1b91-124">X</span><span class="sxs-lookup"><span data-stu-id="e1b91-124">X</span></span></p></td>
<td><p><span data-ttu-id="e1b91-125">X</span><span class="sxs-lookup"><span data-stu-id="e1b91-125">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1b91-126">3</span><span class="sxs-lookup"><span data-stu-id="e1b91-126">3</span></span></p></td>
<td><p><span data-ttu-id="e1b91-127">X</span><span class="sxs-lookup"><span data-stu-id="e1b91-127">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="e1b91-128">X</span><span class="sxs-lookup"><span data-stu-id="e1b91-128">X</span></span></p></td>
<td><p><span data-ttu-id="e1b91-129">X</span><span class="sxs-lookup"><span data-stu-id="e1b91-129">X</span></span></p></td>
<td><p><span data-ttu-id="e1b91-130">X</span><span class="sxs-lookup"><span data-stu-id="e1b91-130">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1b91-131">4</span><span class="sxs-lookup"><span data-stu-id="e1b91-131">4</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="e1b91-132">X</span><span class="sxs-lookup"><span data-stu-id="e1b91-132">X</span></span></p></td>
<td><p><span data-ttu-id="e1b91-133">X</span><span class="sxs-lookup"><span data-stu-id="e1b91-133">X</span></span></p></td>
<td><p><span data-ttu-id="e1b91-134">X</span><span class="sxs-lookup"><span data-stu-id="e1b91-134">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1b91-135">5</span><span class="sxs-lookup"><span data-stu-id="e1b91-135">5</span></span></p></td>
<td><p><span data-ttu-id="e1b91-136">X</span><span class="sxs-lookup"><span data-stu-id="e1b91-136">X</span></span></p></td>
<td><p><span data-ttu-id="e1b91-137">X</span><span class="sxs-lookup"><span data-stu-id="e1b91-137">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="e1b91-138">X</span><span class="sxs-lookup"><span data-stu-id="e1b91-138">X</span></span></p></td>
<td><p><span data-ttu-id="e1b91-139">X</span><span class="sxs-lookup"><span data-stu-id="e1b91-139">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1b91-140">6</span><span class="sxs-lookup"><span data-stu-id="e1b91-140">6</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="e1b91-141">X</span><span class="sxs-lookup"><span data-stu-id="e1b91-141">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="e1b91-142">X</span><span class="sxs-lookup"><span data-stu-id="e1b91-142">X</span></span></p></td>
<td><p><span data-ttu-id="e1b91-143">X</span><span class="sxs-lookup"><span data-stu-id="e1b91-143">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1b91-144">7</span><span class="sxs-lookup"><span data-stu-id="e1b91-144">7</span></span></p></td>
<td><p><span data-ttu-id="e1b91-145">X</span><span class="sxs-lookup"><span data-stu-id="e1b91-145">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="e1b91-146">X</span><span class="sxs-lookup"><span data-stu-id="e1b91-146">X</span></span></p></td>
<td><p><span data-ttu-id="e1b91-147">X</span><span class="sxs-lookup"><span data-stu-id="e1b91-147">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1b91-148">8</span><span class="sxs-lookup"><span data-stu-id="e1b91-148">8</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="e1b91-149">X</span><span class="sxs-lookup"><span data-stu-id="e1b91-149">X</span></span></p></td>
<td><p><span data-ttu-id="e1b91-150">X</span><span class="sxs-lookup"><span data-stu-id="e1b91-150">X</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e1b91-151">Cuando se crea una cuota de suscripción, el precio de ventas con el mayor nivel de detalles (como se indica en la tabla anterior) se selecciona como precio de ventas de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="e1b91-151">When a subscription fee is created, the sales price with the greatest level of detail, as noted in the table above, is selected as the subscription sales price.</span></span>

## <a name="update-and-index-subscription-sales-prices"></a><span data-ttu-id="e1b91-152">Actualizar e indexar precios de ventas de la suscripción</span><span class="sxs-lookup"><span data-stu-id="e1b91-152">Update and index subscription sales prices</span></span>

<span data-ttu-id="e1b91-153">Puede actualizar el precio de ventas de la suscripción actualizando el precio base o el índice.</span><span class="sxs-lookup"><span data-stu-id="e1b91-153">You can update the subscription sales price by updating the base price or the index.</span></span> <span data-ttu-id="e1b91-154">Puede actualizar según un porcentaje o a un valor nuevo.</span><span class="sxs-lookup"><span data-stu-id="e1b91-154">You can update by a percentage or to a new value.</span></span>

## <a name="subscription-fee-sales-prices"></a><span data-ttu-id="e1b91-155">Precios de venta de las cuotas de suscripción</span><span class="sxs-lookup"><span data-stu-id="e1b91-155">Subscription fee sales prices</span></span>

<span data-ttu-id="e1b91-156">Al crear una cuota de suscripción, el precio de ventas se basa en la configuración de precio de ventas de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="e1b91-156">When you create a subscription fee, the sales price is based on the sales price setup of the subscription.</span></span> <span data-ttu-id="e1b91-157">Puede usar el precio de base a partir de la configuración de precio de suscripción, o bien crear precios de venta indexados.</span><span class="sxs-lookup"><span data-stu-id="e1b91-157">You can either use the base price from the subscription price setup or create indexed sales prices.</span></span>

## <a name="example"></a><span data-ttu-id="e1b91-158">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e1b91-158">Example</span></span>

<span data-ttu-id="e1b91-159">Desea configurar precios de venta de suscripción de 500 EUR para un nuevo proyecto 9030.</span><span class="sxs-lookup"><span data-stu-id="e1b91-159">You want to set up subscription sales prices of EUR 500 for a new project 9030.</span></span> <span data-ttu-id="e1b91-160">En el formulario **Precio de venta (suscripción)**, crea una línea de precio de ventas de suscripción como se indica en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="e1b91-160">In the **Sales price (subscription)** form, you create a subscription sales price line as indicated in the following table.</span></span>

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
<th><p><span data-ttu-id="e1b91-161">Válido desde</span><span class="sxs-lookup"><span data-stu-id="e1b91-161">Valid from</span></span></p></th>
<th><p><span data-ttu-id="e1b91-162">Categoría</span><span class="sxs-lookup"><span data-stu-id="e1b91-162">Category</span></span></p></th>
<th><p><span data-ttu-id="e1b91-163">Proyecto</span><span class="sxs-lookup"><span data-stu-id="e1b91-163">Project</span></span></p></th>
<th><p><span data-ttu-id="e1b91-164">Suscripción</span><span class="sxs-lookup"><span data-stu-id="e1b91-164">Subscription</span></span></p></th>
<th><p><span data-ttu-id="e1b91-165">Código del período</span><span class="sxs-lookup"><span data-stu-id="e1b91-165">Period code</span></span></p></th>
<th><p><span data-ttu-id="e1b91-166">Divisa de ventas</span><span class="sxs-lookup"><span data-stu-id="e1b91-166">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="e1b91-167">Precio de venta</span><span class="sxs-lookup"><span data-stu-id="e1b91-167">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e1b91-168">28-08-2006</span><span class="sxs-lookup"><span data-stu-id="e1b91-168">28-08-2006</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e1b91-169">9030</span><span class="sxs-lookup"><span data-stu-id="e1b91-169">9030</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e1b91-170">Mes</span><span class="sxs-lookup"><span data-stu-id="e1b91-170">Month</span></span></p></td>
<td><p><span data-ttu-id="e1b91-171">EUR</span><span class="sxs-lookup"><span data-stu-id="e1b91-171">EUR</span></span></p></td>
<td><p><span data-ttu-id="e1b91-172">500</span><span class="sxs-lookup"><span data-stu-id="e1b91-172">500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e1b91-173">Tenga en cuenta que los campos **Categoría** y **Suscripción** están vacíos.</span><span class="sxs-lookup"><span data-stu-id="e1b91-173">Note that the **Category** and **Subscription** fields are empty.</span></span>

<span data-ttu-id="e1b91-174">A continuación, cree las siguientes suscripciones:</span><span class="sxs-lookup"><span data-stu-id="e1b91-174">You then create the following subscriptions.</span></span>

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
<th><p><span data-ttu-id="e1b91-175">Suscripción de servicio</span><span class="sxs-lookup"><span data-stu-id="e1b91-175">Service subscription</span></span></p></th>
<th><p><span data-ttu-id="e1b91-176">Proyecto</span><span class="sxs-lookup"><span data-stu-id="e1b91-176">Project</span></span></p></th>
<th><p><span data-ttu-id="e1b91-177">Grupo de suscripciones</span><span class="sxs-lookup"><span data-stu-id="e1b91-177">Subscription group</span></span></p></th>
<th><p><span data-ttu-id="e1b91-178">Categoría</span><span class="sxs-lookup"><span data-stu-id="e1b91-178">Category</span></span></p></th>
<th><p><span data-ttu-id="e1b91-179">Divisa</span><span class="sxs-lookup"><span data-stu-id="e1b91-179">Currency</span></span></p></th>
<th><p><span data-ttu-id="e1b91-180">Código de período</span><span class="sxs-lookup"><span data-stu-id="e1b91-180">Period code</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e1b91-181">00020_135</span><span class="sxs-lookup"><span data-stu-id="e1b91-181">00020_135</span></span></p></td>
<td><p><span data-ttu-id="e1b91-182">9030</span><span class="sxs-lookup"><span data-stu-id="e1b91-182">9030</span></span></p></td>
<td><p><span data-ttu-id="e1b91-183">Sub1</span><span class="sxs-lookup"><span data-stu-id="e1b91-183">Sub1</span></span></p></td>
<td><p><span data-ttu-id="e1b91-184">SubCat1</span><span class="sxs-lookup"><span data-stu-id="e1b91-184">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="e1b91-185">EUR</span><span class="sxs-lookup"><span data-stu-id="e1b91-185">EUR</span></span></p></td>
<td><p><span data-ttu-id="e1b91-186">Mensual</span><span class="sxs-lookup"><span data-stu-id="e1b91-186">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1b91-187">00021_135</span><span class="sxs-lookup"><span data-stu-id="e1b91-187">00021_135</span></span></p></td>
<td><p><span data-ttu-id="e1b91-188">9030</span><span class="sxs-lookup"><span data-stu-id="e1b91-188">9030</span></span></p></td>
<td><p><span data-ttu-id="e1b91-189">Sub1</span><span class="sxs-lookup"><span data-stu-id="e1b91-189">Sub1</span></span></p></td>
<td><p><span data-ttu-id="e1b91-190">SubCat2</span><span class="sxs-lookup"><span data-stu-id="e1b91-190">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="e1b91-191">EUR</span><span class="sxs-lookup"><span data-stu-id="e1b91-191">EUR</span></span></p></td>
<td><p><span data-ttu-id="e1b91-192">Mensual</span><span class="sxs-lookup"><span data-stu-id="e1b91-192">Monthly</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e1b91-193">A continuación, cree cuotas de suscripción tanto para suscripciones como para el grupo de suscripciones Sub1:</span><span class="sxs-lookup"><span data-stu-id="e1b91-193">Now you create subscription fees for both subscriptions in the subscription group Sub1:</span></span>

1.  <span data-ttu-id="e1b91-194">Haga clic en **Gestión de servicio** \> **Configuración** \> **Suscripciones de servicio** \> **Grupos de suscripciones**.</span><span class="sxs-lookup"><span data-stu-id="e1b91-194">Click **Service management** \> **Setup** \> **Service subscriptions** \> **Subscription groups**.</span></span>

2.  <span data-ttu-id="e1b91-195">En el formulario **Grupos de suscripciones** , haga clic en **Función** \> **Crear cuota de suscripción**.</span><span class="sxs-lookup"><span data-stu-id="e1b91-195">In the **Subscription groups** form, click **Function** \> **Create subscription fee**.</span></span>

3.  <span data-ttu-id="e1b91-196">En el formulario **Crear cuota de suscripción**, especifique la información adecuada.</span><span class="sxs-lookup"><span data-stu-id="e1b91-196">In the **Create subscription fee** form, enter the appropriate information.</span></span> <span data-ttu-id="e1b91-197">Para obtener más información, vea [Crear transacciones de gastos de suscripción](create-subscription-fee-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="e1b91-197">For more information, see [Create subscription fee transactions](create-subscription-fee-transactions.md).</span></span>

<span data-ttu-id="e1b91-198">Se crean cuotas de suscripción con un precio de ventas de 500 EUR para ambas suscripciones, tal como se muestra en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="e1b91-198">Subscription fees that have a sales price of EUR 500 are created for both subscriptions, as shown in the following table.</span></span>

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
<th><p><span data-ttu-id="e1b91-199">Fecha del proyecto</span><span class="sxs-lookup"><span data-stu-id="e1b91-199">Project date</span></span></p></th>
<th><p><span data-ttu-id="e1b91-200">Suscripción de servicio</span><span class="sxs-lookup"><span data-stu-id="e1b91-200">Service subscription</span></span></p></th>
<th><p><span data-ttu-id="e1b91-201">Proyecto</span><span class="sxs-lookup"><span data-stu-id="e1b91-201">Project</span></span></p></th>
<th><p><span data-ttu-id="e1b91-202">Categoría</span><span class="sxs-lookup"><span data-stu-id="e1b91-202">Category</span></span></p></th>
<th><p><span data-ttu-id="e1b91-203">Fecha inicial</span><span class="sxs-lookup"><span data-stu-id="e1b91-203">Start date</span></span></p></th>
<th><p><span data-ttu-id="e1b91-204">Fecha final</span><span class="sxs-lookup"><span data-stu-id="e1b91-204">End date</span></span></p></th>
<th><p><span data-ttu-id="e1b91-205">Divisa de ventas</span><span class="sxs-lookup"><span data-stu-id="e1b91-205">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="e1b91-206">Precio de venta</span><span class="sxs-lookup"><span data-stu-id="e1b91-206">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e1b91-207">28-08-2006</span><span class="sxs-lookup"><span data-stu-id="e1b91-207">28-08-2006</span></span></p></td>
<td><p><span data-ttu-id="e1b91-208">00020_135</span><span class="sxs-lookup"><span data-stu-id="e1b91-208">00020_135</span></span></p></td>
<td><p><span data-ttu-id="e1b91-209">9030</span><span class="sxs-lookup"><span data-stu-id="e1b91-209">9030</span></span></p></td>
<td><p><span data-ttu-id="e1b91-210">SubCat1</span><span class="sxs-lookup"><span data-stu-id="e1b91-210">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="e1b91-211">01-01-2007</span><span class="sxs-lookup"><span data-stu-id="e1b91-211">01-01-2007</span></span></p></td>
<td><p><span data-ttu-id="e1b91-212">31-03-2007</span><span class="sxs-lookup"><span data-stu-id="e1b91-212">31-03-2007</span></span></p></td>
<td><p><span data-ttu-id="e1b91-213">EUR</span><span class="sxs-lookup"><span data-stu-id="e1b91-213">EUR</span></span></p></td>
<td><p><span data-ttu-id="e1b91-214">500</span><span class="sxs-lookup"><span data-stu-id="e1b91-214">500</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1b91-215">28-08-2006</span><span class="sxs-lookup"><span data-stu-id="e1b91-215">28-08-2006</span></span></p></td>
<td><p><span data-ttu-id="e1b91-216">00021_135</span><span class="sxs-lookup"><span data-stu-id="e1b91-216">00021_135</span></span></p></td>
<td><p><span data-ttu-id="e1b91-217">9030</span><span class="sxs-lookup"><span data-stu-id="e1b91-217">9030</span></span></p></td>
<td><p><span data-ttu-id="e1b91-218">SubCat2</span><span class="sxs-lookup"><span data-stu-id="e1b91-218">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="e1b91-219">01-01-2007</span><span class="sxs-lookup"><span data-stu-id="e1b91-219">01-01-2007</span></span></p></td>
<td><p><span data-ttu-id="e1b91-220">31-03-2007</span><span class="sxs-lookup"><span data-stu-id="e1b91-220">31-03-2007</span></span></p></td>
<td><p><span data-ttu-id="e1b91-221">EUR</span><span class="sxs-lookup"><span data-stu-id="e1b91-221">EUR</span></span></p></td>
<td><p><span data-ttu-id="e1b91-222">500</span><span class="sxs-lookup"><span data-stu-id="e1b91-222">500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e1b91-223">Más adelante, decide que desea especificar precios de venta para la categoría SubCat1 del proyecto 9030.</span><span class="sxs-lookup"><span data-stu-id="e1b91-223">Later, you decide that you want to specify sales prices for the category SubCat1 for project 9030.</span></span> <span data-ttu-id="e1b91-224">Por lo tanto, crea una nueva línea de precios de ventas con un precio de ventas de 550 EUR para la combinación del proyecto 9030 y la categoría de cuota SubCat1.</span><span class="sxs-lookup"><span data-stu-id="e1b91-224">Therefore, you create a new sales price line that has a sales price of EUR 550 for the combination of project 9030 and fee category SubCat1.</span></span> <span data-ttu-id="e1b91-225">Ahora hay dos líneas de precio de ventas de suscripción para el proyecto 9030, tal como se muestra en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="e1b91-225">There are now two subscription sales price lines for project 9030, as shown in the following table.</span></span>

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
<th><p><span data-ttu-id="e1b91-226">Válido desde</span><span class="sxs-lookup"><span data-stu-id="e1b91-226">Valid from</span></span></p></th>
<th><p><span data-ttu-id="e1b91-227">Categoría</span><span class="sxs-lookup"><span data-stu-id="e1b91-227">Category</span></span></p></th>
<th><p><span data-ttu-id="e1b91-228">Proyecto</span><span class="sxs-lookup"><span data-stu-id="e1b91-228">Project</span></span></p></th>
<th><p><span data-ttu-id="e1b91-229">Suscripción</span><span class="sxs-lookup"><span data-stu-id="e1b91-229">Subscription</span></span></p></th>
<th><p><span data-ttu-id="e1b91-230">Código del período</span><span class="sxs-lookup"><span data-stu-id="e1b91-230">Period code</span></span></p></th>
<th><p><span data-ttu-id="e1b91-231">Divisa</span><span class="sxs-lookup"><span data-stu-id="e1b91-231">Currency</span></span></p></th>
<th><p><span data-ttu-id="e1b91-232">Precio de venta</span><span class="sxs-lookup"><span data-stu-id="e1b91-232">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e1b91-233">28-08-2007</span><span class="sxs-lookup"><span data-stu-id="e1b91-233">28-08-2007</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e1b91-234">9030</span><span class="sxs-lookup"><span data-stu-id="e1b91-234">9030</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e1b91-235">Mes</span><span class="sxs-lookup"><span data-stu-id="e1b91-235">Month</span></span></p></td>
<td><p><span data-ttu-id="e1b91-236">EUR</span><span class="sxs-lookup"><span data-stu-id="e1b91-236">EUR</span></span></p></td>
<td><p><span data-ttu-id="e1b91-237">500</span><span class="sxs-lookup"><span data-stu-id="e1b91-237">500</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1b91-238">28-08-2007</span><span class="sxs-lookup"><span data-stu-id="e1b91-238">28-08-2007</span></span></p></td>
<td><p><span data-ttu-id="e1b91-239">SubCat1</span><span class="sxs-lookup"><span data-stu-id="e1b91-239">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="e1b91-240">9030</span><span class="sxs-lookup"><span data-stu-id="e1b91-240">9030</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e1b91-241">Mes</span><span class="sxs-lookup"><span data-stu-id="e1b91-241">Month</span></span></p></td>
<td><p><span data-ttu-id="e1b91-242">EUR</span><span class="sxs-lookup"><span data-stu-id="e1b91-242">EUR</span></span></p></td>
<td><p><span data-ttu-id="e1b91-243">550</span><span class="sxs-lookup"><span data-stu-id="e1b91-243">550</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e1b91-244">Repita el procedimiento descrito anteriormente para crear cuotas de suscripción para ambas suscripciones del grupo de suscripciones Sub1.</span><span class="sxs-lookup"><span data-stu-id="e1b91-244">You repeat the procedure described above to create subscription fees for both subscriptions in the subscription group Sub1.</span></span> <span data-ttu-id="e1b91-245">En la siguiente tabla, se muestran las transacciones que se crean para cada suscripción vinculada al grupo de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="e1b91-245">The following table shows the transactions that are created for each subscription that is attached to the subscription group.</span></span>

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
<th><p><span data-ttu-id="e1b91-246">Fecha del proyecto</span><span class="sxs-lookup"><span data-stu-id="e1b91-246">Project date</span></span></p></th>
<th><p><span data-ttu-id="e1b91-247">Suscripción</span><span class="sxs-lookup"><span data-stu-id="e1b91-247">Subscription</span></span></p></th>
<th><p><span data-ttu-id="e1b91-248">Proyecto</span><span class="sxs-lookup"><span data-stu-id="e1b91-248">Project</span></span></p></th>
<th><p><span data-ttu-id="e1b91-249">Categoría</span><span class="sxs-lookup"><span data-stu-id="e1b91-249">Category</span></span></p></th>
<th><p><span data-ttu-id="e1b91-250">Fecha inicial</span><span class="sxs-lookup"><span data-stu-id="e1b91-250">Start date</span></span></p></th>
<th><p><span data-ttu-id="e1b91-251">Fecha final</span><span class="sxs-lookup"><span data-stu-id="e1b91-251">End date</span></span></p></th>
<th><p><span data-ttu-id="e1b91-252">Divisa de ventas</span><span class="sxs-lookup"><span data-stu-id="e1b91-252">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="e1b91-253">Precio de venta</span><span class="sxs-lookup"><span data-stu-id="e1b91-253">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e1b91-254">28-07-2007</span><span class="sxs-lookup"><span data-stu-id="e1b91-254">28-07-2007</span></span></p></td>
<td><p><span data-ttu-id="e1b91-255">00020_135</span><span class="sxs-lookup"><span data-stu-id="e1b91-255">00020_135</span></span></p></td>
<td><p><span data-ttu-id="e1b91-256">9030</span><span class="sxs-lookup"><span data-stu-id="e1b91-256">9030</span></span></p></td>
<td><p><span data-ttu-id="e1b91-257">SubCat1</span><span class="sxs-lookup"><span data-stu-id="e1b91-257">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="e1b91-258">01-01-2008</span><span class="sxs-lookup"><span data-stu-id="e1b91-258">01-01-2008</span></span></p></td>
<td><p><span data-ttu-id="e1b91-259">31-03-2008</span><span class="sxs-lookup"><span data-stu-id="e1b91-259">31-03-2008</span></span></p></td>
<td><p><span data-ttu-id="e1b91-260">EUR</span><span class="sxs-lookup"><span data-stu-id="e1b91-260">EUR</span></span></p></td>
<td><p><span data-ttu-id="e1b91-261">550</span><span class="sxs-lookup"><span data-stu-id="e1b91-261">550</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1b91-262">28-07-2008</span><span class="sxs-lookup"><span data-stu-id="e1b91-262">28-07-2008</span></span></p></td>
<td><p><span data-ttu-id="e1b91-263">00021_135</span><span class="sxs-lookup"><span data-stu-id="e1b91-263">00021_135</span></span></p></td>
<td><p><span data-ttu-id="e1b91-264">9030</span><span class="sxs-lookup"><span data-stu-id="e1b91-264">9030</span></span></p></td>
<td><p><span data-ttu-id="e1b91-265">SubCat2</span><span class="sxs-lookup"><span data-stu-id="e1b91-265">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="e1b91-266">01-01-2008</span><span class="sxs-lookup"><span data-stu-id="e1b91-266">01-01-2008</span></span></p></td>
<td><p><span data-ttu-id="e1b91-267">31-03-2008</span><span class="sxs-lookup"><span data-stu-id="e1b91-267">31-03-2008</span></span></p></td>
<td><p><span data-ttu-id="e1b91-268">EUR</span><span class="sxs-lookup"><span data-stu-id="e1b91-268">EUR</span></span></p></td>
<td><p><span data-ttu-id="e1b91-269">500</span><span class="sxs-lookup"><span data-stu-id="e1b91-269">500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e1b91-270">En la primera transacción para la suscripción 00020\_135, el precio de ventas 550 EUR procede del precio de ventas de suscripción configurado para la combinación del proyecto específico y la categoría.</span><span class="sxs-lookup"><span data-stu-id="e1b91-270">In the first transaction for subscription 00020\_135, the sales price of EUR 550 derives from the subscription sales price that is set up for the combination of the specific project and category.</span></span> <span data-ttu-id="e1b91-271">En la segunda transacción para la suscripción 00021\_135, el precio de ventas 500 EUR se usa como precio de ventas de suscripción del proyecto porque no hay ningún precio configurado para la combinación de proyecto 9030 y categoría SubCat2.</span><span class="sxs-lookup"><span data-stu-id="e1b91-271">In the second transaction for subscription 00021\_135, the sales price of EUR 500 is used as the project subscription sales price because there is no price set up for the combination of project 9030 and category SubCat2.</span></span>

## <a name="see-also"></a><span data-ttu-id="e1b91-272">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e1b91-272">See also</span></span>

[<span data-ttu-id="e1b91-273">Actualizar e indexar precios de ventas de la suscripción</span><span class="sxs-lookup"><span data-stu-id="e1b91-273">Update and index subscription sales prices</span></span>](update-and-index-subscription-sales-prices.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]