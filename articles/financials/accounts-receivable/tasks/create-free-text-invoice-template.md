--- 
title: Crear una plantilla de factura de servicios
description: "Esta grabación usa la empresa de demostración USMF."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 519d0b0ef8153283aa63bc7fa00b4f4b5283fbc1
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---
# <a name="create-a-free-text-invoice-template"></a><span data-ttu-id="ee5d3-103">Crear una plantilla de factura de servicios</span><span class="sxs-lookup"><span data-stu-id="ee5d3-103">Create a free text invoice template</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ee5d3-104">Esta grabación usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-104">This recording uses the USMF demo company.</span></span> <span data-ttu-id="ee5d3-105">El registro se va a utilizar para el usuario responsable de gestionar y de procesar facturas de cuentas por cobrar.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-105">The recording is intended for the user who is responsible for managing and processing A/R invoices.</span></span>

1. <span data-ttu-id="ee5d3-106">Vaya a Clientes > Facturas > Facturas periódicas > Plantillas de factura de texto libre.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-106">Go to Accounts receivable > Invoices > Recurring invoices > Free text invoice templates.</span></span>
    * <span data-ttu-id="ee5d3-107">Use este formulario para crear plantillas de factura de texto sin formato que pueden incluir líneas de facturas, gastos, una plantilla de distribución contable e información de cuenta contable.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-107">Use this form to create free text invoice templates that can include invoice lines, charges, an accounting distribution template, and ledger account information.</span></span>  
2. <span data-ttu-id="ee5d3-108">Haga clic en Nuevo para crear una plantilla de texto libre nueva.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-108">Click 'New' to create a new free text invoice template.</span></span>
3. <span data-ttu-id="ee5d3-109">En el campo Nombre de plantilla, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-109">In the Template name field, type a value.</span></span>
    * <span data-ttu-id="ee5d3-110">Nombre de plantilla identifica de forma exclusiva una plantilla de factura de texto libre.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-110">‘Template name’ uniquely identifies a free text invoice template.</span></span> <span data-ttu-id="ee5d3-111">Dos plantillas no pueden tener el mismo nombre de plantilla.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-111">No two templates can have the same ‘Template name’.</span></span>  
4. <span data-ttu-id="ee5d3-112">En el campo Descripción, escriba una descripción de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-112">In the Description field, enter a description of the template.</span></span>
5. <span data-ttu-id="ee5d3-113">Expanda la ficha Líneas de factura.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-113">Expand the Invoice lines tab.</span></span>
6. <span data-ttu-id="ee5d3-114">En el campo Descripción, escriba una descripción de la línea de factura.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-114">In the Description field, enter a description of the invoice line.</span></span>
7. <span data-ttu-id="ee5d3-115">En el campo Cuenta principal, seleccione una cuenta de ingresos.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-115">In the Main account field, select a revenue account.</span></span>
    * <span data-ttu-id="ee5d3-116">Puede seleccionar la cuenta de transacción de compensación de un crédito de cliente por el importe total de la factura en la página Perfiles de contabilización del cliente.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-116">You can select the offset transaction account of a customer credit for the total invoice amount in the Customer posting profiles page.</span></span>  
8. <span data-ttu-id="ee5d3-117">En el campo Grupo de impuestos, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-117">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ee5d3-118">El grupo de impuestos para la línea de factura actual es el grupo de impuestos predeterminado para la cuenta del cliente.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-118">The sales tax group for the current invoice line is the default sales tax group for the customer account.</span></span>  
9. <span data-ttu-id="ee5d3-119">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-119">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="ee5d3-120">En el campo Grupo de impuestos del artículo, seleccione el grupo de impuestos de artículo para la línea de factura actual.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-120">In the Item tax group field, select the item sales tax group for the current invoice line.</span></span>
11. <span data-ttu-id="ee5d3-121">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-121">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="ee5d3-122">En el campo Precio unitario, escriba o vea el precio por unidad para la línea de factura.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-122">In the Unit price field, enter or view the price per unit for the invoice line</span></span>
    * <span data-ttu-id="ee5d3-123">Este importe se multiplica por el valor del campo Cantidad para determinar el importe de la línea de factura.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-123">This amount is multiplied by the Quantity field to determine the invoice line amount.</span></span>  
13. <span data-ttu-id="ee5d3-124">Agregue una línea nueva a la plantilla de factura de texto libre.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-124">Add a new line to free text invoice template.</span></span>
14. <span data-ttu-id="ee5d3-125">En el campo Descripción, escriba una descripción de la línea de factura.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-125">In the Description field, enter a description of the invoice line.</span></span>
15. <span data-ttu-id="ee5d3-126">En el campo Cuenta principal, seleccione una cuenta de ingresos.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-126">In the Main account field, select a revenue account.</span></span>
    * <span data-ttu-id="ee5d3-127">Puede seleccionar la cuenta de transacción de compensación de un crédito de cliente por el importe total de la factura en la página Perfiles de contabilización del cliente.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-127">You can select the offset transaction account of a customer credit for the total invoice amount in the Customer posting profiles page.</span></span>  
16. <span data-ttu-id="ee5d3-128">En el campo Grupo de impuestos, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-128">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ee5d3-129">El grupo de impuestos para la línea de factura actual es el grupo de impuestos predeterminado para la cuenta del cliente.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-129">The sales tax group for the current invoice line is the default sales tax group for the customer account.</span></span>  
17. <span data-ttu-id="ee5d3-130">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-130">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="ee5d3-131">En el campo Grupo de impuestos de artículos, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-131">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ee5d3-132">El grupo de impuestos de artículo para la línea de factura actual.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-132">The item sales tax group for the current invoice line.</span></span>  
19. <span data-ttu-id="ee5d3-133">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-133">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="ee5d3-134">Especificación o visualización del número unidades para la línea de factura</span><span class="sxs-lookup"><span data-stu-id="ee5d3-134">Enter or view the number of units for the invoice line</span></span>
    * <span data-ttu-id="ee5d3-135">Este número se multiplica por el valor del campo Precio unitario para determinar el importe de la línea de factura.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-135">This number is multiplied by the value in the Unit price field to determine the invoice line amount.</span></span>  
21. <span data-ttu-id="ee5d3-136">Permite especificar o ver el precio unitario para la línea de factura.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-136">Enter or view the price per unit for the invoice line.</span></span> 
    * <span data-ttu-id="ee5d3-137">Este importe se multiplica por el valor del campo Cantidad para determinar el importe de la línea de factura.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-137">This amount is multiplied by the value in the Quantity field to determine the invoice line amount.</span></span>  
22. <span data-ttu-id="ee5d3-138">Vea y modifique las distribuciones contables para una línea individual y cualquier línea secundaria.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-138">View and modify the accounting distributions for an individual line and any child lines.</span></span>
    * <span data-ttu-id="ee5d3-139">Las distribuciones contables definen cómo se contabilizará un importe; por ejemplo, cómo se contabilizarán los ingresos, impuestos o gastos en una factura de texto libre.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-139">Accounting distributions define how an amount will be accounted for, such as how the revenue, tax, or charges will be accounted for on a free text invoice.</span></span>  
23. <span data-ttu-id="ee5d3-140">Actualice las distribuciones contables para la línea de factura seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-140">Update the accounting distributions for the selected invoice line.</span></span>
24. <span data-ttu-id="ee5d3-141">Haga clic en Cerrar.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-141">Click Close.</span></span>


