---
title: Personalizar navegación del sitio
description: Este tema describe cómo crear una jerarquía de navegación en línea personalizada para organizar sus productos para examinar en su sitio de Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 2d45f116acc19130e09108a246d276bb4b62a1e6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972916"
---
# <a name="customize-site-navigation"></a><span data-ttu-id="dc57c-103">Personalizar navegación del sitio</span><span class="sxs-lookup"><span data-stu-id="dc57c-103">Customize site navigation</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="dc57c-104">Este tema describe cómo crear una jerarquía de navegación en línea personalizada para organizar sus productos para examinar en su sitio de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="dc57c-104">This topic describes how to create a customized online navigation hierarchy to organize your products for browsing on your Microsoft Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="dc57c-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="dc57c-105">Overview</span></span>

<span data-ttu-id="dc57c-106">Los escaparates en línea normalmente permiten a los clientes detectan y examinar productos navegando por categorías de productos.</span><span class="sxs-lookup"><span data-stu-id="dc57c-106">Online storefronts typically let customers discover and browse products by navigating through product categories.</span></span> <span data-ttu-id="dc57c-107">Esta capacidad es suele proporcionar mediante fichas en la parte superior de la página o por una barra de navegación a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="dc57c-107">This capability is usually provided by tabs at the top of the page or by a navigation bar on the left.</span></span> <span data-ttu-id="dc57c-108">En Dynamics 365 Commerce, puede crear y gestionar la estructura jerárquica de su navegación de categorías y los productos que se incluyen en las diversas categorías.</span><span class="sxs-lookup"><span data-stu-id="dc57c-108">In Dynamics 365 Commerce, you can create and manage the hierarchal structure of your category navigation and the products that are included in the various categories.</span></span>

## <a name="create-a-channel-navigation-hierarchy"></a><span data-ttu-id="dc57c-109">Crear una jerarquía de navegación de canales</span><span class="sxs-lookup"><span data-stu-id="dc57c-109">Create a channel navigation hierarchy</span></span>

<span data-ttu-id="dc57c-110">Para crear una jerarquía de navegación de canales, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="dc57c-110">To create a channel navigation hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="dc57c-111">Vaya a **Retail y Commerce \> Productos y categorías \> Administración de categorías y productos**.</span><span class="sxs-lookup"><span data-stu-id="dc57c-111">Go to **Retail and Commerce \> Products and categories \> Category and product management**.</span></span>
1. <span data-ttu-id="dc57c-112">Seleccione **Jerarquías de categorías** y después **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="dc57c-112">Select **Category hierarchies**, and then select **New**.</span></span>
1. <span data-ttu-id="dc57c-113">Asigne un nombre a la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="dc57c-113">Name the hierarchy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dc57c-114">La categoría superior que cree es el nodo de categoría raíz.</span><span class="sxs-lookup"><span data-stu-id="dc57c-114">The topmost category that you create is the root category node.</span></span> <span data-ttu-id="dc57c-115">No se mostrará en el sitio.</span><span class="sxs-lookup"><span data-stu-id="dc57c-115">It won't be shown on your site.</span></span> <span data-ttu-id="dc57c-116">Para crear una jerarquía de categoría donde se muestre un solo nodo de nivel superior en el sitio, cree y asigne un nombre a la categoría como elemento secundario de la categoría raíz.</span><span class="sxs-lookup"><span data-stu-id="dc57c-116">To create a category hierarchy where a single top-level node is shown on your site, create and name the category as a child of the root category.</span></span>

1. <span data-ttu-id="dc57c-117">Seleccione **Nodo de categoría nueva** y asigne un nombre a la categoría.</span><span class="sxs-lookup"><span data-stu-id="dc57c-117">Select **New category node**, and name the category.</span></span>
1. <span data-ttu-id="dc57c-118">Continúe creando categorías secundarias y elemento del mismo nivel como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="dc57c-118">Continue to create sibling and child categories as you require.</span></span>

<span data-ttu-id="dc57c-119">Ahora puede asignar productos a cada categoría que ha creado en la categoría de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="dc57c-119">You can now assign products to each category that you created under the top-level category.</span></span>

## <a name="customize-the-order-of-categories"></a><span data-ttu-id="dc57c-120">Personalizar el orden de categorías</span><span class="sxs-lookup"><span data-stu-id="dc57c-120">Customize the order of categories</span></span>

<span data-ttu-id="dc57c-121">De manera predeterminada, las categorías que defina aparecerán en orden alfabético en su sitio.</span><span class="sxs-lookup"><span data-stu-id="dc57c-121">By default, the categories that you define will appear in alphabetical order on your site.</span></span> <span data-ttu-id="dc57c-122">Sin embargo, también puede personalizar el orden de visualización de las categorías.</span><span class="sxs-lookup"><span data-stu-id="dc57c-122">However, you can also customize the display order of categories.</span></span>

## <a name="assign-a-category-hierarchy-type"></a><span data-ttu-id="dc57c-123">Asignación de un tipo de jerarquía de categoría</span><span class="sxs-lookup"><span data-stu-id="dc57c-123">Assign a category hierarchy type</span></span>

1. <span data-ttu-id="dc57c-124">Vaya a **Retail y Commerce \> Productos y categorías \> Administración de categorías y productos**.</span><span class="sxs-lookup"><span data-stu-id="dc57c-124">Go to **Retail and Commerce \> Products and categories \> Category and product management**.</span></span>
1. <span data-ttu-id="dc57c-125">Seleccione **Jerarquías de categorías**.</span><span class="sxs-lookup"><span data-stu-id="dc57c-125">Select **Category hierarchies**.</span></span>
1. <span data-ttu-id="dc57c-126">En el panel de acciones, en la pestaña **Jerarquía de categoría** del grupo **Configurar**, seleccione **Asociar tipo de jerarquía**.</span><span class="sxs-lookup"><span data-stu-id="dc57c-126">On the Action Pane, on the **Category hierarchy** tab, in the **Set up** group, select **Associate hierarchy type**.</span></span>
1. <span data-ttu-id="dc57c-127">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="dc57c-127">Select **New**.</span></span>
1. <span data-ttu-id="dc57c-128">En el campo **Tipo de jerarquía de categorías**, seleccione **Jerarquía de navegación de canales**.</span><span class="sxs-lookup"><span data-stu-id="dc57c-128">In the **Category hierarchy type** field, select **Channel navigation hierarchy**.</span></span>
1. <span data-ttu-id="dc57c-129">En el campo **Jerarquía de categoría**, seleccione la jerarquía de navegación de canales que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="dc57c-129">In the **Category hierarchy** field, select the channel navigation hierarchy that you created earlier.</span></span>

## <a name="publish-new-or-updated-navigation-hierarchies"></a><span data-ttu-id="dc57c-130">Publicar jerarquías de navegación nuevas o actualizadas</span><span class="sxs-lookup"><span data-stu-id="dc57c-130">Publish new or updated navigation hierarchies</span></span>

<span data-ttu-id="dc57c-131">Para poner la jerarquía de navegación a disposición de su escaparate en línea, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="dc57c-131">To make your navigation hierarchy available to your online storefront, follow these steps.</span></span>

1. <span data-ttu-id="dc57c-132">Vaya a **Retail y Commerce \> Configuración de canal \> Categorías de canal y atributos de producto**.</span><span class="sxs-lookup"><span data-stu-id="dc57c-132">Go to **Retail and Commerce \> Channel setup \> Channel categories and product attributes**.</span></span>
1. <span data-ttu-id="dc57c-133">En el árbol de la izquierda, seleccione su tienda en línea.</span><span class="sxs-lookup"><span data-stu-id="dc57c-133">In the tree on the left, select your online store.</span></span>
1. <span data-ttu-id="dc57c-134">Seleccione **Publicar actualizaciones de canal**.</span><span class="sxs-lookup"><span data-stu-id="dc57c-134">Select **Publish channel updates**.</span></span>
1. <span data-ttu-id="dc57c-135">Vaya a **Retail y Commerce \> TI de Retail y Commerce \> Programación de distribución**.</span><span class="sxs-lookup"><span data-stu-id="dc57c-135">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="dc57c-136">En la lista, busque y seleccione **Trabajo 1040**.</span><span class="sxs-lookup"><span data-stu-id="dc57c-136">In the list, find and select **Job 1040**.</span></span>
1. <span data-ttu-id="dc57c-137">Seleccione **Ejecutar ahora**.</span><span class="sxs-lookup"><span data-stu-id="dc57c-137">Select **Run now**.</span></span>
1. <span data-ttu-id="dc57c-138">Repita los pasos 5 y 6 para los trabajos 1070 y 1150.</span><span class="sxs-lookup"><span data-stu-id="dc57c-138">Repeat steps 5 and 6 for jobs 1070 and 1150.</span></span>

## <a name="show-categories-on-your-site"></a><span data-ttu-id="dc57c-139">Mostrar categorías en su sitio</span><span class="sxs-lookup"><span data-stu-id="dc57c-139">Show categories on your site</span></span>

<span data-ttu-id="dc57c-140">Para mostrar su jerarquía de categoría en su escaparate en línea, debe agregar el módulo de menú de navegación en la ubicación adecuada en una plantilla o fragmento.</span><span class="sxs-lookup"><span data-stu-id="dc57c-140">To show your category hierarchy on your online storefront, you must add the navigation menu module in the appropriate location in a template or fragment.</span></span> <span data-ttu-id="dc57c-141">El módulo de menú de navegación mostrará a continuación la jerarquía de navegación, siempre que haya publicado la jerarquía de navegación para el canal al que está enlazado el sitio.</span><span class="sxs-lookup"><span data-stu-id="dc57c-141">The navigation menu module will then show your navigation hierarchy, provided that you've published your navigation hierarchy to the channel that your site is bound to.</span></span>

> [!NOTE]
> <span data-ttu-id="dc57c-142">El módulo de menú de navegación que se incluye en la biblioteca de módulos permite a los usuarios navegar solo a las categorías que no tienen subcategorías.</span><span class="sxs-lookup"><span data-stu-id="dc57c-142">The navigation menu module that is included in the module library lets users navigate only to categories that don't have subcategories.</span></span> <span data-ttu-id="dc57c-143">Si sus clientes deben poder navegar a las categorías con subcategorías, debe personalizar el módulo del menú de navegación.</span><span class="sxs-lookup"><span data-stu-id="dc57c-143">If your customers should be able to navigate to categories that have subcategories, you must customize the navigation menu module.</span></span>

## <a name="add-custom-navigation-options"></a><span data-ttu-id="dc57c-144">Agregar opciones de navegación personalizadas</span><span class="sxs-lookup"><span data-stu-id="dc57c-144">Add custom navigation options</span></span>

<span data-ttu-id="dc57c-145">En el menú de navegación, puede agregar opciones de navegación que no forman parte de la jerarquía de categoría de productos.</span><span class="sxs-lookup"><span data-stu-id="dc57c-145">On your navigation menu, you can add navigation options that aren't part of your product category hierarchy.</span></span> <span data-ttu-id="dc57c-146">Por ejemplo, al final de la lista de categorías de productos, puede agregar un elemento **Ponerse en contacto con nosotros** que apunte a una página de contacto que haya creado para el sitio.</span><span class="sxs-lookup"><span data-stu-id="dc57c-146">For example, at the end of the list of product categories, you can add a **Contact Us** item that points to a contact page that you've built for your site.</span></span>

<span data-ttu-id="dc57c-147">Para agregar opciones de navegación personalizadas al menú de navegación, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="dc57c-147">To add custom navigation options to your navigation menu, follow these steps.</span></span>

1. <span data-ttu-id="dc57c-148">En la plantilla o el fragmento que desea personalizar, seleccione el módulo del menú de navegación.</span><span class="sxs-lookup"><span data-stu-id="dc57c-148">In the template or fragment that you want to customize, select the navigation menu module.</span></span>
1. <span data-ttu-id="dc57c-149">En el panel de propiedades, en la pestaña **Datos**, seleccione **Agregar artículo** para crear un artículo nuevo de navegación del sistema de gestión de contenidos (CMS).</span><span class="sxs-lookup"><span data-stu-id="dc57c-149">In the property pane, on the **Data** tab, select **Add item** to create a new content management system (CMS) navigation item.</span></span>
1. <span data-ttu-id="dc57c-150">Especificar el texto del vínculo y una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="dc57c-150">Enter link text and a URL.</span></span>
1. <span data-ttu-id="dc57c-151">Repita los pasos 2 y 3 para agregar más opciones de navegación personalizadas.</span><span class="sxs-lookup"><span data-stu-id="dc57c-151">Repeat steps 2 and 3 to add more custom navigation options.</span></span>
1. <span data-ttu-id="dc57c-152">Cuando haya terminado, seleccione **Guardar** para guardar la plantilla o el fragmento y luego seleccione **Finalizar edición** para protegerlos.</span><span class="sxs-lookup"><span data-stu-id="dc57c-152">When you've finished, select **Save** to save the template or fragment, and then select **Finish editing** to check it in.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dc57c-153">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="dc57c-153">Additional resources</span></span>

[<span data-ttu-id="dc57c-154">Visión general de plantillas y diseños</span><span class="sxs-lookup"><span data-stu-id="dc57c-154">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="dc57c-155">Trabajar con plantillas</span><span class="sxs-lookup"><span data-stu-id="dc57c-155">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="dc57c-156">Trabajar con diseños predefinidos</span><span class="sxs-lookup"><span data-stu-id="dc57c-156">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="dc57c-157">Trabajar con fragmentos</span><span class="sxs-lookup"><span data-stu-id="dc57c-157">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="dc57c-158">Trabajar con módulos</span><span class="sxs-lookup"><span data-stu-id="dc57c-158">Work with modules</span></span>](work-with-modules.md)

[<span data-ttu-id="dc57c-159">Crear un URL de página</span><span class="sxs-lookup"><span data-stu-id="dc57c-159">Create a page URL</span></span>](create-page-url.md)

[<span data-ttu-id="dc57c-160">Trabajar con grupos de publicación</span><span class="sxs-lookup"><span data-stu-id="dc57c-160">Work with publish groups</span></span>](publish-groups.md)
