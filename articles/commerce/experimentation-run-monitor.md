---
title: Ejecutar y supervisar un experimento
description: Este tema describe cómo ejecutar y supervisar un experimento en un servicio de terceros. También describe cómo realizar cambios en las variaciones después de que comenzó el experimento.
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
ms.openlocfilehash: 4cb7d863d9d69612aa0c340099c1f7861c9d12ba
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930283"
---
# <a name="run-and-monitor-an-experiment"></a><span data-ttu-id="9ea59-104">Ejecutar y supervisar un experimento</span><span class="sxs-lookup"><span data-stu-id="9ea59-104">Run and monitor an experiment</span></span>

<span data-ttu-id="9ea59-105">Este tema describe cómo ejecutar y supervisar su experimento en una aplicación de terceros y cómo cambiar las variaciones si es necesario.</span><span class="sxs-lookup"><span data-stu-id="9ea59-105">This topic describes how to run and monitor your experiment in a third-party app, and change variations if needed.</span></span> <span data-ttu-id="9ea59-106">Antes de completar los pasos de este tema, deberá [publicar](experimentation-preview-publish.md) su experimento en Commerce.</span><span class="sxs-lookup"><span data-stu-id="9ea59-106">Before you complete the steps in this topic, you'll need to [publish](experimentation-preview-publish.md) your experiment in Commerce.</span></span> <span data-ttu-id="9ea59-107">El siguiente diagrama muestra todos los pasos necesarios para configurar y ejecutar un experimento en un sitio web de comercio electrónico en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9ea59-107">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="9ea59-108">Los pasos adicionales se tratan en temas separados.</span><span class="sxs-lookup"><span data-stu-id="9ea59-108">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="9ea59-109">[ ![Recorrido del usuario de experimentación: ejecutar y supervisar](./media/experimentation_run_monitor.svg) ](./media/experimentation_run_monitor.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="9ea59-109">[ ![Experimentation user journey - Run & Monitor](./media/experimentation_run_monitor.svg) ](./media/experimentation_run_monitor.svg#lightbox)</span></span>

<span data-ttu-id="9ea59-110">Después de publicar sus variaciones, se completan todos los pasos que debe seguir en Commerce para ejecutar su experimento.</span><span class="sxs-lookup"><span data-stu-id="9ea59-110">After you publish your variations, all the steps you need to do in Commerce to run your experiment are done.</span></span> <span data-ttu-id="9ea59-111">El siguiente paso es determinar qué variación mostrar a cada usuario cuando solicita una página.</span><span class="sxs-lookup"><span data-stu-id="9ea59-111">The next step is determining which variation to show to each user when they request a page.</span></span> <span data-ttu-id="9ea59-112">El servicio de terceros toma esa determinación, pero primero debe activar el experimento dentro del servicio.</span><span class="sxs-lookup"><span data-stu-id="9ea59-112">The third-party service makes that determination, but first you have to activate the experiment within the service.</span></span> <span data-ttu-id="9ea59-113">Dado que los pasos para activar un experimento varían de un servicio a otro, deberá seguir las instrucciones incluidas con su servicio o proveedor.</span><span class="sxs-lookup"><span data-stu-id="9ea59-113">Since the steps for activating an experiment vary from service to service, you'll need to follow the instructions included with your service or provider.</span></span> <span data-ttu-id="9ea59-114">Si el experimento no está activado, los usuarios solo verán la versión predeterminada de la página; no se mostrarán variaciones.</span><span class="sxs-lookup"><span data-stu-id="9ea59-114">If the experiment is not activated, users will only see the default version of the page - no variations will be displayed.</span></span>

<span data-ttu-id="9ea59-115">Deberá mantener el experimento en ejecución el tiempo suficiente para recopilar datos y obtener resultados estadísticamente válidos.</span><span class="sxs-lookup"><span data-stu-id="9ea59-115">You'll need to keep the experiment running long enough to gather data for statistically valid results.</span></span> <span data-ttu-id="9ea59-116">Utilice el servicio de terceros para supervisar los datos y análisis relacionados con el experimento mientras se ejecuta el experimento.</span><span class="sxs-lookup"><span data-stu-id="9ea59-116">Use the third-party service to monitor the experiment-related data and analytics while the experiment is running.</span></span>

## <a name="adjust-your-variations"></a><span data-ttu-id="9ea59-117">Ajustar sus variaciones</span><span class="sxs-lookup"><span data-stu-id="9ea59-117">Adjust your variations</span></span>
<span data-ttu-id="9ea59-118">Si por alguna razón necesita modificar sus variaciones, siga los pasos a continuación.</span><span class="sxs-lookup"><span data-stu-id="9ea59-118">If for any reason you need to modify your variations, follow the steps below.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9ea59-119">Si realiza cambios en un experimento en vivo en Commerce o en el servicio de terceros, sus resultados pueden verse afectados significativamente.</span><span class="sxs-lookup"><span data-stu-id="9ea59-119">If you make changes to a live experiment in Commerce or the third-party service, your results may be significantly impacted.</span></span> <span data-ttu-id="9ea59-120">Considere dejar que el experimento siga su curso y luego crear un nuevo experimento para cambios importantes.</span><span class="sxs-lookup"><span data-stu-id="9ea59-120">Consider letting the experiment run its course and then creating a new experiment for major changes.</span></span>

1. <span data-ttu-id="9ea59-121">Vaya a la pestaña **Experimentos** en el Creador de sitios y seleccione el experimento.</span><span class="sxs-lookup"><span data-stu-id="9ea59-121">Go to the **Experiments** tab in site builder and select the experiment.</span></span> 
1. <span data-ttu-id="9ea59-122">Seleccione la variación que desea actualizar en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="9ea59-122">Select the variation you want to update from the drop-down menu.</span></span>
1. <span data-ttu-id="9ea59-123">Realice los cambios necesarios, luego obtenga una vista previa y publique las variaciones.</span><span class="sxs-lookup"><span data-stu-id="9ea59-123">Make needed changes, then preview and publish the variations.</span></span> <span data-ttu-id="9ea59-124">Para más información, vea [Obtener la vista previa y publicar un experimento](experimentation-preview-publish.md).</span><span class="sxs-lookup"><span data-stu-id="9ea59-124">For more information, see [Preview and publish an experiment](experimentation-preview-publish.md).</span></span>
1. <span data-ttu-id="9ea59-125">Vaya al servicio de terceros para realizar cambios relacionados con la configuración del experimento.</span><span class="sxs-lookup"><span data-stu-id="9ea59-125">Go to the third-party service to make any experiment setup-related changes.</span></span>
    
## <a name="previous-step"></a><span data-ttu-id="9ea59-126">Paso anterior</span><span class="sxs-lookup"><span data-stu-id="9ea59-126">Previous step</span></span>
[<span data-ttu-id="9ea59-127">Obtener una vista previa y publicar un experimento</span><span class="sxs-lookup"><span data-stu-id="9ea59-127">Preview and publish an experiment</span></span>](experimentation-preview-publish.md)

## <a name="next-step"></a><span data-ttu-id="9ea59-128">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="9ea59-128">Next step</span></span>
[<span data-ttu-id="9ea59-129">Promover una variación y completar un experimento</span><span class="sxs-lookup"><span data-stu-id="9ea59-129">Promote a variation and complete an experiment</span></span>](experimentation-review-complete.md)