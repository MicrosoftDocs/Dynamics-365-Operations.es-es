---
title: "Calcular un pedido de producción"
description: "Puede ejecutar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 8274e390a177f51649f5cad70ef7ad5bd50a8830
ms.contentlocale: es-es
ms.lasthandoff: 08/07/2018

---
# <a name="estimate-a-production-order"></a><span data-ttu-id="d10c3-103">Calcular un pedido de producción</span><span class="sxs-lookup"><span data-stu-id="d10c3-103">Estimate a production order</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d10c3-104">Puede ejecutar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="d10c3-104">You can run this procedure by using the USMF demo data company or your own data set.</span></span> <span data-ttu-id="d10c3-105">En ambos casos, debe tener un pedido de producción abierto con estado Creado.</span><span class="sxs-lookup"><span data-stu-id="d10c3-105">In both cases, you need to have an open production order that has the Created status.</span></span> <span data-ttu-id="d10c3-106">Este es el segundo procedimiento de siete que explica el ciclo de vida del pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="d10c3-106">This is the second procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="estimate-a-production-order"></a><span data-ttu-id="d10c3-107">Calcular un pedido de producción</span><span class="sxs-lookup"><span data-stu-id="d10c3-107">Estimate a production order</span></span>
1. <span data-ttu-id="d10c3-108">Vaya a Control de producción > Pedidos de producción > Todos los pedidos de producción.</span><span class="sxs-lookup"><span data-stu-id="d10c3-108">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="d10c3-109">Seleccione un pedido con estado Creado en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="d10c3-109">Select an order that has the Created status in the grid.</span></span>
3. <span data-ttu-id="d10c3-110">En el panel de acciones, haga clic en Pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="d10c3-110">On the Action Pane, click Production order.</span></span>
4. <span data-ttu-id="d10c3-111">Haga clic en Estimación.</span><span class="sxs-lookup"><span data-stu-id="d10c3-111">Click Estimate.</span></span>
    * <span data-ttu-id="d10c3-112">En este paso, se calculan los costes estimados de un único pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="d10c3-112">In this step, the estimated costs of a single production order is calculated.</span></span>   
5. <span data-ttu-id="d10c3-113">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="d10c3-113">Click OK.</span></span>

## <a name="view-the-calculation-details"></a><span data-ttu-id="d10c3-114">Visualización de los detalles de cálculo</span><span class="sxs-lookup"><span data-stu-id="d10c3-114">View the calculation details</span></span>
1. <span data-ttu-id="d10c3-115">En el panel de acciones, haga clic en Gestionar costes.</span><span class="sxs-lookup"><span data-stu-id="d10c3-115">On the Action Pane, click Manage costs.</span></span>
2. <span data-ttu-id="d10c3-116">Haga clic en Ver detalles de cálculo.</span><span class="sxs-lookup"><span data-stu-id="d10c3-116">Click View calculation details.</span></span>
    * <span data-ttu-id="d10c3-117">Esta página muestra el análisis de costes.</span><span class="sxs-lookup"><span data-stu-id="d10c3-117">This page displays the cost breakdown.</span></span> <span data-ttu-id="d10c3-118">Por ejemplo, puede ver el precio de coste total por unidad para el producto terminado en la primera fila.</span><span class="sxs-lookup"><span data-stu-id="d10c3-118">For example, you can view the total cost price per unit for the finished product in the first row.</span></span> <span data-ttu-id="d10c3-119">Las filas posteriores contienen costes según la lista de materiales, la ruta de producción y los costes indirectos.</span><span class="sxs-lookup"><span data-stu-id="d10c3-119">The subsequent rows contain costs according to the bill of materials, production route, and indirect costs.</span></span>  

