---
title: Conectar un experimento y editar variaciones
description: Este tema describe cómo conectar un experimento en un servicio de terceros a Dynamics 365 Commerce y cómo editar variaciones para el experimento.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
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
ms.openlocfilehash: 2a33897d01dd98d446c2fb49e417abd9db9f403a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5010033"
---
# <a name="connect-an-experiment-and-edit-variations"></a><span data-ttu-id="70a90-103">Conectar un experimento y editar variaciones</span><span class="sxs-lookup"><span data-stu-id="70a90-103">Connect an experiment and edit variations</span></span>

<span data-ttu-id="70a90-104">Este tema describe cómo conectar su experimento en Commerce y realizar cambios en sus variaciones para que se alineen con su hipótesis.</span><span class="sxs-lookup"><span data-stu-id="70a90-104">This topic describes how to connect your experiment in Commerce and make changes to your variations so that they align with your hypothesis.</span></span> 

<span data-ttu-id="70a90-105">El siguiente diagrama muestra todos los pasos necesarios para configurar y ejecutar un experimento en un sitio web de comercio electrónico en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="70a90-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="70a90-106">Los pasos adicionales se tratan en temas separados.</span><span class="sxs-lookup"><span data-stu-id="70a90-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="70a90-107">[ ![Recorrido del usuario de experimentación: conectar y editar](./media/experimentation_connect_edit.svg) ](./media/experimentation_connect_edit.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="70a90-107">[ ![Experimentation user journey - Connect & Edit](./media/experimentation_connect_edit.svg) ](./media/experimentation_connect_edit.svg#lightbox)</span></span>

<span data-ttu-id="70a90-108">Después de [configurar un experimento](experimentation-setup.md) en un servicio de terceros, conectará el experimento en Dynamics 365 Commerce y editará las variaciones del experimento.</span><span class="sxs-lookup"><span data-stu-id="70a90-108">After you've [set up your experiment](experimentation-setup.md) in a third-party service, you'll connect the experiment in Dynamics 365 Commerce and edit the experiment variations.</span></span>

## <a name="planning-considerations"></a><span data-ttu-id="70a90-109">Consideraciones de planificación</span><span class="sxs-lookup"><span data-stu-id="70a90-109">Planning considerations</span></span>

<span data-ttu-id="70a90-110">Antes de conectar su experimento en Commerce, deberá tomar algunas decisiones que afecten la forma en que Commerce administra su contenido.</span><span class="sxs-lookup"><span data-stu-id="70a90-110">Before you connect your experiment in Commerce, you'll need to make some decisions that impact the way Commerce manages your content.</span></span>

### <a name="determine-the-scope-of-your-experiment"></a><span data-ttu-id="70a90-111">Determine el alcance de su experimento</span><span class="sxs-lookup"><span data-stu-id="70a90-111">Determine the scope of your experiment</span></span>
<span data-ttu-id="70a90-112">Cuando conecta un experimento, se le solicita que defina el alcance del experimento.</span><span class="sxs-lookup"><span data-stu-id="70a90-112">When you connect an experiment, you are prompted to define the scope of the experiment.</span></span> <span data-ttu-id="70a90-113">Los experimentos se definen como de alcance **parcial** o **total**.</span><span class="sxs-lookup"><span data-stu-id="70a90-113">Experiments are defined as **partial** scope or **entire** scope.</span></span>
- <span data-ttu-id="70a90-114">Escoja **parcial** si desea realizar un experimento en una parte específica de una página.</span><span class="sxs-lookup"><span data-stu-id="70a90-114">Choose **partial** if you want to conduct an experiment on a specific portion of a page.</span></span> <span data-ttu-id="70a90-115">Si selecciona esta opción, debe identificar qué módulos se incluyen en el experimento.</span><span class="sxs-lookup"><span data-stu-id="70a90-115">If you select this option, you must identify which modules are included in the experiment.</span></span> <span data-ttu-id="70a90-116">Los cambios que se realizan en partes de la página o el fragmento predeterminados que no están relacionados con el experimento se sincronizan automáticamente entre las variaciones.</span><span class="sxs-lookup"><span data-stu-id="70a90-116">Changes that are made to parts of the default page or fragment that aren't related to the experiment are automatically synchronized across variations.</span></span>
- <span data-ttu-id="70a90-117">Escoja **total** si desea realizar un experimento en una página completa o en un fragmento.</span><span class="sxs-lookup"><span data-stu-id="70a90-117">Choose **entire** if you want to conduct an experiment on an entire page or fragment.</span></span> <span data-ttu-id="70a90-118">Se crean copias separadas de la página o el fragmento predeterminados.</span><span class="sxs-lookup"><span data-stu-id="70a90-118">Separate copies of the default page or fragment are created.</span></span> <span data-ttu-id="70a90-119">No tendrá que seleccionar qué módulos están incluidos en el experimento porque toda la superficie de edición está disponible para cambiar.</span><span class="sxs-lookup"><span data-stu-id="70a90-119">You won't have to select which modules are included in the experiment because the whole editing surface is available to change.</span></span> <span data-ttu-id="70a90-120">Puede agregar, eliminar o reordenar módulos según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="70a90-120">You can add, delete, or re-order modules as needed.</span></span> <span data-ttu-id="70a90-121">Sin embargo, si se realizan cambios en la página predeterminada o en el fragmento con el que está asociado el experimento, esos cambios deben sincronizarse manualmente en todas las variaciones.</span><span class="sxs-lookup"><span data-stu-id="70a90-121">However, if any changes are made to the default page or fragment that the experiment is associated with, those changes have to be manually synchronized across all variations.</span></span>

<!-- not to editors, we're adding an image here to illustrate the difference. it will help.) -->

> [!NOTE]
> <span data-ttu-id="70a90-122">Si asocia su experimento con una página que utiliza un diseño, solo puede definir el alcance del experimento como **total**.</span><span class="sxs-lookup"><span data-stu-id="70a90-122">If you associate your experiment with a page that uses a layout, you can only scope the experiment as **entire**.</span></span>

### <a name="decide-if-you-want-to-schedule-when-your-experiment-is-published"></a><span data-ttu-id="70a90-123">Decida si quiere programar la publicación del experimento</span><span class="sxs-lookup"><span data-stu-id="70a90-123">Decide if you want to schedule when your experiment is published</span></span>
<span data-ttu-id="70a90-124">Si desea programar cuándo se publicará su experimento en su sitio en vivo, asegúrese de que el contenido que desea asociar con el experimento esté disponible en un grupo de publicación *antes de* conectar el experimento.</span><span class="sxs-lookup"><span data-stu-id="70a90-124">If you want to schedule when your experiment is published to your live site, make sure the content you want to associate with the experiment is available in a publish group *before* you connect the experiment.</span></span> 

<span data-ttu-id="70a90-125">Para obtener más información sobre los grupos de publicación, consulte [Trabajar con grupos de publicación](publish-groups.md).</span><span class="sxs-lookup"><span data-stu-id="70a90-125">For more information about publish groups, refer to [Work with publish groups](publish-groups.md).</span></span>


## <a name="connect-your-experiment"></a><span data-ttu-id="70a90-126">Conecte el experimento</span><span class="sxs-lookup"><span data-stu-id="70a90-126">Connect your experiment</span></span>
<span data-ttu-id="70a90-127">Para conectar su experimento, iniciará el asistente **Conectar experimento**.</span><span class="sxs-lookup"><span data-stu-id="70a90-127">To connect your experiment, you'll launch the **Connect experiment** wizard.</span></span> <span data-ttu-id="70a90-128">El asistente lo guía a través de los pasos necesarios para conectar su experimento.</span><span class="sxs-lookup"><span data-stu-id="70a90-128">The wizard walks you through the steps required to connect your experiment.</span></span> <span data-ttu-id="70a90-129">Cuando complete el asistente, su experimento estará conectado y las variaciones se crearán y estarán listas para ser editadas.</span><span class="sxs-lookup"><span data-stu-id="70a90-129">When you complete the wizard, your experiment is connected and variations are created and ready to be edited.</span></span>

<span data-ttu-id="70a90-130">Para empezar a conectar su experimento en el generador de sitios de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="70a90-130">To get started connecting your experiment in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="70a90-131">Para iniciar el asistente **Conectar experimento**, seleccione **Experimentos** en el panel de navegación izquierdo y, a continuación, seleccione **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="70a90-131">To launch the **Connect experiment** wizard, select **Experiments** in the left navigation pane, and then select **Connect**.</span></span> <span data-ttu-id="70a90-132">Como alternativa, puede acceder al asistente desde una página o editor de fragmentos editándolo y seleccionando **Conectar experimento** en la barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="70a90-132">Alternatively, you can access the wizard from a page or fragment editor by editing it and selecting **Connect experiment** on the command bar.</span></span>

    > [!NOTE]
    > <span data-ttu-id="70a90-133">Una página solo se puede conectar a un experimento a la vez.</span><span class="sxs-lookup"><span data-stu-id="70a90-133">A page can only be connected to one experiment at a time.</span></span> <span data-ttu-id="70a90-134">Para conectar una página a un experimento diferente, primero elimine el experimento al que está conectada actualmente la página.</span><span class="sxs-lookup"><span data-stu-id="70a90-134">To connect a page to a different experiment, first delete the experiment that the page is currently connected to.</span></span>

1. <span data-ttu-id="70a90-135">Elija la página o el fragmento en el que desea ejecutar su experimento.</span><span class="sxs-lookup"><span data-stu-id="70a90-135">Choose the page or fragment you want to run your experiment on.</span></span>
1. <span data-ttu-id="70a90-136">Establezca el alcance de la experimentación en **parcial** o **total**, según la elección que hizo en la sección anterior [Determinar el alcance de su experimento](#determine-the-scope-of-your-experiment).</span><span class="sxs-lookup"><span data-stu-id="70a90-136">Set the experimentation scope to **partial** or **entire**, based on the choice you made in the [Determine the scope of your experiment](#determine-the-scope-of-your-experiment) section above.</span></span>
    > [!NOTE]
    > <span data-ttu-id="70a90-137">El indicador de la característica **Experimentar con páginas o fragmentos** debe estar habilitado si desea experimentar en una página completa o en un fragmento.</span><span class="sxs-lookup"><span data-stu-id="70a90-137">The **Experiment on pages or fragments** feature flag must be enabled if you want to experiment on a full page or fragment.</span></span> <span data-ttu-id="70a90-138">Para obtener más información, consulte el tema [Experimención en Dynamics 365 Commerce](experimentation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="70a90-138">Refer to the [Experimentation in Dynamics 365 Commerce](experimentation-overview.md) topic for more information.</span></span>
    
1. <span data-ttu-id="70a90-139">En el paso final del asistente, seleccione **Asistente para generar variaciones y salir**.</span><span class="sxs-lookup"><span data-stu-id="70a90-139">In the final step of the wizard, select **Generate variations and exit wizard**.</span></span> <span data-ttu-id="70a90-140">Se crean variaciones para el experimento.</span><span class="sxs-lookup"><span data-stu-id="70a90-140">Variations are created for the experiment.</span></span> 

## <a name="edit-your-variations"></a><span data-ttu-id="70a90-141">Edita tus variaciones</span><span class="sxs-lookup"><span data-stu-id="70a90-141">Edit your variations</span></span>
<span data-ttu-id="70a90-142">Cuando sale del asistente, se crean variaciones para usted.</span><span class="sxs-lookup"><span data-stu-id="70a90-142">When you exit the wizard, variations are created for you.</span></span> 

<span data-ttu-id="70a90-143">A continuación, editará las variaciones para que reflejen las opciones que necesita verificar en la hipótesis del experimento.</span><span class="sxs-lookup"><span data-stu-id="70a90-143">Next, you'll edit the variations so they reflect the choices that you need to verify in the experiment hypothesis.</span></span> <span data-ttu-id="70a90-144">Elija uno de los siguientes procedimientos que corresponda al alcance que eligió para su experimento en la sección anterior [Determinar el alcance de su experimento](#determine-the-scope-of-your-experiment).</span><span class="sxs-lookup"><span data-stu-id="70a90-144">Choose one of following procedures that corresponds to the scope you chose for your experiment in the [Determine the scope of your experiment](#determine-the-scope-of-your-experiment) section above.</span></span>

### <a name="edit-variations-for-experiments-with-partial-scope"></a><span data-ttu-id="70a90-145">Editar variaciones para experimentos con alcance parcial</span><span class="sxs-lookup"><span data-stu-id="70a90-145">Edit variations for experiments with partial scope</span></span>
<span data-ttu-id="70a90-146">Siga estos pasos si definió el alcance de su experimento como **parcial** en el asistente **Conectar experimento**.</span><span class="sxs-lookup"><span data-stu-id="70a90-146">Follow these steps if you defined the scope of your experiment as **partial** in the **Connect experiment** wizard.</span></span>

1. <span data-ttu-id="70a90-147">En la vista de editor, use el menú desplegable de variaciones debajo de la barra de comandos para editar cada variación según su hipótesis original.</span><span class="sxs-lookup"><span data-stu-id="70a90-147">In editor view, use the variations drop-down menu below the command bar to edit each variation based on your original hypothesis.</span></span> <span data-ttu-id="70a90-148">También es posible que desee establecer una variación de control o base dejando una de las variaciones sin cambios.</span><span class="sxs-lookup"><span data-stu-id="70a90-148">You may also want to establish a control or base variation by leaving one of the variations unchanged.</span></span>
1. <span data-ttu-id="70a90-149">Seleccione el módulo en el que se va a experimentar, seleccione los puntos suspensivos (...) y luego seleccione **Agregar al experimento**.</span><span class="sxs-lookup"><span data-stu-id="70a90-149">Select the module to be experimented on, select the ellipsis (...), and then select **Add to experiment**.</span></span>

### <a name="edit-variations-for-experiments-with-entire-scope"></a><span data-ttu-id="70a90-150">Editar variaciones para experimentos con alcance total</span><span class="sxs-lookup"><span data-stu-id="70a90-150">Edit variations for experiments with entire scope</span></span>
<span data-ttu-id="70a90-151">Si definió el alcance de su experimento como **total** en el asistente **Conectar experimento**, mientras está en la vista de editor, use el menú desplegable de variaciones debajo de la barra de comandos para editar cada variación en función de su hipótesis original.</span><span class="sxs-lookup"><span data-stu-id="70a90-151">If you defined the scope of your experiment as **entire** in the **Connect experiment** wizard, while in editor view, use the variations drop-down menu below the command bar to edit each variation based on your original hypothesis.</span></span> 

> [!NOTE]
> <span data-ttu-id="70a90-152">En cualquier caso, también es posible que desee establecer una variación de control o base dejando una de las variaciones sin cambios.</span><span class="sxs-lookup"><span data-stu-id="70a90-152">In either case, you may also want to establish a control or base variation by leaving one of the variations unchanged.</span></span>

## <a name="previous-step"></a><span data-ttu-id="70a90-153">Paso anterior</span><span class="sxs-lookup"><span data-stu-id="70a90-153">Previous step</span></span>
[<span data-ttu-id="70a90-154">Configurar un experimento</span><span class="sxs-lookup"><span data-stu-id="70a90-154">Set up an experiment</span></span>](experimentation-setup.md) 


## <a name="next-step"></a><span data-ttu-id="70a90-155">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="70a90-155">Next step</span></span>
[<span data-ttu-id="70a90-156">Obtener una vista previa y publicar un experimento</span><span class="sxs-lookup"><span data-stu-id="70a90-156">Preview and publish an experiment</span></span>](experimentation-preview-publish.md)
