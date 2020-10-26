---
title: Configurar un experimento
description: Este tema describe cómo configurar un experimento en un servicio de terceros.
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
ms.openlocfilehash: 0f7db0ce009f6ee7603952891aacfdc16fcde016
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930284"
---
# <a name="set-up-an-experiment"></a><span data-ttu-id="eb1b9-103">Configurar un experimento</span><span class="sxs-lookup"><span data-stu-id="eb1b9-103">Set up an experiment</span></span>

<span data-ttu-id="eb1b9-104">Después [definir una hipótesis y determinar qué métricas de éxito desea utilizar](experimentation-identify.md), deberá configurar su experimento en el servicio de terceros.</span><span class="sxs-lookup"><span data-stu-id="eb1b9-104">After you [define a hypothesis and determine what success metrics you want to use](experimentation-identify.md), you'll need to set up your experiment in the third-party service.</span></span> <span data-ttu-id="eb1b9-105">El siguiente diagrama muestra todos los pasos necesarios para configurar y ejecutar un experimento en un sitio web de comercio electrónico en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="eb1b9-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="eb1b9-106">Los pasos adicionales se tratan en temas separados.</span><span class="sxs-lookup"><span data-stu-id="eb1b9-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="eb1b9-107">[ ![Recorrido del usuario de experimentación: configurar](./media/experimentation_setup.svg) ](./media/experimentation_setup.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="eb1b9-107">[ ![Experimentation user journey - Setup](./media/experimentation_setup.svg) ](./media/experimentation_setup.svg#lightbox)</span></span>


## <a name="set-up-your-experiment-in-the-third-party-service"></a><span data-ttu-id="eb1b9-108">Configure su experimento en el servicio de terceros</span><span class="sxs-lookup"><span data-stu-id="eb1b9-108">Set up your experiment in the third-party service</span></span>
<span data-ttu-id="eb1b9-109">A esta altura, debería haber elegido su servicio de terceros para ejecutar y supervisar su experimento, y configurar el conector de experimentación.</span><span class="sxs-lookup"><span data-stu-id="eb1b9-109">By now you should have chosen your third-party service to run and monitor your experiment, and set up the experimentation connector.</span></span> <span data-ttu-id="eb1b9-110">Estos requisitos previos se enumeran en [Experimentación en Dynamics 365 Commerce](experimentation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="eb1b9-110">These prerequisites are listed in  [Experimentation in Dynamics 365 Commerce](experimentation-overview.md).</span></span>

<span data-ttu-id="eb1b9-111">Siga los pasos necesarios para crear su experimento en el servicio de terceros.</span><span class="sxs-lookup"><span data-stu-id="eb1b9-111">Follow the steps required to create your experiment in the third-party service.</span></span> <span data-ttu-id="eb1b9-112">Si el conector está configurado correctamente, la lista completa de experimentos que configuró en el servicio de terceros aparecerá en el creador del sitio en aproximadamente 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="eb1b9-112">If the connector is configured properly, the complete list of experiments you set up in the third-party service will surface in site builder within about 5 minutes.</span></span>

## <a name="set-up-your-success-metrics"></a><span data-ttu-id="eb1b9-113">Configure sus métricas de éxito</span><span class="sxs-lookup"><span data-stu-id="eb1b9-113">Set up your success metrics</span></span>
<span data-ttu-id="eb1b9-114">Todo experimento necesita métricas para medir el impacto de las variaciones y validar la hipótesis.</span><span class="sxs-lookup"><span data-stu-id="eb1b9-114">Every experiment needs metrics to measure the impact of the variations and to validate the hypothesis.</span></span> <span data-ttu-id="eb1b9-115">Siga los pasos a continuación para habilitar el cálculo de métricas en el servicio de terceros utilizando eventos de telemetría en vivo de Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="eb1b9-115">Follow the steps below to enable the computation of metrics in the third-party service using live telemetry events from Dynamics 365 Commerce.</span></span>

1. <span data-ttu-id="eb1b9-116">En el creador de sitios, seleccione la pestaña **Páginas** en el panel de navegación izquierdo y luego seleccione la página en la que desea recopilar métricas.</span><span class="sxs-lookup"><span data-stu-id="eb1b9-116">In site builder, select the **Pages** tab in the left navigation pane and then select the page that you want to collect metrics on.</span></span> 
1. <span data-ttu-id="eb1b9-117">Vaya a la sección **ID de eventos para rastrear** en el panel de propiedades derecho de la página o módulo que desea rastrear.</span><span class="sxs-lookup"><span data-stu-id="eb1b9-117">Go to the **Event IDs to track** section in the right property pane of the page or module you want to track.</span></span>
1. <span data-ttu-id="eb1b9-118">Seleccione **Ver**.</span><span class="sxs-lookup"><span data-stu-id="eb1b9-118">Select **View**.</span></span> <span data-ttu-id="eb1b9-119">Se muestra una lista de todos los ID de eventos.</span><span class="sxs-lookup"><span data-stu-id="eb1b9-119">A list of all event IDs is displayed.</span></span> <span data-ttu-id="eb1b9-120">Copie el evento que desea rastrear y pegue la clave del evento en la ubicación designada en el servicio de terceros.</span><span class="sxs-lookup"><span data-stu-id="eb1b9-120">Copy the event you want to track, and paste the event key into the designated location in the third-party service.</span></span> <span data-ttu-id="eb1b9-121">Si necesita más de un evento, copie las claves una por una.</span><span class="sxs-lookup"><span data-stu-id="eb1b9-121">If you need more than one event, copy the keys one at a time.</span></span> 
    - <span data-ttu-id="eb1b9-122">Para saber cómo ver todos los eventos y atributos disponibles, incluidas las visitas a la página y el seguimiento de ingresos, consulte [Eventos de componentes comerciales para diagnóstico y resolución de problemas](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="eb1b9-122">To learn how to view all of the available events and attributes, including page views and revenue tracking, see [Commerce component events for diagnostics and troubleshooting](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).</span></span>
1. <span data-ttu-id="eb1b9-123">Tome cualquier otro paso para realizar un seguimiento de las métricas según lo requiera el servicio de terceros.</span><span class="sxs-lookup"><span data-stu-id="eb1b9-123">Take any other steps for tracking metrics as required in the third-party service.</span></span>

## <a name="previous-step"></a><span data-ttu-id="eb1b9-124">Paso anterior</span><span class="sxs-lookup"><span data-stu-id="eb1b9-124">Previous step</span></span>
[<span data-ttu-id="eb1b9-125">Identificar una hipótesis y determinar métricas para un experimento</span><span class="sxs-lookup"><span data-stu-id="eb1b9-125">Identify a hypothesis and determine metrics for an experiment</span></span>](experimentation-identify.md) 


## <a name="next-step"></a><span data-ttu-id="eb1b9-126">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="eb1b9-126">Next step</span></span>
[<span data-ttu-id="eb1b9-127">Conectar y editar un experimento</span><span class="sxs-lookup"><span data-stu-id="eb1b9-127">Connect and edit an experiment</span></span>](experimentation-connect-edit.md)
