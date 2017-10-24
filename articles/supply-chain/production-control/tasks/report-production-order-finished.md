--- 
title: "Notificar un pedido de producción como terminado"
description: "Este procedimiento muestra cómo notificar un pedido de producción como terminado."
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
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 17b2285e4669f1ad8fa6cea1250693a2a70c7dfa
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="report-a-production-order-as-finished"></a><span data-ttu-id="35fba-103">Notificar un pedido de producción como terminado</span><span class="sxs-lookup"><span data-stu-id="35fba-103">Report a production order as finished</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="35fba-104">Este procedimiento muestra cómo notificar un pedido de producción como terminado.</span><span class="sxs-lookup"><span data-stu-id="35fba-104">This procedure shows how to report a production order as finished.</span></span> <span data-ttu-id="35fba-105">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="35fba-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="35fba-106">Este es el sexto procedimiento de siete que explica el ciclo de vida del pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="35fba-106">This is the sixth procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="report-a-production-order-as-finished"></a><span data-ttu-id="35fba-107">Notificar un pedido de producción como terminado</span><span class="sxs-lookup"><span data-stu-id="35fba-107">Report a production order as finished</span></span>
1. <span data-ttu-id="35fba-108">Vaya a Control de producción > Pedidos de producción > Todos los pedidos de producción.</span><span class="sxs-lookup"><span data-stu-id="35fba-108">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="35fba-109">Seleccione un pedido de producción con estado Iniciado.</span><span class="sxs-lookup"><span data-stu-id="35fba-109">Select a production order that has the Started status.</span></span>  
2. <span data-ttu-id="35fba-110">En el panel de acciones, haga clic en Pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="35fba-110">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="35fba-111">Haga clic en Notificar como terminado.</span><span class="sxs-lookup"><span data-stu-id="35fba-111">Click Report as finished.</span></span>
    * <span data-ttu-id="35fba-112">En esta página, puede confirmar la cantidad de producto terminado que se va a notificar como terminado.</span><span class="sxs-lookup"><span data-stu-id="35fba-112">On this page, you can confirm the quantity of the finished product to be reported as finished.</span></span>  
4. <span data-ttu-id="35fba-113">Haga clic en la pestaña General.</span><span class="sxs-lookup"><span data-stu-id="35fba-113">Click the General tab.</span></span>
5. <span data-ttu-id="35fba-114">Defina la Cantidad sin errores en "18".</span><span class="sxs-lookup"><span data-stu-id="35fba-114">Set Good quantity to '18'.</span></span>
6. <span data-ttu-id="35fba-115">Defina la Cantidad con errores en "2".</span><span class="sxs-lookup"><span data-stu-id="35fba-115">Set Error quantity to '2'.</span></span>
7. <span data-ttu-id="35fba-116">En el campo Causa del error, seleccione "Material".</span><span class="sxs-lookup"><span data-stu-id="35fba-116">In the Error cause field, select 'Material'.</span></span>
8. <span data-ttu-id="35fba-117">Active o desactive la casilla Cierre final.</span><span class="sxs-lookup"><span data-stu-id="35fba-117">Select or clear the End job check box.</span></span>
9. <span data-ttu-id="35fba-118">Active o desactive la casilla Aceptar error.</span><span class="sxs-lookup"><span data-stu-id="35fba-118">Select or clear the Accept error check box.</span></span>
10. <span data-ttu-id="35fba-119">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="35fba-119">Click OK.</span></span>

## <a name="verify-the-report-as-finished-journal"></a><span data-ttu-id="35fba-120">Comprobar Notificar como diario terminado</span><span class="sxs-lookup"><span data-stu-id="35fba-120">Verify the Report as finished journal</span></span>
1. <span data-ttu-id="35fba-121">En el panel de acciones, haga clic en Ver.</span><span class="sxs-lookup"><span data-stu-id="35fba-121">On the Action Pane, click View.</span></span>
2. <span data-ttu-id="35fba-122">Haga clic en Notificado como terminado.</span><span class="sxs-lookup"><span data-stu-id="35fba-122">Click Reported as finished.</span></span>
3. <span data-ttu-id="35fba-123">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="35fba-123">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="35fba-124">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="35fba-124">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="35fba-125">Se registra Notificar como diario terminado.</span><span class="sxs-lookup"><span data-stu-id="35fba-125">The Report as finished journal is posted.</span></span> <span data-ttu-id="35fba-126">Si desea realizar ajustes en el diario, puede crear manualmente un nuevo diario en el que puede realizar cambios.</span><span class="sxs-lookup"><span data-stu-id="35fba-126">If you want to make adjustments to the journal, you can manually create  a new journal where you can make changes.</span></span>  


