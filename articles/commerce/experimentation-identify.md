---
title: Identificar una hipótesis y determinar métricas para un experimento
description: Este tema describe cómo identificar la hipótesis y las métricas de éxito para un experimento que ejecutará en un sitio web de comercio electrónico en Dynamics 365 Commerce.
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
ms.openlocfilehash: 5594b81d09eade263487244a14c0305d589ff94e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5010008"
---
# <a name="identify-a-hypothesis-and-determine-success-metrics-for-an-experiment"></a><span data-ttu-id="22226-103">Identificar una hipótesis y determinar métricas de éxito para un experimento</span><span class="sxs-lookup"><span data-stu-id="22226-103">Identify a hypothesis and determine success metrics for an experiment</span></span>
<span data-ttu-id="22226-104">La primera fase del ciclo de vida de la experimentación incluye identificar la hipótesis para el experimento y determinar las métricas que rastreará para evaluar el éxito.</span><span class="sxs-lookup"><span data-stu-id="22226-104">The first phase in the experimentation lifecycle includes identifying the hypothesis for the experiment and determining the metrics you'll track to evaluate success.</span></span> <span data-ttu-id="22226-105">El siguiente diagrama muestra todos los pasos necesarios para [configurar y ejecutar un experimento](experimentation-overview.md) en un sitio web de comercio electrónico en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="22226-105">The following diagram shows all of the steps involved in [setting up and running an experiment](experimentation-overview.md) on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="22226-106">Los pasos adicionales se tratan en temas separados.</span><span class="sxs-lookup"><span data-stu-id="22226-106">Additional steps are covered in separate topics.</span></span> 

<span data-ttu-id="22226-107">[ ![Recorrido del usuario de experimentación: identificar](./media/experimentation_identify.svg) ](./media/experimentation_identify.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="22226-107">[ ![Experimentation user journey - Identify](./media/experimentation_identify.svg) ](./media/experimentation_identify.svg#lightbox)</span></span>

<span data-ttu-id="22226-108">Una hipótesis es una declaración en la que predice el resultado del experimento.</span><span class="sxs-lookup"><span data-stu-id="22226-108">A hypothesis is a statement where you predict the outcome of the experiment.</span></span> <span data-ttu-id="22226-109">Muchos factores intervienen en la definición de una hipótesis, por ejemplo, la investigación sobre el comportamiento del usuario y los datos del sitio web que ha recopilado.</span><span class="sxs-lookup"><span data-stu-id="22226-109">Many factors go into defining a hypothesis, for example, research about user behavior and website data you've collected.</span></span> <span data-ttu-id="22226-110">Con la hipótesis, definirás la suposición o teoría que deseas validar con tu experimento.</span><span class="sxs-lookup"><span data-stu-id="22226-110">With the hypothesis, you'll define the assumption or theory you want to validate with your experiment.</span></span> <span data-ttu-id="22226-111">Un ejemplo de hipótesis para su experimento puede ser "*una imagen de una camiseta blanca en mi página de inicio generará una tasa de clics más alta que un suéter azul marino durante los meses de verano porque la gente quiere usar algo liviano y de colores claros en el verano*".</span><span class="sxs-lookup"><span data-stu-id="22226-111">An example of a hypothesis for your experiment may be "*a picture of a white t-shirt on my home page will drive a higher clickthrough rate than a navy sweater during summer months because people want to wear something lightweight and light colored in the summer.*"</span></span> <span data-ttu-id="22226-112">En ese caso, creará variaciones que incluyen una camiseta blanca y un suéter azul marino, y publicará ambos al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="22226-112">In that case, you'll create variations that include a white t-shirt and a navy sweater, and publish both at the same time.</span></span>

<span data-ttu-id="22226-113">Para validar una hipótesis, el éxito o el fracaso de un experimento debe estar directamente relacionado con las acciones del usuario; por ejemplo, si el usuario del sitio web hace clic en un vínculo o botón.</span><span class="sxs-lookup"><span data-stu-id="22226-113">To validate a hypothesis, the success or failure of an experiment should be directly tied to user actions; for example, if the website user clicks on a link or button.</span></span> <span data-ttu-id="22226-114">Estas acciones deben corresponder con eventos que se informarán al servicio de terceros que realiza el seguimiento del experimento.</span><span class="sxs-lookup"><span data-stu-id="22226-114">These actions must correspond with events that will be reported to the third-party service tracking the experiment.</span></span> <span data-ttu-id="22226-115">Con el tiempo, el porcentaje de usuarios que realizan la acción se contabilizará como una métrica que puede utilizar para generar informes y realizar análisis.</span><span class="sxs-lookup"><span data-stu-id="22226-115">Over time, the percentage of users that take the action will be tallied as a metric you can use to generate reports and conduct analyses.</span></span> <span data-ttu-id="22226-116">Para revisar todos los eventos y atributos disponibles, consulte [Diagnóstico y solución de problemas de eventos de componentes de Commerce](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="22226-116">To review all of the available events and attributes, see [Commerce component events for diagnostics and troubleshooting](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).</span></span>

## <a name="previous-step"></a><span data-ttu-id="22226-117">Paso anterior</span><span class="sxs-lookup"><span data-stu-id="22226-117">Previous step</span></span>
[<span data-ttu-id="22226-118">Experimentación en Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="22226-118">Experimentation in Dynamics 365 Commerce</span></span>](experimentation-overview.md)


## <a name="next-step"></a><span data-ttu-id="22226-119">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="22226-119">Next step</span></span>
[<span data-ttu-id="22226-120">Configurar un experimento</span><span class="sxs-lookup"><span data-stu-id="22226-120">Set up an experiment</span></span>](experimentation-setup.md)
