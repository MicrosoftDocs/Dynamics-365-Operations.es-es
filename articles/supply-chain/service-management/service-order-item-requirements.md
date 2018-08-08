---
title: "Requisitos de los artículos de pedido de servicio"
description: "Si necesita reservar artículos específicos para un pedido de servicio, puede crear requisitos de artículo de inventario para él."
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjSalesItemReq
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 3dc7c721af4b25e1586e546392518648110a3fb6
ms.contentlocale: es-es
ms.lasthandoff: 08/07/2018

---

# <a name="service-order-item-requirements"></a><span data-ttu-id="e17c1-103">Requisitos de los artículos de pedido de servicio</span><span class="sxs-lookup"><span data-stu-id="e17c1-103">Service order item requirements</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="e17c1-104">Puede crear un pedido de servicio para administrar y realizar un seguimiento de los servicios que proporciona a sus clientes.</span><span class="sxs-lookup"><span data-stu-id="e17c1-104">You can create a service order to track and manage services that you provide to your customers.</span></span> <span data-ttu-id="e17c1-105">Si necesita reservar artículos específicos para un pedido de servicio, puede crear requisitos de artículo de inventario para él.</span><span class="sxs-lookup"><span data-stu-id="e17c1-105">If you need to reserve specific items for a service order, you can create inventory item requirements for it.</span></span> <span data-ttu-id="e17c1-106">Un requisito de artículo se puede usar inmediatamente del inventario o bien, puede iniciar un pedido de producción para el artículo.</span><span class="sxs-lookup"><span data-stu-id="e17c1-106">An item requirement can be immediately consumed from inventory, or it can initiate a production order for the item.</span></span>

<span data-ttu-id="e17c1-107">Si usa un requisito de artículo en lugar de una transacción de artículos, podrá planificar la entrega justo antes del uso real del artículo, crear un pedido de compras, incluir el artículo en el marco del acuerdo comercial e incluir el requisito de artículo en la planificación de producción.</span><span class="sxs-lookup"><span data-stu-id="e17c1-107">By using an item requirement instead of an item transaction, you can plan for delivery just before the item is actually used, create a purchase order, include the item in the trade-agreement framework, and include the item requirement in production planning.</span></span>

<span data-ttu-id="e17c1-108">Los requisitos de artículo para los pedidos de servicio se procesan a través de un proyecto.</span><span class="sxs-lookup"><span data-stu-id="e17c1-108">Item requirements for service orders are processed through a project.</span></span> <span data-ttu-id="e17c1-109">Para crear un requisito de artículo en un pedido de servicio, este último debe estar vinculado a un proyecto.</span><span class="sxs-lookup"><span data-stu-id="e17c1-109">To create an item requirement on a service order, the service order must be attached to a project.</span></span>

<span data-ttu-id="e17c1-110">Cuando se crea un requisito de artículo para un pedido de servicio, se podrá ver inmediatamente en la sección **Proyecto** del pedido de servicio individual, o bien a través del formulario **Pedido de ventas**.</span><span class="sxs-lookup"><span data-stu-id="e17c1-110">As soon as an item requirement is created for a service order, it can be viewed from **Project** in the individual service order or through the **Sales order** form.</span></span>

## <a name="view-an-item-requirement-from-a-service-order"></a><span data-ttu-id="e17c1-111">Ver un requisito de artículo desde un pedido de servicio</span><span class="sxs-lookup"><span data-stu-id="e17c1-111">View an item requirement from a service order</span></span>

1.  <span data-ttu-id="e17c1-112">Haga clic en **Gestión de servicio** \> **Común** \> **Pedidos de servicio** \> **Pedidos de servicio**.</span><span class="sxs-lookup"><span data-stu-id="e17c1-112">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="e17c1-113">Haga click en **Distribución** y, a continuación, haga clic en **Requisito de artículo** para abrir el formulario **Requisitos de artículo** .</span><span class="sxs-lookup"><span data-stu-id="e17c1-113">Click **Dispatch**, and then click **Item requirement** to open the **Item requirements** form.</span></span>

3.  <span data-ttu-id="e17c1-114">Haga clic en la ficha **Proyecto** y compruebe el campo **Pedido de servicio** para ver los pedidos de servicio de los requisitos de artículo.</span><span class="sxs-lookup"><span data-stu-id="e17c1-114">Click the **Project** tab, and check the **Service order** field to see the service orders of the item requirement.</span></span>

## <a name="delete-service-orders-with-item-requirements"></a><span data-ttu-id="e17c1-115">Eliminar pedidos de servicio con requisitos de artículo</span><span class="sxs-lookup"><span data-stu-id="e17c1-115">Delete service orders with item requirements</span></span>

<span data-ttu-id="e17c1-116">Si un requisito de artículo se crea en un pedido de servicio, este último no se podrá eliminar.</span><span class="sxs-lookup"><span data-stu-id="e17c1-116">If an item requirement is created on a service order, you cannot delete the service order.</span></span> <span data-ttu-id="e17c1-117">Deberá eliminar primero el requisito de artículo para poder eliminar el pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="e17c1-117">You must delete the item requirement before you can delete the service order.</span></span>

1.  <span data-ttu-id="e17c1-118">Haga clic en **Gestión de servicio** \> **Común** \> **Pedidos de servicio** \> **Pedidos de servicio**.</span><span class="sxs-lookup"><span data-stu-id="e17c1-118">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="e17c1-119">Haga click en **Distribución** y, a continuación, haga clic en **Requisito de artículo** para abrir el formulario **Requisitos de artículo** .</span><span class="sxs-lookup"><span data-stu-id="e17c1-119">Click **Dispatch**, and then click **Item requirement** to open the **Item requirements** form.</span></span> <span data-ttu-id="e17c1-120">En este formulario se enumeran los requisitos de artículo creados en el pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="e17c1-120">This form lists the item requirements that are created on the service order.</span></span>

3.  <span data-ttu-id="e17c1-121">Seleccione el requisito de artículo que desea eliminar y haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="e17c1-121">Select the item requirement to delete, and then click **Delete**.</span></span>

<span data-ttu-id="e17c1-122"> - O bien -</span><span class="sxs-lookup"><span data-stu-id="e17c1-122">–or–</span></span>

1.  <span data-ttu-id="e17c1-123">Haga clic en **Gestión de proyectos y contabilidad** \> **Común** \> **Proyectos** \> **Todos los proyectos**.</span><span class="sxs-lookup"><span data-stu-id="e17c1-123">Click **Project management and accounting** \> **Common** \> **Projects** \> **All projects**.</span></span>

2.  <span data-ttu-id="e17c1-124">Abra el proyecto con el pedido de servicio en el que se creó un requisito de artículo.</span><span class="sxs-lookup"><span data-stu-id="e17c1-124">Open the project that has the service order in which an item requirement is created.</span></span>

3.  <span data-ttu-id="e17c1-125">En el formulario **Proyectos**, en el panel derecho del formulario , haga clic en **Requisitos de artículo**.</span><span class="sxs-lookup"><span data-stu-id="e17c1-125">In the **Projects** form, in the right pane, click **Item requirements**.</span></span> <span data-ttu-id="e17c1-126">Se abrirá el formulario **Requisitos de artículo**, en el que se enumeran los requisitos de artículo asociados con el proyecto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e17c1-126">The **Item requirements** form lists the item requirements that are associated with the selected project.</span></span>

4.  <span data-ttu-id="e17c1-127">Seleccione el requisito de artículo que desea eliminar y haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="e17c1-127">Select the item requirement to delete, and then click **Delete**.</span></span>

## <a name="see-also"></a><span data-ttu-id="e17c1-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e17c1-128">See also</span></span>

<span data-ttu-id="e17c1-129">[Requisitos de artículo (formulario)](https://technet.microsoft.com/en-us/library/aa552021\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="e17c1-129">[Item requirements (form)](https://technet.microsoft.com/en-us/library/aa552021\(v=ax.60\))</span></span>


