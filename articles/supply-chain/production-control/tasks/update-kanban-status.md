---
title: Actualizar estado de trabajos kanban
description: Cuando un kanban se vacía por error o se debe vaciar un kanban recibido, es necesario actualizar el estado del kanban.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Kanban, KanbanResetEmpty
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 97b6eea4e93967dbe1eea5eac9fe3fbf6b336a49
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1838472"
---
# <a name="update-kanban-status"></a><span data-ttu-id="f4096-103">Actualizar estado de trabajos kanban</span><span class="sxs-lookup"><span data-stu-id="f4096-103">Update kanban status</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f4096-104">Cuando un kanban se vacía por error o se debe vaciar un kanban recibido, es necesario actualizar el estado del kanban.</span><span class="sxs-lookup"><span data-stu-id="f4096-104">When a kanban is emptied by mistake or a received kanban needs to be emptied, you need to update kanban status.</span></span> <span data-ttu-id="f4096-105">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="f4096-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="f4096-106">Este procedimiento se va a utilizar para el supervisor de planta.</span><span class="sxs-lookup"><span data-stu-id="f4096-106">This procedure is intended for the shop supervisor.</span></span>


## <a name="find-the-kanban"></a><span data-ttu-id="f4096-107">Encuentre el kanban.</span><span class="sxs-lookup"><span data-stu-id="f4096-107">Find the kanban.</span></span>
1. <span data-ttu-id="f4096-108">Vaya a Control de producción > Kanban > Kanbans.</span><span class="sxs-lookup"><span data-stu-id="f4096-108">Go to Production control > Kanban > Kanbans.</span></span>
2. <span data-ttu-id="f4096-109">Abra el filtro de columna Estado de la unidad de administración de material.</span><span class="sxs-lookup"><span data-stu-id="f4096-109">Open Handling unit status column filter.</span></span>
3. <span data-ttu-id="f4096-110">Haga clic en Borrar.</span><span class="sxs-lookup"><span data-stu-id="f4096-110">Click Clear.</span></span>
    * <span data-ttu-id="f4096-111">Esto restablece los filtros.</span><span class="sxs-lookup"><span data-stu-id="f4096-111">This resets the filters.</span></span>  
4. <span data-ttu-id="f4096-112">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="f4096-112">Use the Quick Filter to find records.</span></span> <span data-ttu-id="f4096-113">Por ejemplo, filtre por el campo Número de tarjeta con un valor de "000149".</span><span class="sxs-lookup"><span data-stu-id="f4096-113">For example, filter on the Card number field with a value of '000149'.</span></span>

## <a name="change-emptied-status-to-received-status"></a><span data-ttu-id="f4096-114">Cambiar el estado vaciado al estado recibido</span><span class="sxs-lookup"><span data-stu-id="f4096-114">Change emptied status to received status</span></span>
1. <span data-ttu-id="f4096-115">Haga clic en Unidad de gestión de material invertida.</span><span class="sxs-lookup"><span data-stu-id="f4096-115">Click Reverse empty handling unit.</span></span>
2. <span data-ttu-id="f4096-116">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="f4096-116">Click OK.</span></span>
    * <span data-ttu-id="f4096-117">Observe que el estado de la Unidad de gestión de material es Recibido.</span><span class="sxs-lookup"><span data-stu-id="f4096-117">Notice that the Handling unit status is Received.</span></span>  

## <a name="change-received-status-to-emptied-status"></a><span data-ttu-id="f4096-118">Cambiar el estado recibido al estado vaciado</span><span class="sxs-lookup"><span data-stu-id="f4096-118">Change received status to emptied status</span></span>
1. <span data-ttu-id="f4096-119">Haga clic en Vaciar kanban.</span><span class="sxs-lookup"><span data-stu-id="f4096-119">Click Empty kanban.</span></span>
2. <span data-ttu-id="f4096-120">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f4096-120">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="f4096-121">Observe que el estado de la Unidad de gestión de material es Vaciado.</span><span class="sxs-lookup"><span data-stu-id="f4096-121">Notice that the Handling unit status is Emptied.</span></span>  

