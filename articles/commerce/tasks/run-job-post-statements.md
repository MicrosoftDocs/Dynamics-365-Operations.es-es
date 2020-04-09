---
title: Configurar y ejecutar trabajo para registrar extractos
description: Este procedimiento le muestra la configuración y ejecución de un trabajo por lotes periódico para registrar extractos para una tienda seleccionada o un grupo de tiendas.
author: josaw1
manager: AnnBe
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f89203850b302b769b22920fa5c42d2b0b877684
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141186"
---
# <a name="configure-and-run-job-to-post-statements"></a><span data-ttu-id="2cd71-103">Configurar y ejecutar trabajo para registrar extractos</span><span class="sxs-lookup"><span data-stu-id="2cd71-103">Configure and run job to post statements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2cd71-104">Este procedimiento le muestra la configuración y ejecución de un trabajo por lotes periódico para registrar extractos para una tienda seleccionada o un grupo de tiendas.</span><span class="sxs-lookup"><span data-stu-id="2cd71-104">This procedure walks through configuring and running a recurrent batch job to post statements for a selected store or group of stores.</span></span> <span data-ttu-id="2cd71-105">Este procedimiento usa la empresa USRT en los datos de demostración.</span><span class="sxs-lookup"><span data-stu-id="2cd71-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="2cd71-106">Vaya a Todos los espacios de trabajo > ..</span><span class="sxs-lookup"><span data-stu-id="2cd71-106">Go to All workspaces > ..</span></span> <span data-ttu-id="2cd71-107">> Operaciones financieras de tiendas.</span><span class="sxs-lookup"><span data-stu-id="2cd71-107">> Store financials.</span></span>
2. <span data-ttu-id="2cd71-108">Haga clic en Registrar extractos por lotes.</span><span class="sxs-lookup"><span data-stu-id="2cd71-108">Click Post statements in batch.</span></span>
    * <span data-ttu-id="2cd71-109">Seleccione una jerarquía organizativa y en el árbol de nodos de la organización, seleccione un nodo o una tienda individual.</span><span class="sxs-lookup"><span data-stu-id="2cd71-109">Select an organizational hierarchy and then in the organization nodes tree, select either an individual store or a node.</span></span> <span data-ttu-id="2cd71-110">Seleccione un nodo si desea crear el trabajo por lotes para un grupo de tiendas.</span><span class="sxs-lookup"><span data-stu-id="2cd71-110">Select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="2cd71-111">Haga clic en la flecha para agregar su selección.</span><span class="sxs-lookup"><span data-stu-id="2cd71-111">Click the arrow to add your selection.</span></span>  
3. <span data-ttu-id="2cd71-112">Haga clic en la pestaña Ejecutar en segundo plano. ![Ejecutar en segundo planoEjecutar en segundo plano](../dev-itpro/media/runbackground.png "Ejecutar en segundo plano")</span><span class="sxs-lookup"><span data-stu-id="2cd71-112">Click the Run in the background tab. ![Run in the background](../dev-itpro/media/runbackground.png "Run in the background")</span></span> 
4. <span data-ttu-id="2cd71-113">Active o desactive la casilla Procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="2cd71-113">Check or uncheck the Batch processing checkbox.</span></span>
<span data-ttu-id="2cd71-114">![Procesamiento por lotes](../dev-itpro/media/batchprocessing.png "Procesamiento por lotes y periodicidad")</span><span class="sxs-lookup"><span data-stu-id="2cd71-114">![Batch Processing](../dev-itpro/media/batchprocessing.png "Batch Processing & Recurrance")</span></span> 
5. <span data-ttu-id="2cd71-115">Haga clic en Periodicidad.</span><span class="sxs-lookup"><span data-stu-id="2cd71-115">Click Recurrence.</span></span>
6. <span data-ttu-id="2cd71-116">En el campo Fecha inicial, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="2cd71-116">In the Start date field, enter a date.</span></span>
7. <span data-ttu-id="2cd71-117">Especifique una hora en el campo Hora inicial.</span><span class="sxs-lookup"><span data-stu-id="2cd71-117">In the Start time field, enter a time.</span></span>
    * <span data-ttu-id="2cd71-118">Seleccione si desea finalizar la periodicidad después de un número específico de ejecuciones, en una fecha concreta, o nunca.</span><span class="sxs-lookup"><span data-stu-id="2cd71-118">Choose whether you want to end the recurrence after a specific number of runs, at a specific date, or never.</span></span> <span data-ttu-id="2cd71-119">A continuación, elija las diversas opciones para definir la frecuencia con la que desea ejecutar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="2cd71-119">Then choose the various options to define how frequently you want the job to run.</span></span>  
8. <span data-ttu-id="2cd71-120">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="2cd71-120">Click OK.</span></span>
9. <span data-ttu-id="2cd71-121">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="2cd71-121">Click OK.</span></span>

