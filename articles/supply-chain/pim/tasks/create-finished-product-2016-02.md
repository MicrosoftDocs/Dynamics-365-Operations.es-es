---
title: Crear un producto terminado (febrero de 2016)
description: Esta tarea se centra en crear un producto terminado.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 71aa4522a9d70883a01914f6aa59a2fba0e0f659
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845080"
---
# <a name="create-a-finished-product-february-2016"></a><span data-ttu-id="cfd23-103">Crear un producto terminado (febrero de 2016)</span><span class="sxs-lookup"><span data-stu-id="cfd23-103">Create a finished product (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cfd23-104">Esta tarea se centra en crear un producto terminado.</span><span class="sxs-lookup"><span data-stu-id="cfd23-104">This task focuses on creating a finished product.</span></span> <span data-ttu-id="cfd23-105">Es la primera tarea en las series de cálculo BOM.</span><span class="sxs-lookup"><span data-stu-id="cfd23-105">It is the first task in the BOM calculation series.</span></span> <span data-ttu-id="cfd23-106">La empresa de datos de prueba utilizada para crear esta tarea es USMF.</span><span class="sxs-lookup"><span data-stu-id="cfd23-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="cfd23-107">Vaya a Gestión de información de productos > Productos > Productos emitidos.</span><span class="sxs-lookup"><span data-stu-id="cfd23-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="cfd23-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="cfd23-108">Click New.</span></span>
3. <span data-ttu-id="cfd23-109">En el campo Número de producto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="cfd23-109">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="cfd23-110">Para la demostración, especifique BOM_1.</span><span class="sxs-lookup"><span data-stu-id="cfd23-110">For the demonstration, type BOM_1.</span></span>  
4. <span data-ttu-id="cfd23-111">En el campo Grupo de modelos de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="cfd23-111">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="cfd23-112">Seleccione STD.</span><span class="sxs-lookup"><span data-stu-id="cfd23-112">Select STD.</span></span> <span data-ttu-id="cfd23-113">El STD representa el coste estándar y es el modelo más usado al trabajar con cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="cfd23-113">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="cfd23-114">En el campo Grupo de artículos, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="cfd23-114">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="cfd23-115">Por ejemplo, seleccione Audio.</span><span class="sxs-lookup"><span data-stu-id="cfd23-115">For example, select Audio.</span></span> <span data-ttu-id="cfd23-116">Esto no tiene aafecta de ninguna manera a los cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="cfd23-116">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="cfd23-117">En el campo Grupo de dimensiones de almacenamiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="cfd23-117">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="cfd23-118">Seleccione SiteWH.</span><span class="sxs-lookup"><span data-stu-id="cfd23-118">Select SiteWH.</span></span> <span data-ttu-id="cfd23-119">Para la demostración solo se usarán el Sitio y el Almacén.</span><span class="sxs-lookup"><span data-stu-id="cfd23-119">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="cfd23-120">En el campo Grupo de dimensiones de seguimiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="cfd23-120">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="cfd23-121">Las dimensiones de seguimiento no se usarán en este ejemplo, seleccione Ninguno.</span><span class="sxs-lookup"><span data-stu-id="cfd23-121">Tracking dimensions will not be used for this example, select None.</span></span>  
8. <span data-ttu-id="cfd23-122">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="cfd23-122">Click OK.</span></span>
9. <span data-ttu-id="cfd23-123">En el panel de acciones, haga clic en Administrar inventario.</span><span class="sxs-lookup"><span data-stu-id="cfd23-123">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="cfd23-124">Haga clic en Configuración predeterminada de pedido.</span><span class="sxs-lookup"><span data-stu-id="cfd23-124">Click Default order settings.</span></span>
11. <span data-ttu-id="cfd23-125">En el campo Tipo de pedido predeterminado, seleccione "Producción".</span><span class="sxs-lookup"><span data-stu-id="cfd23-125">In the Default order type field, select 'Production'.</span></span>
    * <span data-ttu-id="cfd23-126">Dado que este es un producto terminado que se generará, seleccione Producción.</span><span class="sxs-lookup"><span data-stu-id="cfd23-126">Because this is a finished product that will be produced, select Production.</span></span>  
12. <span data-ttu-id="cfd23-127">En el campo Sitio de compra, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="cfd23-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="cfd23-128">Para la demostración, seleccione el Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="cfd23-128">For the demonstration, select Site 1.</span></span>  
13. <span data-ttu-id="cfd23-129">En el campo Sitio de inventario, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="cfd23-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="cfd23-130">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="cfd23-130">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="cfd23-131">En el campo Sitio de centas, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="cfd23-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="cfd23-132">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="cfd23-132">For this example, select Site 1.</span></span>  
15. <span data-ttu-id="cfd23-133">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="cfd23-133">Close the page.</span></span>

