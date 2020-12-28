---
title: Calcular un pedido de producción
description: Puede ejecutar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos.
author: johanhoffmann
manager: tfehr
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5bbb541a09809c1f1bfada42094d840a2f6e7764
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436551"
---
# <a name="estimate-a-production-order"></a><span data-ttu-id="0204a-103">Calcular un pedido de producción</span><span class="sxs-lookup"><span data-stu-id="0204a-103">Estimate a production order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0204a-104">Puede ejecutar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="0204a-104">You can run this procedure by using the USMF demo data company or your own data set.</span></span> <span data-ttu-id="0204a-105">En ambos casos, debe tener un pedido de producción abierto con estado Creado.</span><span class="sxs-lookup"><span data-stu-id="0204a-105">In both cases, you need to have an open production order that has the Created status.</span></span> <span data-ttu-id="0204a-106">Este es el segundo procedimiento de siete que explica el ciclo de vida del pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="0204a-106">This is the second procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="estimate-a-production-order"></a><span data-ttu-id="0204a-107">Calcular un pedido de producción</span><span class="sxs-lookup"><span data-stu-id="0204a-107">Estimate a production order</span></span>
1. <span data-ttu-id="0204a-108">Vaya a Control de producción > Pedidos de producción > Todos los pedidos de producción.</span><span class="sxs-lookup"><span data-stu-id="0204a-108">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="0204a-109">Seleccione un pedido con estado Creado en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="0204a-109">Select an order that has the Created status in the grid.</span></span>
3. <span data-ttu-id="0204a-110">En el panel de acciones, haga clic en Pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="0204a-110">On the Action Pane, click Production order.</span></span>
4. <span data-ttu-id="0204a-111">Haga clic en Estimación.</span><span class="sxs-lookup"><span data-stu-id="0204a-111">Click Estimate.</span></span>
    * <span data-ttu-id="0204a-112">En este paso, se calculan los costes estimados de un único pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="0204a-112">In this step, the estimated costs of a single production order is calculated.</span></span>   
5. <span data-ttu-id="0204a-113">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="0204a-113">Click OK.</span></span>

## <a name="view-the-calculation-details"></a><span data-ttu-id="0204a-114">Visualización de los detalles de cálculo</span><span class="sxs-lookup"><span data-stu-id="0204a-114">View the calculation details</span></span>
1. <span data-ttu-id="0204a-115">En el panel de acciones, haga clic en Gestionar costes.</span><span class="sxs-lookup"><span data-stu-id="0204a-115">On the Action Pane, click Manage costs.</span></span>
2. <span data-ttu-id="0204a-116">Haga clic en Ver detalles de cálculo.</span><span class="sxs-lookup"><span data-stu-id="0204a-116">Click View calculation details.</span></span>
    * <span data-ttu-id="0204a-117">Esta página muestra el análisis de costes.</span><span class="sxs-lookup"><span data-stu-id="0204a-117">This page displays the cost breakdown.</span></span> <span data-ttu-id="0204a-118">Por ejemplo, puede ver el precio de coste total por unidad para el producto terminado en la primera fila.</span><span class="sxs-lookup"><span data-stu-id="0204a-118">For example, you can view the total cost price per unit for the finished product in the first row.</span></span> <span data-ttu-id="0204a-119">Las filas posteriores contienen costes según la lista de materiales, la ruta de producción y los costes indirectos.</span><span class="sxs-lookup"><span data-stu-id="0204a-119">The subsequent rows contain costs according to the bill of materials, production route, and indirect costs.</span></span>  
