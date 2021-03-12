---
title: Crear una jerarquía de navegación de canales
description: En este tema se describe cómo crear una nueva jerarquía de navegación de canales en Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 89e24496d35ea0a02bd985f76d7579e1914d9290
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972991"
---
# <a name="create-a-channel-navigation-hierarchy"></a><span data-ttu-id="86216-103">Crear una jerarquía de navegación de canales</span><span class="sxs-lookup"><span data-stu-id="86216-103">Create a channel navigation hierarchy</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="86216-104">En este tema se describe cómo crear una nueva jerarquía de navegación de canales en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="86216-104">This topic describes how to create a channel navigation hierarchy in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="86216-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="86216-105">Overview</span></span>

<span data-ttu-id="86216-106">Una jerarquía de navegación de canales se usa para agrupar y organizar productos en categorías para que se puedan examinar productos en línea o en los puntos de venta (PDV).</span><span class="sxs-lookup"><span data-stu-id="86216-106">A channel navigation hierarchy is used to group and organize products into categories so that the products can be browsed online or in point of sale (POS).</span></span>

## <a name="create-a-channel-navigation-hierarchy"></a><span data-ttu-id="86216-107">Crear una jerarquía de navegación de canales</span><span class="sxs-lookup"><span data-stu-id="86216-107">Create a channel navigation hierarchy</span></span>

<span data-ttu-id="86216-108">Para crear una jerarquía de navegación de canales, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="86216-108">To create a channel navigation hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="86216-109">En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Productos y categorías \> Categorías de navegación de canales**.</span><span class="sxs-lookup"><span data-stu-id="86216-109">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Channel navigation categories**.</span></span>
1. <span data-ttu-id="86216-110">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="86216-110">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="86216-111">Escriba un nombre en el cuadro **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="86216-111">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="86216-112">En el cuadro **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="86216-112">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="86216-113">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="86216-113">Select **Create**.</span></span>
1. <span data-ttu-id="86216-114">En el panel de acciones, seleccione **Nodo de categoría nueva** para crear un nodo raíz.</span><span class="sxs-lookup"><span data-stu-id="86216-114">On the action pane, select **New category node** to create a root node.</span></span>
1. <span data-ttu-id="86216-115">Escriba un nombre en el cuadro **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="86216-115">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="86216-116">En el cuadro **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="86216-116">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="86216-117">En el cuadro **Nombre descriptivo**, escriba un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="86216-117">In the **Friendly name** box, enter a friendly name.</span></span>
1. <span data-ttu-id="86216-118">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="86216-118">On the action pane, select **Save**.</span></span>

<span data-ttu-id="86216-119">La siguiente imagen muestra un ejemplo de nodo raíz.</span><span class="sxs-lookup"><span data-stu-id="86216-119">The following image shows a example root node.</span></span>

![Ejemplo de nodo raíz](media/create-channel-hierarchy-1.png)

## <a name="create-navigation-category-nodes"></a><span data-ttu-id="86216-121">Crear nodos de categoría de navegación</span><span class="sxs-lookup"><span data-stu-id="86216-121">Create navigation category nodes</span></span>

<span data-ttu-id="86216-122">Para crear nodos de categoría de navegación adicionales para representar las categorías de productos en el canal, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="86216-122">To create any additional navigation category nodes to represent the product categories on the channel, follow these steps.</span></span>

1. <span data-ttu-id="86216-123">En el panel de navegación, seleccione el nodo principal al que desea agregar una categoría.</span><span class="sxs-lookup"><span data-stu-id="86216-123">In the navigation pane, select the parent node to add a category to.</span></span>
1. <span data-ttu-id="86216-124">En el Panel de acción, seleccione **Nueva categoría de nodo**.</span><span class="sxs-lookup"><span data-stu-id="86216-124">On the action pane, select **New category node**.</span></span>
1. <span data-ttu-id="86216-125">Escriba un nombre en el cuadro **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="86216-125">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="86216-126">En el cuadro **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="86216-126">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="86216-127">En el cuadro **Nombre descriptivo**, escriba un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="86216-127">In the **Friendly name** box, enter a friendly name.</span></span>
1. <span data-ttu-id="86216-128">En el cuadro **Orden de visualización**, escriba un orden de visualización (opcional).</span><span class="sxs-lookup"><span data-stu-id="86216-128">In the **Display order** box, enter a display order (optional).</span></span>
1. <span data-ttu-id="86216-129">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="86216-129">On the action pane, select **Save**.</span></span>

<span data-ttu-id="86216-130">La siguiente imagen muestra un ejemplo de jerarquía de navegación de canales completada.</span><span class="sxs-lookup"><span data-stu-id="86216-130">The following image shows an example of a completed channel navigation hierarchy.</span></span>

![Ejemplo de jerarquía de canales](media/create-channel-hierarchy-2.png)

## <a name="add-products-to-category-nodes"></a><span data-ttu-id="86216-132">Agregar productos a nodos de categoría</span><span class="sxs-lookup"><span data-stu-id="86216-132">Add products to category nodes</span></span>

<span data-ttu-id="86216-133">Para agregar productos a nodos de categoría, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="86216-133">To add products to category nodes, follow these steps.</span></span>

1. <span data-ttu-id="86216-134">Seleccione un nodo de categoría.</span><span class="sxs-lookup"><span data-stu-id="86216-134">Select a category node.</span></span>
1. <span data-ttu-id="86216-135">En **Productos**, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="86216-135">Under **Products**, select **Add**.</span></span>
1. <span data-ttu-id="86216-136">Utilice el número de producto o el nombre del producto para buscar los nuevos productos que desea agregar y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="86216-136">Find the new product(s) you want to add using product number or product name, and then select **OK**.</span></span>
1. <span data-ttu-id="86216-137">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="86216-137">On the action pane, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="86216-138">Agregar productos a un nodo dentro de la jerarquía de navegación de canales no es suficiente para que los productos se muestren en un canal seleccionado. Los productos también se deben clasificar en un producto.</span><span class="sxs-lookup"><span data-stu-id="86216-138">Adding products to a node inside the channel navigation hierarchy is not sufficient for the products to show up on a selected channel, the products must also be assorted to a product.</span></span>

<span data-ttu-id="86216-139">La imagen siguiente muestra un ejemplo de nodo con productos agregados.</span><span class="sxs-lookup"><span data-stu-id="86216-139">The following image shows an example node with products added.</span></span>

![Productos agregados a nodos de categoría](media/create-channel-hierarchy-3.png)

## <a name="add-product-attribute-groups-to-category-nodes"></a><span data-ttu-id="86216-141">Agregar grupos de atributos de producto a nodos de categoría</span><span class="sxs-lookup"><span data-stu-id="86216-141">Add product attribute groups to category nodes</span></span>

> [!NOTE]
> <span data-ttu-id="86216-142">Los grupos de atributos deben crearse antes de que pueda agregarlos a un nodo dentro de la jerarquía de navegación de canales.</span><span class="sxs-lookup"><span data-stu-id="86216-142">Attribute groups must be created before you can add them to a node inside the channel navigation hierarchy.</span></span>

<span data-ttu-id="86216-143">Para agregar un grupo de atributos de producto a un nodo de categoría, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="86216-143">To add product an attribute group to a category node, follow these steps.</span></span>

1. <span data-ttu-id="86216-144">Seleccione un nodo de categoría.</span><span class="sxs-lookup"><span data-stu-id="86216-144">Select a category node.</span></span>
1. <span data-ttu-id="86216-145">En **Grupo de atributos de producto**, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="86216-145">Under **Product attribute group**, select **Add**.</span></span>
1. <span data-ttu-id="86216-146">Busque los grupos de atributos que desea agregar y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="86216-146">Find the attribute group(s) you would like to add, and then select **OK**.</span></span>
1. <span data-ttu-id="86216-147">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="86216-147">On the action pane, select **Save**.</span></span>

<span data-ttu-id="86216-148">La imagen siguiente muestra un ejemplo de nodo con grupos de atributos de producto agregados.</span><span class="sxs-lookup"><span data-stu-id="86216-148">The following image shows a sample node with product attribute groups added.</span></span>

![Grupos de atributos de producto en un nodo](media/create-channel-hierarchy-4.png)

## <a name="additional-resources"></a><span data-ttu-id="86216-150">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="86216-150">Additional resources</span></span>

[<span data-ttu-id="86216-151">Configurar selecciones</span><span class="sxs-lookup"><span data-stu-id="86216-151">Set up assortments</span></span>](set-up-assortments.md)

[<span data-ttu-id="86216-152">Administrar atributos y grupos de atributos</span><span class="sxs-lookup"><span data-stu-id="86216-152">Manage attributes and attribute groups</span></span>](attribute-attributegroups-lifecycle.md)
