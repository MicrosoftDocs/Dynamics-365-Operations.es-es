--- 
title: Crear una factura de servicios
description: "Este artículo demuestra cómo crear una factura de servicios."
author: mikefalkner
manager: AnnBe
ms.date: 05/29/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: e6f89a6d77ff8e1cd88632df0d9a72915086ee1e
ms.contentlocale: es-es
ms.lasthandoff: 08/07/2018

---

# <a name="create-a-free-text-invoice"></a><span data-ttu-id="5298a-103">Crear una factura de servicios</span><span class="sxs-lookup"><span data-stu-id="5298a-103">Create a free text invoice</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5298a-104">Este artículo demuestra cómo crear una factura de servicios.</span><span class="sxs-lookup"><span data-stu-id="5298a-104">This article demonstrates how to create a free text invoice.</span></span> <span data-ttu-id="5298a-105">Para este procedimiento, utilice la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="5298a-105">For this procedure, use the USMF demo company.</span></span>

## <a name="create-a-free-text-invoice"></a><span data-ttu-id="5298a-106">Crear una factura de servicios</span><span class="sxs-lookup"><span data-stu-id="5298a-106">Create a free text invoice</span></span>

1. <span data-ttu-id="5298a-107">Vaya a Clientes > Facturas > Todas las facturas de servicios.</span><span class="sxs-lookup"><span data-stu-id="5298a-107">Go to Accounts receivable > Invoices > All free text invoices.</span></span>
2. <span data-ttu-id="5298a-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="5298a-108">Click New.</span></span>
3. <span data-ttu-id="5298a-109">En el campo Cuenta de cliente, seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="5298a-109">In the Customer account field, select a value.</span></span>
    * <span data-ttu-id="5298a-110">La cuenta de facturación cambiará de forma predeterminada a la misma cuenta utilizada para la cuenta de cliente.</span><span class="sxs-lookup"><span data-stu-id="5298a-110">The invoice account will default to the same account used for the customer account.</span></span>   
    * <span data-ttu-id="5298a-111">El estado de la contabilidad comienza en proceso si la factura no se registra.</span><span class="sxs-lookup"><span data-stu-id="5298a-111">The accounting status starts with In process if the invoice is not posted.</span></span>   
    * <span data-ttu-id="5298a-112">El número de factura se asignará al registrar la factura.</span><span class="sxs-lookup"><span data-stu-id="5298a-112">The invoice number will be assigned when the invoice is posted.</span></span>  
    * <span data-ttu-id="5298a-113">Si está usando las órdenes de SEPA, la orden de débito directo se rellenará automáticamente con una orden cuando seleccione la cuenta de cliente.</span><span class="sxs-lookup"><span data-stu-id="5298a-113">If you are using SEPA mandates, the direct debit mandate will be automatically populated with a mandate when you select the customer account.</span></span>  
4. <span data-ttu-id="5298a-114">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="5298a-114">In the Description field, type a value.</span></span>
5. <span data-ttu-id="5298a-115">En el campo Cuenta principal, especifique un número de cuenta sin dimensiones.</span><span class="sxs-lookup"><span data-stu-id="5298a-115">In the Main account field, specify an account number without dimensions.</span></span>
    * <span data-ttu-id="5298a-116">También puede especificar uno o varios caracteres para la cuenta principal y usar la búsqueda para encontrar su cuenta.</span><span class="sxs-lookup"><span data-stu-id="5298a-116">You can also enter one or more characters for the main account and use the lookup to find your account.</span></span> <span data-ttu-id="5298a-117">Especificará las dimensiones más tarde en esta guía.</span><span class="sxs-lookup"><span data-stu-id="5298a-117">You will enter dimensions later on in this guide.</span></span>  
6. <span data-ttu-id="5298a-118">Expanda la ficha desplegable Detalles de línea para poder agregar dimensiones en su cuenta principal.</span><span class="sxs-lookup"><span data-stu-id="5298a-118">Expand the Line details fasttab so you can add dimensions to your main account.</span></span>
7. <span data-ttu-id="5298a-119">Haga clic en la pestaña Línea de dimensiones financieras.</span><span class="sxs-lookup"><span data-stu-id="5298a-119">Click the Financial dimensions line tab.</span></span>
    * <span data-ttu-id="5298a-120">Las dimensiones solo son para la línea seleccionada.</span><span class="sxs-lookup"><span data-stu-id="5298a-120">The dimensions are for the selected line only.</span></span>    
    * <span data-ttu-id="5298a-121">Se rellena el grupo de impuestos del cliente.</span><span class="sxs-lookup"><span data-stu-id="5298a-121">The sales tax group is populated from the customer.</span></span> <span data-ttu-id="5298a-122">Si el cliente no tiene un grupo de impuestos, se usará el grupo de impuestos de la cuenta principal.</span><span class="sxs-lookup"><span data-stu-id="5298a-122">If the customer does not have a sales tax group, the sales tax group from the main account is used.</span></span>  
    * <span data-ttu-id="5298a-123">El grupo de impuestos de artículos se rellena desde la cuenta principal.</span><span class="sxs-lookup"><span data-stu-id="5298a-123">The items sales tax group is populated from the main account.</span></span> <span data-ttu-id="5298a-124">Si la cuenta principal no tiene un grupo de impuestos de artículos, se usa el grupo de impuestos de artículos de los parámetros de impuestos de contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="5298a-124">If the main account does not have an item sales tax group, then the item sales tax group in the General ledger sales tax parameters is used.</span></span>    
8. <span data-ttu-id="5298a-125">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="5298a-125">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="5298a-126">La cantidad es opcional.</span><span class="sxs-lookup"><span data-stu-id="5298a-126">The quantity is optional.</span></span>  
9. <span data-ttu-id="5298a-127">En el campo Precio unitario, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="5298a-127">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="5298a-128">El precio unitario es opcional.</span><span class="sxs-lookup"><span data-stu-id="5298a-128">The unit price is optional.</span></span>  
    * <span data-ttu-id="5298a-129">El importe se calcula como cantidad por el precio unitario.</span><span class="sxs-lookup"><span data-stu-id="5298a-129">The amount is calculated as the quantity times the unit price.</span></span> <span data-ttu-id="5298a-130">Sin embargo, puede reemplazar dicho cálculo y especificar un importe.</span><span class="sxs-lookup"><span data-stu-id="5298a-130">However, you can override that calculation and enter an amount.</span></span>  
10. <span data-ttu-id="5298a-131">Haga clic en Impuestos para ver los impuestos calculados para la factura.</span><span class="sxs-lookup"><span data-stu-id="5298a-131">Click on Sales tax to view the sales tax calculated for your invoice.</span></span>
    * <span data-ttu-id="5298a-132">Vea los importes de impuestos en esta página o reemplace los importes en la ficha Ajuste.</span><span class="sxs-lookup"><span data-stu-id="5298a-132">View the sales tax amounts in this page or you can override the amounts on the Adjustment tab.</span></span>  
11. <span data-ttu-id="5298a-133">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="5298a-133">Click OK.</span></span>
12. <span data-ttu-id="5298a-134">Haga clic en los gastos para agregar un gasto a la factura.</span><span class="sxs-lookup"><span data-stu-id="5298a-134">Click Charges to add a charge to your invoice.</span></span> 
13. <span data-ttu-id="5298a-135">En el campo Código de gastos, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="5298a-135">In the Charges code field, type a value.</span></span>
14. <span data-ttu-id="5298a-136">En el campo Valor de gastos, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="5298a-136">In the Charges value field, enter a number.</span></span>
15. <span data-ttu-id="5298a-137">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="5298a-137">Close the page.</span></span>
16. <span data-ttu-id="5298a-138">Haga clic en Totales para ver los detalles y los totales resumidos de la factura.</span><span class="sxs-lookup"><span data-stu-id="5298a-138">Click Totals to view the summary invoice details and totals.</span></span>
17. <span data-ttu-id="5298a-139">Haga clic en Cerrar.</span><span class="sxs-lookup"><span data-stu-id="5298a-139">Click Close.</span></span>
18. <span data-ttu-id="5298a-140">Haga clic en Registrar para registrar la factura.</span><span class="sxs-lookup"><span data-stu-id="5298a-140">Click Post to post the invoice.</span></span> <span data-ttu-id="5298a-141">Podrá cancelar antes de registrar.</span><span class="sxs-lookup"><span data-stu-id="5298a-141">You will be able to cancel before you post.</span></span>
    * <span data-ttu-id="5298a-142">Para cambiar la hora de la impresión de facturas: seleccione Actual para imprimir cada factura cuando se actualiza o seleccione Posterior para imprimir una vez que se hayan actualizado todas las facturas.</span><span class="sxs-lookup"><span data-stu-id="5298a-142">To change the timing of your invoice printing:  Select Current to print each invoice as it is updated   or  Select After to print after all invoices have been updated.</span></span>  
    * <span data-ttu-id="5298a-143">Si desea cambiar la manera en que se comprueba el límite de crédito del cliente antes de registrar, cambie el tipo de límite de crédito.</span><span class="sxs-lookup"><span data-stu-id="5298a-143">If you want to change how the customer's credit limit is checked before posting, change the Credit limit type.</span></span>  
    * <span data-ttu-id="5298a-144">Si desea imprimir la factura, seleccione Sí.</span><span class="sxs-lookup"><span data-stu-id="5298a-144">If you want to print the invoice, select Yes.</span></span>  
    * <span data-ttu-id="5298a-145">Si desea registrar la factura, seleccione Sí.</span><span class="sxs-lookup"><span data-stu-id="5298a-145">If you want to post the invoice, select Yes.</span></span> <span data-ttu-id="5298a-146">Puede imprimir la factura sin registrarla.</span><span class="sxs-lookup"><span data-stu-id="5298a-146">You can print the invoice without posting.</span></span>  
19. <span data-ttu-id="5298a-147">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="5298a-147">Click OK.</span></span>

## <a name="copy-lines"></a><span data-ttu-id="5298a-148">Copiar líneas</span><span class="sxs-lookup"><span data-stu-id="5298a-148">Copy lines</span></span>
<span data-ttu-id="5298a-149">Para copiar líneas en la factura de servicios, seleccione una o varias líneas y, a continuación, haga clic en Copiar líneas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="5298a-149">To copy lines on the free text invoice, select one or more lines and then click Copy selected lines.</span></span> <span data-ttu-id="5298a-150">Puede especificar el número de copias que desea realizar y también puede copiar notas y archivos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="5298a-150">You can specify the number of copies that you want to make, and you can also copy notes and attachments.</span></span> <span data-ttu-id="5298a-151">Puede copiar las distribuciones o permitir que se vuelvan a crear al registrarlas.</span><span class="sxs-lookup"><span data-stu-id="5298a-151">You can copy the distributions or allow them to be recreated when you post.</span></span> <span data-ttu-id="5298a-152">Una vez que copie las líneas, puede editar la información si es necesario.</span><span class="sxs-lookup"><span data-stu-id="5298a-152">Once you copy the lines, you can edit the information as needed.</span></span> 

## <a name="create-a-free-text-invoice-from-a-template"></a><span data-ttu-id="5298a-153">Crear una factura de servicios a partir de una plantilla</span><span class="sxs-lookup"><span data-stu-id="5298a-153">Create a free text invoice from a template</span></span>
<span data-ttu-id="5298a-154">Puede crear una factura de servicios a partir de una plantilla.</span><span class="sxs-lookup"><span data-stu-id="5298a-154">You can create a free text invoice from a template.</span></span> <span data-ttu-id="5298a-155">Cuando seleccione Nueva a partir de plantilla desde la pestaña Factura, puede seleccionar un nombre de plantilla y la cuenta del cliente para la nueva factura de servicios.</span><span class="sxs-lookup"><span data-stu-id="5298a-155">When you select New from template from the Invoice tab, you can select a template name and the customer account for the new free text invoice.</span></span> <span data-ttu-id="5298a-156">También puede elegir valores predeterminados como las condiciones de pago y el método de pago del cliente o utilizar los valores que se guardaron con la plantilla.</span><span class="sxs-lookup"><span data-stu-id="5298a-156">You can also choose to default values such as the terms of payment and method of payment from the customer or use the values that were saved with the template.</span></span> <span data-ttu-id="5298a-157">Se creará una nueva plantilla de servicios y puede editar los valores en esa factura.</span><span class="sxs-lookup"><span data-stu-id="5298a-157">A new free text invoice will be created and you can edit the values in that invoice.</span></span> 


