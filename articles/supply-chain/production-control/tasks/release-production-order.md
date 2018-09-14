--- 
title: "Publicar un pedido de producción"
description: "Este procedimiento muestra cómo liberar un pedido de producción."
author: johanhoffmann
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdTableListPage, ProdParmRelease, SrsReportViewerForm
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 917fe1ef826c9b112be29ebce78ebd750652db64
ms.contentlocale: es-es
ms.lasthandoff: 09/14/2018

---
# <a name="release-a-production-order"></a><span data-ttu-id="e60df-103">Publicar un pedido de producción</span><span class="sxs-lookup"><span data-stu-id="e60df-103">Release a production order</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e60df-104">Este procedimiento muestra cómo liberar un pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="e60df-104">This procedure shows how to release a production order.</span></span> <span data-ttu-id="e60df-105">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="e60df-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="e60df-106">Este es el cuarto procedimiento de siete que explican el ciclo de vida del pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="e60df-106">This is the fourth procedure out of seven which explains the production order lifecycle.</span></span>

1. <span data-ttu-id="e60df-107">Vaya a Control de producción > Pedidos de producción > Todos los pedidos de producción.</span><span class="sxs-lookup"><span data-stu-id="e60df-107">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="e60df-108">En la cuadrícula, seleccione un pedido de producción con el estado Programado.</span><span class="sxs-lookup"><span data-stu-id="e60df-108">In the grid, select a production order that has the Scheduled status.</span></span>  
2. <span data-ttu-id="e60df-109">En el panel de acciones, haga clic en Pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="e60df-109">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="e60df-110">Haga clic en Liberar.</span><span class="sxs-lookup"><span data-stu-id="e60df-110">Click Release.</span></span>
    * <span data-ttu-id="e60df-111">En esta página, puede confirmar la liberación del intervalo seleccionado de pedidos de producción.</span><span class="sxs-lookup"><span data-stu-id="e60df-111">On this page, you can confirm the release of the selected range of production orders.</span></span> <span data-ttu-id="e60df-112">Haga clic en Seleccionar si desea agregar pedidos.</span><span class="sxs-lookup"><span data-stu-id="e60df-112">Click Select if you want to add orders.</span></span>  
    * <span data-ttu-id="e60df-113">El paso de liberación indica si el pedido de producción se libera en la planta de producción de modo que los operadores de planta pueden notificar el progreso en cuanto a los trabajos de producción.</span><span class="sxs-lookup"><span data-stu-id="e60df-113">The Release step indicates when the production order is released to the production shop floor so that the shop floor operators can report progress on the production jobs.</span></span> <span data-ttu-id="e60df-114">Se pueden emitir documentos de producción que contienen información pertinente sobre el proceso de los trabajos.</span><span class="sxs-lookup"><span data-stu-id="e60df-114">Production papers that contain relevant information about processing the jobs can be issued.</span></span> <span data-ttu-id="e60df-115">El trabajo del almacén para seleccionar la materia prima se genera para los artículos que se configuran para el proceso de almacén.</span><span class="sxs-lookup"><span data-stu-id="e60df-115">The warehouse work for raw material picking is generated for the items that are set up for the warehouse process.</span></span>  
4. <span data-ttu-id="e60df-116">Haga clic en la pestaña General.</span><span class="sxs-lookup"><span data-stu-id="e60df-116">Click the General tab.</span></span>
    * <span data-ttu-id="e60df-117">Seleccione qué informes de producción deben imprimirse.</span><span class="sxs-lookup"><span data-stu-id="e60df-117">Select which production reports should be printed.</span></span> <span data-ttu-id="e60df-118">El informe de la tarjeta de trabajo imprime una página para cada trabajo programado y requiere que el pedido de producción se programe en el nivel de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e60df-118">The Job card report prints a page for each scheduled job and requires the production order to be scheduled at the job level.</span></span> <span data-ttu-id="e60df-119">El informe contiene información acerca del inicio y la hora final programadas, la cantidad de producción y qué recurso procesa el trabajo.</span><span class="sxs-lookup"><span data-stu-id="e60df-119">The report contains information about the scheduled start and end time, the quantity to produce, and which resource processes the job.</span></span> <span data-ttu-id="e60df-120">El informe de trabajo de ruta recoge la misma información en la misma página, pero no imprime una página para cada trabajo.</span><span class="sxs-lookup"><span data-stu-id="e60df-120">The Route job report collects the same information on the same page, but does not print a page for each job.</span></span> <span data-ttu-id="e60df-121">El informe de tarjeta de ruta solo muestra las operaciones pero no los trabajos.</span><span class="sxs-lookup"><span data-stu-id="e60df-121">The Route card report only shows the operations but not the jobs.</span></span> <span data-ttu-id="e60df-122">Por lo tanto, este informe no requiere programación de trabajos, pero se puede usar cuando los pedidos de producción se programan en el nivel de operación.</span><span class="sxs-lookup"><span data-stu-id="e60df-122">Therefore, this report does not require job scheduling, but can be used when production orders are scheduled at the operation level.</span></span>  
5. <span data-ttu-id="e60df-123">Haga clic en la casilla Imprimir tarjeta de ruta.</span><span class="sxs-lookup"><span data-stu-id="e60df-123">Click the Print route card checkbox.</span></span>
6. <span data-ttu-id="e60df-124">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="e60df-124">Click OK.</span></span>
7. <span data-ttu-id="e60df-125">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e60df-125">Close the page.</span></span>


