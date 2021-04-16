---
title: Obtener una vista previa y publicar un experimento
description: Este tema describe cómo obtener una vista previa y publicar un experimento desde Dynamics 365 Commerce.
author: sushma-rao
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 52ca23e5aaeb7058853fed2241d5804180fa7f8d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798972"
---
# <a name="preview-and-publish-an-experiment"></a><span data-ttu-id="ed5e2-103">Obtener una vista previa y publicar un experimento</span><span class="sxs-lookup"><span data-stu-id="ed5e2-103">Preview and publish an experiment</span></span>

<span data-ttu-id="ed5e2-104">Este tema describe cómo obtener una vista previa y publicar su experimento en Dynamics 365 Commerce después de que haya [conectado su experimento y editado sus variaciones](experimentation-connect-edit.md).</span><span class="sxs-lookup"><span data-stu-id="ed5e2-104">This topic describes how to preview and publish your experiment in Dynamics 365 Commerce after you've [connected your experiment and edited your variations](experimentation-connect-edit.md).</span></span> <span data-ttu-id="ed5e2-105">El siguiente diagrama muestra todos los pasos necesarios para configurar y ejecutar un experimento en un sitio web de comercio electrónico en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ed5e2-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="ed5e2-106">Los pasos adicionales se tratan en temas separados.</span><span class="sxs-lookup"><span data-stu-id="ed5e2-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="ed5e2-107">[ ![Recorrido del usuario de experimentación: vista previa y publicación](./media/experimentation_preview_publish.svg) ](./media/experimentation_preview_publish.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="ed5e2-107">[ ![Experimentation user journey - Preview & Publish](./media/experimentation_preview_publish.svg) ](./media/experimentation_preview_publish.svg#lightbox)</span></span>

## <a name="preview-your-experiment-variations"></a><span data-ttu-id="ed5e2-108">Vista previa de las variaciones del experimento</span><span class="sxs-lookup"><span data-stu-id="ed5e2-108">Preview your experiment variations</span></span>
<span data-ttu-id="ed5e2-109">Puede obtener una vista previa de sus variaciones y seguir editándolas hasta que se vean como desea.</span><span class="sxs-lookup"><span data-stu-id="ed5e2-109">You can preview your variations and continue editing them until they look the way you want them to.</span></span>

<span data-ttu-id="ed5e2-110">Para mostrar una vista previa de las variaciones del experimento en el generador de sitios de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ed5e2-110">To preview your experiment variations in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="ed5e2-111">En el menú desplegable de variaciones situado debajo de la barra de comandos, seleccione el contenido del que desea obtener una vista previa.</span><span class="sxs-lookup"><span data-stu-id="ed5e2-111">From the variations drop-down menu below the command bar, select the content you want to preview.</span></span> 
1. <span data-ttu-id="ed5e2-112">En la barra de comandos, seleccione **Vista previa**.</span><span class="sxs-lookup"><span data-stu-id="ed5e2-112">On the command bar, select **Preview**.</span></span> <span data-ttu-id="ed5e2-113">Se muestra una vista previa de cómo se verá el contenido cuando se publique.</span><span class="sxs-lookup"><span data-stu-id="ed5e2-113">A preview of what the content will look like when it's published is displayed.</span></span>
1. <span data-ttu-id="ed5e2-114">Para obtener una vista previa de una variación diferente, selecciónela en el menú desplegable de variaciones y seleccione **Vista previa** de nuevo.</span><span class="sxs-lookup"><span data-stu-id="ed5e2-114">To preview a different variation, select it from the variation drop-down menu and select **Preview** again.</span></span>

## <a name="publish-your-experiment"></a><span data-ttu-id="ed5e2-115">Publique su experimento</span><span class="sxs-lookup"><span data-stu-id="ed5e2-115">Publish your experiment</span></span>
<span data-ttu-id="ed5e2-116">Si no está utilizando un grupo de publicación para programar cuándo se activa su experimento y desea publicarlo de inmediato, seleccione **Publicar** en la barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="ed5e2-116">If you aren't using a publish group to schedule when your experiment goes live and you want to publish immediately, select **Publish** in the command bar.</span></span> <span data-ttu-id="ed5e2-117">Se publicarán todas las variaciones que pertenezcan al experimento.</span><span class="sxs-lookup"><span data-stu-id="ed5e2-117">All variations that belong to the experiment will be published.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="ed5e2-118">Si la página tiene una URL no publicada, primero debe publicar la URL o no será visible para los usuarios de su sitio web.</span><span class="sxs-lookup"><span data-stu-id="ed5e2-118">If the page has an unpublished URL, you must first publish the URL or it won't be visible to your website users.</span></span> <span data-ttu-id="ed5e2-119">Para más detalles, consulte [Guardar, obtener una vista previa y publicar una página](save-preview-publish-page.md).</span><span class="sxs-lookup"><span data-stu-id="ed5e2-119">For details, see [Save, preview, and publish a page](save-preview-publish-page.md).</span></span>
    
### <a name="use-publish-groups-to-schedule-when-your-experiment-goes-live"></a><span data-ttu-id="ed5e2-120">Utilice grupos de publicación para programar cuándo se activa su experimento</span><span class="sxs-lookup"><span data-stu-id="ed5e2-120">Use publish groups to schedule when your experiment goes live</span></span>
<span data-ttu-id="ed5e2-121">Las variaciones creadas en el creador de sitios se pueden programar para su publicación mediante un grupo de publicación.</span><span class="sxs-lookup"><span data-stu-id="ed5e2-121">Variations created in site builder can be scheduled for publishing by using a publish group.</span></span> <span data-ttu-id="ed5e2-122">Dentro de un grupo de publicación, puede conectar una página o un fragmento a su experimento seleccionando **Experimentos** en el panel de navegación izquierdo.</span><span class="sxs-lookup"><span data-stu-id="ed5e2-122">Within a publish group, you can connect a page or fragment to your experiment by selecting **Experiments** in the left navigation pane.</span></span> <span data-ttu-id="ed5e2-123">Para hacer esto también puede seleccionar **Páginas** o **Fragmentos**, y seguir las instrucciones de [Conectar un experimento y editar variaciones](experimentation-connect-edit.md).</span><span class="sxs-lookup"><span data-stu-id="ed5e2-123">You can also do this by selecting **Pages** or **Fragments** and following the instructions in [Connect an experiment and edit variations](experimentation-connect-edit.md).</span></span> <span data-ttu-id="ed5e2-124">Para obtener información sobre los grupos de publicación, consulte [Trabajar con grupos de publicación](publish-groups.md).</span><span class="sxs-lookup"><span data-stu-id="ed5e2-124">For information about publish groups, see [Work with publish groups](publish-groups.md).</span></span>

<span data-ttu-id="ed5e2-125">Al utilizar grupos de publicación con experimentos, hay algunas consideraciones importantes que debe tener en cuenta.</span><span class="sxs-lookup"><span data-stu-id="ed5e2-125">When using publish groups with experiments, there are some important considerations to be aware of.</span></span>
- <span data-ttu-id="ed5e2-126">Cuando agrega una página o un fragmento que tiene un experimento en ejecución a un grupo de publicación, el experimento se eliminará de la página o el fragmento en el grupo de publicación.</span><span class="sxs-lookup"><span data-stu-id="ed5e2-126">When you add a page or fragment that has an experiment running on it to a publish group, the experiment will be removed from the page or fragment in the publish group.</span></span>
- <span data-ttu-id="ed5e2-127">Los experimentos que están conectados a las páginas de un sitio activo no están disponibles para las páginas de los grupos de publicación y viceversa.</span><span class="sxs-lookup"><span data-stu-id="ed5e2-127">Experiments that are connected to pages in a live site aren't available to pages within publish groups and vice-versa.</span></span> <span data-ttu-id="ed5e2-128">Del mismo modo, las páginas que tienen experimentos en ejecución en un sitio en vivo no están disponibles para otros experimentos en grupos de publicación y viceversa.</span><span class="sxs-lookup"><span data-stu-id="ed5e2-128">Similarly, pages that have experiments running on them in a live site aren't available to other experiments in publish groups and vice versa.</span></span>
- <span data-ttu-id="ed5e2-129">Cuando publica o programa un grupo de publicación, se publica todo el contenido del grupo de publicación, independientemente de si hay un experimento asociado con el grupo de publicación.</span><span class="sxs-lookup"><span data-stu-id="ed5e2-129">When you publish or schedule a publish group, all content in the publish group is published, regardless of whether there's an experiment associated with the publish group.</span></span>
- <span data-ttu-id="ed5e2-130">Debido a que un grupo de publicación continúa persistiendo después de que se haya publicado en un sitio activo, los experimentos en el grupo de publicación también persistirán.</span><span class="sxs-lookup"><span data-stu-id="ed5e2-130">Because a publish group continues to persist after it's been published to a live site, experiments in the publish group will also persist.</span></span> <span data-ttu-id="ed5e2-131">Por lo tanto, no podrá asociar otros experimentos con la misma página o fragmento.</span><span class="sxs-lookup"><span data-stu-id="ed5e2-131">Therefore, you won't be able to associate other experiments with the same page or fragment.</span></span> <span data-ttu-id="ed5e2-132">Para evitar esta limitación, elimine cualquier grupo de publicación con experimentos persistentes.</span><span class="sxs-lookup"><span data-stu-id="ed5e2-132">To avoid this limitation, delete any publish groups with persisting experiments.</span></span> <span data-ttu-id="ed5e2-133">Del mismo modo, si desea eliminar un experimento en un sitio activo que también existe en un grupo de publicación, elimínelo primero del grupo de publicación.</span><span class="sxs-lookup"><span data-stu-id="ed5e2-133">Similarly, if you want to delete an experiment in a live site that also exists in a publish group, delete it from the publish group first.</span></span>

## <a name="previous-step"></a><span data-ttu-id="ed5e2-134">Paso anterior</span><span class="sxs-lookup"><span data-stu-id="ed5e2-134">Previous step</span></span>
[<span data-ttu-id="ed5e2-135">Conectar y editar un experimento</span><span class="sxs-lookup"><span data-stu-id="ed5e2-135">Connect and edit an experiment</span></span>](experimentation-connect-edit.md)

## <a name="next-step"></a><span data-ttu-id="ed5e2-136">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="ed5e2-136">Next step</span></span>
[<span data-ttu-id="ed5e2-137">Ejecutar y supervisar un experimento</span><span class="sxs-lookup"><span data-stu-id="ed5e2-137">Run and monitor an experiment</span></span>](experimentation-run-monitor.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]