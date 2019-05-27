---
title: Finalizar un pedido de producción
description: Este procedimiento muestra cómo terminar un pedido de producción.
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8f5cb4afdc0285a6ccf28dbd362df3799c0ecc74
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1555848"
---
# <a name="end-a-production-order"></a><span data-ttu-id="d80e8-103">Finalizar un pedido de producción</span><span class="sxs-lookup"><span data-stu-id="d80e8-103">End a production order</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d80e8-104">Este procedimiento muestra cómo terminar un pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="d80e8-104">This procedure shows how to end a production order.</span></span> <span data-ttu-id="d80e8-105">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="d80e8-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="d80e8-106">Este es el último procedimiento de siete que explica el ciclo de vida del pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="d80e8-106">This is the final procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="end-a-production-order"></a><span data-ttu-id="d80e8-107">Finalizar un pedido de producción</span><span class="sxs-lookup"><span data-stu-id="d80e8-107">End a production order</span></span>
1. <span data-ttu-id="d80e8-108">Vaya a Control de producción > Pedidos de producción > Todos los pedidos de producción.</span><span class="sxs-lookup"><span data-stu-id="d80e8-108">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="d80e8-109">Seleccione un pedido de producción con estado Notificado como terminado.</span><span class="sxs-lookup"><span data-stu-id="d80e8-109">Select a production order that has the status Reported as finished.</span></span>  
2. <span data-ttu-id="d80e8-110">En el panel de acciones, haga clic en Pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="d80e8-110">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="d80e8-111">Haga clic en Fin.</span><span class="sxs-lookup"><span data-stu-id="d80e8-111">Click End.</span></span>
    * <span data-ttu-id="d80e8-112">En esta página, puede confirmar que desea finalizar el pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="d80e8-112">On this page, you can confirm that you want to end the production order.</span></span>  
4. <span data-ttu-id="d80e8-113">Haga clic en la pestaña General.</span><span class="sxs-lookup"><span data-stu-id="d80e8-113">Click the General tab.</span></span>
5. <span data-ttu-id="d80e8-114">En el campo Fecha, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="d80e8-114">In the Date field, enter a date.</span></span>
6. <span data-ttu-id="d80e8-115">En el campo Método de valoración del residuo, seleccione Asignación.</span><span class="sxs-lookup"><span data-stu-id="d80e8-115">In the Scrap method field, select 'Allocation'.</span></span>
    * <span data-ttu-id="d80e8-116">Cuando selecciona el método Asignación, los costes de los materiales desechados se agregan a los productos terminados.</span><span class="sxs-lookup"><span data-stu-id="d80e8-116">When you select the Allocation method, costs from the scrapped materials are added to the finished goods.</span></span>  
7. <span data-ttu-id="d80e8-117">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="d80e8-117">Click OK.</span></span>

## <a name="validate-calculation-results"></a><span data-ttu-id="d80e8-118">Validación de resultados de cálculo</span><span class="sxs-lookup"><span data-stu-id="d80e8-118">Validate calculation results</span></span>
1. <span data-ttu-id="d80e8-119">En el panel de acciones, haga clic en Gestionar costes.</span><span class="sxs-lookup"><span data-stu-id="d80e8-119">On the Action Pane, click Manage costs.</span></span>
2. <span data-ttu-id="d80e8-120">Haga clic en Ver comparación del coste.</span><span class="sxs-lookup"><span data-stu-id="d80e8-120">Click View cost comparison.</span></span>
    * <span data-ttu-id="d80e8-121">Una vez finalizado el pedido de producción, puede comparar el precio de coste estimado con el precio de coste real para obtener una visión general de las desviaciones de producción.</span><span class="sxs-lookup"><span data-stu-id="d80e8-121">After you have ended the production order, you can compare the estimated cost price against the realized cost price to get an overview of the production variances.</span></span>  
