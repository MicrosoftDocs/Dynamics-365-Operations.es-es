---
title: Trabajar con fragmentos
description: Este tema describe por qué, cuándo y cómo usar fragmentos en Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 01/31/2020
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
ms.openlocfilehash: f29046ded47ed9c49a2cc841aa7c1f6492b49aec
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2020
ms.locfileid: "3026049"
---
# <a name="work-with-fragments"></a><span data-ttu-id="fc00b-103">Trabajar con fragmentos</span><span class="sxs-lookup"><span data-stu-id="fc00b-103">Work with fragments</span></span> 


[!include [banner](includes/banner.md)]

<span data-ttu-id="fc00b-104">Este tema describe por qué, cuándo y cómo usar fragmentos en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="fc00b-104">This topic describes why, when, and how to use fragments in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="fc00b-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="fc00b-105">Overview</span></span>

<span data-ttu-id="fc00b-106">Los fragmentos permiten una experiencia de creación centralizada para configuraciones de módulos que se deben volver a utilizar en el sitio.</span><span class="sxs-lookup"><span data-stu-id="fc00b-106">Fragments allow for a centralized authoring experience for module configurations that must be reused throughout your site.</span></span> <span data-ttu-id="fc00b-107">Por ejemplo, los encabezados, los pies de página y los banners a menudo se configuran como fragmentos, ya que se comparten entre muchas páginas.</span><span class="sxs-lookup"><span data-stu-id="fc00b-107">For example, headers, footers, and banners are often configured as fragments, because they are shared across many pages.</span></span> <span data-ttu-id="fc00b-108">Puede pensar en fragmentos como páginas web en miniatura que se pueden insertar en otras páginas del sitio.</span><span class="sxs-lookup"><span data-stu-id="fc00b-108">You can think of fragments as miniature webpages that can be inserted into other pages on your site.</span></span> <span data-ttu-id="fc00b-109">Los fragmentos tienen su propio ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="fc00b-109">Fragments have their own lifecycle.</span></span> <span data-ttu-id="fc00b-110">Es decir, se crean, se hace referencia a ellas, se actualizan y se eliminan como entidades independientes en las herramientas de creación.</span><span class="sxs-lookup"><span data-stu-id="fc00b-110">In other words, they are created, referenced, updated, and deleted as independent entities in the authoring tools.</span></span>

<span data-ttu-id="fc00b-111">Una vez que se configuran los fragmentos, se pueden usar en cualquier lugar donde se puedan usar los módulos en su estructura de sitio.</span><span class="sxs-lookup"><span data-stu-id="fc00b-111">After fragments are configured, they can be used wherever modules can be used in your site structure.</span></span> <span data-ttu-id="fc00b-112">Se puede hacer referencia a fragmentos en páginas, diseños, plantillas y otros fragmentos.</span><span class="sxs-lookup"><span data-stu-id="fc00b-112">Fragments can be referenced on pages, in layouts, in templates, and in other fragments.</span></span>

> [!NOTE]
> <span data-ttu-id="fc00b-113">Los fragmentos se pueden anidar hasta en siete niveles de profundidad dentro de otros fragmentos.</span><span class="sxs-lookup"><span data-stu-id="fc00b-113">Fragments can be nested up to seven levels deep inside other fragments.</span></span>

<span data-ttu-id="fc00b-114">Por ejemplo, si desea promocionar un evento de temporada en muchas páginas de nuestro sitio, puede usar un fragmento.</span><span class="sxs-lookup"><span data-stu-id="fc00b-114">For example, if you want to promote a seasonal event cross many pages on our site, you can use a fragment.</span></span> <span data-ttu-id="fc00b-115">El primer paso en el proceso de crear un fragmento nuevo es seleccionar el tipo de módulo desde el que deseas empezar.</span><span class="sxs-lookup"><span data-stu-id="fc00b-115">The first step in the process of creating a new fragment is to select the type of module that you want to start from.</span></span> <span data-ttu-id="fc00b-116">Para este ejemplo, puede crear el fragmento desde un módulo de elemento principal.</span><span class="sxs-lookup"><span data-stu-id="fc00b-116">For this example, you can build the fragment from a hero module.</span></span>

> [!NOTE]
> <span data-ttu-id="fc00b-117">Los fragmentos se pueden crear desde cualquier tipo de módulo.</span><span class="sxs-lookup"><span data-stu-id="fc00b-117">Fragments can be built from any module type.</span></span>

<span data-ttu-id="fc00b-118">A continuación puede configurar el fragmento de elemento principal con su contenido promocional específico.</span><span class="sxs-lookup"><span data-stu-id="fc00b-118">You can then configure the hero fragment with your specific promotional content.</span></span> <span data-ttu-id="fc00b-119">También puede localizarlo según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="fc00b-119">You can also localize it as you require.</span></span> <span data-ttu-id="fc00b-120">El nuevo fragmento de elemento principal independiente se puede consumir a continuación como módulo preconfigurado a través del sitio.</span><span class="sxs-lookup"><span data-stu-id="fc00b-120">The new stand-alone hero fragment can then be consumed as a preconfigured module throughout your site.</span></span> <span data-ttu-id="fc00b-121">Puede agregarlo fácilmente a plantillas, a páginas específicas o a otros fragmentos que pueden contener módulos de elementos principales.</span><span class="sxs-lookup"><span data-stu-id="fc00b-121">You can easily add it to templates, to specific pages, or to other fragments that can contain hero modules.</span></span>

<span data-ttu-id="fc00b-122">Todos los lugares donde se agrega el fragmento son referencias al fragmento de elemento principal central de héroe que ha creado.</span><span class="sxs-lookup"><span data-stu-id="fc00b-122">All the places where the fragment is added are references to the central hero fragment that you created.</span></span> <span data-ttu-id="fc00b-123">Si publica cambios en el fragmento, estos cambios se reflejan inmediatamente en todos los lugares donde se hace referencia al fragmento en el sitio.</span><span class="sxs-lookup"><span data-stu-id="fc00b-123">If you publish changes to the fragment, those changes are immediately reflected in all the places where the fragment is referenced across the site.</span></span> <span data-ttu-id="fc00b-124">Por lo tanto, los fragmentos ofrecen una manera potente y eficaz de volver a usar y administrar centralmente las configuraciones de módulo en un sitio.</span><span class="sxs-lookup"><span data-stu-id="fc00b-124">Therefore, fragments provide a powerful and efficient way to reuse and centrally manage module configurations on a site.</span></span> <span data-ttu-id="fc00b-125">Al usarlos de manera eficaz, pueden aumentar significativamente la agilidad y ayudar a reducir el coste que está asociado a la administración del contenido del sitio.</span><span class="sxs-lookup"><span data-stu-id="fc00b-125">By effectively using them, you can significantly increase agility and help reduce the cost that is associated with managing site content.</span></span>

<span data-ttu-id="fc00b-126">La ilustración siguiente muestra cómo se pueden usar los fragmentos para centralizar la creación de las configuraciones de módulo compartidas en un sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="fc00b-126">The following illustration shows how fragments can be used to centralize authoring of shared module configurations across an e-Commerce site.</span></span>

![Una ilustración que muestra cómo se pueden usar los fragmentos para centralizar la creación de las configuraciones de módulo compartidas en un sitio de comercio electrónico](./media/fragment-figure1.png)

## <a name="create-a-fragment"></a><span data-ttu-id="fc00b-128">Crear un fragmento</span><span class="sxs-lookup"><span data-stu-id="fc00b-128">Create a fragment</span></span>

<span data-ttu-id="fc00b-129">Puede crear un nuevo fragmento o guardar una configuración de módulo existente como fragmento.</span><span class="sxs-lookup"><span data-stu-id="fc00b-129">You can either create a new fragment or save an existing module configuration as a fragment.</span></span>

### <a name="save-an-existing-module-configuration-as-a-fragment"></a><span data-ttu-id="fc00b-130">Guardar una configuración de módulo existente como fragmento</span><span class="sxs-lookup"><span data-stu-id="fc00b-130">Save an existing module configuration as a fragment</span></span>

<span data-ttu-id="fc00b-131">Para convertir un módulo configurado anteriormente en un fragmento reutilizable, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="fc00b-131">To convert a previously configured module to a reusable fragment, follow these steps.</span></span>

1. <span data-ttu-id="fc00b-132">Abra una página o una plantilla que contenga el módulo que desea convertir en un fragmento.</span><span class="sxs-lookup"><span data-stu-id="fc00b-132">Open a page or template that contains the module that you want to convert to a fragment.</span></span>
1. <span data-ttu-id="fc00b-133">En el panel de esquema de la izquierda, seleccione el botón de puntos suspensivos (**...**) junto al nombre del módulo.</span><span class="sxs-lookup"><span data-stu-id="fc00b-133">In the outline pane on the left, select the ellipsis button (**...**) next to the name of the module.</span></span> 
1. <span data-ttu-id="fc00b-134">Seleccione **Compartir como fragmento**.</span><span class="sxs-lookup"><span data-stu-id="fc00b-134">Select **Share as Fragment**.</span></span> 
1. <span data-ttu-id="fc00b-135">Aparece un cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="fc00b-135">A dialog box appears.</span></span> <span data-ttu-id="fc00b-136">Especifique un nombre y metadatos para el fragmento.</span><span class="sxs-lookup"><span data-stu-id="fc00b-136">Enter a name and metadata for the fragment.</span></span>
1. <span data-ttu-id="fc00b-137">Seleccione **Aceptar** para guardar la configuración del módulo como fragmento que se pueda agregar a otras páginas.</span><span class="sxs-lookup"><span data-stu-id="fc00b-137">Select **OK** to save the module configuration as a fragment that can be added to other pages.</span></span>

<span data-ttu-id="fc00b-138">La siguiente imagen muestra cómo guardar la configuración de un módulo como fragmento.</span><span class="sxs-lookup"><span data-stu-id="fc00b-138">The following image shows how to save a module configuration as a fragment.</span></span>

![Una captura de pantalla de cómo guardar la configuración de un módulo como un fragmento](./media/save-as-fragment.png)

### <a name="create-a-new-fragment"></a><span data-ttu-id="fc00b-140">Crear un fragmento nuevo</span><span class="sxs-lookup"><span data-stu-id="fc00b-140">Create a new fragment</span></span>

<span data-ttu-id="fc00b-141">Para crear un nuevo fragmento, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="fc00b-141">To create a new fragment, follow these steps.</span></span>

1. <span data-ttu-id="fc00b-142">En el panel de navegación de la izquierda, seleccione **Fragmentos**.</span><span class="sxs-lookup"><span data-stu-id="fc00b-142">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="fc00b-143">Seleccione **Nuevo fragmento de página**.</span><span class="sxs-lookup"><span data-stu-id="fc00b-143">Select **New Page Fragment**.</span></span> <span data-ttu-id="fc00b-144">Aparece un cuadro de diálogo que muestra todos los tipos de módulos disponibles.</span><span class="sxs-lookup"><span data-stu-id="fc00b-144">A dialog box appears that shows all the available module types.</span></span> <span data-ttu-id="fc00b-145">Como se mencionó anteriormente, los fragmentos se pueden crear a partir de cualquier tipo de módulo.</span><span class="sxs-lookup"><span data-stu-id="fc00b-145">As was mentioned earlier, fragments can be created from any module type.</span></span>
1. <span data-ttu-id="fc00b-146">Seleccione un tipo de módulo para su fragmento.</span><span class="sxs-lookup"><span data-stu-id="fc00b-146">Select a module type for your fragment.</span></span>

<span data-ttu-id="fc00b-147">La siguiente imagen muestra dónde crear un nuevo fragmento.</span><span class="sxs-lookup"><span data-stu-id="fc00b-147">The following image shows where to create a new fragment.</span></span>

![Una captura de pantalla de dónde crear un nuevo fragmento](./media/fragment-nav-menu.png)

> [!TIP]
> <span data-ttu-id="fc00b-149">Al seleccionar un tipo de módulo de contenedor genérico, obtiene la máxima flexibilidad cuando tiene que actualizar y configurar el fragmento posteriormente.</span><span class="sxs-lookup"><span data-stu-id="fc00b-149">By selecting a generic container module type, you get the most flexibility when you need to update and configure your fragment later.</span></span>

## <a name="add-remove-or-edit-fragments-on-a-page"></a><span data-ttu-id="fc00b-150">Agregar, eliminar o editar fragmentos en una página</span><span class="sxs-lookup"><span data-stu-id="fc00b-150">Add, remove, or edit fragments on a page</span></span>

<span data-ttu-id="fc00b-151">Los siguientes procedimientos describen cómo agregar, quitar y editar fragmentos.</span><span class="sxs-lookup"><span data-stu-id="fc00b-151">The following procedures describe how to add, remove, and edit fragments.</span></span>

### <a name="add-a-fragment"></a><span data-ttu-id="fc00b-152">Agregar un fragmento</span><span class="sxs-lookup"><span data-stu-id="fc00b-152">Add a fragment</span></span>

<span data-ttu-id="fc00b-153">Para agregar un fragmento a una página, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="fc00b-153">To add a fragment to a page, follow these steps.</span></span>

1. <span data-ttu-id="fc00b-154">En el panel de esquema de la izquierda, seleccione un contenedor o una franja a la que se pueden agregar módulos secundarios.</span><span class="sxs-lookup"><span data-stu-id="fc00b-154">In the outline pane on the left, select a container or slot that child modules can be added to.</span></span>
1. <span data-ttu-id="fc00b-155">Seleccione el botón de puntos suspensivos junto al nombre del contenedor o franja y, a continuación, seleccione **Agregar fragmento**.</span><span class="sxs-lookup"><span data-stu-id="fc00b-155">Select the ellipsis button next to the name of the container or slot, and then select **Add Fragment**.</span></span> <span data-ttu-id="fc00b-156">Aparece un cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="fc00b-156">A dialog box appears.</span></span>

    ![Una captura de pantalla de cómo agregar un fragmento existente a un franja o contenedor](./media/add-fragment.png)
 
    > [!NOTE]
    > <span data-ttu-id="fc00b-158">Si el contenedor o la franja no admiten nuevos módulos secundarios, la opción **Agregar fragmento** no está disponible.</span><span class="sxs-lookup"><span data-stu-id="fc00b-158">If the container or slot doesn't support new child modules, the **Add Fragment** option is unavailable.</span></span>
    
1. <span data-ttu-id="fc00b-159">En el cuadro de diálogo, busque y seleccione un fragmento para agregarlo.</span><span class="sxs-lookup"><span data-stu-id="fc00b-159">In the dialog box, search for and select a fragment to add.</span></span> <span data-ttu-id="fc00b-160">Si no se muestran fragmentos disponibles, es posible que tenga que crear primero un fragmento de un tipo de módulo que la franja o el contenedor seleccionado admita.</span><span class="sxs-lookup"><span data-stu-id="fc00b-160">If no available fragments are listed, you might first have to create a fragment from a module type that the selected container or slot supports.</span></span>
1. <span data-ttu-id="fc00b-161">Seleccione el fragmento que desee para agregarlo a la franja o al contenedor seleccionado de su página.</span><span class="sxs-lookup"><span data-stu-id="fc00b-161">Select your desired fragment to add it to the container or slot on your page.</span></span>

    ![Una captura de pantalla de la ventana modal del selector de fragmentos](./media/fragment-picker.png)

> [!NOTE]
> <span data-ttu-id="fc00b-163">Los módulos que se permiten en un contenedor o una franja se definen por plantilla de la página o las propias definiciones de los módulos.</span><span class="sxs-lookup"><span data-stu-id="fc00b-163">The modules that are allowed in a container or slot are defined by the page's template or the modules' own definitions.</span></span>

### <a name="remove-a-fragment"></a><span data-ttu-id="fc00b-164">Eliminar un fragmento</span><span class="sxs-lookup"><span data-stu-id="fc00b-164">Remove a fragment</span></span>

<span data-ttu-id="fc00b-165">Para eliminar un fragmento de una franja o un contenedor de una página, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="fc00b-165">To remove a fragment from a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="fc00b-166">En el panel de esquema de la izquierda, seleccione el botón de puntos suspensivos que se encuentra junto al nombre del fragmento que se va a eliminar y, a continuación, seleccione el botón de papelera.</span><span class="sxs-lookup"><span data-stu-id="fc00b-166">In the outline pane on the left, select the ellipsis button next to the name of the fragment to remove, and then select the trash can button.</span></span>
1. <span data-ttu-id="fc00b-167">Cuando se le pida confirmar que desea quitar el fragmento, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fc00b-167">When you're prompted to confirm that you want to remove the fragment, select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="fc00b-168">Al quitar un fragmento de una página, solo quitará la referencia a él de esa página.</span><span class="sxs-lookup"><span data-stu-id="fc00b-168">When you remove a fragment from a page, you just remove the reference to it from that page.</span></span> <span data-ttu-id="fc00b-169">**No** elimina el fragmento del sitio.</span><span class="sxs-lookup"><span data-stu-id="fc00b-169">You do **not** delete the fragment from your site.</span></span> <span data-ttu-id="fc00b-170">Para eliminar fragmentos del sitio, debe usar la interfaz de usuario (IU) del inspector de fragmentos.</span><span class="sxs-lookup"><span data-stu-id="fc00b-170">To delete fragments from your site, you must use the fragment inspector user interface (UI).</span></span> <span data-ttu-id="fc00b-171">Puede eliminar fragmentos de un sitio solo si no se hace referencia a ellos actualmente por ninguna página o plantilla u otros fragmentos.</span><span class="sxs-lookup"><span data-stu-id="fc00b-171">You can delete fragments from a site only if they aren't currently referenced by any pages, templates, or other fragments.</span></span>

### <a name="edit-a-fragment"></a><span data-ttu-id="fc00b-172">Editar un fragmento</span><span class="sxs-lookup"><span data-stu-id="fc00b-172">Edit a fragment</span></span>

<span data-ttu-id="fc00b-173">Para editar fragmentos, debe usar la interfaz de usuario del editor de fragmentos.</span><span class="sxs-lookup"><span data-stu-id="fc00b-173">To edit fragments, you must use the fragment editor UI.</span></span> <span data-ttu-id="fc00b-174">Esta restricción es por diseño.</span><span class="sxs-lookup"><span data-stu-id="fc00b-174">This restriction is by design.</span></span> <span data-ttu-id="fc00b-175">Ayuda garantizar que los autores no confunden el proceso de editar los módulos para una página determinada por el proceso de editar fragmentos que se pueden compartir entre varias páginas.</span><span class="sxs-lookup"><span data-stu-id="fc00b-175">It helps guarantee that authors don't confuse the process of editing the modules for a specific page with the process of editing fragments that might be shared across many pages.</span></span>

<span data-ttu-id="fc00b-176">Para editar un fragmento, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="fc00b-176">To edit a fragment, follow these steps.</span></span>

1. <span data-ttu-id="fc00b-177">En el panel de navegación de la izquierda, seleccione **Fragmentos**.</span><span class="sxs-lookup"><span data-stu-id="fc00b-177">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="fc00b-178">En **Fragmentos**, seleccione el fragmento que se editará.</span><span class="sxs-lookup"><span data-stu-id="fc00b-178">Under **Fragments**, select the fragment to edit.</span></span>
1. <span data-ttu-id="fc00b-179">Edite la estructura y las propiedades del módulo del fragmento según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="fc00b-179">Edit the fragment's module properties and structure as you require.</span></span> <span data-ttu-id="fc00b-180">El proceso es similar al que se usa para editar módulos en la vista del editor de páginas.</span><span class="sxs-lookup"><span data-stu-id="fc00b-180">The process resembles the process for editing modules are edited in the page editor view.</span></span>

<span data-ttu-id="fc00b-181">También puede editar un fragmento seleccionándolo en una página, en una plantilla o en un fragmento principal y, a continuación, seleccionando **Editar fragmento** en el panel de propiedades de la derecha.</span><span class="sxs-lookup"><span data-stu-id="fc00b-181">You can also edit a fragment by selecting it on a page, in a template, or in a parent fragment, and then selecting **Edit Fragment** in the properties pane on the right.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fc00b-182">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="fc00b-182">Additional resources</span></span>

[<span data-ttu-id="fc00b-183">Visión general de plantillas y diseños</span><span class="sxs-lookup"><span data-stu-id="fc00b-183">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="fc00b-184">Trabajar con plantillas</span><span class="sxs-lookup"><span data-stu-id="fc00b-184">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="fc00b-185">Trabajar con diseños predefinidos</span><span class="sxs-lookup"><span data-stu-id="fc00b-185">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="fc00b-186">Trabajar con grupos de publicación</span><span class="sxs-lookup"><span data-stu-id="fc00b-186">Work with publish groups</span></span>](publish-groups.md)
