--- 
title: "Crear un producto terminado (febrero de 2016 únicamente)"
description: Esta tarea se centra en crear un producto terminado.
author: YuyuScheller
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: f1cfd25f44182650330e0ff927c2e660f27f134d
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---
# <a name="create-a-finished-product-february-2016-only"></a><span data-ttu-id="990c9-103">Crear un producto terminado (febrero de 2016 únicamente)</span><span class="sxs-lookup"><span data-stu-id="990c9-103">Create a finished product (February 2016 only)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="990c9-104">Esta tarea se centra en crear un producto terminado.</span><span class="sxs-lookup"><span data-stu-id="990c9-104">This task focuses on creating a finished product.</span></span> <span data-ttu-id="990c9-105">Es la primera tarea en las series de cálculo BOM.</span><span class="sxs-lookup"><span data-stu-id="990c9-105">It is the first task in the BOM calculation series.</span></span> <span data-ttu-id="990c9-106">La empresa de datos de prueba utilizada para crear esta tarea es USMF.</span><span class="sxs-lookup"><span data-stu-id="990c9-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="990c9-107">Vaya a Gestión de información de productos > Productos > Productos emitidos.</span><span class="sxs-lookup"><span data-stu-id="990c9-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="990c9-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="990c9-108">Click New.</span></span>
3. <span data-ttu-id="990c9-109">En el campo Número de producto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="990c9-109">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="990c9-110">Para la demostración, especifique BOM_1.</span><span class="sxs-lookup"><span data-stu-id="990c9-110">For the demonstration, type BOM_1.</span></span>  
4. <span data-ttu-id="990c9-111">En el campo Grupo de modelos de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="990c9-111">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="990c9-112">Seleccione STD.</span><span class="sxs-lookup"><span data-stu-id="990c9-112">Select STD.</span></span> <span data-ttu-id="990c9-113">El STD representa el coste estándar y es el modelo más usado al trabajar con cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="990c9-113">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="990c9-114">En el campo Grupo de artículos, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="990c9-114">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="990c9-115">Por ejemplo, seleccione Audio.</span><span class="sxs-lookup"><span data-stu-id="990c9-115">For example, select Audio.</span></span> <span data-ttu-id="990c9-116">Esto no tiene aafecta de ninguna manera a los cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="990c9-116">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="990c9-117">En el campo Grupo de dimensiones de almacenamiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="990c9-117">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="990c9-118">Seleccione SiteWH.</span><span class="sxs-lookup"><span data-stu-id="990c9-118">Select SiteWH.</span></span> <span data-ttu-id="990c9-119">Para la demostración solo se usarán el Sitio y el Almacén.</span><span class="sxs-lookup"><span data-stu-id="990c9-119">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="990c9-120">En el campo Grupo de dimensiones de seguimiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="990c9-120">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="990c9-121">Las dimensiones de seguimiento no se usarán en este ejemplo, seleccione Ninguno.</span><span class="sxs-lookup"><span data-stu-id="990c9-121">Tracking dimensions will not be used for this example, select None.</span></span>  
8. <span data-ttu-id="990c9-122">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="990c9-122">Click OK.</span></span>
9. <span data-ttu-id="990c9-123">En el panel de acciones, haga clic en Administrar inventario.</span><span class="sxs-lookup"><span data-stu-id="990c9-123">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="990c9-124">Haga clic en Configuración predeterminada de pedido.</span><span class="sxs-lookup"><span data-stu-id="990c9-124">Click Default order settings.</span></span>
11. <span data-ttu-id="990c9-125">En el campo Tipo de pedido predeterminado, seleccione "Producción".</span><span class="sxs-lookup"><span data-stu-id="990c9-125">In the Default order type field, select 'Production'.</span></span>
    * <span data-ttu-id="990c9-126">Dado que este es un producto terminado que se generará, seleccione Producción.</span><span class="sxs-lookup"><span data-stu-id="990c9-126">Because this is a finished product that will be produced, select Production.</span></span>  
12. <span data-ttu-id="990c9-127">En el campo Sitio de compra, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="990c9-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="990c9-128">Para la demostración, seleccione el Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="990c9-128">For the demonstration, select Site 1.</span></span>  
13. <span data-ttu-id="990c9-129">En el campo Sitio de inventario, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="990c9-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="990c9-130">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="990c9-130">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="990c9-131">En el campo Sitio de centas, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="990c9-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="990c9-132">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="990c9-132">For this example, select Site 1.</span></span>  
15. <span data-ttu-id="990c9-133">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="990c9-133">Close the page.</span></span>


