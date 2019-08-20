---
title: Crear una plantilla de factura de servicios
description: Este procedimiento demuestra cómo crear una plantilla de la factura de servicios.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/29/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8281de3cb336d9392a6a97f98e51a2a139a384c5
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835192"
---
# <a name="create-a-free-text-invoice-template"></a><span data-ttu-id="a49cb-103">Crear una plantilla de factura de servicios</span><span class="sxs-lookup"><span data-stu-id="a49cb-103">Create a free text invoice template</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a49cb-104">Para este tutorial, utilice la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="a49cb-104">For this walkthrough, use the USMF demo company.</span></span> <span data-ttu-id="a49cb-105">Este procedimiento se va a utilizar para el usuario responsable de gestionar y de procesar facturas de cuentas por cobrar.</span><span class="sxs-lookup"><span data-stu-id="a49cb-105">This procedure is intended for the user who is responsible for managing and processing A/R invoices.</span></span>

## <a name="create-a-template"></a><span data-ttu-id="a49cb-106">Crear una plantilla</span><span class="sxs-lookup"><span data-stu-id="a49cb-106">Create a template</span></span>

1. <span data-ttu-id="a49cb-107">Vaya a Clientes > Facturas > Facturas periódicas > Plantillas de factura de texto libre.</span><span class="sxs-lookup"><span data-stu-id="a49cb-107">Go to Accounts receivable > Invoices > Recurring invoices > Free text invoice templates.</span></span>
    * <span data-ttu-id="a49cb-108">Use este formulario para crear plantillas de factura de texto sin formato que pueden incluir líneas de facturas, gastos, una plantilla de distribución contable e información de cuenta contable.</span><span class="sxs-lookup"><span data-stu-id="a49cb-108">Use this form to create free text invoice templates that can include invoice lines, charges, an accounting distribution template, and ledger account information.</span></span>  
2. <span data-ttu-id="a49cb-109">Haga clic en Nuevo para crear una plantilla de texto libre nueva.</span><span class="sxs-lookup"><span data-stu-id="a49cb-109">Click 'New' to create a new free text invoice template.</span></span>
3. <span data-ttu-id="a49cb-110">En el campo Nombre de plantilla, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="a49cb-110">In the Template name field, type a value.</span></span>
    * <span data-ttu-id="a49cb-111">Nombre de plantilla identifica de forma exclusiva una plantilla de factura de texto libre.</span><span class="sxs-lookup"><span data-stu-id="a49cb-111">‘Template name’ uniquely identifies a free text invoice template.</span></span> <span data-ttu-id="a49cb-112">Dos plantillas no pueden tener el mismo nombre de plantilla.</span><span class="sxs-lookup"><span data-stu-id="a49cb-112">No two templates can have the same ‘Template name’.</span></span>  
4. <span data-ttu-id="a49cb-113">En el campo Descripción, escriba una descripción de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="a49cb-113">In the Description field, enter a description of the template.</span></span>
5. <span data-ttu-id="a49cb-114">Expanda la ficha Líneas de factura.</span><span class="sxs-lookup"><span data-stu-id="a49cb-114">Expand the Invoice lines tab.</span></span>
6. <span data-ttu-id="a49cb-115">En el campo Descripción, escriba una descripción de la línea de factura.</span><span class="sxs-lookup"><span data-stu-id="a49cb-115">In the Description field, enter a description of the invoice line.</span></span>
7. <span data-ttu-id="a49cb-116">En el campo Cuenta principal, seleccione una cuenta de ingresos.</span><span class="sxs-lookup"><span data-stu-id="a49cb-116">In the Main account field, select a revenue account.</span></span>
    * <span data-ttu-id="a49cb-117">Puede seleccionar la cuenta de transacción de compensación de un crédito de cliente por el importe total de la factura en la página Perfiles de contabilización del cliente.</span><span class="sxs-lookup"><span data-stu-id="a49cb-117">You can select the offset transaction account of a customer credit for the total invoice amount in the Customer posting profiles page.</span></span>  
8. <span data-ttu-id="a49cb-118">En el campo Grupo de impuestos, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a49cb-118">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="a49cb-119">El grupo de impuestos para la línea de factura actual es el grupo de impuestos predeterminado para la cuenta del cliente.</span><span class="sxs-lookup"><span data-stu-id="a49cb-119">The sales tax group for the current invoice line is the default sales tax group for the customer account.</span></span>  
9. <span data-ttu-id="a49cb-120">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a49cb-120">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="a49cb-121">En el campo Grupo de impuestos del artículo, seleccione el grupo de impuestos de artículo para la línea de factura actual.</span><span class="sxs-lookup"><span data-stu-id="a49cb-121">In the Item tax group field, select the item sales tax group for the current invoice line.</span></span>
11. <span data-ttu-id="a49cb-122">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a49cb-122">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="a49cb-123">En el campo Precio unitario, escriba o vea el precio por unidad para la línea de factura.</span><span class="sxs-lookup"><span data-stu-id="a49cb-123">In the Unit price field, enter or view the price per unit for the invoice line</span></span>
    * <span data-ttu-id="a49cb-124">Este importe se multiplica por el valor del campo Cantidad para determinar el importe de la línea de factura.</span><span class="sxs-lookup"><span data-stu-id="a49cb-124">This amount is multiplied by the Quantity field to determine the invoice line amount.</span></span>  
13. <span data-ttu-id="a49cb-125">Agregue una línea nueva a la plantilla de factura de texto libre.</span><span class="sxs-lookup"><span data-stu-id="a49cb-125">Add a new line to free text invoice template.</span></span>
14. <span data-ttu-id="a49cb-126">En el campo Descripción, escriba una descripción de la línea de factura.</span><span class="sxs-lookup"><span data-stu-id="a49cb-126">In the Description field, enter a description of the invoice line.</span></span>
15. <span data-ttu-id="a49cb-127">En el campo Cuenta principal, seleccione una cuenta de ingresos.</span><span class="sxs-lookup"><span data-stu-id="a49cb-127">In the Main account field, select a revenue account.</span></span>
    * <span data-ttu-id="a49cb-128">Puede seleccionar la cuenta de transacción de compensación de un crédito de cliente por el importe total de la factura en la página Perfiles de contabilización del cliente.</span><span class="sxs-lookup"><span data-stu-id="a49cb-128">You can select the offset transaction account of a customer credit for the total invoice amount in the Customer posting profiles page.</span></span>  
16. <span data-ttu-id="a49cb-129">En el campo Grupo de impuestos, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a49cb-129">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="a49cb-130">El grupo de impuestos para la línea de factura actual es el grupo de impuestos predeterminado para la cuenta del cliente.</span><span class="sxs-lookup"><span data-stu-id="a49cb-130">The sales tax group for the current invoice line is the default sales tax group for the customer account.</span></span>  
17. <span data-ttu-id="a49cb-131">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a49cb-131">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="a49cb-132">En el campo Grupo de impuestos de artículos, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a49cb-132">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="a49cb-133">El grupo de impuestos de artículo para la línea de factura actual.</span><span class="sxs-lookup"><span data-stu-id="a49cb-133">The item sales tax group for the current invoice line.</span></span>  
19. <span data-ttu-id="a49cb-134">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a49cb-134">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="a49cb-135">Especificación o visualización del número unidades para la línea de factura</span><span class="sxs-lookup"><span data-stu-id="a49cb-135">Enter or view the number of units for the invoice line</span></span>
    * <span data-ttu-id="a49cb-136">Este número se multiplica por el valor del campo Precio unitario para determinar el importe de la línea de factura.</span><span class="sxs-lookup"><span data-stu-id="a49cb-136">This number is multiplied by the value in the Unit price field to determine the invoice line amount.</span></span>  
21. <span data-ttu-id="a49cb-137">Permite especificar o ver el precio unitario para la línea de factura.</span><span class="sxs-lookup"><span data-stu-id="a49cb-137">Enter or view the price per unit for the invoice line.</span></span> 
    * <span data-ttu-id="a49cb-138">Este importe se multiplica por el valor del campo Cantidad para determinar el importe de la línea de factura.</span><span class="sxs-lookup"><span data-stu-id="a49cb-138">This amount is multiplied by the value in the Quantity field to determine the invoice line amount.</span></span>  
22. <span data-ttu-id="a49cb-139">Vea y modifique las distribuciones contables para una línea individual y cualquier línea secundaria.</span><span class="sxs-lookup"><span data-stu-id="a49cb-139">View and modify the accounting distributions for an individual line and any child lines.</span></span>
    * <span data-ttu-id="a49cb-140">Las distribuciones contables definen cómo se contabilizará un importe; por ejemplo, cómo se contabilizarán los ingresos, impuestos o gastos en una factura de texto libre.</span><span class="sxs-lookup"><span data-stu-id="a49cb-140">Accounting distributions define how an amount will be accounted for, such as how the revenue, tax, or charges will be accounted for on a free text invoice.</span></span>  
23. <span data-ttu-id="a49cb-141">Actualice las distribuciones contables para la línea de factura seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a49cb-141">Update the accounting distributions for the selected invoice line.</span></span>
24. <span data-ttu-id="a49cb-142">Haga clic en Cerrar.</span><span class="sxs-lookup"><span data-stu-id="a49cb-142">Click Close.</span></span>

## <a name="save-a-free-text-invoice-as-a-template"></a><span data-ttu-id="a49cb-143">Guardar una factura de servicios como una plantilla</span><span class="sxs-lookup"><span data-stu-id="a49cb-143">Save a free text invoice as a template</span></span>
<span data-ttu-id="a49cb-144">También puede guardar una factura de servicios existente como una plantilla.</span><span class="sxs-lookup"><span data-stu-id="a49cb-144">You can also save an existing free text invoice as a template.</span></span> <span data-ttu-id="a49cb-145">Al seleccionar Guardar en plantilla desde la pestaña Factura, especifique un nombre y una descripción para la plantilla.</span><span class="sxs-lookup"><span data-stu-id="a49cb-145">When you select Save to template from the Invoice tab, provide a name and a description for the template.</span></span> <span data-ttu-id="a49cb-146">Si ya existe una plantilla con el nombre, verá una notificación de que ya existe una plantilla con ese nombre.</span><span class="sxs-lookup"><span data-stu-id="a49cb-146">If a template with the name already exists, you will see a notification that a template with that name already exists.</span></span> <span data-ttu-id="a49cb-147">Todavía puede hacer clic en Aceptar para reemplazarla.</span><span class="sxs-lookup"><span data-stu-id="a49cb-147">You can still click on Ok to replace it.</span></span> 
