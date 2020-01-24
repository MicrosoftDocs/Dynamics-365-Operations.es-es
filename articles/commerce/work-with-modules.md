---
title: Trabajar con módulos
description: Este tema describe cómo y cuándo usar módulos en Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: phinneyridge
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3c4161e7a40cdbbb40292a6ce9acab58347460bd
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914803"
---
# <a name="work-with-modules"></a><span data-ttu-id="1470f-103">Trabajar con módulos</span><span class="sxs-lookup"><span data-stu-id="1470f-103">Work with modules</span></span>

<span data-ttu-id="1470f-104">Este tema describe cómo y cuándo usar módulos en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1470f-104">This topic describes how and when to use modules in Microsoft Dynamics 365 Commerce.</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

## <a name="overview"></a><span data-ttu-id="1470f-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="1470f-105">Overview</span></span>

<span data-ttu-id="1470f-106">Los módulos son bloques de creación lógicos que componen su estructura de página y tienen diversos propósitos y ámbitos.</span><span class="sxs-lookup"><span data-stu-id="1470f-106">Modules are logical building blocks that make up your page structure, and they have various purposes and scopes.</span></span> <span data-ttu-id="1470f-107">Algunos módulos son contenedores de alto nivel y su único propósito es mantener y organizar otros módulos (módulos secundarios).</span><span class="sxs-lookup"><span data-stu-id="1470f-107">Some modules are high-level containers, and their only purpose is to hold and organize other modules (child modules).</span></span> <span data-ttu-id="1470f-108">Otros módulos, como un módulo de ubicación de imagen sencillo, tienen un propósito muy específico.</span><span class="sxs-lookup"><span data-stu-id="1470f-108">Other modules, such as a simple image placement module, have a very specific purpose.</span></span> <span data-ttu-id="1470f-109">Otros módulos, como un módulo de carrusel, se encuentren en algún lugar entre esas dos categorías.</span><span class="sxs-lookup"><span data-stu-id="1470f-109">Other modules, such as a carousel module, fall somewhere between those two categories.</span></span>

<span data-ttu-id="1470f-110">De manera predeterminada, el sitio de Dynamics 365 Commerce incluye una biblioteca de módulo de kit de inicio que le permite lograr la mayoría de escenarios comercio electrónico básicos.</span><span class="sxs-lookup"><span data-stu-id="1470f-110">By default, your Dynamics 365 Commerce site includes a starter kit module library that lets you achieve most basic e-Commerce scenarios.</span></span> <span data-ttu-id="1470f-111">Debería poder crear un sitio de comercio electrónico integral solo con estos módulos.</span><span class="sxs-lookup"><span data-stu-id="1470f-111">You should be able to construct an end-to-end e-Commerce site just by using these modules.</span></span> <span data-ttu-id="1470f-112">Sin embargo, también podría desea personalizar estos módulos o crear módulos personalizados nuevos para necesidades específicas.</span><span class="sxs-lookup"><span data-stu-id="1470f-112">However, you might also want to customize these modules or build new, custom modules for specific needs.</span></span> <span data-ttu-id="1470f-113">Si desea crear módulos personalizados, un kit de desarrollo de software (SDK) de diseño de módulo está disponible para ayudarle a crear una biblioteca de módulo personalizada.</span><span class="sxs-lookup"><span data-stu-id="1470f-113">If you want to build custom modules, a module design software development kit (SDK) is available to help you create a custom module library.</span></span>

## <a name="container-modules-and-slots"></a><span data-ttu-id="1470f-114">Franjas y módulos de contenedor</span><span class="sxs-lookup"><span data-stu-id="1470f-114">Container modules and slots</span></span>

<span data-ttu-id="1470f-115">Como se mencionó anteriormente, algunos módulos están diseñados para mantener módulos secundarios.</span><span class="sxs-lookup"><span data-stu-id="1470f-115">As was mentioned earlier, some modules are designed to hold child modules.</span></span> <span data-ttu-id="1470f-116">Esos módulos se conocen como *contenedores* y permiten jerarquías de módulos anidados.</span><span class="sxs-lookup"><span data-stu-id="1470f-116">These modules are known as *containers*, and they allow for hierarchies of nested modules.</span></span> <span data-ttu-id="1470f-117">Los módulos de contenedor incluyen *franjas*.</span><span class="sxs-lookup"><span data-stu-id="1470f-117">Container modules include *slots*.</span></span> <span data-ttu-id="1470f-118">Las franjas se usan para administrar el diseño y el propósito de módulos secundarios en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="1470f-118">Slots are used to handle the layout and purpose of child modules in the container.</span></span> <span data-ttu-id="1470f-119">Un ejemplo es un módulo de contenedor de página básica (un módulo de nivel superior para cualquier página) que define varias franjas importantes:</span><span class="sxs-lookup"><span data-stu-id="1470f-119">An example is a basic page container module (a top-level module for any page) that defines several important slots:</span></span>

- <span data-ttu-id="1470f-120">Una franja de encabezado</span><span class="sxs-lookup"><span data-stu-id="1470f-120">A header slot</span></span>
- <span data-ttu-id="1470f-121">Una franja de cuerpo</span><span class="sxs-lookup"><span data-stu-id="1470f-121">A body slot</span></span>
- <span data-ttu-id="1470f-122">Una franja de pie de página</span><span class="sxs-lookup"><span data-stu-id="1470f-122">A footer slot</span></span>

<span data-ttu-id="1470f-123">El desarrollador del módulo define estas franjas y determina los módulos secundarios y cuántos módulos secundarios se pueden colocar directamente en él.</span><span class="sxs-lookup"><span data-stu-id="1470f-123">The module's developer defines these slots, and determines which child modules and how many child modules can be put directly inside it.</span></span> <span data-ttu-id="1470f-124">Por ejemplo, la franja de encabezado solo puede admitir un módulo del tipo **Módulo de encabezado**, mientras que la franja del cuerpo puede admitir un número ilimitado de módulos de cualquier tipo (sin incluir otros módulos de contenedor de página).</span><span class="sxs-lookup"><span data-stu-id="1470f-124">For example, the header slot might support only one module of the **Header Module** type, whereas the body slot might support an unlimited number of modules of any type (except other page container modules).</span></span>

<span data-ttu-id="1470f-125">En las herramientas de creación, los autores de página no tienen que saber por adelantado qué módulos se pueden y no se pueden colocar en cada franja.</span><span class="sxs-lookup"><span data-stu-id="1470f-125">In the authoring tools, page authors don't have to know in advance which modules can and can't be put in each slot.</span></span> <span data-ttu-id="1470f-126">Cuando los autores de la página seleccionan una franja e intentan seleccionar un módulo para agregarlo a él, ven una vista filtrada de tipos de módulo que se admiten para esa franja.</span><span class="sxs-lookup"><span data-stu-id="1470f-126">When page authors select a slot and then try to select a module to add to it, they see a filtered view of module types that are supported for that slot.</span></span>

## <a name="content-modules"></a><span data-ttu-id="1470f-127">Módulos de contenido</span><span class="sxs-lookup"><span data-stu-id="1470f-127">Content modules</span></span>

<span data-ttu-id="1470f-128">Los módulos de contenido contienen elementos multimedia y de contenido, como texto (por ejemplo, encabezados, párrafos y vínculos) o referencias de activos (por ejemplo, imágenes, vídeo y PDF).</span><span class="sxs-lookup"><span data-stu-id="1470f-128">Content modules contain content and media elements, such as text (for example, headlines, paragraphs, and links) or asset references (for example, images, video, and PDFs).</span></span> <span data-ttu-id="1470f-129">Algunos ejemplos de tipos de módulo de contenido típicos son **Elemento principal**, **Característica** y **Banner**.</span><span class="sxs-lookup"><span data-stu-id="1470f-129">Examples of typical content module types are **Hero**, **Feature**, and **Banner**.</span></span> <span data-ttu-id="1470f-130">Los módulos de estos tres tipos pueden contener texto o medios, y no requieren módulos secundarios para hacer que algo sea visible en una página.</span><span class="sxs-lookup"><span data-stu-id="1470f-130">Modules of these three types can contain text or media, and they don't require any child modules to make something visible on a page.</span></span>

<span data-ttu-id="1470f-131">La mayoría de las actividades de creación de contenido y página típicas y diaria implican módulos de contenido, principalmente porque estos módulos definen el contenido real que se representa en sus módulos de contenedor principal.</span><span class="sxs-lookup"><span data-stu-id="1470f-131">The majority of typical, day-to-day page and content authoring activities involve content modules, primarily because these modules define the actual content that is rendered in their parent container modules.</span></span> <span data-ttu-id="1470f-132">Hay muchos módulos de contenido disponibles y estos módulos suelen ser las últimos piezas que agregará a la jerarquía de una página de módulos anidados.</span><span class="sxs-lookup"><span data-stu-id="1470f-132">Many content modules are available, and these modules are typically the last pieces that you will add to a page's hierarchy of nested modules.</span></span>

<span data-ttu-id="1470f-133">La ilustración siguiente muestra cómo los módulos se anidan dentro de franjas de módulo de contenedor principal.</span><span class="sxs-lookup"><span data-stu-id="1470f-133">The following illustration shows how modules are nested inside parent container module slots.</span></span>

![Anidación de módulos](../commerce/media/basic-module-nesting.png)

## <a name="add-or-remove-modules"></a><span data-ttu-id="1470f-135">Agregar o quitar módulos</span><span class="sxs-lookup"><span data-stu-id="1470f-135">Add or remove modules</span></span>

<span data-ttu-id="1470f-136">Los siguientes procedimientos describen cómo agregar y quitar módulos.</span><span class="sxs-lookup"><span data-stu-id="1470f-136">The following procedures describe how to add and remove modules.</span></span>

### <a name="add-a-module"></a><span data-ttu-id="1470f-137">Agregar un módulo</span><span class="sxs-lookup"><span data-stu-id="1470f-137">Add a module</span></span>

<span data-ttu-id="1470f-138">Para agregar un módulo a una franja o un contenedor de una página, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="1470f-138">To add a module to a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="1470f-139">En el panel de esquema de la izquierda, seleccione un contenedor o una franja a la que se pueda agregar un módulo secundario.</span><span class="sxs-lookup"><span data-stu-id="1470f-139">In the outline pane on the left, select a container or slot that a child module can be added to.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1470f-140">El diseñador del módulo define la lista de tipos de módulos que se pueden agregar a una franja específica del módulo.</span><span class="sxs-lookup"><span data-stu-id="1470f-140">The module designer defines the list of modules types that can be added to a specific module slot.</span></span> <span data-ttu-id="1470f-141">A continuación, los autores de plantilla pueden limitar las opciones de módulo permitidas para ayudar a garantizar la optimización de motor de búsqueda (SEO) coherente y la eficiencia de creación para todas las páginas que se crean a partir de una plantilla específica.</span><span class="sxs-lookup"><span data-stu-id="1470f-141">Template authors can then refine the allowed module options to help guarantee consistent search engine optimization (SEO) and authoring efficiency for all the pages pages that are built from a specific template.</span></span>

1. <span data-ttu-id="1470f-142">Seleccione el botón de puntos suspensivos (**...**) para el módulo y, a continuación, seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="1470f-142">Select the ellipsis button (**...**) for the module, and then select **Add Module**.</span></span> <span data-ttu-id="1470f-143">Aparece el cuadro **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="1470f-143">The **Add Module** dialog box appears.</span></span> <span data-ttu-id="1470f-144">Este cuadro de diálogo se filtra automáticamente de modo que muestre solo los módulos que se admiten en la franja o el contenedor seleccionado.</span><span class="sxs-lookup"><span data-stu-id="1470f-144">This dialog box is automatically filtered so that it shows only modules that are supported in the selected container or slot.</span></span> <span data-ttu-id="1470f-145">La lista de módulos viene determinada por la plantilla de la página o la definición del módulo de contenedor.</span><span class="sxs-lookup"><span data-stu-id="1470f-145">The list of modules is determined by the page's template or the container module definition.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1470f-146">Si un contenedor o franja no admite nuevos módulos secundarios, la opción **Agregar módulo** no está disponible.</span><span class="sxs-lookup"><span data-stu-id="1470f-146">If a container or slot doesn't support new child modules, the **Add Module** option is unavailable.</span></span>

1. <span data-ttu-id="1470f-147">En el cuadro de diálogo, busque y seleccione un módulo para agregarlo a la página.</span><span class="sxs-lookup"><span data-stu-id="1470f-147">In the dialog box, search for and select a module to add to your page.</span></span>

    > [!TIP]
    > <span data-ttu-id="1470f-148">**Característica** y **Elemento principal** son buenos tipos de módulos para que los principiantes trabajen con ellos.</span><span class="sxs-lookup"><span data-stu-id="1470f-148">**Feature** and **Hero** are good module types for beginners to work with.</span></span>

1. <span data-ttu-id="1470f-149">Seleccione **Aceptar** para agregar el módulo seleccionado a la franja o al contenedor seleccionado de su página.</span><span class="sxs-lookup"><span data-stu-id="1470f-149">Select **OK** to add the selected module to the selected container or slot on your page.</span></span>

### <a name="remove-a-module"></a><span data-ttu-id="1470f-150">Quitar un módulo</span><span class="sxs-lookup"><span data-stu-id="1470f-150">Remove a module</span></span>

<span data-ttu-id="1470f-151">Para eliminar un módulo de una franja o un contenedor de una página, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="1470f-151">To remove a module from a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="1470f-152">En el panel de esquema de la izquierda, seleccione el botón de puntos suspensivos que se encuentra junto al módulo que se va a eliminar y, a continuación, seleccione el botón de papelera.</span><span class="sxs-lookup"><span data-stu-id="1470f-152">In the outline pane on the left, select the ellipsis button next to the name of the module to remove, and then select the trash can button.</span></span>
1. <span data-ttu-id="1470f-153">Cuando se le pida confirmar que desea quitar el módulo, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1470f-153">When you're prompted to confirm that you want to remove the module, select **OK**.</span></span>

## <a name="configure-modules"></a><span data-ttu-id="1470f-154">Configurar módulos</span><span class="sxs-lookup"><span data-stu-id="1470f-154">Configure modules</span></span>

<span data-ttu-id="1470f-155">Los siguientes procedimientos describen cómo configurar contenido y módulos de contenedor.</span><span class="sxs-lookup"><span data-stu-id="1470f-155">The following procedures describe how to configure content and container modules.</span></span>

### <a name="configure-a-content-module"></a><span data-ttu-id="1470f-156">Configurar un módulo de contenido</span><span class="sxs-lookup"><span data-stu-id="1470f-156">Configure a content module</span></span>

<span data-ttu-id="1470f-157">Para configurar un módulo de contenido en una página, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="1470f-157">To configure a content module on a page, follow these steps.</span></span>

1. <span data-ttu-id="1470f-158">En el panel de esquema de la izquierda, seleccione un tipo de módulo de contenido (por ejemplo, **Característica**, **Elemento principal** o **Banner**).</span><span class="sxs-lookup"><span data-stu-id="1470f-158">In the outline pane on the left, select a content module type (for example, **Feature**, **Hero**, or **Banner**).</span></span>
1. <span data-ttu-id="1470f-159">En el panel de propiedades de la derecha, expanda los controles anidados seleccionando los encabezados y establezca los valores de control necesarios.</span><span class="sxs-lookup"><span data-stu-id="1470f-159">In the properties pane on the right, expand the nested controls by selecting the headers, and set any required control values.</span></span>
1. <span data-ttu-id="1470f-160">Si el panel de propiedades tiene una sección **Configuración de datos**, selecciónela para expandirla.</span><span class="sxs-lookup"><span data-stu-id="1470f-160">If the properties pane has a **Data Configuration** section, select it to expand it.</span></span> <span data-ttu-id="1470f-161">De lo contrario, vaya al paso 5.</span><span class="sxs-lookup"><span data-stu-id="1470f-161">Otherwise, go to step 5.</span></span>
1. <span data-ttu-id="1470f-162">Si hay un botón **Agregar origen de datos**, selecciónelo y seleccione los elementos de contenido que desea agregar.</span><span class="sxs-lookup"><span data-stu-id="1470f-162">If there is a **Add Data Source** button, select it, and then select the content items to add.</span></span>
1. <span data-ttu-id="1470f-163">Especificar valores para controles de módulos requeridos o deseados.</span><span class="sxs-lookup"><span data-stu-id="1470f-163">Enter settings for any required or desired module controls.</span></span>
1. <span data-ttu-id="1470f-164">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1470f-164">Select **Save**.</span></span>

### <a name="configure-a-container-module"></a><span data-ttu-id="1470f-165">Configurar un módulo de contenedor</span><span class="sxs-lookup"><span data-stu-id="1470f-165">Configure a container module</span></span>

<span data-ttu-id="1470f-166">Para configurar un módulo de contenedor en una página, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="1470f-166">To configure a container module on a page, follow these steps.</span></span>

1. <span data-ttu-id="1470f-167">Seleccione un módulo de contenedor en su página (por ejemplo, un módulo de contenido de fluido o carrusel).</span><span class="sxs-lookup"><span data-stu-id="1470f-167">Select a container module on your page (for example, a carousel or fluid container module).</span></span>
1. <span data-ttu-id="1470f-168">En el panel de propiedades de la derecha, expanda los controles anidados seleccionando los encabezados y establezca los valores de control necesarios.</span><span class="sxs-lookup"><span data-stu-id="1470f-168">In the properties pane on the right, expand the nested controls by selecting the headers, and set any required control values.</span></span>
1. <span data-ttu-id="1470f-169">En el panel de esquema de la izquierda, seleccione el botón de puntos suspensivos que se encuentra junto al nombre del contenedor o de cualquier franja que se encuentre dentro del contenedor y, a continuación, seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="1470f-169">In the outline pane on the left, select the ellipsis button next to the name of either the container or any slots inside the container, and then select **Add Module**.</span></span> <span data-ttu-id="1470f-170">A continuación, agregue módulos secundarios al contenedor seleccionado.</span><span class="sxs-lookup"><span data-stu-id="1470f-170">Then add child modules to the selected container.</span></span> <span data-ttu-id="1470f-171">Para obtener más información, consulte el procedimiento [Agregar un módulo](#add-a-module) descrito anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="1470f-171">For more information, see the [Add a module](#add-a-module) procedure earlier in this topic.</span></span>
1. <span data-ttu-id="1470f-172">Si existen varios módulos secundarios como elementos del mismo nivel en un contenedor principal, puede cambiar su orden de visualización en el contenedor principal.</span><span class="sxs-lookup"><span data-stu-id="1470f-172">If multiple child modules exist as siblings in a parent container, you can change their display order in the parent container.</span></span> <span data-ttu-id="1470f-173">Seleccione el botón de puntos suspensivos para un módulo y utilice los botones de flecha arriba y flecha abajo.</span><span class="sxs-lookup"><span data-stu-id="1470f-173">Select the ellipsis button for a module, and then use the up arrow and down arrow buttons.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1470f-174">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="1470f-174">Additional resources</span></span>

[<span data-ttu-id="1470f-175">Visión general de plantillas y diseños</span><span class="sxs-lookup"><span data-stu-id="1470f-175">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="1470f-176">Trabajar con plantillas</span><span class="sxs-lookup"><span data-stu-id="1470f-176">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="1470f-177">Trabajar con diseños predefinidos</span><span class="sxs-lookup"><span data-stu-id="1470f-177">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="1470f-178">Trabajar con fragmentos</span><span class="sxs-lookup"><span data-stu-id="1470f-178">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="1470f-179">Agregar un módulo de contenedor a una página</span><span class="sxs-lookup"><span data-stu-id="1470f-179">Add a container module to a page</span></span>](add-container-module.md)

[<span data-ttu-id="1470f-180">Agregar módulos de colocación de contenido a una página</span><span class="sxs-lookup"><span data-stu-id="1470f-180">Add content placement modules to a page</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="1470f-181">Trabajar con grupos de publicación</span><span class="sxs-lookup"><span data-stu-id="1470f-181">Work with publish groups</span></span>](publish-groups.md)

