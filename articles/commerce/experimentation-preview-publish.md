---
title: Obtener una vista previa y publicar un experimento
description: Este tema describe cómo obtener una vista previa y publicar un experimento desde Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 10/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 91e2e4840a2d53f195d881279050b6415d48b070
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930285"
---
# <a name="preview-and-publish-an-experiment"></a><span data-ttu-id="3fdb9-103">Obtener una vista previa y publicar un experimento</span><span class="sxs-lookup"><span data-stu-id="3fdb9-103">Preview and publish an experiment</span></span>

<span data-ttu-id="3fdb9-104">Este tema describe cómo obtener una vista previa y publicar su experimento en Dynamics 365 Commerce después de que haya [conectado su experimento y editado sus variaciones](experimentation-connect-edit.md).</span><span class="sxs-lookup"><span data-stu-id="3fdb9-104">This topic describes how to preview and publish your experiment in Dynamics 365 Commerce after you've [connected your experiment and edited your variations](experimentation-connect-edit.md).</span></span> <span data-ttu-id="3fdb9-105">El siguiente diagrama muestra todos los pasos necesarios para configurar y ejecutar un experimento en un sitio web de comercio electrónico en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3fdb9-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="3fdb9-106">Los pasos adicionales se tratan en temas separados.</span><span class="sxs-lookup"><span data-stu-id="3fdb9-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="3fdb9-107">[ ![Recorrido del usuario de experimentación: vista previa y publicación](./media/experimentation_preview_publish.svg) ](./media/experimentation_preview_publish.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="3fdb9-107">[ ![Experimentation user journey - Preview & Publish](./media/experimentation_preview_publish.svg) ](./media/experimentation_preview_publish.svg#lightbox)</span></span>

## <a name="preview-your-experiment-variations"></a><span data-ttu-id="3fdb9-108">Vista previa de las variaciones del experimento</span><span class="sxs-lookup"><span data-stu-id="3fdb9-108">Preview your experiment variations</span></span>
<span data-ttu-id="3fdb9-109">Puede obtener una vista previa de sus variaciones y seguir editándolas hasta que se vean como desea.</span><span class="sxs-lookup"><span data-stu-id="3fdb9-109">You can preview your variations and continue editing them until they look the way you want them to.</span></span>

1. <span data-ttu-id="3fdb9-110">En el generador de sitios, use el menú desplegable de variaciones debajo de la barra de comandos para seleccionar el contenido del que desea obtener una vista previa.</span><span class="sxs-lookup"><span data-stu-id="3fdb9-110">In site builder, use the variations drop-down menu below the command bar to select the content you want to preview.</span></span> 
1. <span data-ttu-id="3fdb9-111">Seleccione **Vista previa** en la barra superior.</span><span class="sxs-lookup"><span data-stu-id="3fdb9-111">Select **Preview** in the top bar.</span></span> <span data-ttu-id="3fdb9-112">Se muestra una vista previa de cómo se verá el contenido cuando se publique.</span><span class="sxs-lookup"><span data-stu-id="3fdb9-112">A preview of what the content will look like when it's published is displayed.</span></span>
1. <span data-ttu-id="3fdb9-113">Para obtener una vista previa de una variación diferente, selecciónela en el menú desplegable de variaciones y seleccione **Vista previa** otra vez.</span><span class="sxs-lookup"><span data-stu-id="3fdb9-113">To preview a different variation, select it from the variation drop-down and select **Preview** again.</span></span>

## <a name="publish-your-experiment"></a><span data-ttu-id="3fdb9-114">Publique su experimento</span><span class="sxs-lookup"><span data-stu-id="3fdb9-114">Publish your experiment</span></span>
<span data-ttu-id="3fdb9-115">Si no está utilizando un grupo de publicación para programar cuándo se activa su experimento y desea publicarlo de inmediato, seleccione **Publicar** en la barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="3fdb9-115">If you aren't using a publish group to schedule when your experiment goes live and you want to publish immediately, select **Publish** in the command bar.</span></span> <span data-ttu-id="3fdb9-116">Se publicarán todas las variaciones que pertenezcan al experimento.</span><span class="sxs-lookup"><span data-stu-id="3fdb9-116">All variations that belong to the experiment will be published.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="3fdb9-117">Si la página tiene una URL no publicada, primero debe publicar la URL o no será visible para los usuarios de su sitio web.</span><span class="sxs-lookup"><span data-stu-id="3fdb9-117">If the page has an unpublished URL, you must first publish the URL or it won't be visible to your website users.</span></span> <span data-ttu-id="3fdb9-118">Para más detalles, consulte [Guardar, obtener una vista previa y publicar una página](save-preview-publish-page.md).</span><span class="sxs-lookup"><span data-stu-id="3fdb9-118">For details, see [Save, preview, and publish a page](save-preview-publish-page.md).</span></span>
    
### <a name="use-publish-groups-to-schedule-when-your-experiment-goes-live"></a><span data-ttu-id="3fdb9-119">Utilice grupos de publicación para programar cuándo se activa su experimento</span><span class="sxs-lookup"><span data-stu-id="3fdb9-119">Use publish groups to schedule when your experiment goes live</span></span>
<span data-ttu-id="3fdb9-120">Las variaciones creadas en el creador de sitios se pueden programar para su publicación mediante un grupo de publicación.</span><span class="sxs-lookup"><span data-stu-id="3fdb9-120">Variations created in site builder can be scheduled for publishing by using a publish group.</span></span> <span data-ttu-id="3fdb9-121">Dentro de un grupo de publicación, puede conectar una página o un fragmento a su experimento yendo a la pestaña **Experimentos** o las pestañas **Páginas** o **Fragmentos**. Para más información, vea [Conectar un experimento y editar variaciones](experimentation-connect-edit.md).</span><span class="sxs-lookup"><span data-stu-id="3fdb9-121">Within a publish group, you can connect a page or fragment to your experiment by going to the **Experiments** tab or the **Pages** or **Fragments** tab. For more information, see [Connect an experiment and edit variations](experimentation-connect-edit.md) topic.</span></span> <span data-ttu-id="3fdb9-122">Para obtener información sobre los grupos de publicación, consulte [Trabajar con grupos de publicación](publish-groups.md).</span><span class="sxs-lookup"><span data-stu-id="3fdb9-122">For information about publish groups, see [Work with publish groups](publish-groups.md).</span></span>

<span data-ttu-id="3fdb9-123">Al utilizar grupos de publicación con experimentos, hay algunas consideraciones importantes que debe tener en cuenta.</span><span class="sxs-lookup"><span data-stu-id="3fdb9-123">When using publish groups with experiments, there are some important considerations to be aware of.</span></span>
- <span data-ttu-id="3fdb9-124">Cuando agrega una página o un fragmento que tiene un experimento en ejecución a un grupo de publicación, el experimento se eliminará de la página o el fragmento en el grupo de publicación.</span><span class="sxs-lookup"><span data-stu-id="3fdb9-124">When you add a page or fragment that has an experiment running on it to a publish group, the experiment will be removed from the page or fragment in the publish group.</span></span>
- <span data-ttu-id="3fdb9-125">Los experimentos que están conectados a las páginas de un sitio activo no están disponibles para las páginas de los grupos de publicación y viceversa.</span><span class="sxs-lookup"><span data-stu-id="3fdb9-125">Experiments that are connected to pages in a live site aren't available to pages within publish groups and vice-versa.</span></span> <span data-ttu-id="3fdb9-126">Del mismo modo, las páginas que tienen experimentos en ejecución en un sitio en vivo no están disponibles para otros experimentos en grupos de publicación y viceversa.</span><span class="sxs-lookup"><span data-stu-id="3fdb9-126">Similarly, pages that have experiments running on them in a live site aren't available to other experiments in publish groups and vice versa.</span></span>
- <span data-ttu-id="3fdb9-127">Cuando publica o programa un grupo de publicación, se publica todo el contenido del grupo de publicación, independientemente de si hay un experimento asociado con el grupo de publicación.</span><span class="sxs-lookup"><span data-stu-id="3fdb9-127">When you publish or schedule a publish group, all content in the publish group is published, regardless of whether there's an experiment associated with the publish group.</span></span>
- <span data-ttu-id="3fdb9-128">Debido a que un grupo de publicación continúa persistiendo después de que se haya publicado en un sitio activo, los experimentos en el grupo de publicación también persistirán.</span><span class="sxs-lookup"><span data-stu-id="3fdb9-128">Because a publish group continues to persist after it's been published to a live site, experiments in the publish group will also persist.</span></span> <span data-ttu-id="3fdb9-129">Por lo tanto, no podrá asociar otros experimentos con la misma página o fragmento.</span><span class="sxs-lookup"><span data-stu-id="3fdb9-129">Therefore, you won't be able to associate other experiments with the same page or fragment.</span></span> <span data-ttu-id="3fdb9-130">Para evitar esta limitación, elimine cualquier grupo de publicación con experimentos persistentes.</span><span class="sxs-lookup"><span data-stu-id="3fdb9-130">To avoid this limitation, delete any publish groups with persisting experiments.</span></span> <span data-ttu-id="3fdb9-131">Del mismo modo, si desea eliminar un experimento en un sitio activo que también existe en un grupo de publicación, elimínelo primero del grupo de publicación.</span><span class="sxs-lookup"><span data-stu-id="3fdb9-131">Similarly, if you want to delete an experiment in a live site that also exists in a publish group, delete it from the publish group first.</span></span>

## <a name="previous-step"></a><span data-ttu-id="3fdb9-132">Paso anterior</span><span class="sxs-lookup"><span data-stu-id="3fdb9-132">Previous step</span></span>
[<span data-ttu-id="3fdb9-133">Conectar y editar un experimento</span><span class="sxs-lookup"><span data-stu-id="3fdb9-133">Connect and edit an experiment</span></span>](experimentation-connect-edit.md)

## <a name="next-step"></a><span data-ttu-id="3fdb9-134">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="3fdb9-134">Next step</span></span>
[<span data-ttu-id="3fdb9-135">Ejecutar y supervisar un experimento</span><span class="sxs-lookup"><span data-stu-id="3fdb9-135">Run and monitor an experiment</span></span>](experimentation-run-monitor.md)
