--- 
title: Crear un plan para un sitio
description: "El planificador de producción calcula los requisitos de materiales y capacidad para la producción de un artículo específico."
author: ShylaThompson
manager: AnnBe
ms.date: 06/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: f22b7271432316aa745e0c4cd3f1ed533805403e
ms.contentlocale: es-es
ms.lasthandoff: 08/07/2018

---
# <a name="create-a-plan-for-a-site"></a><span data-ttu-id="02692-103">Crear un plan para un sitio</span><span class="sxs-lookup"><span data-stu-id="02692-103">Create a plan for a site</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="02692-104">El planificador de producción calcula los requisitos de materiales y capacidad para la producción de un artículo específico.</span><span class="sxs-lookup"><span data-stu-id="02692-104">The production planner calculates the material and capacity requirements for the production of a specific item.</span></span> <span data-ttu-id="02692-105">Una vez creadas las sugerencias de abastecimiento, encuentra los pedidos en el sitio para el que está planificando y pone en firme los pedidos, empezando por los urgentes.</span><span class="sxs-lookup"><span data-stu-id="02692-105">After the sourcing suggestions are created, he finds the orders at the site for which he is planning and firms the orders, starting from the urgent ones.</span></span> <span data-ttu-id="02692-106">Los pedidos más urgentes son los que se deben poner en firme en la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="02692-106">The most urgent orders are the ones that need to be firmed on the current date.</span></span> <span data-ttu-id="02692-107">Use la empresa de datos de demostración USMF para llevar a cabo estas tareas.</span><span class="sxs-lookup"><span data-stu-id="02692-107">Use the demo data company USMF to perform these tasks.</span></span>


## <a name="create-a-materials-and-capacity-plan-for-an-item"></a><span data-ttu-id="02692-108">Crear un plan de capacidad y materiales para un artículo</span><span class="sxs-lookup"><span data-stu-id="02692-108">Create a materials and capacity plan for an item</span></span>
1. <span data-ttu-id="02692-109">Haga clic en Planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="02692-109">Click Master planning.</span></span>
    * <span data-ttu-id="02692-110">Necesita desplazarse al panel de información predeterminado.</span><span class="sxs-lookup"><span data-stu-id="02692-110">You need to navigate to the default Dashboard.</span></span>  
2. <span data-ttu-id="02692-111">Haga clic en Ejecutar.</span><span class="sxs-lookup"><span data-stu-id="02692-111">Click Run.</span></span>
3. <span data-ttu-id="02692-112">Expanda la sección Registros que incluir.</span><span class="sxs-lookup"><span data-stu-id="02692-112">Expand the Records to include section.</span></span>
4. <span data-ttu-id="02692-113">Haga clic en Filtro.</span><span class="sxs-lookup"><span data-stu-id="02692-113">Click Filter.</span></span>
5. <span data-ttu-id="02692-114">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="02692-114">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="02692-115">En el campo Criterios, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="02692-115">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="02692-116">Ejemplo: D0001</span><span class="sxs-lookup"><span data-stu-id="02692-116">Example: D0001</span></span>  
7. <span data-ttu-id="02692-117">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="02692-117">Click OK.</span></span>
8. <span data-ttu-id="02692-118">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="02692-118">Click OK.</span></span>
    * <span data-ttu-id="02692-119">Esto puede tardar unos minutos.</span><span class="sxs-lookup"><span data-stu-id="02692-119">This may take a few minutes.</span></span>  
9. <span data-ttu-id="02692-120">Actualice la página.</span><span class="sxs-lookup"><span data-stu-id="02692-120">Refresh the page.</span></span>

## <a name="identify-the-urgent-planned-orders-for-the-item"></a><span data-ttu-id="02692-121">Identificar los pedidos planificados urgentes para el artículo</span><span class="sxs-lookup"><span data-stu-id="02692-121">Identify the urgent planned orders for the item</span></span>
1. <span data-ttu-id="02692-122">Abra el filtro de columna Número de artículo.</span><span class="sxs-lookup"><span data-stu-id="02692-122">Open Item number column filter.</span></span>
2. <span data-ttu-id="02692-123">Aplique un filtro en el campo "Número de artículo" con un valor de "D0001", mediante el operador de filtro "empieza por".</span><span class="sxs-lookup"><span data-stu-id="02692-123">Apply a filter on the "Item number" field, with a value of "D0001", using the "begins with" filter operator.</span></span>
3. <span data-ttu-id="02692-124">Abra el filtro de columna Fecha del pedido.</span><span class="sxs-lookup"><span data-stu-id="02692-124">Open Order date column filter.</span></span>
4. <span data-ttu-id="02692-125">Aplique un filtro en el campo "Fecha del pedido", con un valor de la fecha actual, usando el operador de filtro "es exactamente".</span><span class="sxs-lookup"><span data-stu-id="02692-125">Apply a filter on the "Order date" field, with a value of current date, using the "is exactly" filter operator.</span></span>

## <a name="firm-all-the-urgent-orders-for-the-item"></a><span data-ttu-id="02692-126">Poner en firme todos los pedidos urgentes para el artículo</span><span class="sxs-lookup"><span data-stu-id="02692-126">Firm all the urgent orders for the item</span></span>
1. <span data-ttu-id="02692-127">En la lista, active o desactive todas las filas.</span><span class="sxs-lookup"><span data-stu-id="02692-127">In the list, mark or unmark all rows.</span></span>
2. <span data-ttu-id="02692-128">Haga clic en En firme.</span><span class="sxs-lookup"><span data-stu-id="02692-128">Click Firm.</span></span>
3. <span data-ttu-id="02692-129">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="02692-129">Click OK.</span></span>


