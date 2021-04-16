---
title: Crear un nuevo producto en Commerce
description: En este tema se describe cómo crear un nuevo producto en Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 44a58da0be280b06d96cdeae6929042bb50ed4a6
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795724"
---
# <a name="create-a-new-product-in-commerce"></a><span data-ttu-id="3a129-103">Crear un nuevo producto en Commerce</span><span class="sxs-lookup"><span data-stu-id="3a129-103">Create a new product in Commerce</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="3a129-104">En este tema se describe cómo crear un nuevo producto en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3a129-104">This topic describes how to create a new product in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="3a129-105">Información general</span><span class="sxs-lookup"><span data-stu-id="3a129-105">Overview</span></span>

<span data-ttu-id="3a129-106">Un producto se define principalmente con un número de producto, un nombre y una descripción.</span><span class="sxs-lookup"><span data-stu-id="3a129-106">A product is primarily defined by a product number, name, and description.</span></span> <span data-ttu-id="3a129-107">Sin embargo, otros datos también son necesarios para describir un producto o servicio:</span><span class="sxs-lookup"><span data-stu-id="3a129-107">However, other data is also required in order to describe a product or service:</span></span>

## <a name="create-a-new-product"></a><span data-ttu-id="3a129-108">Crear un nuevo producto</span><span class="sxs-lookup"><span data-stu-id="3a129-108">Create a new product</span></span>

1. <span data-ttu-id="3a129-109">En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Productos y categorías \> Productos por categoría**.</span><span class="sxs-lookup"><span data-stu-id="3a129-109">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Products by category**.</span></span>
1. <span data-ttu-id="3a129-110">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="3a129-110">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="3a129-111">En la lista desplegable **Tipo de producto**, seleccione **Artículo** o **Servicio**.</span><span class="sxs-lookup"><span data-stu-id="3a129-111">In the **Product type** drop-down list, select either **Item** or **Service**.</span></span>
1. <span data-ttu-id="3a129-112">En la lista desplegable **Subtipo de producto**, seleccione **Producto** (si el producto no tiene variantes) o **Producto maestro** (si el producto tiene variantes).</span><span class="sxs-lookup"><span data-stu-id="3a129-112">In the **Product subtype** drop-down list, select either **Product** (if the product will have no variants) or **Product master** (if the product will have variants).</span></span>
1. <span data-ttu-id="3a129-113">En el cuadro **Número de producto**, introduzca un número de producto si no aparece especificado.</span><span class="sxs-lookup"><span data-stu-id="3a129-113">In the **Product number** box, enter a product number if one is not already prepopulated.</span></span>
1. <span data-ttu-id="3a129-114">En el cuadro **Nombre del producto**, introduzca un nombre de producto.</span><span class="sxs-lookup"><span data-stu-id="3a129-114">In the **Product name** box, enter a product name.</span></span>
1. <span data-ttu-id="3a129-115">En el cuadro **Nombre de búsqueda**, escriba un nombre de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3a129-115">In the **Search name** box, enter a search name.</span></span>
1. <span data-ttu-id="3a129-116">En la lista desplegable **Categoría comercial**, seleccione una categoría apropiada.</span><span class="sxs-lookup"><span data-stu-id="3a129-116">In the **Retail category** drop-down list, select an appropriate category.</span></span>
1. <span data-ttu-id="3a129-117">Si el producto es un kit, seleccione **Sí** para **Kit de productos**.</span><span class="sxs-lookup"><span data-stu-id="3a129-117">If the product is a kit, select **Yes** for **Product kit**.</span></span>
1. <span data-ttu-id="3a129-118">Si el subtipo de producto es producto maestro, establezca el valor de **Grupo de dimensiones del producto** para incluir las variantes ofrecidas.</span><span class="sxs-lookup"><span data-stu-id="3a129-118">If the product subtype is product master, set the **Product dimension group** to include the supported variants.</span></span> <span data-ttu-id="3a129-119">Entre las opciones se incluyen **Color**, **Tamaño**, **Estilo** y **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="3a129-119">Options include **Color**, **Size**, **Style**, and **Configuration**.</span></span> <span data-ttu-id="3a129-120">Es posible que tenga que crear grupos de dimensiones de productos adicionales si es necesario.</span><span class="sxs-lookup"><span data-stu-id="3a129-120">You may need to create additional product dimension groups if needed.</span></span>
1. <span data-ttu-id="3a129-121">En la lista desplegable **Tecnología de configuración**, seleccione una opción apropiada.</span><span class="sxs-lookup"><span data-stu-id="3a129-121">In the **Configuration technology** drop-down list, select an appropriate option.</span></span>
1. <span data-ttu-id="3a129-122">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3a129-122">Select **OK**.</span></span>

<span data-ttu-id="3a129-123">La imagen siguiente muestra un ejemplo de adición de producto.</span><span class="sxs-lookup"><span data-stu-id="3a129-123">The following image shows an example product being added.</span></span>

![Crear un producto](media/create-new-product.png)

<span data-ttu-id="3a129-125">Una vez que se agrega un producto, se pueden establecer datos adicionales para él, como **Descripción del producto**, **Grupos de variantes**, **Grupos de dimensiones**, **Atributos del producto** y **Productos relacionados**.</span><span class="sxs-lookup"><span data-stu-id="3a129-125">Once a product is added, additional data can be set for it, such as **Product description**, **Variant groups**, **Dimension groups**, **Product attributes**, and **Related products**.</span></span>

<span data-ttu-id="3a129-126">La imagen siguiente muestra los detalles adicionales de un producto.</span><span class="sxs-lookup"><span data-stu-id="3a129-126">The following image shows a product's additional details.</span></span>

![Detalles de producto](media/create-new-product-2.png)

### <a name="create-product-variants"></a><span data-ttu-id="3a129-128">Crear variantes de productos</span><span class="sxs-lookup"><span data-stu-id="3a129-128">Create product variants</span></span>

<span data-ttu-id="3a129-129">Si el subtipo de producto es **Producto maestro**, deberán crearse variantes específicas.</span><span class="sxs-lookup"><span data-stu-id="3a129-129">If the product subtype is **Product master**, specific variants will need to be created.</span></span> 

<span data-ttu-id="3a129-130">Para crear variantes de producto, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="3a129-130">To create product variants, follow these steps.</span></span>

1. <span data-ttu-id="3a129-131">En el panel de acciones, seleccione **Variantes del producto**.</span><span class="sxs-lookup"><span data-stu-id="3a129-131">On the action pane, select **Product variants**.</span></span>
1. <span data-ttu-id="3a129-132">Si se seleccionaron grupos de variantes en el panel de acciones, seleccione \**Sugerencias de variantes*.</span><span class="sxs-lookup"><span data-stu-id="3a129-132">If variant groups have been selected on the action pane, select \**Variant suggestions*.</span></span>
1. <span data-ttu-id="3a129-133">Seleccione las variantes que desea ofrecer para el producto.</span><span class="sxs-lookup"><span data-stu-id="3a129-133">Select the variants you would like to support for the product.</span></span>
1. <span data-ttu-id="3a129-134">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="3a129-134">Select **Create**.</span></span>

## <a name="release-a-product"></a><span data-ttu-id="3a129-135">Liberar un producto</span><span class="sxs-lookup"><span data-stu-id="3a129-135">Release a product</span></span>

<span data-ttu-id="3a129-136">Para vender un producto, primero debe liberarse en una entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="3a129-136">To sell a product it must first be released to a legal entity.</span></span>

1. <span data-ttu-id="3a129-137">En la página del producto, seleccione **Emitir productos**.</span><span class="sxs-lookup"><span data-stu-id="3a129-137">From the product page, select **Release products**.</span></span>

    ![Liberar producto](media/create-new-product-3.png)

1. <span data-ttu-id="3a129-139">Seleccione el producto que desea liberar y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3a129-139">Select the product to release, and then select **Next**.</span></span>

    ![Elija el producto que desea liberar](media/create-new-product-4.png)

1. <span data-ttu-id="3a129-141">Seleccione el conjunto de variantes de producto que desea liberar y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3a129-141">Select the set of product variants to release, and then select **Next**.</span></span>

    ![Elegir las variantes que se van a liberar](media/create-new-product-5.png)

1. <span data-ttu-id="3a129-143">Seleccione la entidad jurídica y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3a129-143">Select the legal entity, and then select **Next**.</span></span>

    ![Elegir entidad jurídica](media/create-new-product-6.png)

1. <span data-ttu-id="3a129-145">Seleccione **Fin**.</span><span class="sxs-lookup"><span data-stu-id="3a129-145">Select **Finish**.</span></span>

    ![Finalizar liberación de producto](media/create-new-product-7.png)

## <a name="configure-a-released-product"></a><span data-ttu-id="3a129-147">Configurar un producto liberado</span><span class="sxs-lookup"><span data-stu-id="3a129-147">Configure a released product</span></span>

<span data-ttu-id="3a129-148">Una vez que se ha liberado un producto, requerirá una configuración adicional que incluya agregar un precio al producto.</span><span class="sxs-lookup"><span data-stu-id="3a129-148">Once a product is released, it will then require further configuration that includes adding a price to the product.</span></span>

1. <span data-ttu-id="3a129-149">En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Productos y categorías \> Productos liberados por categoría**.</span><span class="sxs-lookup"><span data-stu-id="3a129-149">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Released products by category**.</span></span>
1. <span data-ttu-id="3a129-150">Seleccione el nodo de categoría de productos para el producto liberado y después seleccione el producto en la lista de productos.</span><span class="sxs-lookup"><span data-stu-id="3a129-150">Select the product category node for the product that was released, and then select the product from the product list.</span></span>
1. <span data-ttu-id="3a129-151">En el panel de acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="3a129-151">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="3a129-152">En la sección **Comprar** configure las propiedades requeridas, como **Unidad**, **Precio** y **Cantidad**.</span><span class="sxs-lookup"><span data-stu-id="3a129-152">In the **Purchase** section, configure any required properties including **Unit**, **Price**,  and **Quantity**.</span></span>
1. <span data-ttu-id="3a129-153">En el panel de acciones, seleccione **Validar** para asegurarse de que no se notifiquen errores de campos que faltan.</span><span class="sxs-lookup"><span data-stu-id="3a129-153">On the action pane, select **Validate** to ensure that no errors are reported for missing fields.</span></span>
1. <span data-ttu-id="3a129-154">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3a129-154">On the action pane, select **Save**.</span></span>

<span data-ttu-id="3a129-155">En la siguiente imagen se muestra un ejemplo de configuración para un producto liberado.</span><span class="sxs-lookup"><span data-stu-id="3a129-155">The following image shows an example configuration for a released product.</span></span>

![Configurar un producto liberado](media/create-new-product-8.png)

## <a name="additional-resources"></a><span data-ttu-id="3a129-157">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="3a129-157">Additional resources</span></span>

[<span data-ttu-id="3a129-158">Crear entidades jurídicas</span><span class="sxs-lookup"><span data-stu-id="3a129-158">Create legal entities</span></span>](channels-legal-entities.md)

[<span data-ttu-id="3a129-159">Crear un grupo de variantes</span><span class="sxs-lookup"><span data-stu-id="3a129-159">Create a variant group</span></span>](create-variant-group.md) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]