---
title: Trabajar con módulos
description: Este tema describe cómo y cuándo usar módulos en Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6d872719d3b1aa27ccfdcf36d7739c883e7b4996
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801370"
---
# <a name="work-with-modules"></a><span data-ttu-id="2abbc-103">Trabajar con módulos</span><span class="sxs-lookup"><span data-stu-id="2abbc-103">Work with modules</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2abbc-104">Este tema describe cómo y cuándo usar módulos en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2abbc-104">This topic describes how and when to use modules in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="2abbc-105">Los módulos son bloques de creación lógicos que componen su estructura de página y tienen diversos propósitos y ámbitos.</span><span class="sxs-lookup"><span data-stu-id="2abbc-105">Modules are logical building blocks that make up your page structure, and they have various purposes and scopes.</span></span> <span data-ttu-id="2abbc-106">Algunos módulos son contenedores de alto nivel y su único propósito es mantener y organizar otros módulos (módulos secundarios).</span><span class="sxs-lookup"><span data-stu-id="2abbc-106">Some modules are high-level containers, and their only purpose is to hold and organize other modules (child modules).</span></span> <span data-ttu-id="2abbc-107">Otros módulos, como un módulo de ubicación de imagen sencillo, tienen un propósito muy específico.</span><span class="sxs-lookup"><span data-stu-id="2abbc-107">Other modules, such as a simple image placement module, have a very specific purpose.</span></span> <span data-ttu-id="2abbc-108">Otros módulos, como un módulo de carrusel, se encuentren en algún lugar entre esas dos categorías.</span><span class="sxs-lookup"><span data-stu-id="2abbc-108">Other modules, such as a carousel module, fall somewhere between those two categories.</span></span>

<span data-ttu-id="2abbc-109">De manera predeterminada, el sitio de Dynamics 365 Commerce incluye una biblioteca de módulos que le permite obtener la mayoría de los escenarios de comercio electrónico básicos.</span><span class="sxs-lookup"><span data-stu-id="2abbc-109">By default, your Dynamics 365 Commerce site includes a module library that lets you achieve most basic e-Commerce scenarios.</span></span> <span data-ttu-id="2abbc-110">Debería poder crear un sitio de comercio electrónico integral solo con estos módulos.</span><span class="sxs-lookup"><span data-stu-id="2abbc-110">You should be able to construct an end-to-end e-Commerce site just by using these modules.</span></span> <span data-ttu-id="2abbc-111">Sin embargo, también podría desea personalizar estos módulos o crear módulos personalizados nuevos para necesidades específicas.</span><span class="sxs-lookup"><span data-stu-id="2abbc-111">However, you might also want to customize these modules or build new, custom modules for specific needs.</span></span> <span data-ttu-id="2abbc-112">Si desea crear módulos personalizados, un kit de desarrollo de software (SDK) de diseño de módulo está disponible para ayudarle a crear una biblioteca de módulo personalizada.</span><span class="sxs-lookup"><span data-stu-id="2abbc-112">If you want to build custom modules, a module design software development kit (SDK) is available to help you create a custom module library.</span></span>

## <a name="container-modules-and-slots"></a><span data-ttu-id="2abbc-113">Franjas y módulos de contenedor</span><span class="sxs-lookup"><span data-stu-id="2abbc-113">Container modules and slots</span></span>

<span data-ttu-id="2abbc-114">Como se mencionó anteriormente, algunos módulos están diseñados para mantener módulos secundarios.</span><span class="sxs-lookup"><span data-stu-id="2abbc-114">As was mentioned earlier, some modules are designed to hold child modules.</span></span> <span data-ttu-id="2abbc-115">Esos módulos se conocen como *contenedores* y permiten jerarquías de módulos anidados.</span><span class="sxs-lookup"><span data-stu-id="2abbc-115">These modules are known as *containers*, and they allow for hierarchies of nested modules.</span></span> <span data-ttu-id="2abbc-116">Los módulos de contenedor incluyen *franjas*.</span><span class="sxs-lookup"><span data-stu-id="2abbc-116">Container modules include *slots*.</span></span> <span data-ttu-id="2abbc-117">Las franjas se usan para administrar el diseño y el propósito de módulos secundarios en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="2abbc-117">Slots are used to handle the layout and purpose of child modules in the container.</span></span> <span data-ttu-id="2abbc-118">Un ejemplo es un módulo de contenedor de página básica (un módulo de nivel superior para cualquier página) que define varias franjas importantes:</span><span class="sxs-lookup"><span data-stu-id="2abbc-118">An example is a basic page container module (a top-level module for any page) that defines several important slots:</span></span>

- <span data-ttu-id="2abbc-119">Una franja de encabezado</span><span class="sxs-lookup"><span data-stu-id="2abbc-119">A header slot</span></span>
- <span data-ttu-id="2abbc-120">Una franja de subencabezado</span><span class="sxs-lookup"><span data-stu-id="2abbc-120">A sub-header slot</span></span>
- <span data-ttu-id="2abbc-121">Una franja principal</span><span class="sxs-lookup"><span data-stu-id="2abbc-121">A main slot</span></span>
- <span data-ttu-id="2abbc-122">Una franja de pie de página</span><span class="sxs-lookup"><span data-stu-id="2abbc-122">A footer slot</span></span>
- <span data-ttu-id="2abbc-123">Una franja de subpie de página</span><span class="sxs-lookup"><span data-stu-id="2abbc-123">A sub-footer slot</span></span>

<span data-ttu-id="2abbc-124">El desarrollador del módulo define estas franjas y determina los módulos secundarios y cuántos módulos secundarios se pueden colocar directamente en él.</span><span class="sxs-lookup"><span data-stu-id="2abbc-124">The module's developer defines these slots, and determines which child modules and how many child modules can be put directly inside it.</span></span> <span data-ttu-id="2abbc-125">Por ejemplo, la franja de encabezado solo puede admitir un módulo del tipo **Módulo de encabezado**, mientras que la franja del cuerpo puede admitir un número ilimitado de módulos de cualquier tipo (sin incluir otros módulos de contenedor de página).</span><span class="sxs-lookup"><span data-stu-id="2abbc-125">For example, the header slot might support only one module of the **Header Module** type, whereas the body slot might support an unlimited number of modules of any type (except other page container modules).</span></span>

<span data-ttu-id="2abbc-126">En las herramientas de creación, los autores de página no tienen que saber por adelantado qué módulos se pueden y no se pueden colocar en cada franja.</span><span class="sxs-lookup"><span data-stu-id="2abbc-126">In the authoring tools, page authors don't have to know in advance which modules can and can't be put in each slot.</span></span> <span data-ttu-id="2abbc-127">Cuando los autores de la página seleccionan una franja e intentan seleccionar un módulo para agregarlo a él, ven una vista filtrada de tipos de módulo que se admiten para esa franja.</span><span class="sxs-lookup"><span data-stu-id="2abbc-127">When page authors select a slot and then try to select a module to add to it, they see a filtered view of module types that are supported for that slot.</span></span>

## <a name="content-modules"></a><span data-ttu-id="2abbc-128">Módulos de contenido</span><span class="sxs-lookup"><span data-stu-id="2abbc-128">Content modules</span></span>

<span data-ttu-id="2abbc-129">Los módulos de contenido contienen elementos multimedia y de contenido, como texto (por ejemplo, encabezados, párrafos y vínculos) o referencias de activos (por ejemplo, imágenes, vídeo y PDF).</span><span class="sxs-lookup"><span data-stu-id="2abbc-129">Content modules contain content and media elements, such as text (for example, headlines, paragraphs, and links) or asset references (for example, images, video, and PDFs).</span></span> <span data-ttu-id="2abbc-130">Los tipos de módulos de contenido típicos incluyen bloques de contenido, bloques de texto y módulos de banner promocional.</span><span class="sxs-lookup"><span data-stu-id="2abbc-130">Typical content module types include content block, text block, and promo banner modules.</span></span> <span data-ttu-id="2abbc-131">Los módulos de estos tres tipos pueden contener texto o medios, y no requieren módulos secundarios para hacer que algo sea visible en una página.</span><span class="sxs-lookup"><span data-stu-id="2abbc-131">Modules of these three types can contain text or media, and they don't require any child modules to make something visible on a page.</span></span>

<span data-ttu-id="2abbc-132">La mayoría de las actividades de creación de contenido y página típicas y diaria implican módulos de contenido, principalmente porque estos módulos definen el contenido real que se representa en sus módulos de contenedor principal.</span><span class="sxs-lookup"><span data-stu-id="2abbc-132">The majority of typical, day-to-day page and content authoring activities involve content modules, primarily because these modules define the actual content that is rendered in their parent container modules.</span></span> <span data-ttu-id="2abbc-133">Hay muchos módulos de contenido disponibles y estos módulos suelen ser las últimos piezas que agregará a la jerarquía de una página de módulos anidados.</span><span class="sxs-lookup"><span data-stu-id="2abbc-133">Many content modules are available, and these modules are typically the last pieces that you will add to a page's hierarchy of nested modules.</span></span>

<span data-ttu-id="2abbc-134">La ilustración siguiente muestra cómo los módulos se anidan dentro de franjas de módulo de contenedor principal.</span><span class="sxs-lookup"><span data-stu-id="2abbc-134">The following illustration shows how modules are nested inside parent container module slots.</span></span>

![Anidación de módulos](../commerce/media/basic-module-nesting.png)

## <a name="add-or-remove-modules"></a><span data-ttu-id="2abbc-136">Agregar o quitar módulos</span><span class="sxs-lookup"><span data-stu-id="2abbc-136">Add or remove modules</span></span>

<span data-ttu-id="2abbc-137">Los siguientes procedimientos describen cómo agregar y quitar módulos.</span><span class="sxs-lookup"><span data-stu-id="2abbc-137">The following procedures describe how to add and remove modules.</span></span>

### <a name="add-a-module"></a><span data-ttu-id="2abbc-138">Agregar un módulo</span><span class="sxs-lookup"><span data-stu-id="2abbc-138">Add a module</span></span>

<span data-ttu-id="2abbc-139">Para agregar un módulo a una franja o un contenedor de una página, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2abbc-139">To add a module to a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="2abbc-140">En el panel de esquema de la izquierda o directamente en el lienzo principal, seleccione un contenedor o una franja a la que se pueda agregar un módulo secundario.</span><span class="sxs-lookup"><span data-stu-id="2abbc-140">In the outline pane on the left or directly in the main canvas, select a container or slot to which a child module can be added.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2abbc-141">El diseñador del módulo define la lista de tipos de módulos que se pueden agregar a una franja específica del módulo.</span><span class="sxs-lookup"><span data-stu-id="2abbc-141">The module designer defines the list of modules types that can be added to a specific module slot.</span></span> <span data-ttu-id="2abbc-142">A continuación, los autores de plantilla pueden limitar las opciones de módulo permitidas para ayudar a garantizar la optimización de motor de búsqueda (SEO) coherente y la eficiencia de creación para todas las páginas que se crean a partir de una plantilla específica.</span><span class="sxs-lookup"><span data-stu-id="2abbc-142">Template authors can then refine the allowed module options to help guarantee consistent search engine optimization (SEO) and authoring efficiency for all the pages that are built from a specific template.</span></span> <span data-ttu-id="2abbc-143">Cuando agregue un módulo a una franja, el cuadro de diálogo **Agregar módulo** se filtra automáticamente de modo que muestre solo los módulos que se admiten en la franja o el contenedor seleccionado.</span><span class="sxs-lookup"><span data-stu-id="2abbc-143">When adding a module to a slot, the **Add Module** dialog box is automatically filtered so that it shows only modules that are supported in the selected container or slot.</span></span> <span data-ttu-id="2abbc-144">Esta lista de módulos permitidos viene determinada por la plantilla de la página o la definición del módulo de contenedor.</span><span class="sxs-lookup"><span data-stu-id="2abbc-144">This list of allowed modules is determined by the page's template or the container's module definition.</span></span>

1. <span data-ttu-id="2abbc-145">Si usa el panel de contorno, seleccione los puntos suspensivos (**...**) junto al nombre del módulo y luego seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="2abbc-145">If using the outline pane, select the ellipsis (**...**) next to the module name, and then select **Add Module**.</span></span> <span data-ttu-id="2abbc-146">Si usa los controles directamente dentro del lienzo, seleccione el símbolo más (**+**) en una franja vacía o adyacente al módulo seleccionado actualmente, y luego seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="2abbc-146">If using the controls directly within the canvas, select the plus symbol (**+**) in an empty slot or adjacent to the currently selected module, and then select **Add Module**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2abbc-147">Si un contenedor o franja no admite nuevos módulos secundarios, la opción **Agregar módulo** no está disponible.</span><span class="sxs-lookup"><span data-stu-id="2abbc-147">If a container or slot doesn't support new child modules, the **Add Module** option is unavailable.</span></span>

1. <span data-ttu-id="2abbc-148">En el cuadro de diálogo **Agregar módulo**, seleccione un módulo para agregarlo a la página.</span><span class="sxs-lookup"><span data-stu-id="2abbc-148">In the **Add Module** dialog box, select a module to add to your page.</span></span>

    > [!TIP]
    > <span data-ttu-id="2abbc-149">**Bloque de contenido** es un buen tipo de módulo para que trabajen con él los principiantes.</span><span class="sxs-lookup"><span data-stu-id="2abbc-149">**Content block** is a good module type for beginners to work with.</span></span>

1. <span data-ttu-id="2abbc-150">Seleccione **Aceptar** para agregar el módulo seleccionado a la franja o al contenedor seleccionado de su página.</span><span class="sxs-lookup"><span data-stu-id="2abbc-150">Select **OK** to add the selected module to the selected container or slot on your page.</span></span>

### <a name="remove-a-module"></a><span data-ttu-id="2abbc-151">Quitar un módulo</span><span class="sxs-lookup"><span data-stu-id="2abbc-151">Remove a module</span></span>

<span data-ttu-id="2abbc-152">Para eliminar un módulo de una franja o un contenedor de una página, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2abbc-152">To remove a module from a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="2abbc-153">En el panel de esquema de la izquierda, seleccione el botón de puntos suspensivos (**...**) que se encuentra junto al módulo que se va a eliminar y, a continuación, seleccione el símbolo de papelera.</span><span class="sxs-lookup"><span data-stu-id="2abbc-153">In the outline pane on the left, select the ellipsis (**...**) next to the name of the module to be removed, and then select the trash can symbol.</span></span> <span data-ttu-id="2abbc-154">Alternativamente, en el lienzo principal puede seleccionar el símbolo de la papelera en la barra de herramientas de un módulo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="2abbc-154">Alternately, in the main canvas you can select the trash can symbol on a selected module's toolbar.</span></span>
1. <span data-ttu-id="2abbc-155">Cuando se le pida confirmar que desea quitar el módulo, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2abbc-155">When prompted to confirm that you want to remove the module, select **OK**.</span></span>

## <a name="move-a-module-to-a-new-position"></a><span data-ttu-id="2abbc-156">Mover un módulo a una nueva posición</span><span class="sxs-lookup"><span data-stu-id="2abbc-156">Move a module to a new position</span></span>

<span data-ttu-id="2abbc-157">Para mover un módulo a una nueva posición dentro de su página, use cualquiera de los siguientes métodos.</span><span class="sxs-lookup"><span data-stu-id="2abbc-157">To move a module to a new position within your page, use any of the following methods.</span></span>

### <a name="move-a-module-using-the-outline-pane"></a><span data-ttu-id="2abbc-158">Mover un módulo usando el panel de esquema</span><span class="sxs-lookup"><span data-stu-id="2abbc-158">Move a module using the outline pane</span></span>

<span data-ttu-id="2abbc-159">Para mover un módulo usando el panel de contorno, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2abbc-159">To move a module using the outline pane, follow these steps.</span></span>

1. <span data-ttu-id="2abbc-160">Seleccione y mantenga presionado el módulo que desea mover en el panel de contorno, luego arrastre el módulo a una nueva posición en el esquema.</span><span class="sxs-lookup"><span data-stu-id="2abbc-160">Select and hold the module you want to move in the outline pane, then drag the module to a new position in the outline.</span></span> <span data-ttu-id="2abbc-161">La línea azul en el contorno y en el lienzo indica dónde se puede colocar el módulo.</span><span class="sxs-lookup"><span data-stu-id="2abbc-161">The blue line in the outline and on the canvas indicates where the module can be placed.</span></span>
1. <span data-ttu-id="2abbc-162">Suelte el módulo para colocarlo en la nueva posición.</span><span class="sxs-lookup"><span data-stu-id="2abbc-162">Release the module to drop it into the new position.</span></span>

### <a name="move-a-module-directly-within-the-canvas"></a><span data-ttu-id="2abbc-163">Mover un módulo directamente dentro del lienzo</span><span class="sxs-lookup"><span data-stu-id="2abbc-163">Move a module directly within the canvas</span></span>

<span data-ttu-id="2abbc-164">Para mover un módulo directamente dentro del lienzo, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2abbc-164">To move a module directly within the canvas, follow these steps.</span></span>

1. <span data-ttu-id="2abbc-165">Seleccione el módulo que desea mover en el lienzo.</span><span class="sxs-lookup"><span data-stu-id="2abbc-165">Select the module you want to move in the canvas.</span></span> 
1. <span data-ttu-id="2abbc-166">Seleccione un símbolo de flecha hacia arriba o hacia abajo en la barra de herramientas del módulo y luego arrastre la flecha a una nueva posición en la página.</span><span class="sxs-lookup"><span data-stu-id="2abbc-166">Select either an upward or downward pointing arrow symbol in the module's toolbar, and then drag the arrow to a new position on the page.</span></span> <span data-ttu-id="2abbc-167">La línea azul en el contorno y en el lienzo indica dónde se puede colocar el módulo.</span><span class="sxs-lookup"><span data-stu-id="2abbc-167">The blue line in the canvas and outline indicates where the module can be placed.</span></span> <span data-ttu-id="2abbc-168">Si un módulo no se puede mover hacia arriba o hacia abajo, ese símbolo de flecha aparecerá atenuado.</span><span class="sxs-lookup"><span data-stu-id="2abbc-168">If a module cannot be moved up or down, that arrow symbol will be grayed out.</span></span> 
1. <span data-ttu-id="2abbc-169">Suelte el módulo para colocarlo en la nueva posición.</span><span class="sxs-lookup"><span data-stu-id="2abbc-169">Release the module to drop it into the new position.</span></span>

### <a name="move-a-module-using-the-ellipsis-menu"></a><span data-ttu-id="2abbc-170">Mover un módulo usando el menú de los puntos suspensivos</span><span class="sxs-lookup"><span data-stu-id="2abbc-170">Move a module using the ellipsis menu</span></span>

<span data-ttu-id="2abbc-171">Para mover un módulo usando el menú de los puntos suspensivos, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2abbc-171">To move a module using the ellipsis menu, follow these steps.</span></span>

1. <span data-ttu-id="2abbc-172">Seleccione un módulo en el esquema o el lienzo.</span><span class="sxs-lookup"><span data-stu-id="2abbc-172">Select a module in either the outline or the canvas.</span></span>
1. <span data-ttu-id="2abbc-173">Seleccione los puntos suspensivos (**...**) junto al nombre del módulo en el panel de contorno o en la barra de herramientas del módulo en el lienzo.</span><span class="sxs-lookup"><span data-stu-id="2abbc-173">Select the ellipsis (**...**) next to the module's name in the outline pane, or in the module's toolbar in the canvas.</span></span>
1. <span data-ttu-id="2abbc-174">Si el módulo se puede mover hacia arriba o hacia abajo dentro del contenedor o la ranura, verá opciones para **Ascender** o **Descender**.</span><span class="sxs-lookup"><span data-stu-id="2abbc-174">If the module can be moved up or down within the container or slot, you will see options for **Move up** or **Move down**.</span></span> <span data-ttu-id="2abbc-175">Seleccione la opción de movimiento deseada para mover el módulo hacia arriba o hacia abajo en relación con los elementos del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="2abbc-175">Select the desired move option to move the module up or down relative to its siblings.</span></span>

## <a name="configure-modules"></a><span data-ttu-id="2abbc-176">Configurar módulos</span><span class="sxs-lookup"><span data-stu-id="2abbc-176">Configure modules</span></span>

<span data-ttu-id="2abbc-177">Los siguientes procedimientos describen cómo configurar contenido y módulos de contenedor.</span><span class="sxs-lookup"><span data-stu-id="2abbc-177">The following procedures describe how to configure content and container modules.</span></span>

### <a name="configure-a-content-module"></a><span data-ttu-id="2abbc-178">Configurar un módulo de contenido</span><span class="sxs-lookup"><span data-stu-id="2abbc-178">Configure a content module</span></span>

<span data-ttu-id="2abbc-179">Para configurar un módulo de contenido en una página, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2abbc-179">To configure a content module on a page, follow these steps.</span></span>

1. <span data-ttu-id="2abbc-180">En el panel de esquema de la izquierda, expanda el árbol y seleccione cualquier módulo de contenido (por ejemplo,**Bloque de contenido**).</span><span class="sxs-lookup"><span data-stu-id="2abbc-180">In the outline pane on the left, expand the tree and select any content module (for example, **Content block**).</span></span> <span data-ttu-id="2abbc-181">De forma alternativa, puede seleccionar el módulo en el lienzo principal.</span><span class="sxs-lookup"><span data-stu-id="2abbc-181">Alternately, you can select the module in the main canvas.</span></span>
1. <span data-ttu-id="2abbc-182">En el panel de propiedades del módulo a la derecha, indique las propiedades de los controles de módulo deseados.</span><span class="sxs-lookup"><span data-stu-id="2abbc-182">In the module properties pane on the right, enter properties for any desired module controls.</span></span>
1. <span data-ttu-id="2abbc-183">En la barra de comandos, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2abbc-183">On the command bar, select **Save**.</span></span> <span data-ttu-id="2abbc-184">Esto también actualizará el lienzo de vista previa.</span><span class="sxs-lookup"><span data-stu-id="2abbc-184">This will also refresh the preview canvas.</span></span>

### <a name="edit-module-text-properties"></a><span data-ttu-id="2abbc-185">Editar las propiedades del texto del módulo</span><span class="sxs-lookup"><span data-stu-id="2abbc-185">Edit module text properties</span></span>

<span data-ttu-id="2abbc-186">Las propiedades de texto del módulo que no son de solo lectura se pueden editar directamente en el lienzo.</span><span class="sxs-lookup"><span data-stu-id="2abbc-186">Module text properties that are not read-only can be edited directly in the canvas.</span></span>

<span data-ttu-id="2abbc-187">Para editar las propiedades del texto del módulo, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2abbc-187">To edit module text properties, follow these steps.</span></span>

1. <span data-ttu-id="2abbc-188">Seleccione el control de texto en el lienzo, luego coloque el cursor donde desee editar el texto.</span><span class="sxs-lookup"><span data-stu-id="2abbc-188">Select the text control in the canvas, then place your cursor where you wish to edit text.</span></span>
1. <span data-ttu-id="2abbc-189">Especifique el contenido de texto.</span><span class="sxs-lookup"><span data-stu-id="2abbc-189">Enter your text content.</span></span>
1. <span data-ttu-id="2abbc-190">Seleccione cualquier lugar fuera del contenido de texto para continuar editando otro contenido.</span><span class="sxs-lookup"><span data-stu-id="2abbc-190">Select anywhere outside the text content to continue editing other content.</span></span>

### <a name="inline-image-selection"></a><span data-ttu-id="2abbc-191">Selección de una imagen en línea</span><span class="sxs-lookup"><span data-stu-id="2abbc-191">Inline image selection</span></span>

<span data-ttu-id="2abbc-192">Las imágenes del módulo que no son de solo lectura se pueden cambiar directamente en el lienzo.</span><span class="sxs-lookup"><span data-stu-id="2abbc-192">Module images that are not read-only can be changed directly from the canvas.</span></span>

<span data-ttu-id="2abbc-193">Para elegir una nueva imagen para un módulo de contenido, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2abbc-193">To choose a new image for a content module, follow these steps.</span></span>

1. <span data-ttu-id="2abbc-194">En el lienzo, haga doble clic en la imagen.</span><span class="sxs-lookup"><span data-stu-id="2abbc-194">In the canvas, double-click the image.</span></span> <span data-ttu-id="2abbc-195">Esto abrirá la ventana del selector multimedia.</span><span class="sxs-lookup"><span data-stu-id="2abbc-195">This will bring up the media picker window.</span></span>
1. <span data-ttu-id="2abbc-196">Busque y seleccione una nueva imagen que desee usar, y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2abbc-196">Find and select a new image you want to use, and then select **OK**.</span></span> <span data-ttu-id="2abbc-197">La nueva imagen ahora se representa en el lienzo.</span><span class="sxs-lookup"><span data-stu-id="2abbc-197">The new image is now rendered in the canvas.</span></span>

### <a name="configure-a-container-module"></a><span data-ttu-id="2abbc-198">Configurar un módulo de contenedor</span><span class="sxs-lookup"><span data-stu-id="2abbc-198">Configure a container module</span></span>

<span data-ttu-id="2abbc-199">Para configurar un módulo de contenedor en una página, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2abbc-199">To configure a container module on a page, follow these steps.</span></span>

1. <span data-ttu-id="2abbc-200">Seleccione un módulo de contenedor en su página (por ejemplo, un módulo de contenido de fluido o carrusel).</span><span class="sxs-lookup"><span data-stu-id="2abbc-200">Select a container module on your page (for example, a carousel or fluid container module).</span></span>
1. <span data-ttu-id="2abbc-201">En el panel de propiedades de la derecha, expanda los controles anidados seleccionando los encabezados y establezca los valores de control necesarios.</span><span class="sxs-lookup"><span data-stu-id="2abbc-201">In the properties pane on the right, expand the nested controls by selecting the headers, and set any required control values.</span></span>
1. <span data-ttu-id="2abbc-202">En el panel de esquema de la izquierda, seleccione el botón de puntos suspensivos que se encuentra junto al nombre del contenedor o de cualquier franja que se encuentre dentro del contenedor y, a continuación, seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="2abbc-202">In the outline pane on the left, select the ellipsis button next to the name of either the container or any slots inside the container, and then select **Add Module**.</span></span> <span data-ttu-id="2abbc-203">A continuación, agregue módulos secundarios al contenedor seleccionado.</span><span class="sxs-lookup"><span data-stu-id="2abbc-203">Then, add child modules to the selected container.</span></span> <span data-ttu-id="2abbc-204">Para obtener más información, consulte la sección [Trabajar con módulos](#add-a-module) descrita anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="2abbc-204">For more information, see the [Work with modules](#add-a-module) section earlier in this topic.</span></span>
1. <span data-ttu-id="2abbc-205">Si existen varios módulos secundarios como elementos del mismo nivel en un contenedor principal, puede cambiar su orden de visualización en el contenedor principal.</span><span class="sxs-lookup"><span data-stu-id="2abbc-205">If multiple child modules exist as siblings in a parent container, you can change their display order in the parent container.</span></span> <span data-ttu-id="2abbc-206">Seleccione el botón de puntos suspensivos para un módulo y utilice los botones de flecha arriba y flecha abajo.</span><span class="sxs-lookup"><span data-stu-id="2abbc-206">Select the ellipsis button for a module, and then use the up arrow and down arrow buttons.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2abbc-207">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="2abbc-207">Additional resources</span></span>

[<span data-ttu-id="2abbc-208">Visión general de plantillas y diseños</span><span class="sxs-lookup"><span data-stu-id="2abbc-208">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="2abbc-209">Trabajar con plantillas</span><span class="sxs-lookup"><span data-stu-id="2abbc-209">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="2abbc-210">Trabajar con diseños predefinidos</span><span class="sxs-lookup"><span data-stu-id="2abbc-210">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="2abbc-211">Trabajar con fragmentos</span><span class="sxs-lookup"><span data-stu-id="2abbc-211">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="2abbc-212">Agregar un módulo de contenedor a una página</span><span class="sxs-lookup"><span data-stu-id="2abbc-212">Add a container module to a page</span></span>](add-container-module.md)

[<span data-ttu-id="2abbc-213">Trabajar con grupos de publicación</span><span class="sxs-lookup"><span data-stu-id="2abbc-213">Work with publish groups</span></span>](publish-groups.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
