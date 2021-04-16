---
title: Actualizar estado de trabajos kanban
description: Cuando un kanban se vacía por error o se debe vaciar un kanban recibido, es necesario actualizar el estado del kanban.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Kanban, KanbanResetEmpty
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5a0e03da4671ffec4ecf4835b20a00ef87971c94
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831827"
---
# <a name="update-kanban-status"></a><span data-ttu-id="2e508-103">Actualizar estado de trabajos kanban</span><span class="sxs-lookup"><span data-stu-id="2e508-103">Update kanban status</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2e508-104">Cuando un kanban se vacía por error o se debe vaciar un kanban recibido, es necesario actualizar el estado del kanban.</span><span class="sxs-lookup"><span data-stu-id="2e508-104">When a kanban is emptied by mistake or a received kanban needs to be emptied, you need to update kanban status.</span></span> <span data-ttu-id="2e508-105">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="2e508-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="2e508-106">Este procedimiento se va a utilizar para el supervisor de planta.</span><span class="sxs-lookup"><span data-stu-id="2e508-106">This procedure is intended for the shop supervisor.</span></span>


## <a name="find-the-kanban"></a><span data-ttu-id="2e508-107">Encuentre el kanban.</span><span class="sxs-lookup"><span data-stu-id="2e508-107">Find the kanban.</span></span>
1. <span data-ttu-id="2e508-108">Vaya a Control de producción > Kanban > Kanbans.</span><span class="sxs-lookup"><span data-stu-id="2e508-108">Go to Production control > Kanban > Kanbans.</span></span>
2. <span data-ttu-id="2e508-109">Abra el filtro de columna Estado de la unidad de administración de material.</span><span class="sxs-lookup"><span data-stu-id="2e508-109">Open Handling unit status column filter.</span></span>
3. <span data-ttu-id="2e508-110">Haga clic en Borrar.</span><span class="sxs-lookup"><span data-stu-id="2e508-110">Click Clear.</span></span>
    * <span data-ttu-id="2e508-111">Esto restablece los filtros.</span><span class="sxs-lookup"><span data-stu-id="2e508-111">This resets the filters.</span></span>  
4. <span data-ttu-id="2e508-112">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="2e508-112">Use the Quick Filter to find records.</span></span> <span data-ttu-id="2e508-113">Por ejemplo, filtre por el campo Número de tarjeta con un valor de "000149".</span><span class="sxs-lookup"><span data-stu-id="2e508-113">For example, filter on the Card number field with a value of '000149'.</span></span>

## <a name="change-emptied-status-to-received-status"></a><span data-ttu-id="2e508-114">Cambiar el estado vaciado al estado recibido</span><span class="sxs-lookup"><span data-stu-id="2e508-114">Change emptied status to received status</span></span>
1. <span data-ttu-id="2e508-115">Haga clic en Unidad de gestión de material invertida.</span><span class="sxs-lookup"><span data-stu-id="2e508-115">Click Reverse empty handling unit.</span></span>
2. <span data-ttu-id="2e508-116">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="2e508-116">Click OK.</span></span>
    * <span data-ttu-id="2e508-117">Observe que el estado de la Unidad de gestión de material es Recibido.</span><span class="sxs-lookup"><span data-stu-id="2e508-117">Notice that the Handling unit status is Received.</span></span>  

## <a name="change-received-status-to-emptied-status"></a><span data-ttu-id="2e508-118">Cambiar el estado recibido al estado vaciado</span><span class="sxs-lookup"><span data-stu-id="2e508-118">Change received status to emptied status</span></span>
1. <span data-ttu-id="2e508-119">Haga clic en Vaciar kanban.</span><span class="sxs-lookup"><span data-stu-id="2e508-119">Click Empty kanban.</span></span>
2. <span data-ttu-id="2e508-120">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="2e508-120">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="2e508-121">Observe que el estado de la Unidad de gestión de material es Vaciado.</span><span class="sxs-lookup"><span data-stu-id="2e508-121">Notice that the Handling unit status is Emptied.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]