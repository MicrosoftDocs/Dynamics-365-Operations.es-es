--- 
title: Crear una factura de servicios
description: "Esta guía de la tarea demuestra la creación de una factura de servicios."
author: mikefalkner
manager: AnnBe
ms.date: 10/26/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ef3cad6538d9efbd1c1881f4b7d771382d9b1ba8
ms.openlocfilehash: 87e293008fd748aa0dcc6b3caa94a4889bed35de
ms.contentlocale: es-es
ms.lasthandoff: 10/26/2017

---
# <a name="create-a-free-text-invoice"></a><span data-ttu-id="0ff4d-103">Crear una factura de servicios</span><span class="sxs-lookup"><span data-stu-id="0ff4d-103">Create a free text invoice</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0ff4d-104">Esta guía de la tarea demuestra la creación de una factura de servicios.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-104">This task guide demonstrates creating a free text invoice.</span></span> <span data-ttu-id="0ff4d-105">Esta tarea usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="0ff4d-106">Vaya a Clientes > Facturas > Todas las facturas de servicios.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-106">Go to Accounts receivable > Invoices > All free text invoices.</span></span>
2. <span data-ttu-id="0ff4d-107">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-107">Click New.</span></span>
3. <span data-ttu-id="0ff4d-108">En el campo Cuenta de cliente, seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-108">In the Customer account field, select a value.</span></span>
    * <span data-ttu-id="0ff4d-109">La cuenta de facturación cambiará de forma predeterminada a la misma cuenta utilizada para la cuenta de cliente.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-109">The invoice account will default to the same account used for the customer account.</span></span>   
    * <span data-ttu-id="0ff4d-110">El estado de la contabilidad comienza en proceso si la factura no se registra.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-110">The accounting status starts with In process if the invoice is not posted.</span></span>   
    * <span data-ttu-id="0ff4d-111">El número de factura se asignará al registrar la factura.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-111">The invoice number will be assigned when the invoice is posted.</span></span>  
    * <span data-ttu-id="0ff4d-112">Si está usando las órdenes de SEPA, la orden de débito directo se rellenará automáticamente con una orden cuando seleccione la cuenta de cliente.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-112">If you are using SEPA mandates, the direct debit mandate will be automatically populated with a mandate when you select the customer account.</span></span>  
4. <span data-ttu-id="0ff4d-113">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="0ff4d-114">En el campo Cuenta principal, especifique un número de cuenta sin dimensiones.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-114">In the Main account field, specify an account number without dimensions.</span></span>
    * <span data-ttu-id="0ff4d-115">También puede especificar uno o varios caracteres para la cuenta principal y usar la búsqueda para encontrar su cuenta.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-115">You can also enter one or more characters for the main account and use the lookup to find your account.</span></span> <span data-ttu-id="0ff4d-116">Especificará las dimensiones más tarde en esta guía.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-116">You will enter dimensions later on in this guide.</span></span>  
6. <span data-ttu-id="0ff4d-117">Expanda la ficha desplegable Detalles de línea para poder agregar dimensiones en su cuenta principal.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-117">Expand the Line details fasttab so you can add dimensions to your main account.</span></span>
7. <span data-ttu-id="0ff4d-118">Haga clic en la pestaña Línea de dimensiones financieras.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-118">Click the Financial dimensions line tab.</span></span>
    * <span data-ttu-id="0ff4d-119">Las dimensiones solo son para la línea seleccionada.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-119">The dimensions are for the selected line only.</span></span>    
    * <span data-ttu-id="0ff4d-120">Se rellena el grupo de impuestos del cliente.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-120">The sales tax group is populated from the customer.</span></span> <span data-ttu-id="0ff4d-121">Si el cliente no tiene un grupo de impuestos, se usará el grupo de impuestos de la cuenta principal.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-121">If the customer does not have a sales tax group, the sales tax group from the main account is used.</span></span>  
    * <span data-ttu-id="0ff4d-122">El grupo de impuestos de artículos se rellena desde la cuenta principal.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-122">The items sales tax group is populated from the main account.</span></span> <span data-ttu-id="0ff4d-123">Si la cuenta principal no tiene un grupo de impuestos de artículos, se usa el grupo de impuestos de artículos de los parámetros de impuestos de contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-123">If the main account does not have an item sales tax group, then the item sales tax group in the General ledger sales tax parameters is used.</span></span>    
8. <span data-ttu-id="0ff4d-124">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-124">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="0ff4d-125">La cantidad es opcional.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-125">The quantity is optional.</span></span>  
9. <span data-ttu-id="0ff4d-126">En el campo Precio unitario, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-126">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="0ff4d-127">El precio unitario es opcional.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-127">The unit price is optional.</span></span>  
    * <span data-ttu-id="0ff4d-128">El importe se calcula como cantidad por el precio unitario.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-128">The amount is calculated as the quantity times the unit price.</span></span> <span data-ttu-id="0ff4d-129">Sin embargo, puede reemplazar dicho cálculo y especificar un importe.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-129">However, you can override that calculation and enter an amount.</span></span>  
10. <span data-ttu-id="0ff4d-130">Haga clic en Impuestos para ver los impuestos calculados para la factura.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-130">Click on Sales tax to view the sales tax calculated for your invoice.</span></span>
    * <span data-ttu-id="0ff4d-131">Vea los importes de impuestos en esta página o reemplace los importes en la ficha Ajuste.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-131">View the sales tax amounts in this page or you can override the amounts on the Adjustment tab.</span></span>  
11. <span data-ttu-id="0ff4d-132">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="0ff4d-132">Click OK.</span></span>
12. <span data-ttu-id="0ff4d-133">Haga clic en los gastos para agregar un gasto a la factura.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-133">Click Charges to add a charge to your invoice.</span></span> 
13. <span data-ttu-id="0ff4d-134">En el campo Código de gastos, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-134">In the Charges code field, type a value.</span></span>
14. <span data-ttu-id="0ff4d-135">En el campo Valor de gastos, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-135">In the Charges value field, enter a number.</span></span>
15. <span data-ttu-id="0ff4d-136">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-136">Close the page.</span></span>
16. <span data-ttu-id="0ff4d-137">Haga clic en Totales para ver los detalles y los totales resumidos de la factura.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-137">Click Totals to view the summary invoice details and totals.</span></span>
17. <span data-ttu-id="0ff4d-138">Haga clic en Cerrar.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-138">Click Close.</span></span>
18. <span data-ttu-id="0ff4d-139">Haga clic en Registrar para registrar la factura.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-139">Click Post to post the invoice.</span></span> <span data-ttu-id="0ff4d-140">Podrá cancelar antes de registrar.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-140">You will be able to cancel before you post.</span></span>
    * <span data-ttu-id="0ff4d-141">Para cambiar la hora de la impresión de facturas: seleccione Actual para imprimir cada factura cuando se actualiza o seleccione Posterior para imprimir una vez que se hayan actualizado todas las facturas.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-141">To change the timing of your invoice printing:  Select Current to print each invoice as it is updated   or  Select After to print after all invoices have been updated.</span></span>  
    * <span data-ttu-id="0ff4d-142">Si desea cambiar la manera en que se comprueba el límite de crédito del cliente antes de registrar, cambie el tipo de límite de crédito.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-142">If you want to change how the customer's credit limit is checked before posting, change the Credit limit type.</span></span>  
    * <span data-ttu-id="0ff4d-143">Si desea imprimir la factura, seleccione Sí.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-143">If you want to print the invoice, select Yes.</span></span>  
    * <span data-ttu-id="0ff4d-144">Si desea registrar la factura, seleccione Sí.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-144">If you want to post the invoice, select Yes.</span></span> <span data-ttu-id="0ff4d-145">Puede imprimir la factura sin registrarla.</span><span class="sxs-lookup"><span data-stu-id="0ff4d-145">You can print the invoice without posting.</span></span>  
19. <span data-ttu-id="0ff4d-146">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="0ff4d-146">Click OK.</span></span>


