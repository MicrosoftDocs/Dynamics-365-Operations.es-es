--- 
title: Configurar y ejecutar un trabajo para registrar extractos
description: "Este procedimiento le muestra la configuración y ejecución de un trabajo por lotes periódico para registrar extractos para una tienda seleccionada o un grupo de tiendas."
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9b080ff46a0fbc73ed4f8fa3f03d71e9d758cc2
ms.openlocfilehash: e3523de23d36f7f5e46850b40a85b25019e6bfa9
ms.contentlocale: es-es
ms.lasthandoff: 01/18/2018

---
# <a name="configure-and-run-a-job-to-post-statements"></a><span data-ttu-id="973bf-103">Configurar y ejecutar un trabajo para registrar extractos</span><span class="sxs-lookup"><span data-stu-id="973bf-103">Configure and run a job to post statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="973bf-104">Este procedimiento le muestra la configuración y ejecución de un trabajo por lotes periódico para registrar extractos para una tienda seleccionada o un grupo de tiendas.</span><span class="sxs-lookup"><span data-stu-id="973bf-104">This procedure walks through configuring and running a recurrent batch job to post statements for a selected store or group of stores.</span></span> <span data-ttu-id="973bf-105">Este procedimiento usa la empresa USRT en los datos de demostración.</span><span class="sxs-lookup"><span data-stu-id="973bf-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="973bf-106">Vaya a Todos los espacios de trabajo > ..</span><span class="sxs-lookup"><span data-stu-id="973bf-106">Go to All workspaces > ..</span></span> <span data-ttu-id="973bf-107">> Operaciones financieras de tienda.</span><span class="sxs-lookup"><span data-stu-id="973bf-107">> Retail store financials.</span></span>
2. <span data-ttu-id="973bf-108">Haga clic en Registrar extractos.</span><span class="sxs-lookup"><span data-stu-id="973bf-108">Click Post statements.</span></span>
    * <span data-ttu-id="973bf-109">Seleccione una jerarquía organizativa y en el árbol de nodos de la organización, seleccione un nodo o una tienda individual.</span><span class="sxs-lookup"><span data-stu-id="973bf-109">Select an organizational hierarchy and then in the organization nodes tree, select either an individual store or a node.</span></span> <span data-ttu-id="973bf-110">Seleccione un nodo si desea crear el trabajo por lotes para un grupo de tiendas.</span><span class="sxs-lookup"><span data-stu-id="973bf-110">Select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="973bf-111">Haga clic en la flecha para agregar su selección.</span><span class="sxs-lookup"><span data-stu-id="973bf-111">Click the arrow to add your selection.</span></span>  
3. <span data-ttu-id="973bf-112">Haga clic en la ficha Ejecutar en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="973bf-112">Click the Run in the background tab.</span></span>
4. <span data-ttu-id="973bf-113">Active o desactive la casilla Procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="973bf-113">Check or uncheck the Batch processing checkbox.</span></span>
5. <span data-ttu-id="973bf-114">Haga clic en Periodicidad.</span><span class="sxs-lookup"><span data-stu-id="973bf-114">Click Recurrence.</span></span>
6. <span data-ttu-id="973bf-115">En el campo Fecha inicial, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="973bf-115">In the Start date field, enter a date.</span></span>
7. <span data-ttu-id="973bf-116">Especifique una hora en el campo Hora inicial.</span><span class="sxs-lookup"><span data-stu-id="973bf-116">In the Start time field, enter a time.</span></span>
    * <span data-ttu-id="973bf-117">Seleccione si desea finalizar la periodicidad después de un número específico de ejecuciones, en una fecha concreta, o nunca.</span><span class="sxs-lookup"><span data-stu-id="973bf-117">Choose whether you want to end the recurrence after a specific number of runs, at a specific date, or never.</span></span> <span data-ttu-id="973bf-118">A continuación, elija las diversas opciones para definir la frecuencia con la que desea ejecutar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="973bf-118">Then choose the various options to define how frequently you want the job to run.</span></span>  
8. <span data-ttu-id="973bf-119">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="973bf-119">Click OK.</span></span>
9. <span data-ttu-id="973bf-120">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="973bf-120">Click OK.</span></span>


