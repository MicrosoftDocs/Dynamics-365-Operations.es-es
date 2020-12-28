---
title: Realizar el seguimiento de un artículo o una materia prima
description: Este procedimiento muestra cómo usar el seguimiento de artículos para identificar dónde se han usado los artículos o las materias primas o dónde se están usando.
author: pjacobse
manager: tfehr
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTrackingDimTracing, InventTrackingDimTracingCriteria, InventTrackingItemIdLookup, InventBatchIdLookup, CustTable, SalesLine
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: pjacobse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0c39d34773a2b36cbf9477e4bdda8e45491d9c03
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437109"
---
# <a name="trace-an-item-or-raw-material"></a><span data-ttu-id="fc4e9-103">Realizar el seguimiento de un artículo o una materia prima</span><span class="sxs-lookup"><span data-stu-id="fc4e9-103">Trace an item or raw material</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fc4e9-104">Este procedimiento muestra cómo usar el seguimiento de artículos para identificar dónde se han usado los artículos o las materias primas o dónde se están usando.</span><span class="sxs-lookup"><span data-stu-id="fc4e9-104">This procedure demonstrates how to use item tracing to identify where items or raw materials have been used or are being used.</span></span> <span data-ttu-id="fc4e9-105">Con este procedimiento, puede identificar un artículo, realizar un seguimiento de él hasta el origen y después, hacia la producción y la venta del producto terminado.</span><span class="sxs-lookup"><span data-stu-id="fc4e9-105">With this procedure, you can identify an item, trace it back to the source, and then trace forward through the production and sale of the finished product.</span></span> <span data-ttu-id="fc4e9-106">El proceso se puede usar para investigar los clientes y los pedidos de ventas afectados, entre otros.</span><span class="sxs-lookup"><span data-stu-id="fc4e9-106">The process can be used to investigate the customers impacted, the sales orders affected, and more.</span></span> <span data-ttu-id="fc4e9-107">Este procedimiento usa la empresa de datos de demostración USP2.</span><span class="sxs-lookup"><span data-stu-id="fc4e9-107">This procedure uses demo data company USP2.</span></span>


## <a name="trace-an-item-backwards-using-a-known-batch-number"></a><span data-ttu-id="fc4e9-108">Realizar un seguimiento hacia de un artículo con un número de lote conocido</span><span class="sxs-lookup"><span data-stu-id="fc4e9-108">Trace an item backwards using a known batch number</span></span>
1. <span data-ttu-id="fc4e9-109">En el **Panel de navegación**, vaya a **Módulos > Gestión del inventario > Consultas e informes > Dimensiones de seguimiento > Seguimiento de artículos**.</span><span class="sxs-lookup"><span data-stu-id="fc4e9-109">In the **Navigation pane**, go to **Modules > Inventory management > Inquiries and reports > Tracking dimensions > Item tracing**.</span></span>
2. <span data-ttu-id="fc4e9-110">En el campo **Código de artículo**, seleccione 'P9100'.</span><span class="sxs-lookup"><span data-stu-id="fc4e9-110">In the **Item number** field, select 'P9100'.</span></span>
3. <span data-ttu-id="fc4e9-111">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="fc4e9-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="fc4e9-112">En el campo **Adelante o atrás**, seleccione 'Atrás'.</span><span class="sxs-lookup"><span data-stu-id="fc4e9-112">In the **Forward or backward** field, select 'Backward'.</span></span>
5. <span data-ttu-id="fc4e9-113">En el campo **Número de lote**, seleccione 'as-12-344-01'.</span><span class="sxs-lookup"><span data-stu-id="fc4e9-113">In the **Batch number** field, select 'as-12-344-01'.</span></span>
6. <span data-ttu-id="fc4e9-114">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="fc4e9-114">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="fc4e9-115">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fc4e9-115">Click **OK**.</span></span>

## <a name="identify-an-item-trace-it-forward-and-make-an-analysis"></a><span data-ttu-id="fc4e9-116">Identificar un artículo, realizar un seguimiento de él hacia adelante y hacer un análisis</span><span class="sxs-lookup"><span data-stu-id="fc4e9-116">Identify an item, trace it forward, and make an analysis</span></span>

<span data-ttu-id="fc4e9-117">El nodo superior del árbol representa la cantidad disponible del artículo y del lote seleccionados.</span><span class="sxs-lookup"><span data-stu-id="fc4e9-117">The top node of the tree represents the on hand quantity of the selected item and batch.</span></span> <span data-ttu-id="fc4e9-118">Necesita expandir los nodos del árbol para encontrar el artículo en el que se debe ejecutar el seguimiento progresivo.</span><span class="sxs-lookup"><span data-stu-id="fc4e9-118">You need to expand the nodes of the tree to find the item that the forward trace should be executed on.</span></span>   
1. <span data-ttu-id="fc4e9-119">En el árbol, expanda "los nodos descritos a continuación y después seleccione el último nodo".</span><span class="sxs-lookup"><span data-stu-id="fc4e9-119">In the tree, expand 'the nodes described below, and then select the last node'.</span></span>
    
    <span data-ttu-id="fc4e9-120">Expanda: "P9100 / 1 / 10 / as-12-344-01 ● 2 keg ● 7,00 gal  \P9100 ● Seleccionado ● Pedido de venta 000072 ● 12/22/2015  ● -1 keg ● -4.00 gal ● Sitio=1, Almacén=10, Número de lote=as-12-344-01  \P9100 ● Producción B-000050 ● 12/9/2015● 7 keg ● 27.00 gal ● Sitio=1,Almacén=10,Número de lote=as-12-344-01 ● Productos asociados: P9101' y después seleccione ese nodo.</span><span class="sxs-lookup"><span data-stu-id="fc4e9-120">Expand: 'P9100 / 1 / 10 / as-12-344-01 ● 2 keg ● 7.00 gal  \P9100 ● Picked ● Sales order 000072 ● 12/22/2015  ● -1 keg ● -4.00 gal ● Site=1, Warehouse=10, Batch number=as-12-344-01  \P9100 ● Production B-000050 ● 12/9/2015● 7 keg ● 27.00 gal ● Site=1,Warehouse=10,Batch number=as-12-344-01 ● Co-products: P9101' and then select that node.</span></span>     
2. <span data-ttu-id="fc4e9-121">En el árbol, expanda "el nodo descrito a continuación y después seleccione ese nodo".</span><span class="sxs-lookup"><span data-stu-id="fc4e9-121">In the tree, expand 'the node described below and then select that node'.</span></span>
    
    <span data-ttu-id="fc4e9-122">Empezando por el nodo que acaba de seleccionar, expanda "M9103 ● Línea de producción B-000050 ● 12/9/2015 ● -160,00 lb ● Tamaño=70, Color=Aceptar, Sitio=1, Almacén=10, Número de lote=App01" y a continuación seleccione ese nodo.</span><span class="sxs-lookup"><span data-stu-id="fc4e9-122">Starting from the node that you've just selected,  expand 'M9103 ● Production line B-000050 ● 12/9/2015  ● -160.00 lb ● Size=70, Color=OK, Site=1, Warehouse=10, Batch number=App01' and then select that node.</span></span>  
3. <span data-ttu-id="fc4e9-123">Haga clic en **Hacer seguimiento a partir del nodo**.</span><span class="sxs-lookup"><span data-stu-id="fc4e9-123">Click **Trace from node**.</span></span>
4. <span data-ttu-id="fc4e9-124">Haga clic en **Hacia adelante.**</span><span class="sxs-lookup"><span data-stu-id="fc4e9-124">Click **Forward**.</span></span>
5. <span data-ttu-id="fc4e9-125">En el **Panel de acciones**, haga clic en **Seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="fc4e9-125">On the **Action Pane**, click **Tracing**.</span></span>
    
    <span data-ttu-id="fc4e9-126">Hay varias opciones de seguimiento que proporcionan información acerca de los clientes afectados por el artículo del que está realizando el seguimiento y los pedidos de ventas relacionados con el artículo que se han enviado y que no se han enviado.</span><span class="sxs-lookup"><span data-stu-id="fc4e9-126">There are several tracing options which provide information about the customers impacted by the item that you're tracing, and the sales orders related to the item which have and haven't been shipped.</span></span>   
6. <span data-ttu-id="fc4e9-127">Haga clic en **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="fc4e9-127">Click **Customers**.</span></span>
7. <span data-ttu-id="fc4e9-128">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fc4e9-128">Close the page.</span></span>
8. <span data-ttu-id="fc4e9-129">En el **Panel de acciones**, haga clic en **Seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="fc4e9-129">On the **Action Pane**, click **Tracing**.</span></span>
9. <span data-ttu-id="fc4e9-130">Haga clic en **Pedidos de ventas enviados**.</span><span class="sxs-lookup"><span data-stu-id="fc4e9-130">Click **Shipped sales orders**.</span></span>
10. <span data-ttu-id="fc4e9-131">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fc4e9-131">Close the page.</span></span>

