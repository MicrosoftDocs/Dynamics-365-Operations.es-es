--- 
title: Configurar y ejecutar un trabajo para calcular extractos
description: "Este procedimiento le muestra la configuración y ejecución de trabajos por lotes periódicos para crear y calcular extractos para una tienda seleccionada o un grupo de tiendas."
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 7bc936cdba771d322676565c2615ad75649cc50b
ms.contentlocale: es-es
ms.lasthandoff: 02/07/2018

---
# <a name="configure-and-run-a-job-to-calculate-statements"></a><span data-ttu-id="74283-103">Configurar y ejecutar un trabajo para calcular extractos</span><span class="sxs-lookup"><span data-stu-id="74283-103">Configure and run a job to calculate statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="74283-104">Este procedimiento le muestra la configuración y ejecución de trabajos por lotes periódicos para crear y calcular extractos para una tienda seleccionada o un grupo de tiendas.</span><span class="sxs-lookup"><span data-stu-id="74283-104">This procedure walks through configuring and running recurrent batch jobs to create and calculate statements for a selected store or group of stores.</span></span> <span data-ttu-id="74283-105">Este procedimiento usa la empresa USRT en los datos de demostración.</span><span class="sxs-lookup"><span data-stu-id="74283-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="74283-106">Vaya a Todos los espacios de trabajo > Operaciones financieras de tienda.</span><span class="sxs-lookup"><span data-stu-id="74283-106">Go to All workspaces > Retail store financials.</span></span>
2. <span data-ttu-id="74283-107">Haga clic en Calcular extractos.</span><span class="sxs-lookup"><span data-stu-id="74283-107">Click Calculate statements.</span></span>
    * <span data-ttu-id="74283-108">Seleccione una tienda concreta o un nodo si desea crear el trabajo por lotes para un grupo de tiendas.</span><span class="sxs-lookup"><span data-stu-id="74283-108">Select either a specific store, or a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="74283-109">Haga clic en la flecha para agregar su selección.</span><span class="sxs-lookup"><span data-stu-id="74283-109">Click the arrow to add your selection.</span></span>  
3. <span data-ttu-id="74283-110">Haga clic en la ficha Ejecutar en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="74283-110">Click the Run in the background tab.</span></span>
4. <span data-ttu-id="74283-111">Seleccione "Sí" en Procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="74283-111">Under Batch processing, select 'Yes'.</span></span>
5. <span data-ttu-id="74283-112">Haga clic en Periodicidad.</span><span class="sxs-lookup"><span data-stu-id="74283-112">Click Recurrence.</span></span>
6. <span data-ttu-id="74283-113">En el campo Fecha inicial, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="74283-113">In the Start date field, enter a date.</span></span>
7. <span data-ttu-id="74283-114">Especifique una hora en el campo Hora inicial.</span><span class="sxs-lookup"><span data-stu-id="74283-114">In the Start time field, enter a time.</span></span>
8. <span data-ttu-id="74283-115">Seleccione la opción No hay fecha final.</span><span class="sxs-lookup"><span data-stu-id="74283-115">Select the No end date option.</span></span>
9. <span data-ttu-id="74283-116">En el campo PatternUnit, especifique "Days".</span><span class="sxs-lookup"><span data-stu-id="74283-116">In the PatternUnit field, enter 'Days'.</span></span>
10. <span data-ttu-id="74283-117">En el campo Por, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="74283-117">In the Per field, enter a number.</span></span>
11. <span data-ttu-id="74283-118">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="74283-118">Click OK.</span></span>
12. <span data-ttu-id="74283-119">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="74283-119">Click OK.</span></span>


