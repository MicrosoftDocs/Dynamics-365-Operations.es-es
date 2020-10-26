---
title: Promover una variación y completar un experimento
description: Este tema describe cómo promover una variación exitosa y completar un experimento en Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 09/15/2020
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
ms.openlocfilehash: 2e011f10e908d6a2efe2e928fc5e0abc7659cb8b
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930280"
---
# <a name="promote-a-variation-and-complete-an-experiment"></a><span data-ttu-id="9e507-103">Promover una variación y completar un experimento</span><span class="sxs-lookup"><span data-stu-id="9e507-103">Promote a variation and complete an experiment</span></span>

<span data-ttu-id="9e507-104">Este tema describe cómo promover la variación que produjo los mejores resultados en su experimento y cómo completar el experimento.</span><span class="sxs-lookup"><span data-stu-id="9e507-104">This topic describes how to promote the variation that produced the best results in your experiment, and how to complete the experiment.</span></span> <span data-ttu-id="9e507-105">El siguiente diagrama muestra todos los pasos necesarios para configurar y ejecutar un experimento en un sitio web de comercio electrónico en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9e507-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="9e507-106">Los pasos adicionales se tratan en temas separados.</span><span class="sxs-lookup"><span data-stu-id="9e507-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="9e507-107">[ ![Recorrido del usuario de experimentación: revisar y completar](./media/experimentation_review_complete.svg) ](./media/experimentation_review_complete.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="9e507-107">[ ![Experimentation user journey - Review & Complete](./media/experimentation_review_complete.svg) ](./media/experimentation_review_complete.svg#lightbox)</span></span>

<span data-ttu-id="9e507-108">Después de que haya [ejecutado su experimento](experimentation-run-monitor.md) y recopilado datos suficientes para determinar qué variación desea utilizar en su sitio en vivo, promoverá la variación y finalizará el experimento.</span><span class="sxs-lookup"><span data-stu-id="9e507-108">After you've [run your experiment](experimentation-run-monitor.md) and collected sufficient data to determine which variation you want to use on your live site, you'll promote the variation and end the experiment.</span></span>

## <a name="promote-a-variation"></a><span data-ttu-id="9e507-109">Promocionar una variación</span><span class="sxs-lookup"><span data-stu-id="9e507-109">Promote a variation</span></span>
<span data-ttu-id="9e507-110">Utilice los datos y análisis relacionados con el experimento en el servicio de terceros para decidir qué variación produjo los mejores resultados.</span><span class="sxs-lookup"><span data-stu-id="9e507-110">Use the data and analytics related to the experiment in the third-party service to decide which variation produced the best results.</span></span> <span data-ttu-id="9e507-111">Para reemplazar el contenido actual en el sitio en vivo con la variación ganadora para que esté disponible para todos los usuarios de su sitio web, haga lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="9e507-111">To replace the current content on the live site with the winning variation so that it's available to all users of your website, do the following.</span></span> 

1. <span data-ttu-id="9e507-112">Vaya a la pestaña **Experimentos** en el Creador de sitios y seleccione el experimento.</span><span class="sxs-lookup"><span data-stu-id="9e507-112">Go to the **Experiments** tab in site builder and select the experiment.</span></span>
1. <span data-ttu-id="9e507-113">Seleccione **Experimento completo** en la barra superior.</span><span class="sxs-lookup"><span data-stu-id="9e507-113">Select **Complete experiment** on the top bar.</span></span>
1. <span data-ttu-id="9e507-114">En el menú del cuadro de diálogo **Completar el experimento**, seleccione **Revisar los datos del experimento**.</span><span class="sxs-lookup"><span data-stu-id="9e507-114">In the **Complete the experiment** dialog menu, select **Review the experiment data**.</span></span> <span data-ttu-id="9e507-115">Se abre el servicio de terceros donde puede validar las métricas y determinar qué variación se desempeñó mejor.</span><span class="sxs-lookup"><span data-stu-id="9e507-115">The third-party service opens where you can validate the metrics and determine which variation performed the best.</span></span>
1. <span data-ttu-id="9e507-116">En el menú del cuadro de diálogo **Completar el experimento** en el creador de sitios, seleccione la variación ganadora y luego seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9e507-116">In the **Complete the experiment** dialog menu in site builder, select the winning variation and then select **Next**.</span></span>
1. <span data-ttu-id="9e507-117">Abra el servicio de terceros y detenga el experimento.</span><span class="sxs-lookup"><span data-stu-id="9e507-117">Open the third-party service and stop the experiment.</span></span>
1. <span data-ttu-id="9e507-118">En el creador de sitios, seleccione **Completar** para sobrescribir la página en vivo original y publicar la variación ganadora para que esté disponible para todos los usuarios de su sitio web.</span><span class="sxs-lookup"><span data-stu-id="9e507-118">In site builder, select **Complete** to overwrite the original live page and publish the winning variation so that it's available to all users of your website.</span></span> 

> [!NOTE]
> <span data-ttu-id="9e507-119">Si elige mantener la página activa actual y no publicar una variación, seleccione **Volver a publicar la página original**.</span><span class="sxs-lookup"><span data-stu-id="9e507-119">If you choose to keep the current live page and not publish a variation, select **Republish the original page**.</span></span>

## <a name="delete-your-experiment"></a><span data-ttu-id="9e507-120">Eliminar el experimento</span><span class="sxs-lookup"><span data-stu-id="9e507-120">Delete your experiment</span></span>
<span data-ttu-id="9e507-121">Si bien no es necesario que elimine un experimento completado en Commerce, puede optar por eliminarlo para ahorrar espacio o limpiar su espacio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9e507-121">While it's not required that you delete a completed experiment in Commerce, you may choose to delete it to save space or clean up your workspace.</span></span> <span data-ttu-id="9e507-122">Para eliminar un experimento, haga lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="9e507-122">To delete an experiment, do the following.</span></span>

1. <span data-ttu-id="9e507-123">Vaya a la pestaña **Experimentos** en el Creador de sitios y seleccione el experimento.</span><span class="sxs-lookup"><span data-stu-id="9e507-123">Go to the **Experiments** tab in site builder and select the experiment.</span></span> 
    > [!NOTE]
    > <span data-ttu-id="9e507-124">Si el experimento aún está activo, detenga el experimento en el servicio de terceros antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="9e507-124">If the experiment is still active, stop the experiment in the third-party service before proceeding.</span></span>
1. <span data-ttu-id="9e507-125">Seleccione **Anular publicación** en la barra de comandos para eliminar el contenido de la variación del sitio en vivo.</span><span class="sxs-lookup"><span data-stu-id="9e507-125">Select **Unpublish** in the command bar to remove the variation content from the live site.</span></span>
1. <span data-ttu-id="9e507-126">Seleccione **Eliminar** en la barra de comandos para eliminar el experimento.</span><span class="sxs-lookup"><span data-stu-id="9e507-126">Select **Delete** in the command bar to delete the experiment.</span></span>

## <a name="previous-step"></a><span data-ttu-id="9e507-127">Paso anterior</span><span class="sxs-lookup"><span data-stu-id="9e507-127">Previous step</span></span>
[<span data-ttu-id="9e507-128">Ejecutar y supervisar un experimento</span><span class="sxs-lookup"><span data-stu-id="9e507-128">Run and monitor an experiment</span></span>](experimentation-run-monitor.md)
