---
title: Promover una variación y completar un experimento
description: Este tema describe cómo promover una variación exitosa y completar un experimento en Dynamics 365 Commerce.
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
ms.openlocfilehash: fe07dc01aa62342275d3fa0a5980ecd5cfca3efc
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5238567"
---
# <a name="promote-a-variation-and-complete-an-experiment"></a><span data-ttu-id="65cad-103">Promover una variación y completar un experimento</span><span class="sxs-lookup"><span data-stu-id="65cad-103">Promote a variation and complete an experiment</span></span>

<span data-ttu-id="65cad-104">Este tema describe cómo promover la variación que produjo los mejores resultados en su experimento y cómo completar el experimento.</span><span class="sxs-lookup"><span data-stu-id="65cad-104">This topic describes how to promote the variation that produced the best results in your experiment, and how to complete the experiment.</span></span> <span data-ttu-id="65cad-105">El siguiente diagrama muestra todos los pasos necesarios para configurar y ejecutar un experimento en un sitio web de comercio electrónico en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="65cad-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="65cad-106">Los pasos adicionales se tratan en temas separados.</span><span class="sxs-lookup"><span data-stu-id="65cad-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="65cad-107">[ ![Recorrido del usuario de experimentación: revisar y completar](./media/experimentation_review_complete.svg) ](./media/experimentation_review_complete.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="65cad-107">[ ![Experimentation user journey - Review & Complete](./media/experimentation_review_complete.svg) ](./media/experimentation_review_complete.svg#lightbox)</span></span>

<span data-ttu-id="65cad-108">Después de que haya [ejecutado su experimento](experimentation-run-monitor.md) y recopilado datos suficientes para determinar qué variación desea utilizar en su sitio en vivo, promoverá la variación y finalizará el experimento.</span><span class="sxs-lookup"><span data-stu-id="65cad-108">After you've [run your experiment](experimentation-run-monitor.md) and collected sufficient data to determine which variation you want to use on your live site, you'll promote the variation and end the experiment.</span></span>

## <a name="promote-a-variation"></a><span data-ttu-id="65cad-109">Promocionar una variación</span><span class="sxs-lookup"><span data-stu-id="65cad-109">Promote a variation</span></span>
<span data-ttu-id="65cad-110">Utilice los datos y análisis relacionados con el experimento en el servicio de terceros para decidir qué variación produjo los mejores resultados.</span><span class="sxs-lookup"><span data-stu-id="65cad-110">Use the data and analytics related to the experiment in the third-party service to decide which variation produced the best results.</span></span> <span data-ttu-id="65cad-111">Puede promocionarlo reemplazando el contenido actual en el sitio en vivo con la variación ganadora para que esté disponible para todos los usuarios de su sitio web.</span><span class="sxs-lookup"><span data-stu-id="65cad-111">You can then promote it by replacing the current content on the live site with the winning variation so that it's available to all users of your website.</span></span>

<span data-ttu-id="65cad-112">Para promocionar la variación ganadora, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="65cad-112">To promote the winning variation, follow these steps.</span></span> 

1. <span data-ttu-id="65cad-113">En el generador de sitios de Commerce, vaya a la pestaña **Experimentos** del panel de navegación izquierdo y seleccione el experimento.</span><span class="sxs-lookup"><span data-stu-id="65cad-113">In Commerce site builder, select **Experiments** in the left navigation pane, and then select the experiment.</span></span>
1. <span data-ttu-id="65cad-114">En la barra de comandos, seleccione **Experimento completo**.</span><span class="sxs-lookup"><span data-stu-id="65cad-114">On the command bar, select **Complete experiment**.</span></span>
1. <span data-ttu-id="65cad-115">En el cuadro de diálogo **Completar el experimento**, seleccione **Revisar los datos del experimento**.</span><span class="sxs-lookup"><span data-stu-id="65cad-115">In the **Complete the experiment** dialog box, select **Review the experiment data**.</span></span> <span data-ttu-id="65cad-116">Se abre el servicio de terceros donde puede validar las métricas y determinar qué variación se desempeñó mejor.</span><span class="sxs-lookup"><span data-stu-id="65cad-116">The third-party service opens where you can validate the metrics and determine which variation performed the best.</span></span>
1. <span data-ttu-id="65cad-117">En el menú del cuadro de diálogo **Completar el experimento**, seleccione la variación ganadora y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="65cad-117">In the **Complete the experiment** dialog box, select the winning variation, and then select **Next**.</span></span>
1. <span data-ttu-id="65cad-118">Abra el servicio de terceros y detenga el experimento.</span><span class="sxs-lookup"><span data-stu-id="65cad-118">Open the third-party service and stop the experiment.</span></span>
1. <span data-ttu-id="65cad-119">En el creador de sitios, seleccione **Completar** para sobrescribir la página en vivo original y publicar la variación ganadora para que esté disponible para todos los usuarios de su sitio web.</span><span class="sxs-lookup"><span data-stu-id="65cad-119">In site builder, select **Complete** to overwrite the original live page and publish the winning variation so that it's available to all users of your website.</span></span> 

> [!NOTE]
> <span data-ttu-id="65cad-120">Si elige mantener la página activa actual y no publicar una variación, seleccione **Volver a publicar la página original**.</span><span class="sxs-lookup"><span data-stu-id="65cad-120">If you choose to keep the current live page and not publish a variation, select **Republish the original page**.</span></span>

## <a name="delete-your-experiment"></a><span data-ttu-id="65cad-121">Eliminar el experimento</span><span class="sxs-lookup"><span data-stu-id="65cad-121">Delete your experiment</span></span>
<span data-ttu-id="65cad-122">Si bien no es necesario que elimine un experimento completado en Commerce, puede optar por eliminarlo para ahorrar espacio o limpiar su espacio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="65cad-122">While it's not required that you delete a completed experiment in Commerce, you may choose to delete it to save space or clean up your workspace.</span></span> 

<span data-ttu-id="65cad-123">Para eliminar un experimento en el generador de sitios de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="65cad-123">To delete an experiment in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="65cad-124">Seleccione **Experimentos** en el panel de navegación izquierdo y seleccione el experimento.</span><span class="sxs-lookup"><span data-stu-id="65cad-124">Select **Experiments** in the left navigation pane, and then select the experiment.</span></span> 
    > [!NOTE]
    > <span data-ttu-id="65cad-125">Si el experimento aún está activo, detenga el experimento en el servicio de terceros antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="65cad-125">If the experiment is still active, stop the experiment in the third-party service before proceeding.</span></span>
1. <span data-ttu-id="65cad-126">En la barra de comandos, seleccione **Anular publicación** en la barra de comandos para eliminar el contenido de la variación del sitio en vivo.</span><span class="sxs-lookup"><span data-stu-id="65cad-126">On the command bar, select **Unpublish**  to remove the variation content from the live site.</span></span>
1. <span data-ttu-id="65cad-127">Seleccione **Eliminar** para eliminar el experimento.</span><span class="sxs-lookup"><span data-stu-id="65cad-127">Select **Delete** to delete the experiment.</span></span>

## <a name="previous-step"></a><span data-ttu-id="65cad-128">Paso anterior</span><span class="sxs-lookup"><span data-stu-id="65cad-128">Previous step</span></span>
[<span data-ttu-id="65cad-129">Ejecutar y supervisar un experimento</span><span class="sxs-lookup"><span data-stu-id="65cad-129">Run and monitor an experiment</span></span>](experimentation-run-monitor.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]