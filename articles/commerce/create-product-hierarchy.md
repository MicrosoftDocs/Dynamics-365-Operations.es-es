---
title: Crear una nueva jerarquía de productos
description: En este tema se describe cómo crear una nueva jerarquía de productos en Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 724ec2e5af7837d574298d662911cd9c6ee9e9f2
ms.sourcegitcommit: 3dede95a3b17de920bb0adcb33029f990682752b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2020
ms.locfileid: "3070430"
---
# <a name="create-a-new-product-hierarchy"></a><span data-ttu-id="f4e3f-103">Crear una nueva jerarquía de productos</span><span class="sxs-lookup"><span data-stu-id="f4e3f-103">Create a new product hierarchy</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="f4e3f-104">En este tema se describe cómo crear una nueva jerarquía de productos en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f4e3f-104">This topic describes how to create a new product hierarchy in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="f4e3f-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="f4e3f-105">Overview</span></span>

<span data-ttu-id="f4e3f-106">Dynamics 365 Commerce admite varios canales comerciales.</span><span class="sxs-lookup"><span data-stu-id="f4e3f-106">Dynamics 365 Commerce supports multiple retail channels.</span></span> <span data-ttu-id="f4e3f-107">Estos canales de venta minorista incluyen tiendas en línea, centros de llamadas y tiendas minoristas (también conocidas como tiendas físicas).</span><span class="sxs-lookup"><span data-stu-id="f4e3f-107">These retail channels include online stores, call centers, and retail stores (also known as brick-and-mortar stores).</span></span> <span data-ttu-id="f4e3f-108">Cada canal de tienda puede tener sus propios métodos de pago, grupos de precios, registros de puntos de venta (PDV), cuentas de ingresos y gastos, o personal.</span><span class="sxs-lookup"><span data-stu-id="f4e3f-108">Each retail store channel can have its own payment methods, price groups, point of sale (POS) registers, income accounts and expense accounts, and staff.</span></span> <span data-ttu-id="f4e3f-109">Debe configurar todos estos elementos antes de crear una canal de tienda.</span><span class="sxs-lookup"><span data-stu-id="f4e3f-109">You must set up all of these elements before you can create a retail store channel.</span></span> 

<span data-ttu-id="f4e3f-110">Se usa una jerarquía de productos de Commerce para definir la jerarquía de productos global para su organización.</span><span class="sxs-lookup"><span data-stu-id="f4e3f-110">A Commerce product hierarchy is used to define the overall product hierarchy for your organization.</span></span> <span data-ttu-id="f4e3f-111">Puede usar este tipo de jerarquía de productos de Commerce para comercialización, precios y promociones, informes y planificación de selecciones.</span><span class="sxs-lookup"><span data-stu-id="f4e3f-111">You can use a Commerce product hierarchy for merchandising, pricing and promotions, reporting, and assortment planning.</span></span> <span data-ttu-id="f4e3f-112">Solo se puede asignar una jerarquía de productos de Commerce por organización.</span><span class="sxs-lookup"><span data-stu-id="f4e3f-112">Only one Commerce product hierarchy can be assigned per organization.</span></span>

## <a name="create-and-configure-a-product-hierarchy"></a><span data-ttu-id="f4e3f-113">Crear y configurar una jerarquía de productos</span><span class="sxs-lookup"><span data-stu-id="f4e3f-113">Create and configure a product hierarchy</span></span>

<span data-ttu-id="f4e3f-114">Para crear y configurar una jerarquía de productos de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="f4e3f-114">To create and configure a Commerce product hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="f4e3f-115">En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Productos y categorías \> Jerarquía de productos de Commerce**.</span><span class="sxs-lookup"><span data-stu-id="f4e3f-115">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Commerce product hierarchy**.</span></span>
1. <span data-ttu-id="f4e3f-116">Si aún no existe una jerarquía, en el **Panel de acciones**, seleccione **Nuevo** para crear la raíz de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="f4e3f-116">If no hierachy exists yet, on the **Action pane**, select **New** to create the root of the hierarchy.</span></span>
1. <span data-ttu-id="f4e3f-117">En **General**:</span><span class="sxs-lookup"><span data-stu-id="f4e3f-117">Under **General**:</span></span>
    1. <span data-ttu-id="f4e3f-118">Escriba un nombre en el cuadro **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="f4e3f-118">In the **Name** box, enter a name.</span></span>
    1. <span data-ttu-id="f4e3f-119">En el cuadro **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="f4e3f-119">In the **Description** box, enter a description.</span></span>
    1. <span data-ttu-id="f4e3f-120">En el cuadro **Nombre descriptivo**, escriba un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="f4e3f-120">In the **Friendly name** box, enter a friendly name.</span></span>
    1. <span data-ttu-id="f4e3f-121">Establezca **Activo** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="f4e3f-121">Set **Active** to **Yes**.</span></span>

## <a name="add-hierarchy-nodes"></a><span data-ttu-id="f4e3f-122">Agregar nodos de jerarquía</span><span class="sxs-lookup"><span data-stu-id="f4e3f-122">Add hierarchy nodes</span></span>

<span data-ttu-id="f4e3f-123">Para agregar nodos de jerarquía, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="f4e3f-123">To add hierarchy nodes, follow these steps.</span></span>

1. <span data-ttu-id="f4e3f-124">En el Panel de acción, seleccione **Editar jerarquía de categoría**.</span><span class="sxs-lookup"><span data-stu-id="f4e3f-124">On the action pane, select **Edit category hierarchy**.</span></span>
1. <span data-ttu-id="f4e3f-125">Seleccione el nodo principal al que desea agregar un nuevo nodo y, a continuación, seleccione **Nuevo nodo de categoría**.</span><span class="sxs-lookup"><span data-stu-id="f4e3f-125">Select the parent node you want to add a new node to, and then select **New category node**.</span></span>
1. <span data-ttu-id="f4e3f-126">En la sección **General**, especifique valores de **Nombre**, **Descripción**, **Nombre descriptivo** y **Palabras clave**.</span><span class="sxs-lookup"><span data-stu-id="f4e3f-126">In the **General** section provide a **Name**, **Description**, **Friendly name** and **Keywords**.</span></span>
1. <span data-ttu-id="f4e3f-127">En **General**:</span><span class="sxs-lookup"><span data-stu-id="f4e3f-127">Under **General**:</span></span>
    1. <span data-ttu-id="f4e3f-128">Escriba un nombre en el cuadro **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="f4e3f-128">In the **Name** box, enter a name.</span></span>
    1. <span data-ttu-id="f4e3f-129">En el cuadro **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="f4e3f-129">In the **Description** box, enter a description.</span></span>
    1. <span data-ttu-id="f4e3f-130">En el cuadro **Nombre descriptivo**, escriba un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="f4e3f-130">In the **Friendly name** box, enter a friendly name.</span></span>
    1. <span data-ttu-id="f4e3f-131">En el cuadro **Palabras clave**, introduzca palabras clave pertinentes.</span><span class="sxs-lookup"><span data-stu-id="f4e3f-131">In the **Keywords** box, enter relevant keywords.</span></span>
    1. <span data-ttu-id="f4e3f-132">En el cuadro **Orden de visualización**, escriba un número para el orden de visualización (opcional).</span><span class="sxs-lookup"><span data-stu-id="f4e3f-132">In the **Display order**box, enter a number for the display order (optional).</span></span>
1. <span data-ttu-id="f4e3f-133">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f4e3f-133">On the action pane, select **Save**.</span></span>
1. <span data-ttu-id="f4e3f-134">Repita los pasos anteriores para agregar nodos adicionales.</span><span class="sxs-lookup"><span data-stu-id="f4e3f-134">Repeat the steps above to add additional nodes.</span></span>

<span data-ttu-id="f4e3f-135">La siguiente imagen muestra la creación de un nuevo nodo de jerarquía de productos.</span><span class="sxs-lookup"><span data-stu-id="f4e3f-135">The following image shows the creation of a new product hierarchy node.</span></span>

![Crear jerarquía de productos](media/create-product-hierarchy.png)

## <a name="other-settings"></a><span data-ttu-id="f4e3f-137">Otras opciones de configuración</span><span class="sxs-lookup"><span data-stu-id="f4e3f-137">Other settings</span></span>

<span data-ttu-id="f4e3f-138">También se pueden asignar grupos de atributos de categoría a cada grupo según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="f4e3f-138">Category attribute groups can also be assigned to each group as required.</span></span>  

## <a name="additional-resources"></a><span data-ttu-id="f4e3f-139">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="f4e3f-139">Additional resources</span></span>

[<span data-ttu-id="f4e3f-140">jerarquías comerciales</span><span class="sxs-lookup"><span data-stu-id="f4e3f-140">commerce hierarchies</span></span>](retail-hierarchies.md)

[<span data-ttu-id="f4e3f-141">Administrar las categorías de productos y los productos</span><span class="sxs-lookup"><span data-stu-id="f4e3f-141">Manage product categories and products </span></span>](category-management-product-creation.md)

[<span data-ttu-id="f4e3f-142">Cambiar el orden de clasificación de entidades de comercialización</span><span class="sxs-lookup"><span data-stu-id="f4e3f-142">Change the sort order for merchandizing entities</span></span>](custom-order-categories-nav-retail-prod-hierarchy.md)
