--- 
title: Crear transacciones de impuestos en documentos
description: "Los impuestos en los documentos se calculan si proporciona un grupo de impuestos y un grupo de impuestos de artículos en las líneas del documento."
author: twheeloc
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 4a5fb8782b0e7aecd0e01a7d61046d904d46fc54
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---
# <a name="create-sales-tax-transactions-on-documents"></a><span data-ttu-id="c142c-103">Crear transacciones de impuestos en documentos</span><span class="sxs-lookup"><span data-stu-id="c142c-103">Create sales tax transactions on documents</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c142c-104">Los impuestos en los documentos se calculan si proporciona un grupo de impuestos y un grupo de impuestos de artículos en las líneas del documento.</span><span class="sxs-lookup"><span data-stu-id="c142c-104">Sales tax on documents is calculated by providing a Sales tax group and an Item sales tax group on document lines.</span></span> <span data-ttu-id="c142c-105">Los valores predeterminados provienen de los datos maestros pero se pueden cambiar manualmente en caso necesario.</span><span class="sxs-lookup"><span data-stu-id="c142c-105">These default from master data but can be changed manually if necessary.</span></span> <span data-ttu-id="c142c-106">Los impuestos calculados se pueden comprobar en el nivel de línea y de documento.</span><span class="sxs-lookup"><span data-stu-id="c142c-106">The calculated sales tax can be checked on a line and document level.</span></span> <span data-ttu-id="c142c-107">Esta tarea usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="c142c-107">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="c142c-108">Vaya a Clientes > Pedidos > Todos los pedidos de venta.</span><span class="sxs-lookup"><span data-stu-id="c142c-108">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="c142c-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="c142c-109">Click New.</span></span>
3. <span data-ttu-id="c142c-110">En el campo Cuenta de cliente, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c142c-110">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="c142c-111">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="c142c-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="c142c-112">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c142c-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="c142c-113">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="c142c-113">Click OK.</span></span>
7. <span data-ttu-id="c142c-114">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c142c-114">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="c142c-115">En el campo Código de artículo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c142c-115">In the Item number field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="c142c-116">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c142c-116">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="c142c-117">En el campo Precio unitario, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="c142c-117">In the Unit price field, enter a number.</span></span>
11. <span data-ttu-id="c142c-118">Expanda o contraiga la sección Detalles de línea.</span><span class="sxs-lookup"><span data-stu-id="c142c-118">Expand or collapse the Line details section.</span></span>
12. <span data-ttu-id="c142c-119">Haga clic en la ficha Configurar.</span><span class="sxs-lookup"><span data-stu-id="c142c-119">Click the Setup tab.</span></span>
13. <span data-ttu-id="c142c-120">En el campo Grupo de impuestos de artículos, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c142c-120">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="c142c-121">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="c142c-121">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="c142c-122">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c142c-122">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="c142c-123">Haga clic en Operaciones financieras.</span><span class="sxs-lookup"><span data-stu-id="c142c-123">Click Financials.</span></span>
17. <span data-ttu-id="c142c-124">Haga clic en Impuestos.</span><span class="sxs-lookup"><span data-stu-id="c142c-124">Click Sales tax.</span></span>
18. <span data-ttu-id="c142c-125">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="c142c-125">Click OK.</span></span>
19. <span data-ttu-id="c142c-126">Haga clic en Agregar línea.</span><span class="sxs-lookup"><span data-stu-id="c142c-126">Click Add line.</span></span>
20. <span data-ttu-id="c142c-127">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c142c-127">In the list, mark the selected row.</span></span>
21. <span data-ttu-id="c142c-128">En el campo Código de artículo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c142c-128">In the Item number field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="c142c-129">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="c142c-129">In the list, find and select the desired record.</span></span>
23. <span data-ttu-id="c142c-130">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c142c-130">In the list, click the link in the selected row.</span></span>
24. <span data-ttu-id="c142c-131">En el campo Precio unitario, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="c142c-131">In the Unit price field, enter a number.</span></span>
25. <span data-ttu-id="c142c-132">En el campo Grupo de impuestos de artículos, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c142c-132">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
26. <span data-ttu-id="c142c-133">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="c142c-133">In the list, find and select the desired record.</span></span>
27. <span data-ttu-id="c142c-134">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c142c-134">In the list, click the link in the selected row.</span></span>
28. <span data-ttu-id="c142c-135">En el panel de acciones, haga clic en Vender.</span><span class="sxs-lookup"><span data-stu-id="c142c-135">On the Action Pane, click Sell.</span></span>
29. <span data-ttu-id="c142c-136">Haga clic en Impuestos.</span><span class="sxs-lookup"><span data-stu-id="c142c-136">Click Sales tax.</span></span>
30. <span data-ttu-id="c142c-137">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="c142c-137">Click OK.</span></span>


