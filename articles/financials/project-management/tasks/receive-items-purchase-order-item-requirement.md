--- 
title: "Recibir artículos de un pedido de compra a partir de un artículo requerido"
description: "Este procedimiento muestra cómo recibir artículos en un pedido de compra desde un artículo requerido."
author: KimANelson
manager: AnnBe
ms.date: 02/13/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: fef6a597ed126ff4e1148fd9710b214c0425c3ab
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---
# <a name="receive-items-on-purchase-order-from-item-requirement"></a><span data-ttu-id="ab676-103">Recibir artículos de un pedido de compra a partir de un artículo requerido</span><span class="sxs-lookup"><span data-stu-id="ab676-103">Receive items on purchase order from item requirement</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ab676-104">Este procedimiento muestra cómo recibir artículos en un pedido de compra desde un artículo requerido.</span><span class="sxs-lookup"><span data-stu-id="ab676-104">This procedure shows how to receive items on a purchase order from an item requirement.</span></span>

<span data-ttu-id="ab676-105">Si usa un requisito de artículo en lugar de una transacción de artículos, podrá planificar la entrega justo antes del uso real del artículo, crear un pedido de compras, incluir el artículo en el marco del acuerdo comercial e incluir el requisito de artículo en la planificación de producción.</span><span class="sxs-lookup"><span data-stu-id="ab676-105">By using an item requirement instead of an item transaction, you can plan for delivery just before the item is actually used, create a purchase order, include the item in the trade-agreement framework, and include the item requirement in production planning.</span></span> 

<span data-ttu-id="ab676-106">Esta tarea usa el conjunto de datos USSI.</span><span class="sxs-lookup"><span data-stu-id="ab676-106">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="ab676-107">Vaya a Gestión de proyectos y contabilidad > Proyectos > Todos los proyectos.</span><span class="sxs-lookup"><span data-stu-id="ab676-107">Go to Project management and accounting > Projects > All projects.</span></span>
2. <span data-ttu-id="ab676-108">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ab676-108">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="ab676-109">En el panel de acciones, haga clic en Plan.</span><span class="sxs-lookup"><span data-stu-id="ab676-109">On the Action Pane, click Plan.</span></span>
4. <span data-ttu-id="ab676-110">Haga clic en Requisitos de artículo.</span><span class="sxs-lookup"><span data-stu-id="ab676-110">Click Item requirements.</span></span>
5. <span data-ttu-id="ab676-111">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="ab676-111">Click New.</span></span>
6. <span data-ttu-id="ab676-112">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ab676-112">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="ab676-113">En el campo Número de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ab676-113">In the Item number field, enter or select a value.</span></span>
8. <span data-ttu-id="ab676-114">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="ab676-114">In the Quantity field, enter a number.</span></span>
9. <span data-ttu-id="ab676-115">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="ab676-115">Click Save.</span></span>
10. <span data-ttu-id="ab676-116">En el panel de acciones, haga clic en Gestionar.</span><span class="sxs-lookup"><span data-stu-id="ab676-116">On the Action Pane, click Manage.</span></span>
11. <span data-ttu-id="ab676-117">Haga clic en Funciones.</span><span class="sxs-lookup"><span data-stu-id="ab676-117">Click Functions.</span></span>
12. <span data-ttu-id="ab676-118">Haga clic en Crear pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="ab676-118">Click Create purchase order.</span></span>
13. <span data-ttu-id="ab676-119">Seleccione la casilla de verificación Incluir.</span><span class="sxs-lookup"><span data-stu-id="ab676-119">Select the Include check box.</span></span>
14. <span data-ttu-id="ab676-120">En el campo Cuenta de proveedor, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ab676-120">In the Vendor account field, enter or select a value.</span></span>
15. <span data-ttu-id="ab676-121">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="ab676-121">Click OK.</span></span>
16. <span data-ttu-id="ab676-122">Vaya a Proveedores > Pedidos de compra > Todos los pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="ab676-122">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
17. <span data-ttu-id="ab676-123">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ab676-123">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="ab676-124">En el panel de acciones, haga clic en Compra.</span><span class="sxs-lookup"><span data-stu-id="ab676-124">On the Action Pane, click Purchase.</span></span>
19. <span data-ttu-id="ab676-125">Haga clic en Confirmar.</span><span class="sxs-lookup"><span data-stu-id="ab676-125">Click Confirm.</span></span>
20. <span data-ttu-id="ab676-126">En el panel de acciones, haga clic en Recibir.</span><span class="sxs-lookup"><span data-stu-id="ab676-126">On the Action Pane, click Receive.</span></span>
21. <span data-ttu-id="ab676-127">Haga clic en Recepción de producto.</span><span class="sxs-lookup"><span data-stu-id="ab676-127">Click Product receipt.</span></span>
22. <span data-ttu-id="ab676-128">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ab676-128">In the list, mark the selected row.</span></span>
23. <span data-ttu-id="ab676-129">En el campo Recepción de producto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="ab676-129">In the Product receipt field, type a value.</span></span>
24. <span data-ttu-id="ab676-130">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="ab676-130">Click OK.</span></span>


