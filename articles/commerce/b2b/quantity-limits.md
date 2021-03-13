---
title: Establecer límites de cantidad de productos para sitios de comercio electrónico B2B
description: Este tema describe cómo configurar límites de cantidad de productos para sitios de comercio electrónico de empresa a empresa (B2B).
author: josaw1
manager: AnnBe
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: e70648da2cc1c526625b6e34fd0867d40abb5a85
ms.sourcegitcommit: f9df202aefef761be52c0360b0e22da88773914c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "5035962"
---
# <a name="set-product-quantity-limits-for-b2b-e-commerce-sites"></a><span data-ttu-id="1b217-103">Establecer límites de cantidad de productos para sitios de comercio electrónico B2B</span><span class="sxs-lookup"><span data-stu-id="1b217-103">Set product quantity limits for B2B e-commerce sites</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1b217-104">Este tema describe cómo configurar límites de cantidad de productos para sitios de comercio electrónico de empresa a empresa (B2B).</span><span class="sxs-lookup"><span data-stu-id="1b217-104">This topic describes how to set product quantity limits for business-to-business (B2B) e-commerce sites.</span></span>

<span data-ttu-id="1b217-105">La mayoría de los productos tienen una unidad de medida que define su agrupación.</span><span class="sxs-lookup"><span data-stu-id="1b217-105">Most products have a unit of measure that defines their grouping.</span></span> <span data-ttu-id="1b217-106">La agrupación afecta a cómo se pueden vender los productos.</span><span class="sxs-lookup"><span data-stu-id="1b217-106">The grouping affects how the products can be sold.</span></span> <span data-ttu-id="1b217-107">Algunos productos pueden tener una agrupación adicional de cantidades.</span><span class="sxs-lookup"><span data-stu-id="1b217-107">Some products might have an additional grouping for quantities.</span></span> <span data-ttu-id="1b217-108">Esta agrupación determina si los productos se pueden vender como unidades individuales o múltiples, y si hay un límite mínimo o máximo de cantidad de pedido que se debe seguir.</span><span class="sxs-lookup"><span data-stu-id="1b217-108">This grouping determines whether the products can be sold as individual units or multiples, and whether there is a minimum or maximum order quantity limit that must be followed.</span></span>

<span data-ttu-id="1b217-109">La característica de limitación de la cantidad garantiza que las cantidades mínima, máxima, múltiple y estándar configuradas en Microsoft Dynamics 365 Commerce (en la configuración de pedidos predeterminada o en la configuración del sitio del generador de sitios de Commerce) se aplican a los pedidos de clientes que se realizan en un sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="1b217-109">The quantity limiting feature ensures that the minimum, maximum, multiple, and standard quantities that are configured in Microsoft Dynamics 365 Commerce (in the default order settings or the Commerce site builder site settings) are applied to customer orders that are placed on an e-commerce site.</span></span> <span data-ttu-id="1b217-110">Actualmente, los límites de cantidad de productos no se admiten en los puntos de venta (PDV) y los centros de llamadas.</span><span class="sxs-lookup"><span data-stu-id="1b217-110">Product quantity limits aren't currently supported for the point of sale (POS) and call centers.</span></span>

<span data-ttu-id="1b217-111">Muchos minoristas ofrecen la opción de pedidos de cliente (también llamados pedidos especiales) para satisfacer distintos requisitos de producto y de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="1b217-111">Many retailers provide the option of customer orders (also known as special orders) to meet various product and fulfillment requirements.</span></span> <span data-ttu-id="1b217-112">Aquí hay algunas situaciones habituales:</span><span class="sxs-lookup"><span data-stu-id="1b217-112">Here are some typical scenarios:</span></span>

- <span data-ttu-id="1b217-113">Un cliente quiere que los productos de variantes específicas se vendan en múltiplos de unos pocos.</span><span class="sxs-lookup"><span data-stu-id="1b217-113">A customer wants products of specific variants to be sold in multiples of a few.</span></span>
- <span data-ttu-id="1b217-114">Un cliente desea elegir productos de una tienda o de una ubicación diferente de la tienda o de la ubicación donde el cliente compró los productos.</span><span class="sxs-lookup"><span data-stu-id="1b217-114">A customer wants to pick up products from a store or location that differs from the store or location where the customer purchased those products.</span></span> <span data-ttu-id="1b217-115">Sin embargo, los estándares de empaquetado para las tiendas difieren de los estándares de empaquetado para la distribución de ventas en línea.</span><span class="sxs-lookup"><span data-stu-id="1b217-115">However, the packing standards for the stores differ from the packing standards for online sales distribution.</span></span>
- <span data-ttu-id="1b217-116">Un cliente desea comprar un producto de edición limitada que tiene un límite máximo de cantidad de artículos que se pueden comprar.</span><span class="sxs-lookup"><span data-stu-id="1b217-116">A customer wants to buy a limited-edition product that has a maximum quantity limit for items that can be purchased.</span></span>

## <a name="turn-on-the-default-order-settings-feature-in-commerce-headquarters"></a><span data-ttu-id="1b217-117">Activar la característica de configuración de pedidos predeterminada en la sede central de Commerce</span><span class="sxs-lookup"><span data-stu-id="1b217-117">Turn on the default order settings feature in Commerce headquarters</span></span>

<span data-ttu-id="1b217-118">Para poder establecer límites de cantidad de productos, la característica de configuración de pedidos predeterminada debe estar activada en la sede central de Commerce.</span><span class="sxs-lookup"><span data-stu-id="1b217-118">Before you can set product quantity limits, the default order settings feature must be turned on in Commerce headquarters.</span></span>

<span data-ttu-id="1b217-119">Para activar la característica de configuración de pedidos predeterminada, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="1b217-119">To turn on the default order settings feature, follow these steps.</span></span>

1. <span data-ttu-id="1b217-120">Vaya a **Administración del sistema \> Espacios de trabajo \> Administración de características**.</span><span class="sxs-lookup"><span data-stu-id="1b217-120">Go to **System administration \> Workspaces \> Feature management**.</span></span>
1. <span data-ttu-id="1b217-121">Busque y seleccione la característica **Admitir la configuración de pedido del sitio y predeterminada en el pedido del cliente**.</span><span class="sxs-lookup"><span data-stu-id="1b217-121">Find and select the **Support the Site and Default order settings in the customer order** feature.</span></span>
1. <span data-ttu-id="1b217-122">En la parte inferior del panel derecho, seleccione **Habilitar ahora**.</span><span class="sxs-lookup"><span data-stu-id="1b217-122">At the bottom of the right pane, select **Enable now**.</span></span> 

## <a name="define-quantity-settings"></a><span data-ttu-id="1b217-123">Definir la configuración de cantidad</span><span class="sxs-lookup"><span data-stu-id="1b217-123">Define quantity settings</span></span> 

<span data-ttu-id="1b217-124">Puede definir la configuración de cantidad en la página **Configuración predeterminada de pedido**.</span><span class="sxs-lookup"><span data-stu-id="1b217-124">You can define the quantity settings on the **Default order settings** page.</span></span>

<span data-ttu-id="1b217-125">Para definir la configuración de cantidad, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="1b217-125">To define the quantity settings, follow these steps.</span></span> 

1. <span data-ttu-id="1b217-126">Vaya a Producto **Retail y Commerce \> Productos y categorías \> Productos liberados por categoría**.</span><span class="sxs-lookup"><span data-stu-id="1b217-126">Go to Product **Retail and Commerce \> Products and categories \> Released products by category**.</span></span>
1. <span data-ttu-id="1b217-127">Seleccione un producto liberado.</span><span class="sxs-lookup"><span data-stu-id="1b217-127">Select a released product.</span></span>
1. <span data-ttu-id="1b217-128">En el panel de acciones, en la pestaña **Administrar inventario**, en el grupo **Configuración de pedido**, seleccione **Configuración de pedido predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="1b217-128">On the Action Pane, on the **Manage inventory** tab, in the **Order settings** group, select **Default order settings**.</span></span> 
1. <span data-ttu-id="1b217-129">En la página **Configuración de pedido predeterminada**, en la ficha desplegable **Pedido de ventas**, en la sección **Cantidad de ventas**, establezca las cantidades de ventas del producto:</span><span class="sxs-lookup"><span data-stu-id="1b217-129">On the **Default order settings** page, on the **Sales order** FastTab, in the **Sales quantity** section, set the product sales quantities:</span></span>

    - <span data-ttu-id="1b217-130">**Múltiplos**: la cantidad en cuyos múltiplos se puede comprar el producto.</span><span class="sxs-lookup"><span data-stu-id="1b217-130">**Multiple** – The quantity that the product can be bought in multiples of.</span></span>
    - <span data-ttu-id="1b217-131">**Cantidad mínima de pedido**: el número mínimo de productos que se deben comprar.</span><span class="sxs-lookup"><span data-stu-id="1b217-131">**Minimum Order Quantity** – The minimum number of products that must be purchased.</span></span>
    - <span data-ttu-id="1b217-132">**Cantidad máxima de pedido**: el número máximo de productos que se pueden comprar.</span><span class="sxs-lookup"><span data-stu-id="1b217-132">**Maximum Order Quantity** – The maximum number of products that can be purchased.</span></span>
    - <span data-ttu-id="1b217-133">**Cantidad de pedido estándar**: la cantidad predeterminada que se introduce automáticamente al seleccionar el producto.</span><span class="sxs-lookup"><span data-stu-id="1b217-133">**Standard Order Quantity** – The default quantity that is automatically entered when the product is selected.</span></span>

## <a name="turn-on-the-b2b-order-quantity-limits-feature-in-commerce-site-builder"></a><span data-ttu-id="1b217-134">Activar la característica de límites de cantidad de pedidos B2B en el generador de sitios de Commerce</span><span class="sxs-lookup"><span data-stu-id="1b217-134">Turn on the B2B order quantity limits feature in Commerce site builder</span></span>

<span data-ttu-id="1b217-135">Para activar la característica de límites de cantidad de pedidos B2B en el generador de sitios de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="1b217-135">To turn on the B2B order quantity limits feature in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="1b217-136">Vaya a **Configuración del sitio \> Extensiones**.</span><span class="sxs-lookup"><span data-stu-id="1b217-136">Go to **Site settings \> Extensions**</span></span>
1. <span data-ttu-id="1b217-137">En **Habilitar límites de cantidad de pedidos**, seleccione **Habilitado para clientes de B2B** en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="1b217-137">Under **Enable Order Quantity Limits**, select **Enabled for B2B customers** in the drop-down menu.</span></span> 

> [!NOTE] 
> <span data-ttu-id="1b217-138">La configuración actualizada del generador de sitios solo se aplicará después de que se haya actualizado el archivo app.settings.json.</span><span class="sxs-lookup"><span data-stu-id="1b217-138">Updated site builder settings take effect only after the app.settings.json file has been updated.</span></span> <span data-ttu-id="1b217-139">Para obtener más información, consulte [Actualizaciones del SDK y la biblioteca de módulos](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="1b217-139">For more information, see [SDK and Module library updates](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1b217-140">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="1b217-140">Additional resources</span></span>

[<span data-ttu-id="1b217-141">Configurar un sitio de comercio electrónico B2B</span><span class="sxs-lookup"><span data-stu-id="1b217-141">Set up a B2B e-commerce site</span></span>](set-up-b2b-site.md)

[<span data-ttu-id="1b217-142">Crear jerarquías de modelado de organización para organizaciones B2B</span><span class="sxs-lookup"><span data-stu-id="1b217-142">Create org modeling hierarchies for B2B organizations</span></span>](org-model.md)

[<span data-ttu-id="1b217-143">Administrar usuarios socios comerciales en sitios de comercio electrónico B2B</span><span class="sxs-lookup"><span data-stu-id="1b217-143">Manage business partner users on B2B e-commerce sites</span></span>](manage-b2b-users.md)

[<span data-ttu-id="1b217-144">Configurar el método de pago de la cuenta del cliente para sitios de comercio electrónico B2B</span><span class="sxs-lookup"><span data-stu-id="1b217-144">Configure the customer account payment method for B2B e-commerce sites</span></span>](payment-method.md)
