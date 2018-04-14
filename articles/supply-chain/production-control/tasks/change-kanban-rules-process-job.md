--- 
title: Cambiar las reglas kanban para un trabajo de proceso
description: Este procedimiento se centra en el cambio de la regla kanban usada para un kanban dado.
author: ChristianRytt
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 55498a68b3f03ed8c360b479c6dcbd607a186e13
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---
# <a name="change-kanban-rules-for-a-process-job"></a><span data-ttu-id="3e27a-103">Cambiar las reglas kanban para un trabajo de proceso</span><span class="sxs-lookup"><span data-stu-id="3e27a-103">Change kanban rules for a process job</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3e27a-104">Este procedimiento se centra en el cambio de la regla kanban usada para un kanban dado.</span><span class="sxs-lookup"><span data-stu-id="3e27a-104">This procedure focuses on changing the used kanban rule for a given kanban.</span></span> <span data-ttu-id="3e27a-105">Esto resulta útil para nivelar recursos de carga o en caso de desglose.</span><span class="sxs-lookup"><span data-stu-id="3e27a-105">This is useful to level load resources or in case of breakdown.</span></span> <span data-ttu-id="3e27a-106">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="3e27a-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="3e27a-107">Este procedimiento está para el planificador, que trabaja en una empresa de lean manufacturing, el responsable del flujo de valor.</span><span class="sxs-lookup"><span data-stu-id="3e27a-107">This procedure is intended for the planner, working at a lean manufacturing company, responsible for the value stream.</span></span>


## <a name="copy-kanban-rule"></a><span data-ttu-id="3e27a-108">Copiar regla kanban</span><span class="sxs-lookup"><span data-stu-id="3e27a-108">Copy kanban rule</span></span>
1. <span data-ttu-id="3e27a-109">Vaya a Reglas kanban.</span><span class="sxs-lookup"><span data-stu-id="3e27a-109">Go to Kanban rules.</span></span>
2. <span data-ttu-id="3e27a-110">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="3e27a-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="3e27a-111">Seleccione la regla kanban de evento 000022 para L0001.</span><span class="sxs-lookup"><span data-stu-id="3e27a-111">Select Event Kanban rule 000022 for L0001.</span></span>  
3. <span data-ttu-id="3e27a-112">Haga clic en Duplicar regla kanban.</span><span class="sxs-lookup"><span data-stu-id="3e27a-112">Click Duplicate kanban rule.</span></span>
4. <span data-ttu-id="3e27a-113">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="3e27a-113">Click OK.</span></span>

## <a name="change-kanban-rule"></a><span data-ttu-id="3e27a-114">Cambiar regla kanban</span><span class="sxs-lookup"><span data-stu-id="3e27a-114">Change kanban rule</span></span>
1. <span data-ttu-id="3e27a-115">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3e27a-115">Close the page.</span></span>
2. <span data-ttu-id="3e27a-116">Vaya a Programación de trabajos kanban.</span><span class="sxs-lookup"><span data-stu-id="3e27a-116">Go to Kanban job scheduling.</span></span>
3. <span data-ttu-id="3e27a-117">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3e27a-117">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="3e27a-118">Seleccione la línea con kanban 000177.</span><span class="sxs-lookup"><span data-stu-id="3e27a-118">Select line with Kanban 000177.</span></span>  
4. <span data-ttu-id="3e27a-119">Haga clic en Usar regla kanban alternativa.</span><span class="sxs-lookup"><span data-stu-id="3e27a-119">Click Use alternative kanban rule.</span></span>
5. <span data-ttu-id="3e27a-120">Haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="3e27a-120">Click Next.</span></span>
6. <span data-ttu-id="3e27a-121">En el campo Regla kanban, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="3e27a-121">In the Kanban rule field, enter or select a value.</span></span>
    * <span data-ttu-id="3e27a-122">Seleccione la regla kanban que se creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="3e27a-122">Select the kanban rule that was created earlier.</span></span> <span data-ttu-id="3e27a-123">Esta es la regla kanban con el número mayor.</span><span class="sxs-lookup"><span data-stu-id="3e27a-123">This is the kanban rule with the highest number.</span></span>  
7. <span data-ttu-id="3e27a-124">Haga clic en Finalizar.</span><span class="sxs-lookup"><span data-stu-id="3e27a-124">Click Finish.</span></span>
    * <span data-ttu-id="3e27a-125">Ahora el trabajo kanban está usando otra regla kanban.</span><span class="sxs-lookup"><span data-stu-id="3e27a-125">Now the kanban job is using an another kanban rule.</span></span> <span data-ttu-id="3e27a-126">Esto puede resultar útil para nivelar celdas de trabajo de carga.</span><span class="sxs-lookup"><span data-stu-id="3e27a-126">This can be useful to level load work cells.</span></span>  


