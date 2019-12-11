---
title: Trabajar con fragmentos
description: Este tema describe por qué, cuándo y cómo usar fragmentos en Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
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
ms.author: phinneyridge
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d92b9077f8584bfa0710bbaacbc7caa3220baa4a
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698105"
---
# <a name="work-with-fragments"></a><span data-ttu-id="e958c-103">Trabajar con fragmentos</span><span class="sxs-lookup"><span data-stu-id="e958c-103">Work with fragments</span></span> 

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="e958c-104">Este tema describe por qué, cuándo y cómo usar fragmentos en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e958c-104">This topic describes why, when, and how to use fragments in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="e958c-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="e958c-105">Overview</span></span>

<span data-ttu-id="e958c-106">Los fragmentos permiten una experiencia de creación centralizada para configuraciones de módulos que se deben volver a utilizar en el sitio.</span><span class="sxs-lookup"><span data-stu-id="e958c-106">Fragments allow for a centralized authoring experience for module configurations that must be reused throughout your site.</span></span> <span data-ttu-id="e958c-107">Por ejemplo, los encabezados, los pies de página y los banners a menudo se configuran como fragmentos, ya que se comparten entre muchas páginas.</span><span class="sxs-lookup"><span data-stu-id="e958c-107">For example, headers, footers, and banners are often configured as fragments, because they are shared across many pages.</span></span> <span data-ttu-id="e958c-108">Puede pensar en fragmentos como páginas web en miniatura que se pueden insertar en otras páginas del sitio.</span><span class="sxs-lookup"><span data-stu-id="e958c-108">You can think of fragments as miniature webpages that can be inserted into other pages on your site.</span></span> <span data-ttu-id="e958c-109">Los fragmentos tienen su propio ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="e958c-109">Fragments have their own lifecycle.</span></span> <span data-ttu-id="e958c-110">Es decir, se crean, se hace referencia a ellas, se actualizan y se eliminan como entidades independientes en las herramientas de creación.</span><span class="sxs-lookup"><span data-stu-id="e958c-110">In other words, they are created, referenced, updated, and deleted as independent entities in the authoring tools.</span></span>

<span data-ttu-id="e958c-111">Una vez que se configuran los fragmentos, se pueden usar en cualquier lugar donde se puedan usar los módulos en su estructura de sitio.</span><span class="sxs-lookup"><span data-stu-id="e958c-111">After fragments are configured, they can be used wherever modules can be used in your site structure.</span></span> <span data-ttu-id="e958c-112">Se puede hacer referencia a fragmentos en páginas, diseños, plantillas y otros fragmentos.</span><span class="sxs-lookup"><span data-stu-id="e958c-112">Fragments can be referenced on pages, in layouts, in templates, and in other fragments.</span></span>

> [!NOTE]
> <span data-ttu-id="e958c-113">Los fragmentos se pueden anidar hasta en siete niveles de profundidad dentro de otros fragmentos.</span><span class="sxs-lookup"><span data-stu-id="e958c-113">Fragments can be nested up to seven levels deep inside other fragments.</span></span>

<span data-ttu-id="e958c-114">Por ejemplo, si desea promocionar un evento de temporada en muchas páginas de nuestro sitio, puede usar un fragmento.</span><span class="sxs-lookup"><span data-stu-id="e958c-114">For example, if you want to promote a seasonal event cross many pages on our site, you can use a fragment.</span></span> <span data-ttu-id="e958c-115">El primer paso en el proceso de crear un fragmento nuevo es seleccionar el tipo de módulo desde el que deseas empezar.</span><span class="sxs-lookup"><span data-stu-id="e958c-115">The first step in the process of creating a new fragment is to select the type of module that you want to start from.</span></span> <span data-ttu-id="e958c-116">Para este ejemplo, puede crear el fragmento desde un módulo de elemento principal.</span><span class="sxs-lookup"><span data-stu-id="e958c-116">For this example, you can build the fragment from a hero module.</span></span>

> [!NOTE]
> <span data-ttu-id="e958c-117">Los fragmentos se pueden crear desde cualquier tipo de módulo.</span><span class="sxs-lookup"><span data-stu-id="e958c-117">Fragments can be built from any module type.</span></span>

<span data-ttu-id="e958c-118">A continuación puede configurar el fragmento de elemento principal con su contenido promocional específico.</span><span class="sxs-lookup"><span data-stu-id="e958c-118">You can then configure the hero fragment with your specific promotional content.</span></span> <span data-ttu-id="e958c-119">También puede localizarlo según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="e958c-119">You can also localize it as you require.</span></span> <span data-ttu-id="e958c-120">El nuevo fragmento de elemento principal independiente se puede consumir a continuación como módulo preconfigurado a través del sitio.</span><span class="sxs-lookup"><span data-stu-id="e958c-120">The new stand-alone hero fragment can then be consumed as a preconfigured module throughout your site.</span></span> <span data-ttu-id="e958c-121">Puede agregarlo fácilmente a plantillas, a páginas específicas o a otros fragmentos que pueden contener módulos de elementos principales.</span><span class="sxs-lookup"><span data-stu-id="e958c-121">You can easily add it to templates, to specific pages, or to other fragments that can contain hero modules.</span></span>

<span data-ttu-id="e958c-122">Todos los lugares donde se agrega el fragmento son referencias al fragmento de elemento principal central de héroe que ha creado.</span><span class="sxs-lookup"><span data-stu-id="e958c-122">All the places where the fragment is added are references to the central hero fragment that you created.</span></span> <span data-ttu-id="e958c-123">Si publica cambios en el fragmento, estos cambios se reflejan inmediatamente en todos los lugares donde se hace referencia al fragmento en el sitio.</span><span class="sxs-lookup"><span data-stu-id="e958c-123">If you publish changes to the fragment, those changes are immediately reflected in all the places where the fragment is referenced across the site.</span></span> <span data-ttu-id="e958c-124">Por lo tanto, los fragmentos ofrecen una manera potente y eficaz de volver a usar y administrar centralmente las configuraciones de módulo en un sitio.</span><span class="sxs-lookup"><span data-stu-id="e958c-124">Therefore, fragments provide a powerful and efficient way to reuse and centrally manage module configurations on a site.</span></span> <span data-ttu-id="e958c-125">Al usarlos de manera eficaz, pueden aumentar significativamente la agilidad y ayudar a reducir el coste que está asociado a la administración del contenido del sitio.</span><span class="sxs-lookup"><span data-stu-id="e958c-125">By effectively using them, you can significantly increase agility and help reduce the cost that is associated with managing site content.</span></span>

<span data-ttu-id="e958c-126">La ilustración siguiente muestra cómo se pueden usar los fragmentos para centralizar la creación de las configuraciones de módulo compartidas en un sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="e958c-126">The following illustration shows how fragments can be used to centralize authoring of shared module configurations across an e-Commerce site.</span></span>

![Una ilustración que muestra cómo se pueden usar los fragmentos para centralizar la creación de las configuraciones de módulo compartidas en un sitio de comercio electrónico](./media/fragment-figure1.png)

## <a name="create-a-fragment"></a><span data-ttu-id="e958c-128">Crear un fragmento</span><span class="sxs-lookup"><span data-stu-id="e958c-128">Create a fragment</span></span>

<span data-ttu-id="e958c-129">Puede crear un nuevo fragmento o guardar una configuración de módulo existente como fragmento.</span><span class="sxs-lookup"><span data-stu-id="e958c-129">You can either create a new fragment or save an existing module configuration as a fragment.</span></span>

### <a name="create-a-new-fragment"></a><span data-ttu-id="e958c-130">Crear un fragmento nuevo</span><span class="sxs-lookup"><span data-stu-id="e958c-130">Create a new fragment</span></span>

<span data-ttu-id="e958c-131">Para crear un nuevo fragmento, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="e958c-131">To create a new fragment, follow these steps.</span></span>

1. <span data-ttu-id="e958c-132">En el panel de navegación de la izquierda, seleccione **Fragmentos**.</span><span class="sxs-lookup"><span data-stu-id="e958c-132">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="e958c-133">Seleccione **Nuevo fragmento de página**.</span><span class="sxs-lookup"><span data-stu-id="e958c-133">Select **New Page Fragment**.</span></span> <span data-ttu-id="e958c-134">Aparece un cuadro de diálogo que muestra todos los tipos de módulos disponibles.</span><span class="sxs-lookup"><span data-stu-id="e958c-134">A dialog box appears that shows all the available module types.</span></span> <span data-ttu-id="e958c-135">Como se mencionó anteriormente, los fragmentos se pueden crear a partir de cualquier tipo de módulo.</span><span class="sxs-lookup"><span data-stu-id="e958c-135">As was mentioned earlier, fragments can be created from any module type.</span></span>
1. <span data-ttu-id="e958c-136">Seleccione un tipo de módulo para el fragmento y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e958c-136">Select a module type for your fragment, and then select **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="e958c-137">Al seleccionar un tipo de módulo de contenedor genérico, obtiene la máxima flexibilidad cuando debe actualizar y configurar el fragmento posteriormente.</span><span class="sxs-lookup"><span data-stu-id="e958c-137">By selecting a generic container module type, you get the most flexibility when you must update and configure your fragment later.</span></span>

### <a name="save-an-existing-module-configuration-as-a-fragment"></a><span data-ttu-id="e958c-138">Guardar una configuración de módulo existente como fragmento</span><span class="sxs-lookup"><span data-stu-id="e958c-138">Save an existing module configuration as a fragment</span></span>

<span data-ttu-id="e958c-139">Para convertir un módulo configurado anteriormente en un fragmento reutilizable, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="e958c-139">To convert a previously configured module to a reusable fragment, follow these steps.</span></span>

1. <span data-ttu-id="e958c-140">Abra una página o una plantilla que contenga el módulo que desea convertir en un fragmento.</span><span class="sxs-lookup"><span data-stu-id="e958c-140">Open a page or template that contains the module that you want to convert to a fragment.</span></span>
1. <span data-ttu-id="e958c-141">En el panel de esquema de la izquierda, seleccione el botón de puntos suspensivos (**...**) que se encuentra junto al nombre del módulo y, a continuación, seleccione **Guardar como fragmento**.</span><span class="sxs-lookup"><span data-stu-id="e958c-141">In the outline pane on the left, select the ellipsis button (**...**) next to the name of the module, and then select **Save as Fragment**.</span></span> <span data-ttu-id="e958c-142">Aparece un cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="e958c-142">A dialog box appears.</span></span>
1. <span data-ttu-id="e958c-143">Especifique un nombre y metadatos para el fragmento.</span><span class="sxs-lookup"><span data-stu-id="e958c-143">Enter a name and metadata for the fragment.</span></span>
1. <span data-ttu-id="e958c-144">Seleccione **Aceptar** para guardar la configuración del módulo como fragmento que se pueda agregar a otras páginas.</span><span class="sxs-lookup"><span data-stu-id="e958c-144">Select **OK** to save the module configuration as a fragment that can be added to other pages.</span></span>

## <a name="add-remove-or-edit-fragments-on-a-page"></a><span data-ttu-id="e958c-145">Agregar, eliminar o editar fragmentos en una página</span><span class="sxs-lookup"><span data-stu-id="e958c-145">Add, remove, or edit fragments on a page</span></span>

<span data-ttu-id="e958c-146">Los siguientes procedimientos describen cómo agregar, quitar y editar fragmentos.</span><span class="sxs-lookup"><span data-stu-id="e958c-146">The following procedures describe how to add, remove, and edit fragments.</span></span>

### <a name="add-a-fragment"></a><span data-ttu-id="e958c-147">Agregar un fragmento</span><span class="sxs-lookup"><span data-stu-id="e958c-147">Add a fragment</span></span>

<span data-ttu-id="e958c-148">Para agregar un fragmento a una página, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="e958c-148">To add a fragment to a page, follow these steps.</span></span>

1. <span data-ttu-id="e958c-149">En el panel de esquema de la izquierda, seleccione un contenedor o una franja a la que se pueden agregar módulos secundarios.</span><span class="sxs-lookup"><span data-stu-id="e958c-149">In the outline pane on the left, select a container or slot that child modules can be added to.</span></span>
1. <span data-ttu-id="e958c-150">Seleccione el botón de puntos suspensivos junto al nombre del contenedor o franja y, a continuación, seleccione **Agregar fragmento**.</span><span class="sxs-lookup"><span data-stu-id="e958c-150">Select the ellipsis button next to the name of the container or slot, and then select **Add Fragment**.</span></span> <span data-ttu-id="e958c-151">Aparece un cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="e958c-151">A dialog box appears.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e958c-152">Si el contenedor o la franja no admiten nuevos módulos secundarios, la opción **Agregar fragmento** no está disponible.</span><span class="sxs-lookup"><span data-stu-id="e958c-152">If the container or slot doesn't support new child modules, the **Add Fragment** option is unavailable.</span></span>

1. <span data-ttu-id="e958c-153">En el cuadro de diálogo, busque y seleccione un fragmento para agregarlo.</span><span class="sxs-lookup"><span data-stu-id="e958c-153">In the dialog box, search for and select a fragment to add.</span></span> <span data-ttu-id="e958c-154">Si no se muestran fragmentos disponibles, es posible que tenga que crear primero un fragmento de un tipo de módulo que la franja o el contenedor seleccionado admita.</span><span class="sxs-lookup"><span data-stu-id="e958c-154">If no available fragments are listed, you might first have to create a fragment from a module type that the selected container or slot supports.</span></span>
1. <span data-ttu-id="e958c-155">Seleccione **Aceptar** para agregar el fragmento seleccionado a la franja o al contenedor seleccionado de su página.</span><span class="sxs-lookup"><span data-stu-id="e958c-155">Select **OK** to add the selected fragment to the selected container or slot on your page.</span></span>

> [!NOTE]
> <span data-ttu-id="e958c-156">Los módulos que se permiten en un contenedor o una franja se definen por plantilla de la página o las propias definiciones de los módulos.</span><span class="sxs-lookup"><span data-stu-id="e958c-156">The modules that are allowed in a container or slot are defined by the page's template or the modules' own definitions.</span></span>

### <a name="remove-a-fragment"></a><span data-ttu-id="e958c-157">Eliminar un fragmento</span><span class="sxs-lookup"><span data-stu-id="e958c-157">Remove a fragment</span></span>

<span data-ttu-id="e958c-158">Para eliminar un fragmento de una franja o un contenedor de una página, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="e958c-158">To remove a fragment from a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="e958c-159">En el panel de esquema de la izquierda, seleccione el botón de puntos suspensivos que se encuentra junto al nombre del fragmento que se va a eliminar y, a continuación, seleccione el botón de papelera.</span><span class="sxs-lookup"><span data-stu-id="e958c-159">In the outline pane on the left, select the ellipsis button next to the name of the fragment to remove, and then select the trash can button.</span></span>
1. <span data-ttu-id="e958c-160">Cuando se le pida confirmar que desea quitar el fragmento, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e958c-160">When you're prompted to confirm that you want to remove the fragment, select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="e958c-161">Al quitar un fragmento de una página, solo quitará la referencia a él de esa página.</span><span class="sxs-lookup"><span data-stu-id="e958c-161">When you remove a fragment from a page, you just remove the reference to it from that page.</span></span> <span data-ttu-id="e958c-162">**No** elimina el fragmento del sitio.</span><span class="sxs-lookup"><span data-stu-id="e958c-162">You do **not** delete the fragment from your site.</span></span> <span data-ttu-id="e958c-163">Para eliminar fragmentos del sitio, debe usar la interfaz de usuario (IU) del inspector de fragmentos.</span><span class="sxs-lookup"><span data-stu-id="e958c-163">To delete fragments from your site, you must use the fragment inspector user interface (UI).</span></span> <span data-ttu-id="e958c-164">Puede eliminar fragmentos de un sitio solo si no se hace referencia a ellos actualmente por ninguna página o plantilla u otros fragmentos.</span><span class="sxs-lookup"><span data-stu-id="e958c-164">You can delete fragments from a site only if they aren't currently referenced by any pages, templates, or other fragments.</span></span>

### <a name="edit-a-fragment"></a><span data-ttu-id="e958c-165">Editar un fragmento</span><span class="sxs-lookup"><span data-stu-id="e958c-165">Edit a fragment</span></span>

<span data-ttu-id="e958c-166">Para editar fragmentos, debe usar la interfaz de usuario del editor de fragmentos.</span><span class="sxs-lookup"><span data-stu-id="e958c-166">To edit fragments, you must use the fragment editor UI.</span></span> <span data-ttu-id="e958c-167">Esta restricción es por diseño.</span><span class="sxs-lookup"><span data-stu-id="e958c-167">This restriction is by design.</span></span> <span data-ttu-id="e958c-168">Ayuda garantizar que los autores no confunden el proceso de editar los módulos para una página determinada por el proceso de editar fragmentos que se pueden compartir entre varias páginas.</span><span class="sxs-lookup"><span data-stu-id="e958c-168">It helps guarantee that authors don't confuse the process of editing the modules for a specific page with the process of editing fragments that might be shared across many pages.</span></span>

<span data-ttu-id="e958c-169">Para editar un fragmento, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="e958c-169">To edit a fragment, follow these steps.</span></span>

1. <span data-ttu-id="e958c-170">En el panel de navegación de la izquierda, seleccione **Fragmentos**.</span><span class="sxs-lookup"><span data-stu-id="e958c-170">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="e958c-171">En **Fragmentos**, seleccione el fragmento que se editará.</span><span class="sxs-lookup"><span data-stu-id="e958c-171">Under **Fragments**, select the fragment to edit.</span></span>
1. <span data-ttu-id="e958c-172">Edite la estructura y las propiedades del módulo del fragmento según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="e958c-172">Edit the fragment's module properties and structure as you require.</span></span> <span data-ttu-id="e958c-173">El proceso es similar al que se usa para editar módulos en la vista del editor de páginas.</span><span class="sxs-lookup"><span data-stu-id="e958c-173">The process resembles the process for editing modules are edited in the page editor view.</span></span>

<span data-ttu-id="e958c-174">También puede editar un fragmento seleccionándolo en una página, en una plantilla o en un fragmento principal y, a continuación, seleccionando **Editar fragmento** en el panel de propiedades de la derecha.</span><span class="sxs-lookup"><span data-stu-id="e958c-174">You can also edit a fragment by selecting it on a page, in a template, or in a parent fragment, and then selecting **Edit Fragment** in the properties pane on the right.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e958c-175">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e958c-175">Additional resources</span></span>

[<span data-ttu-id="e958c-176">Visión general de plantillas y diseños</span><span class="sxs-lookup"><span data-stu-id="e958c-176">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="e958c-177">Trabajar con plantillas</span><span class="sxs-lookup"><span data-stu-id="e958c-177">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="e958c-178">Trabajar con diseños predefinidos</span><span class="sxs-lookup"><span data-stu-id="e958c-178">Work with preset layouts</span></span>](work-with-layouts.md)
