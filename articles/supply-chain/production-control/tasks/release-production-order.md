--- 
title: "Publicar un pedido de producción"
description: "Este procedimiento muestra cómo liberar un pedido de producción."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 2ae2d84bd12d338c9bada5518c43178b22112006
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="release-a-production-order"></a><span data-ttu-id="dc6c8-103">Publicar un pedido de producción</span><span class="sxs-lookup"><span data-stu-id="dc6c8-103">Release a production order</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="dc6c8-104">Este procedimiento muestra cómo liberar un pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="dc6c8-104">This procedure shows how to release a production order.</span></span> <span data-ttu-id="dc6c8-105">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="dc6c8-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="dc6c8-106">Este es el cuarto procedimiento de siete que explican el ciclo de vida del pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="dc6c8-106">This is the fourth procedure out of seven which explains the production order lifecycle.</span></span>

1. <span data-ttu-id="dc6c8-107">Vaya a Control de producción > Pedidos de producción > Todos los pedidos de producción.</span><span class="sxs-lookup"><span data-stu-id="dc6c8-107">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="dc6c8-108">En la cuadrícula, seleccione un pedido de producción con el estado Programado.</span><span class="sxs-lookup"><span data-stu-id="dc6c8-108">In the grid, select a production order that has the Scheduled status.</span></span>  
2. <span data-ttu-id="dc6c8-109">En el panel de acciones, haga clic en Pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="dc6c8-109">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="dc6c8-110">Haga clic en Liberar.</span><span class="sxs-lookup"><span data-stu-id="dc6c8-110">Click Release.</span></span>
    * <span data-ttu-id="dc6c8-111">En esta página, puede confirmar la liberación del intervalo seleccionado de pedidos de producción.</span><span class="sxs-lookup"><span data-stu-id="dc6c8-111">On this page, you can confirm the release of the selected range of production orders.</span></span> <span data-ttu-id="dc6c8-112">Haga clic en Seleccionar si desea agregar pedidos.</span><span class="sxs-lookup"><span data-stu-id="dc6c8-112">Click Select if you want to add orders.</span></span>  
    * <span data-ttu-id="dc6c8-113">El paso de liberación indica si el pedido de producción se libera en la planta de producción de modo que los operadores de planta pueden notificar el progreso en cuanto a los trabajos de producción.</span><span class="sxs-lookup"><span data-stu-id="dc6c8-113">The Release step indicates when the production order is released to the production shop floor so that the shop floor operators can report progress on the production jobs.</span></span> <span data-ttu-id="dc6c8-114">Se pueden emitir documentos de producción que contienen información pertinente sobre el proceso de los trabajos.</span><span class="sxs-lookup"><span data-stu-id="dc6c8-114">Production papers that contain relevant information about processing the jobs can be issued.</span></span> <span data-ttu-id="dc6c8-115">El trabajo del almacén para seleccionar la materia prima se genera para los artículos que se configuran para el proceso de almacén.</span><span class="sxs-lookup"><span data-stu-id="dc6c8-115">The warehouse work for raw material picking is generated for the items that are set up for the warehouse process.</span></span>  
4. <span data-ttu-id="dc6c8-116">Haga clic en la pestaña General.</span><span class="sxs-lookup"><span data-stu-id="dc6c8-116">Click the General tab.</span></span>
    * <span data-ttu-id="dc6c8-117">Seleccione qué informes de producción deben imprimirse.</span><span class="sxs-lookup"><span data-stu-id="dc6c8-117">Select which production reports should be printed.</span></span> <span data-ttu-id="dc6c8-118">El informe de la tarjeta de trabajo imprime una página para cada trabajo programado y requiere que el pedido de producción se programe en el nivel de trabajo.</span><span class="sxs-lookup"><span data-stu-id="dc6c8-118">The Job card report prints a page for each scheduled job and requires the production order to be scheduled at the job level.</span></span> <span data-ttu-id="dc6c8-119">El informe contiene información acerca del inicio y la hora final programadas, la cantidad de producción y qué recurso procesa el trabajo.</span><span class="sxs-lookup"><span data-stu-id="dc6c8-119">The report contains information about the scheduled start and end time, the quantity to produce, and which resource processes the job.</span></span> <span data-ttu-id="dc6c8-120">El informe de trabajo de ruta recoge la misma información en la misma página, pero no imprime una página para cada trabajo.</span><span class="sxs-lookup"><span data-stu-id="dc6c8-120">The Route job report collects the same information on the same page, but does not print a page for each job.</span></span> <span data-ttu-id="dc6c8-121">El informe de tarjeta de ruta solo muestra las operaciones pero no los trabajos.</span><span class="sxs-lookup"><span data-stu-id="dc6c8-121">The Route card report only shows the operations but not the jobs.</span></span> <span data-ttu-id="dc6c8-122">Por lo tanto, este informe no requiere programación de trabajos, pero se puede usar cuando los pedidos de producción se programan en el nivel de operación.</span><span class="sxs-lookup"><span data-stu-id="dc6c8-122">Therefore, this report does not require job scheduling, but can be used when production orders are scheduled at the operation level.</span></span>  
5. <span data-ttu-id="dc6c8-123">Haga clic en la casilla Imprimir tarjeta de ruta.</span><span class="sxs-lookup"><span data-stu-id="dc6c8-123">Click the Print route card checkbox.</span></span>
6. <span data-ttu-id="dc6c8-124">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="dc6c8-124">Click OK.</span></span>
7. <span data-ttu-id="dc6c8-125">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="dc6c8-125">Close the page.</span></span>


