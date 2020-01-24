---
title: Personalizar navegación del sitio
description: Este tema describe cómo crear una jerarquía de navegación en línea personalizada para organizar sus productos para examinar en su sitio de Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: annbe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 642cb5c145dec68631eb9ab27d926ba8ab75c59b
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914919"
---
# <a name="customize-site-navigation"></a><span data-ttu-id="cb039-103">Personalizar navegación del sitio</span><span class="sxs-lookup"><span data-stu-id="cb039-103">Customize site navigation</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="cb039-104">Este tema describe cómo crear una jerarquía de navegación en línea personalizada para organizar sus productos para examinar en su sitio de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="cb039-104">This topic describes how to create a customized online navigation hierarchy to organize your products for browsing on your Microsoft Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="cb039-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="cb039-105">Overview</span></span>

<span data-ttu-id="cb039-106">Los escaparates en línea normalmente permiten a los clientes detectan y examinar productos navegando por categorías de productos.</span><span class="sxs-lookup"><span data-stu-id="cb039-106">Online storefronts typically let customers discover and browse products by navigating through product categories.</span></span> <span data-ttu-id="cb039-107">Esta capacidad es suele proporcionar mediante fichas en la parte superior de la página o por una barra de navegación a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="cb039-107">This capability is usually provided by tabs at the top of the page or by a navigation bar on the left.</span></span> <span data-ttu-id="cb039-108">En Dynamics 365 Commerce, puede crear y gestionar la estructura jerárquica de su navegación de categorías y los productos que se incluyen en las diversas categorías.</span><span class="sxs-lookup"><span data-stu-id="cb039-108">In Dynamics 365 Commerce, you can create and manage the hierarchal structure of your category navigation and the products that are included in the various categories.</span></span>

## <a name="create-a-retail-channel-navigation-hierarchy"></a><span data-ttu-id="cb039-109">Crear una jerarquía de navegación de canales comerciales</span><span class="sxs-lookup"><span data-stu-id="cb039-109">Create a retail channel navigation hierarchy</span></span>

<span data-ttu-id="cb039-110">Para crear una jerarquía de navegación de canales comerciales, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="cb039-110">To create a retail channel navigation hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="cb039-111">Vaya a **Venta minorista y comercio \> Productos y categorías \> Administración de categorías y productos**.</span><span class="sxs-lookup"><span data-stu-id="cb039-111">Go to **Retail \> Products and categories \> Category and product management**.</span></span>
1. <span data-ttu-id="cb039-112">Seleccione **Jerarquías de categorías** y después **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="cb039-112">Select **Category hierarchies**, and then select **New**.</span></span>
1. <span data-ttu-id="cb039-113">Asigne un nombre a la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="cb039-113">Name the hierarchy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cb039-114">La categoría superior que cree es el nodo de categoría raíz.</span><span class="sxs-lookup"><span data-stu-id="cb039-114">The topmost category that you create is the root category node.</span></span> <span data-ttu-id="cb039-115">No se mostrará en el sitio.</span><span class="sxs-lookup"><span data-stu-id="cb039-115">It won't be shown on your site.</span></span> <span data-ttu-id="cb039-116">Para crear una jerarquía de categoría donde se muestre un solo nodo de nivel superior en el sitio, cree y asigne un nombre a la categoría como elemento secundario de la categoría raíz.</span><span class="sxs-lookup"><span data-stu-id="cb039-116">To create a category hierarchy where a single top-level node is shown on your site, create and name the category as a child of the root category.</span></span>

1. <span data-ttu-id="cb039-117">Seleccione **Nodo de categoría nueva** y asigne un nombre a la categoría.</span><span class="sxs-lookup"><span data-stu-id="cb039-117">Select **New category node**, and name the category.</span></span>
1. <span data-ttu-id="cb039-118">Continúe creando categorías secundarias y elemento del mismo nivel como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="cb039-118">Continue to create sibling and child categories as you require.</span></span>

<span data-ttu-id="cb039-119">Ahora puede asignar productos a cada categoría que ha creado en la categoría de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="cb039-119">You can now assign products to each category that you created under the top-level category.</span></span>

## <a name="customize-the-order-of-categories"></a><span data-ttu-id="cb039-120">Personalizar el orden de categorías</span><span class="sxs-lookup"><span data-stu-id="cb039-120">Customize the order of categories</span></span>

<span data-ttu-id="cb039-121">De manera predeterminada, las categorías que defina aparecerán en orden alfabético en su sitio.</span><span class="sxs-lookup"><span data-stu-id="cb039-121">By default, the categories that you define will appear in alphabetical order on your site.</span></span> <span data-ttu-id="cb039-122">Sin embargo, también puede personalizar el orden de visualización de las categorías.</span><span class="sxs-lookup"><span data-stu-id="cb039-122">However, you can also customize the display order of categories.</span></span>

## <a name="assign-a-category-hierarchy-type"></a><span data-ttu-id="cb039-123">Asignación de un tipo de jerarquía de categoría</span><span class="sxs-lookup"><span data-stu-id="cb039-123">Assign a category hierarchy type</span></span>

1. <span data-ttu-id="cb039-124">Vaya a **Venta minorista y comercio \> Productos y categorías \> Administración de categorías y productos**.</span><span class="sxs-lookup"><span data-stu-id="cb039-124">Go to **Retail \> Products and categories \> Category and product management**.</span></span>
1. <span data-ttu-id="cb039-125">Seleccione **Jerarquías de categorías**.</span><span class="sxs-lookup"><span data-stu-id="cb039-125">Select **Category hierarchies**.</span></span>
1. <span data-ttu-id="cb039-126">En el panel de acciones, en la pestaña **Jerarquía de categoría** del grupo **Configurar**, seleccione **Asociar tipo de jerarquía**.</span><span class="sxs-lookup"><span data-stu-id="cb039-126">On the Action Pane, on the **Category hierarchy** tab, in the **Set up** group, select **Associate hierarchy type**.</span></span>
1. <span data-ttu-id="cb039-127">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="cb039-127">Select **New**.</span></span>
1. <span data-ttu-id="cb039-128">En el campo **Tipo de jerarquía de categorías**, seleccione **Jerarquía de navegación de canales comerciales**.</span><span class="sxs-lookup"><span data-stu-id="cb039-128">In the **Category hierarchy type** field, select **Retail channel navigation hierarchy**.</span></span>
1. <span data-ttu-id="cb039-129">En el campo **Jerarquía de categoría**, seleccione la jerarquía de navegación de canales que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="cb039-129">In the **Category hierarchy** field, select the channel navigation hierarchy that you created earlier.</span></span>

## <a name="publish-new-or-updated-navigation-hierarchies"></a><span data-ttu-id="cb039-130">Publicar jerarquías de navegación nuevas o actualizadas</span><span class="sxs-lookup"><span data-stu-id="cb039-130">Publish new or updated navigation hierarchies</span></span>

<span data-ttu-id="cb039-131">Para poner la jerarquía de navegación a disposición de su escaparate en línea, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="cb039-131">To make your navigation hierarchy available to your online storefront, follow these steps.</span></span>

1. <span data-ttu-id="cb039-132">Vaya a **Venta al por menor \> Configuración de canal \> Categorías de canal y atributos de producto**.</span><span class="sxs-lookup"><span data-stu-id="cb039-132">Go to **Retail \> Channel setup \> Channel categories and product attributes**.</span></span>
1. <span data-ttu-id="cb039-133">En el árbol de la izquierda, seleccione su tienda en línea.</span><span class="sxs-lookup"><span data-stu-id="cb039-133">In the tree on the left, select your online store.</span></span>
1. <span data-ttu-id="cb039-134">Seleccione **Publicar actualizaciones de canal**.</span><span class="sxs-lookup"><span data-stu-id="cb039-134">Select **Publish channel updates**.</span></span>
1. <span data-ttu-id="cb039-135">Vaya a **Retail \> TI de Retail \> Programación de distribución**.</span><span class="sxs-lookup"><span data-stu-id="cb039-135">Go to **Retail \> Retail IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="cb039-136">En la lista, busque y seleccione **Trabajo 1040**.</span><span class="sxs-lookup"><span data-stu-id="cb039-136">In the list, find and select **Job 1040**.</span></span>
1. <span data-ttu-id="cb039-137">Seleccione **Ejecutar ahora**.</span><span class="sxs-lookup"><span data-stu-id="cb039-137">Select **Run now**.</span></span>
1. <span data-ttu-id="cb039-138">Repita los pasos 5 y 6 para los trabajos 1070 y 1150.</span><span class="sxs-lookup"><span data-stu-id="cb039-138">Repeat steps 5 and 6 for jobs 1070 and 1150.</span></span>

## <a name="show-categories-on-your-site"></a><span data-ttu-id="cb039-139">Mostrar categorías en su sitio</span><span class="sxs-lookup"><span data-stu-id="cb039-139">Show categories on your site</span></span>

<span data-ttu-id="cb039-140">Para mostrar su jerarquía de categoría en su escaparate en línea, debe agregar el módulo de menú de navegación en la ubicación adecuada en una plantilla o fragmento.</span><span class="sxs-lookup"><span data-stu-id="cb039-140">To show your category hierarchy on your online storefront, you must add the navigation menu module in the appropriate location in a template or fragment.</span></span> <span data-ttu-id="cb039-141">El módulo de menú de navegación mostrará a continuación la jerarquía de navegación, siempre que haya publicado la jerarquía de navegación comercial para el canal al que está enlazado el sitio.</span><span class="sxs-lookup"><span data-stu-id="cb039-141">The navigation menu module will then show your navigation hierarchy, provided that you've published your retail navigation hierarchy to the channel that your site is bound to.</span></span>

> [!NOTE]
> <span data-ttu-id="cb039-142">El módulo de menú de navegación que se incluye en el kit de inicio de la tienda permite a los usuarios navegar solo a las categorías que no tienen subcategorías.</span><span class="sxs-lookup"><span data-stu-id="cb039-142">The navigation menu module that is included in the store starter kit lets users navigate only to categories that don't have subcategories.</span></span> <span data-ttu-id="cb039-143">Si sus clientes deben poder navegar a las categorías con subcategorías, debe personalizar el módulo del menú de navegación.</span><span class="sxs-lookup"><span data-stu-id="cb039-143">If your customers should be able to navigate to categories that have subcategories, you must customize the navigation menu module.</span></span>

## <a name="add-custom-navigation-options"></a><span data-ttu-id="cb039-144">Agregar opciones de navegación personalizadas</span><span class="sxs-lookup"><span data-stu-id="cb039-144">Add custom navigation options</span></span>

<span data-ttu-id="cb039-145">En el menú de navegación, puede agregar opciones de navegación que no forman parte de la jerarquía de categoría de productos.</span><span class="sxs-lookup"><span data-stu-id="cb039-145">On your navigation menu, you can add navigation options that aren't part of your product category hierarchy.</span></span> <span data-ttu-id="cb039-146">Por ejemplo, al final de la lista de categorías de productos, puede agregar un elemento **Ponerse en contacto con nosotros** que apunte a una página de contacto que haya creado para el sitio.</span><span class="sxs-lookup"><span data-stu-id="cb039-146">For example, at the end of the list of product categories, you can add a **Contact Us** item that points to a contact page that you've built for your site.</span></span>

<span data-ttu-id="cb039-147">Para agregar opciones de navegación personalizadas al menú de navegación, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="cb039-147">To add custom navigation options to your navigation menu, follow these steps.</span></span>

1. <span data-ttu-id="cb039-148">En la plantilla o el fragmento que desea personalizar, seleccione el módulo del menú de navegación.</span><span class="sxs-lookup"><span data-stu-id="cb039-148">In the template or fragment that you want to customize, select the navigation menu module.</span></span>
1. <span data-ttu-id="cb039-149">En el panel de propiedades, en la pestaña **Datos**, seleccione **Agregar artículo** para crear un artículo nuevo de navegación del sistema de gestión de contenidos (CMS).</span><span class="sxs-lookup"><span data-stu-id="cb039-149">In the property pane, on the **Data** tab, select **Add item** to create a new content management system (CMS) navigation item.</span></span>
1. <span data-ttu-id="cb039-150">Especificar el texto del vínculo y una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="cb039-150">Enter link text and a URL.</span></span>
1. <span data-ttu-id="cb039-151">Repita los pasos 2 y 3 para agregar más opciones de navegación personalizadas.</span><span class="sxs-lookup"><span data-stu-id="cb039-151">Repeat steps 2 and 3 to add more custom navigation options.</span></span>
1. <span data-ttu-id="cb039-152">Cuando haya terminado, guarde la plantilla o el fragmento, y protéjalo.</span><span class="sxs-lookup"><span data-stu-id="cb039-152">When you've finished, save the template or fragment, and check it in.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cb039-153">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="cb039-153">Additional resources</span></span>

[<span data-ttu-id="cb039-154">Visión general de plantillas y diseños</span><span class="sxs-lookup"><span data-stu-id="cb039-154">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="cb039-155">Trabajar con plantillas</span><span class="sxs-lookup"><span data-stu-id="cb039-155">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="cb039-156">Trabajar con diseños predefinidos</span><span class="sxs-lookup"><span data-stu-id="cb039-156">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="cb039-157">Trabajar con fragmentos</span><span class="sxs-lookup"><span data-stu-id="cb039-157">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="cb039-158">Trabajar con módulos</span><span class="sxs-lookup"><span data-stu-id="cb039-158">Work with modules</span></span>](work-with-modules.md)

[<span data-ttu-id="cb039-159">Crear un URL de página</span><span class="sxs-lookup"><span data-stu-id="cb039-159">Create a page URL</span></span>](create-page-url.md)

[<span data-ttu-id="cb039-160">Trabajar con grupos de publicación</span><span class="sxs-lookup"><span data-stu-id="cb039-160">Work with publish groups</span></span>](publish-groups.md)
