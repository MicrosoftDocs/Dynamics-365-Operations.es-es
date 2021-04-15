---
title: Trabajar con diseños predefinidos
description: En este tema se describe cómo trabajar con diseños preestablecidos en Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ce54be1032777ffcaac474773cdeeef3b9028110
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5793930"
---
# <a name="work-with-preset-layouts"></a><span data-ttu-id="5b4d7-103">Trabajar con diseños predefinidos</span><span class="sxs-lookup"><span data-stu-id="5b4d7-103">Work with preset layouts</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="5b4d7-104">En este tema se describe cómo trabajar con diseños preestablecidos en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-104">This topic describes how to work with preset layouts in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="5b4d7-105">Antes de completar los procedimientos de este tema, asegúrese de leer [Diseños personalizados y preestablecidos](templates-layouts-overview.md#preset-and-custom-layouts).</span><span class="sxs-lookup"><span data-stu-id="5b4d7-105">Before you complete the procedures in this topic, be sure to read [Preset and custom layouts](templates-layouts-overview.md#preset-and-custom-layouts).</span></span> <span data-ttu-id="5b4d7-106">Para una visión general, consulte [Visión general de plantillas y diseños](templates-layouts-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5b4d7-106">For a general overview, see [Templates and layouts overview](templates-layouts-overview.md).</span></span>

## <a name="create-a-new-preset-layout"></a><span data-ttu-id="5b4d7-107">Creación de un nuevo diseño preestablecido</span><span class="sxs-lookup"><span data-stu-id="5b4d7-107">Create a new preset layout</span></span>

<span data-ttu-id="5b4d7-108">Existen dos métodos para crear un diseño preestablecido.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-108">There are two methods for creating a preset layout.</span></span> <span data-ttu-id="5b4d7-109">Puede guardar un diseño personalizado existente como nuevo diseño preestablecido o bien, crear un diseño preestablecido a partir de cero.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-109">You can save an existing custom layout as a new preset layout, or you can create a preset layout from scratch.</span></span>

### <a name="create-a-preset-layout-from-an-existing-custom-layout"></a><span data-ttu-id="5b4d7-110">Crear un diseño preestablecido de un diseño personalizado existente</span><span class="sxs-lookup"><span data-stu-id="5b4d7-110">Create a preset layout from an existing custom layout</span></span>

<span data-ttu-id="5b4d7-111">Para crear un diseño preestablecido de un diseño personalizado existente, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-111">To create a preset layout from an existing custom layout, follow these steps.</span></span>

1. <span data-ttu-id="5b4d7-112">Abra una página existente que no use actualmente un diseño preestablecido, y que tiene una estructura de módulo que desee volver a usar para otras páginas del sitio.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-112">Open an existing page that doesn't currently use a preset layout, and that has a module structure that you want to reuse for other pages on your site.</span></span>
1. <span data-ttu-id="5b4d7-113">Seleccione **Editar** para comprobar la página.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-113">Select **Edit** to check out the page.</span></span>
1. <span data-ttu-id="5b4d7-114">Seleccione **Guardar como nuevo diseño**.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-114">Select **Save as new layout**.</span></span> <span data-ttu-id="5b4d7-115">Aparece el cuadro de diálogo **Guardar como nuevo diseño**.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-115">The **Save as new layout** dialog box appears.</span></span>
1. <span data-ttu-id="5b4d7-116">Especifique un nombre y una descripción para su diseño preestablecido.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-116">Enter a name and description for your preset layout.</span></span> <span data-ttu-id="5b4d7-117">Los valores que especifique se mostrarán a otros autores cuando creen páginas nuevas desde su diseño o pasen a él.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-117">The values that you enter will be shown to other authors when they create new pages from your layout or switch to it.</span></span> <span data-ttu-id="5b4d7-118">Por lo tanto, especifique valores que serán útiles para autores de página.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-118">Therefore, enter values that will be useful to page authors.</span></span>
1. <span data-ttu-id="5b4d7-119">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-119">Select **OK**.</span></span>

<span data-ttu-id="5b4d7-120">El diseño preestablecido estará ahora disponible al crear páginas nuevas o seleccionar un diseño diferente para una página en la misma jerarquía de plantilla.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-120">The preset layout will now be available when you create new pages or select a different layout for a page in the same template hierarchy.</span></span>

> [!TIP]
> <span data-ttu-id="5b4d7-121">Para ver rápidamente si una página determinada está enlazada actualmente a un diseño preestablecido, seleccione la página en la vista de lista de páginas e inspeccione los metadatos de diseño en el panel de propiedades de la derecha.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-121">To quickly see whether a specific page is currently bound to a preset layout, select the page in the pages list view, and inspect the layout metadata in the property pane on the right.</span></span>

### <a name="create-a-new-preset-layout"></a><span data-ttu-id="5b4d7-122">Creación de un nuevo diseño preestablecido</span><span class="sxs-lookup"><span data-stu-id="5b4d7-122">Create a new preset layout</span></span>

<span data-ttu-id="5b4d7-123">Para crear un diseño preestablecido a partir de cero, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-123">To create a preset layout from scratch, follow these steps.</span></span>

1. <span data-ttu-id="5b4d7-124">En el panel de navegación de la izquierda, seleccione **Diseños**.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-124">In the navigation pane on the left, select **Layouts**.</span></span>
1. <span data-ttu-id="5b4d7-125">Seleccione **Nuevo diseño**.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-125">Select **New Layout**.</span></span> <span data-ttu-id="5b4d7-126">Aparece el cuadro de diálogo **Nuevo diseño**.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-126">The **New layout** dialog box appears.</span></span>
1. <span data-ttu-id="5b4d7-127">Seleccione la plantilla que se usará para su diseño preestablecido.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-127">Select the template to use for your preset layout.</span></span>
1. <span data-ttu-id="5b4d7-128">Especifique un nombre y una descripción para su diseño preestablecido.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-128">Enter a name and description for your preset layout.</span></span> <span data-ttu-id="5b4d7-129">Los valores que especifique se mostrarán a otros autores cuando creen páginas nuevas desde su diseño o pasen a él.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-129">The values that you enter will be shown to other authors when they create new pages from your layout or switch to it.</span></span> <span data-ttu-id="5b4d7-130">Por lo tanto, especifique valores que serán útiles para autores de página.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-130">Therefore, enter values that will be useful to page authors.</span></span>
1. <span data-ttu-id="5b4d7-131">Seleccione **Aceptar** para crear el nuevo diseño preestablecido y abrir el editor de diseño.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-131">Select **OK** to create the new preset layout and open the layout editor.</span></span>
1. <span data-ttu-id="5b4d7-132">En el editor de diseño, agregue y configure módulos mediante el árbol de esquema de la izquierda y el panel de propiedades de la derecha.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-132">In the layout editor, add and configure modules by using the outline tree on the left and the property pane on the right.</span></span> <span data-ttu-id="5b4d7-133">(El proceso es similar al de agregar y configurar módulos para una plantilla en el editor de plantillas.) La organización de los módulos y cualquier configuración predeterminada bloqueada se convertirá en la configuración de módulo centralizada para las páginas que usan este diseño preestablecido.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-133">(The process resembles the process for adding and configuring modules for a template in the template editor.) The arrangement of modules and any locked default settings become the centralized module configuration for any pages that use this preset layout.</span></span>

## <a name="modify-a-preset-layout"></a><span data-ttu-id="5b4d7-134">Modificar un diseño preestablecido</span><span class="sxs-lookup"><span data-stu-id="5b4d7-134">Modify a preset layout</span></span>

<span data-ttu-id="5b4d7-135">Para modificar un diseño preestablecido, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-135">To modify a preset layout, follow these steps.</span></span>

1. <span data-ttu-id="5b4d7-136">En el panel de navegación de la izquierda, seleccione **Diseños**.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-136">In the navigation pane on the left, select **Layouts**.</span></span>
1. <span data-ttu-id="5b4d7-137">En el editor de diseño, en el árbol de esquema de la izquierda, seleccione el módulo que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-137">In the layout editor, in the outline tree on the left, select the module to modify.</span></span> <span data-ttu-id="5b4d7-138">Luego siga cualquiera de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="5b4d7-138">Then follow any of these steps:</span></span>

    - <span data-ttu-id="5b4d7-139">Para subir o bajar un módulo dentro de su elemento principal, seleccione los puntos suspensivos (**...**) para el módulo y, a continuación, seleccione **Subir** o **Bajar**.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-139">To move a module up or down inside its parent, select the ellipsis button (**...**) for the module, and then select **Move up** or **Move down**.</span></span>
    - <span data-ttu-id="5b4d7-140">Para cambiar la configuración predeterminada de un módulo, use el panel de propiedades para especificar valores predeterminados y bloquearlos opcionalmente para todas las páginas en sentido descendente.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-140">To change a module's default settings, use the property pane to enter default values and optionally lock them for all downstream pages.</span></span>
    - <span data-ttu-id="5b4d7-141">Para agregar nuevos módulos o fragmentos a los módulos de contenedor, seleccione el botón de puntos suspensivos y después seleccione **Agregar módulo** o **Agregar fragmento**.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-141">To add new modules or fragments to container modules, select the ellipsis button, and then select **Add module** or **Add fragment**.</span></span>
    - <span data-ttu-id="5b4d7-142">Para quitar un módulo del diseño, seleccione los puntos suspensivos y, a continuación, seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-142">To remove a module from the layout, select the ellipsis button, and then select **Delete**.</span></span>

## <a name="change-a-preset-layout-theme"></a><span data-ttu-id="5b4d7-143">Cambiar un tema de diseño preestablecido</span><span class="sxs-lookup"><span data-stu-id="5b4d7-143">Change a preset layout theme</span></span>

<span data-ttu-id="5b4d7-144">Una práctica típica es establecer un tema predeterminado para todas las páginas que utilicen un diseño preestablecido.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-144">A typical practice is to set a default theme for all pages that use a preset layout.</span></span>

<span data-ttu-id="5b4d7-145">Para establecer o cambiar el tema para todas las páginas secundarias que utilicen su diseño preestablecido, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-145">To set or change the theme for all child pages that use your preset layout, follow these steps.</span></span>

1. <span data-ttu-id="5b4d7-146">En el editor de diseño, en el árbol de esquema de la izquierda, seleccione el módulo de contenedor de páginas.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-146">In the layout editor, in the outline tree on the left, select the page container module.</span></span> <span data-ttu-id="5b4d7-147">(Normalmente, este módulo es el segundo nodo y se llama **Página predeterminada**.)</span><span class="sxs-lookup"><span data-stu-id="5b4d7-147">(Typically, this module is the second node and is named **Default page**.)</span></span>
1. <span data-ttu-id="5b4d7-148">En el panel de propiedades de la derecha, en el campo **Tema**, seleccione un tema.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-148">In the property pane on the right, in the **Theme** field, select a theme.</span></span>

## <a name="save-check-in-preview-and-publish-a-preset-layout"></a><span data-ttu-id="5b4d7-149">Guardar, proteger, obtener una vista previa y publicar un diseño preestablecido</span><span class="sxs-lookup"><span data-stu-id="5b4d7-149">Save, check in, preview, and publish a preset layout</span></span>

<span data-ttu-id="5b4d7-150">Para guardar y proteger su diseño preestablecido, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-150">To save and check in your preset layout, follow these steps.</span></span>

1. <span data-ttu-id="5b4d7-151">Seleccione **Guardar** en la parte superior del editor de diseño.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-151">Select **Save** at the top of the layout editor.</span></span> <span data-ttu-id="5b4d7-152">Los cambios guardados no afectan a las páginas en sentido descendente hasta que se protegen.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-152">Saved changes don't affect downstream pages until they are checked in.</span></span>
1. <span data-ttu-id="5b4d7-153">Seleccione **Finalizar edición**.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-153">Select **Finish editing**.</span></span> <span data-ttu-id="5b4d7-154">Sus cambios son ahora detectables para flujos de trabajo en sentido descendente.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-154">Your changes are now discoverable for downstream workflows.</span></span>

<span data-ttu-id="5b4d7-155">Para obtener una vista previa de los cambios, abra una página existente que utilice el diseño preestablecido o cree una nueva página a partir del diseño.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-155">To preview your changes, either open an existing page that uses the preset layout or create a new page from the layout.</span></span>

<span data-ttu-id="5b4d7-156">Cuando haya obtenido una vista previa de los cambios para su diseño preestablecido, siga uno de estos pasos para publicar el diseño en el sitio activo:</span><span class="sxs-lookup"><span data-stu-id="5b4d7-156">After you've previewed the changes to your preset layout, follow one of these steps to publish the layout to your live site:</span></span>

* <span data-ttu-id="5b4d7-157">Vaya a **Diseños**, seleccione el diseño y, a continuación, **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-157">Go to **Layouts**, select the layout, and then select **Publish**.</span></span>
* <span data-ttu-id="5b4d7-158">Seleccione el nombre del diseño para abrir el editor de diseño y después seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-158">Select the layout name to open the layout editor, and then select **Publish**.</span></span>
* <span data-ttu-id="5b4d7-159">Publique una página que haga referencia al diseño sin publicar.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-159">Publish a page that references the unpublished layout.</span></span> <span data-ttu-id="5b4d7-160">El diseño se publicará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-160">The layout will automatically be published.</span></span>

> [!WARNING]
> <span data-ttu-id="5b4d7-161">Varias páginas pueden hacer referencia a diseños preestablecidos.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-161">Preset layouts can be referenced by multiple pages.</span></span> <span data-ttu-id="5b4d7-162">Al publicar un diseño preestablecido, tenga en cuenta que puede afectar al diseño de varias páginas.</span><span class="sxs-lookup"><span data-stu-id="5b4d7-162">When you publish a preset layout, be aware that you might affect the layout of multiple pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5b4d7-163">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="5b4d7-163">Additional resources</span></span>

[<span data-ttu-id="5b4d7-164">Visión general de plantillas y diseños</span><span class="sxs-lookup"><span data-stu-id="5b4d7-164">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="5b4d7-165">Trabajar con plantillas</span><span class="sxs-lookup"><span data-stu-id="5b4d7-165">Work with templates</span></span>](work-with-templates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
