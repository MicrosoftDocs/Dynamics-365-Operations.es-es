---
title: Trabajar con fragmentos
description: Este tema describe por qué, cuándo y cómo usar fragmentos en Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: retail
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f1525610fb16edd5ff9ccefe0194f6f27b797b62
ms.sourcegitcommit: b063bf3a52f19baa11ddba31ef9313d58a0f610e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "4019573"
---
# <a name="work-with-fragments"></a><span data-ttu-id="b504d-103">Trabajar con fragmentos</span><span class="sxs-lookup"><span data-stu-id="b504d-103">Work with fragments</span></span> 

[!include [banner](includes/banner.md)]

<span data-ttu-id="b504d-104">Este tema describe por qué, cuándo y cómo usar fragmentos en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b504d-104">This topic describes why, when, and how to use fragments in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="b504d-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="b504d-105">Overview</span></span>

<span data-ttu-id="b504d-106">Los fragmentos permiten una experiencia de creación centralizada para configuraciones de módulos que se deben volver a utilizar en el sitio.</span><span class="sxs-lookup"><span data-stu-id="b504d-106">Fragments allow for a centralized authoring experience for module configurations that must be reused throughout your site.</span></span> <span data-ttu-id="b504d-107">Por ejemplo, los encabezados, los pies de página y los banners a menudo se configuran como fragmentos, ya que se comparten entre muchas páginas.</span><span class="sxs-lookup"><span data-stu-id="b504d-107">For example, headers, footers, and banners are often configured as fragments, because they are shared across many pages.</span></span> <span data-ttu-id="b504d-108">Puede pensar en fragmentos como páginas web en miniatura que se pueden insertar en otras páginas del sitio.</span><span class="sxs-lookup"><span data-stu-id="b504d-108">You can think of fragments as miniature webpages that can be inserted into other pages on your site.</span></span> <span data-ttu-id="b504d-109">Los fragmentos tienen su propio ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="b504d-109">Fragments have their own lifecycle.</span></span> <span data-ttu-id="b504d-110">Es decir, se crean, se hace referencia a ellas, se actualizan y se eliminan como entidades independientes en las herramientas de creación.</span><span class="sxs-lookup"><span data-stu-id="b504d-110">In other words, they are created, referenced, updated, and deleted as independent entities in the authoring tools.</span></span>

<span data-ttu-id="b504d-111">Una vez que se configuran los fragmentos, se pueden usar en cualquier lugar donde se puedan usar los módulos en su estructura de sitio.</span><span class="sxs-lookup"><span data-stu-id="b504d-111">After fragments are configured, they can be used wherever modules can be used in your site structure.</span></span> <span data-ttu-id="b504d-112">Se puede hacer referencia a fragmentos en páginas, diseños, plantillas y otros fragmentos.</span><span class="sxs-lookup"><span data-stu-id="b504d-112">Fragments can be referenced on pages, in layouts, in templates, and in other fragments.</span></span>

> [!NOTE]
> <span data-ttu-id="b504d-113">Los fragmentos se pueden anidar hasta en siete niveles de profundidad dentro de otros fragmentos.</span><span class="sxs-lookup"><span data-stu-id="b504d-113">Fragments can be nested up to seven levels deep inside other fragments.</span></span>

<span data-ttu-id="b504d-114">Por ejemplo, si desea promocionar un evento de temporada en muchas páginas de nuestro sitio, puede usar un fragmento.</span><span class="sxs-lookup"><span data-stu-id="b504d-114">For example, if you want to promote a seasonal event cross many pages on our site, you can use a fragment.</span></span> <span data-ttu-id="b504d-115">El primer paso en el proceso de crear un fragmento nuevo es seleccionar el tipo de módulo desde el que deseas empezar.</span><span class="sxs-lookup"><span data-stu-id="b504d-115">The first step in the process of creating a new fragment is to select the type of module that you want to start from.</span></span> <span data-ttu-id="b504d-116">Para este ejemplo, puede crear el fragmento desde un módulo de elemento principal.</span><span class="sxs-lookup"><span data-stu-id="b504d-116">For this example, you can build the fragment from a hero module.</span></span>

> [!NOTE]
> <span data-ttu-id="b504d-117">Los fragmentos se pueden crear desde cualquier tipo de módulo.</span><span class="sxs-lookup"><span data-stu-id="b504d-117">Fragments can be built from any module type.</span></span>

<span data-ttu-id="b504d-118">A continuación puede configurar el fragmento de elemento principal con su contenido promocional específico.</span><span class="sxs-lookup"><span data-stu-id="b504d-118">You can then configure the hero fragment with your specific promotional content.</span></span> <span data-ttu-id="b504d-119">También puede localizarlo según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="b504d-119">You can also localize it as you require.</span></span> <span data-ttu-id="b504d-120">El nuevo fragmento de elemento principal independiente se puede consumir a continuación como módulo preconfigurado a través del sitio.</span><span class="sxs-lookup"><span data-stu-id="b504d-120">The new stand-alone hero fragment can then be consumed as a preconfigured module throughout your site.</span></span> <span data-ttu-id="b504d-121">Puede agregarlo fácilmente a plantillas, a páginas específicas o a otros fragmentos que pueden contener módulos de elementos principales.</span><span class="sxs-lookup"><span data-stu-id="b504d-121">You can easily add it to templates, to specific pages, or to other fragments that can contain hero modules.</span></span>

<span data-ttu-id="b504d-122">Todos los lugares donde se agrega el fragmento son referencias al fragmento de elemento principal central de héroe que ha creado.</span><span class="sxs-lookup"><span data-stu-id="b504d-122">All the places where the fragment is added are references to the central hero fragment that you created.</span></span> <span data-ttu-id="b504d-123">Si publica cambios en el fragmento, estos cambios se reflejan inmediatamente en todos los lugares donde se hace referencia al fragmento en el sitio.</span><span class="sxs-lookup"><span data-stu-id="b504d-123">If you publish changes to the fragment, those changes are immediately reflected in all the places where the fragment is referenced across the site.</span></span> <span data-ttu-id="b504d-124">Por lo tanto, los fragmentos ofrecen una manera potente y eficaz de volver a usar y administrar centralmente las configuraciones de módulo en un sitio.</span><span class="sxs-lookup"><span data-stu-id="b504d-124">Therefore, fragments provide a powerful and efficient way to reuse and centrally manage module configurations on a site.</span></span> <span data-ttu-id="b504d-125">Al usarlos de manera eficaz, pueden aumentar significativamente la agilidad y ayudar a reducir el coste que está asociado a la administración del contenido del sitio.</span><span class="sxs-lookup"><span data-stu-id="b504d-125">By effectively using them, you can significantly increase agility and help reduce the cost that is associated with managing site content.</span></span>

<span data-ttu-id="b504d-126">La ilustración siguiente muestra cómo se pueden usar los fragmentos para centralizar la creación de las configuraciones de módulo compartidas en un sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="b504d-126">The following illustration shows how fragments can be used to centralize authoring of shared module configurations across an e-Commerce site.</span></span>

![Una ilustración que muestra cómo se pueden usar los fragmentos para centralizar la creación de las configuraciones de módulo compartidas en un sitio de comercio electrónico](./media/fragment-figure1.png)

## <a name="create-a-fragment"></a><span data-ttu-id="b504d-128">Crear un fragmento</span><span class="sxs-lookup"><span data-stu-id="b504d-128">Create a fragment</span></span>

<span data-ttu-id="b504d-129">Puede crear un nuevo fragmento o guardar una configuración de módulo existente como fragmento.</span><span class="sxs-lookup"><span data-stu-id="b504d-129">You can either create a new fragment or save an existing module configuration as a fragment.</span></span>

### <a name="save-an-existing-module-configuration-as-a-fragment"></a><span data-ttu-id="b504d-130">Guardar una configuración de módulo existente como fragmento</span><span class="sxs-lookup"><span data-stu-id="b504d-130">Save an existing module configuration as a fragment</span></span>

<span data-ttu-id="b504d-131">Para convertir un módulo configurado anteriormente en un fragmento reutilizable en el generador de sitios de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="b504d-131">To convert a previously configured module to a reusable fragment in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="b504d-132">Abra una página o una plantilla que contenga el módulo que desea convertir en un fragmento.</span><span class="sxs-lookup"><span data-stu-id="b504d-132">Open a page or template that contains the module that you want to convert to a fragment.</span></span>
1. <span data-ttu-id="b504d-133">En el panel de contorno a la izquierda o directamente en el generador de páginas visual, seleccione el módulo configurado previamente.</span><span class="sxs-lookup"><span data-stu-id="b504d-133">In the outline pane on the left or directly in visual page builder, select the previously configured module.</span></span>
1. <span data-ttu-id="b504d-134">Seleccione los puntos suspensivos ( **...** ) junto al módulo en el panel de contorno o en la barra de herramientas del módulo en el generador de páginas visual.</span><span class="sxs-lookup"><span data-stu-id="b504d-134">Select the ellipsis ( **...** ) next to the name of the module in either the outline pane or the selected module's toolbar in visual page builder.</span></span> 
1. <span data-ttu-id="b504d-135">Seleccione **Compartir como fragmento**.</span><span class="sxs-lookup"><span data-stu-id="b504d-135">Select **Share as fragment**.</span></span> 
1. <span data-ttu-id="b504d-136">En el cuadro de diálogo **Guardar como fragmento** , especifique un nombre para el fragmento.</span><span class="sxs-lookup"><span data-stu-id="b504d-136">In the **Save as fragment** dialog box, enter a name for the fragment.</span></span>
1. <span data-ttu-id="b504d-137">Seleccione **Aceptar** para guardar la configuración del módulo como fragmento que se pueda agregar a otras páginas.</span><span class="sxs-lookup"><span data-stu-id="b504d-137">Select **OK** to save the module configuration as a fragment that can be added to other pages.</span></span>
<!-- The following image shows how to save a module configuration as a fragment.-->
<!--![A screen capture of how to save a module configuration as a fragment](./media/save-as-fragment.png)-->

### <a name="create-a-new-fragment"></a><span data-ttu-id="b504d-138">Crear un nuevo fragmento</span><span class="sxs-lookup"><span data-stu-id="b504d-138">Create a new fragment</span></span>

<span data-ttu-id="b504d-139">Para crear un fragmento nuevo en el generador de sitios de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="b504d-139">To create a new fragment in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="b504d-140">En el panel de navegación de la izquierda, seleccione **Fragmentos**.</span><span class="sxs-lookup"><span data-stu-id="b504d-140">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="b504d-141">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="b504d-141">Select **New**.</span></span> <span data-ttu-id="b504d-142">Aparece el cuadro de diálogo **Nuevo fragmento** , que muestra todos los tipos de módulos disponibles.</span><span class="sxs-lookup"><span data-stu-id="b504d-142">A **New fragment** dialog box appears that shows all the available module types.</span></span> <span data-ttu-id="b504d-143">Como se mencionó anteriormente, los fragmentos se pueden crear a partir de cualquier tipo de módulo.</span><span class="sxs-lookup"><span data-stu-id="b504d-143">As was mentioned earlier, fragments can be created from any module type.</span></span>
1. <span data-ttu-id="b504d-144">Seleccione un tipo de módulo para su fragmento.</span><span class="sxs-lookup"><span data-stu-id="b504d-144">Select a module type for your fragment.</span></span>

<!-- The following image shows where to create a new fragment.-->
<!-- ![A screen capture of where to create a new fragment](./media/fragment-nav-menu.png)-->
> [!TIP]
> <span data-ttu-id="b504d-145">Al seleccionar un tipo de módulo de contenedor genérico, obtiene la máxima flexibilidad cuando tiene que actualizar y configurar el fragmento posteriormente.</span><span class="sxs-lookup"><span data-stu-id="b504d-145">By selecting a generic container module type, you get the most flexibility when you need to update and configure your fragment later.</span></span>

## <a name="add-remove-or-edit-fragments-on-a-page"></a><span data-ttu-id="b504d-146">Agregar, eliminar o editar fragmentos en una página</span><span class="sxs-lookup"><span data-stu-id="b504d-146">Add, remove, or edit fragments on a page</span></span>

<span data-ttu-id="b504d-147">Los siguientes procedimientos describen cómo agregar, quitar y editar fragmentos.</span><span class="sxs-lookup"><span data-stu-id="b504d-147">The following procedures describe how to add, remove, and edit fragments.</span></span>

### <a name="add-a-fragment"></a><span data-ttu-id="b504d-148">Agregar un fragmento</span><span class="sxs-lookup"><span data-stu-id="b504d-148">Add a fragment</span></span>

<span data-ttu-id="b504d-149">Para agregar un fragmento a una página en el generador de sitios de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="b504d-149">To add a fragment to a page in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="b504d-150">En el panel de esquema de la izquierda o directamente en el generador de páginas visual, seleccione un contenedor o una franja a la que se pueda agregar módulos secundarios.</span><span class="sxs-lookup"><span data-stu-id="b504d-150">In the outline pane on the left or directly in visual page builder, select a container or slot to which child modules can be added.</span></span>
1. <span data-ttu-id="b504d-151">Seleccione los puntos suspensivos ( **...** ) junto al nombre del contenedor o la franja.</span><span class="sxs-lookup"><span data-stu-id="b504d-151">Select the ellipsis ( **...** ) next to the name of the container or slot.</span></span>  <span data-ttu-id="b504d-152">Alternativamente, si usa el generador de páginas visual, seleccione el símbolo más ( **+** ).</span><span class="sxs-lookup"><span data-stu-id="b504d-152">Alternately, if using visual page builder, select the plus symbol ( **+** ).</span></span>  
1. <span data-ttu-id="b504d-153">Seleccione **Agregar fragmento**.</span><span class="sxs-lookup"><span data-stu-id="b504d-153">Select **Add fragment**.</span></span>
    <!-- ![A screen capture of how to add an existing fragment to a slot or container](./media/add-fragment.png)-->
 
    > [!NOTE]
    > <span data-ttu-id="b504d-154">Si el contenedor o la franja no admiten nuevos módulos secundarios, la opción **Agregar fragmento** no está disponible.</span><span class="sxs-lookup"><span data-stu-id="b504d-154">If the container or slot doesn't support new child modules, the **Add fragment** option is unavailable.</span></span>
    
1. <span data-ttu-id="b504d-155">En el cuadro de diálogo **Seleccionar fragmento** , busque y seleccione un fragmento para agregarlo.</span><span class="sxs-lookup"><span data-stu-id="b504d-155">In the **Select fragment** dialog box, search for and select a fragment to add.</span></span> <span data-ttu-id="b504d-156">Si no se muestran fragmentos disponibles, es posible que tenga que crear primero un fragmento de un tipo de módulo que la franja o el contenedor seleccionado admita.</span><span class="sxs-lookup"><span data-stu-id="b504d-156">If no available fragments are listed, you might first have to create a fragment from a module type that the selected container or slot supports.</span></span>
1. <span data-ttu-id="b504d-157">Seleccione el fragmento que desee para agregarlo a la franja o al contenedor seleccionado de su página.</span><span class="sxs-lookup"><span data-stu-id="b504d-157">Select your desired fragment to add it to the container or slot on your page.</span></span>
<!--    ![A screen capture of the fragment picker modal window](./media/fragment-picker.png)-->

> [!NOTE]
> <span data-ttu-id="b504d-158">Los módulos que se permiten en un contenedor o una franja se definen por plantilla de la página o las propias definiciones de los módulos.</span><span class="sxs-lookup"><span data-stu-id="b504d-158">The modules that are allowed in a container or slot are defined by the page's template or the modules' own definitions.</span></span>

### <a name="remove-a-fragment"></a><span data-ttu-id="b504d-159">Eliminar un fragmento</span><span class="sxs-lookup"><span data-stu-id="b504d-159">Remove a fragment</span></span>

<span data-ttu-id="b504d-160">Para quitar un fragmento de una franja o un contenedor en una página del generador de sitios de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="b504d-160">To remove a fragment from a slot or container on a page in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="b504d-161">En el panel de esquema de la izquierda, seleccione el botón de puntos suspensivos ( **...** ) que se encuentra junto al fragmento que se va a eliminar y, a continuación, seleccione el símbolo de papelera.</span><span class="sxs-lookup"><span data-stu-id="b504d-161">In the outline pane on the left, select the ellipsis ( **...** ) next to the name of the fragment to be removed, and then select the trash can symbol.</span></span>  <span data-ttu-id="b504d-162">Alternativamente, puede seleccionar el fragmento en el generador de páginas visual y seleccionar el símbolo de la papelera en la barra de herramientas del fragmento.</span><span class="sxs-lookup"><span data-stu-id="b504d-162">Alternately, you can select the fragment in visual page builder and select the trash can symbol in the fragment's toolbar.</span></span>
1. <span data-ttu-id="b504d-163">Cuando se le pida confirmar que desea quitar el fragmento, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b504d-163">When you're prompted to confirm that you want to remove the fragment, select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="b504d-164">Al quitar un fragmento de una página, solo quitará la referencia a él de esa página.</span><span class="sxs-lookup"><span data-stu-id="b504d-164">When you remove a fragment from a page, you just remove the reference to it from that page.</span></span> <span data-ttu-id="b504d-165">**No** elimina el fragmento del sitio.</span><span class="sxs-lookup"><span data-stu-id="b504d-165">You do **not** delete the fragment from your site.</span></span> <span data-ttu-id="b504d-166">Para eliminar fragmentos del sitio, debe usar la interfaz de usuario (IU) del inspector de fragmentos.</span><span class="sxs-lookup"><span data-stu-id="b504d-166">To delete fragments from your site, you must use the fragment inspector user interface (UI).</span></span> <span data-ttu-id="b504d-167">Puede eliminar fragmentos de un sitio solo si no se hace referencia a ellos actualmente por ninguna página o plantilla u otros fragmentos.</span><span class="sxs-lookup"><span data-stu-id="b504d-167">You can delete fragments from a site only if they aren't currently referenced by any pages, templates, or other fragments.</span></span>

### <a name="edit-a-fragment"></a><span data-ttu-id="b504d-168">Editar un fragmento</span><span class="sxs-lookup"><span data-stu-id="b504d-168">Edit a fragment</span></span>

<span data-ttu-id="b504d-169">Para editar fragmentos, debe usar la interfaz de usuario del editor de fragmentos.</span><span class="sxs-lookup"><span data-stu-id="b504d-169">To edit fragments, you must use the fragment editor UI.</span></span> <span data-ttu-id="b504d-170">Esta restricción es por diseño.</span><span class="sxs-lookup"><span data-stu-id="b504d-170">This restriction is by design.</span></span> <span data-ttu-id="b504d-171">Ayuda garantizar que los autores no confunden el proceso de editar los módulos para una página determinada por el proceso de editar fragmentos que se pueden compartir entre varias páginas.</span><span class="sxs-lookup"><span data-stu-id="b504d-171">It helps guarantee that authors don't confuse the process of editing the modules for a specific page with the process of editing fragments that might be shared across many pages.</span></span>

<span data-ttu-id="b504d-172">Para editar un fragmento en el generador de sitios de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="b504d-172">To edit a fragment in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="b504d-173">En el panel de navegación de la izquierda, seleccione **Fragmentos**.</span><span class="sxs-lookup"><span data-stu-id="b504d-173">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="b504d-174">En **Fragmentos** , seleccione el fragmento que se editará.</span><span class="sxs-lookup"><span data-stu-id="b504d-174">Under **Fragments** , select the fragment to edit.</span></span>
1. <span data-ttu-id="b504d-175">Edite la estructura y las propiedades del módulo del fragmento según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="b504d-175">Edit the fragment's module properties and structure as you require.</span></span> <span data-ttu-id="b504d-176">El proceso es similar al que se usa para editar módulos en la vista del editor de páginas.</span><span class="sxs-lookup"><span data-stu-id="b504d-176">The process resembles the process for editing modules are edited in the page editor view.</span></span>

<span data-ttu-id="b504d-177">También puede editar un fragmento seleccionándolo en una página, en una plantilla o en un fragmento principal y, a continuación, seleccionando **Editar fragmento** en el panel de propiedades de la derecha.</span><span class="sxs-lookup"><span data-stu-id="b504d-177">You can also edit a fragment by selecting it on a page, in a template, or in a parent fragment, and then selecting **Edit Fragment** in the properties pane on the right.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b504d-178">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="b504d-178">Additional resources</span></span>

[<span data-ttu-id="b504d-179">Visión general de plantillas y diseños</span><span class="sxs-lookup"><span data-stu-id="b504d-179">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="b504d-180">Trabajar con plantillas</span><span class="sxs-lookup"><span data-stu-id="b504d-180">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="b504d-181">Trabajar con diseños predefinidos</span><span class="sxs-lookup"><span data-stu-id="b504d-181">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="b504d-182">Trabajar con grupos de publicación</span><span class="sxs-lookup"><span data-stu-id="b504d-182">Work with publish groups</span></span>](publish-groups.md)
