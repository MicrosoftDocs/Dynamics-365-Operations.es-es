---
title: Crear una factura de servicios
description: Este tema explica cómo crear facturas de texto sin formato.
author: mikefalkner
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: caebd0ba0a3863920c165e1c6a61be35bcaf1e44
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833194"
---
# <a name="create-a-free-text-invoice"></a><span data-ttu-id="833d1-103">Crear una factura de servicios</span><span class="sxs-lookup"><span data-stu-id="833d1-103">Create a free text invoice</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="833d1-104">Este tema explica cómo crear facturas de texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="833d1-104">This topic explains how to create free text invoices.</span></span> <span data-ttu-id="833d1-105">Para el procedimiento, utilice la empresa de demostración **USMF**.</span><span class="sxs-lookup"><span data-stu-id="833d1-105">For the procedure, use the **USMF** demo company.</span></span>

## <a name="create-a-free-text-invoice"></a><span data-ttu-id="833d1-106">Crear una factura de servicio</span><span class="sxs-lookup"><span data-stu-id="833d1-106">Create a free text invoice</span></span>

1. <span data-ttu-id="833d1-107">Vaya a **Clientes (o libro mayor de ventas) \> Facturas \> Todas las facturas de servicios**.</span><span class="sxs-lookup"><span data-stu-id="833d1-107">Go to **Accounts receivable (or Sales Ledger) \> Invoices \> All free text invoices**.</span></span>
2. <span data-ttu-id="833d1-108">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="833d1-108">Select **New**.</span></span>
3. <span data-ttu-id="833d1-109">En el campo **Cuenta de cliente**, seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="833d1-109">In the **Customer account** field, select a value.</span></span>

    * <span data-ttu-id="833d1-110">De forma predeterminada, la cuenta que se selecciona como cuenta de cliente es utilizada como la cuenta de facturación.</span><span class="sxs-lookup"><span data-stu-id="833d1-110">By default, the account that is selected as the customer account is used as the invoice account.</span></span>
    * <span data-ttu-id="833d1-111">Si no se registra la factura, el estado de contabilidad comienza con **En proceso**.</span><span class="sxs-lookup"><span data-stu-id="833d1-111">If the invoice isn't posted, the accounting status starts with **In process**.</span></span>
    * <span data-ttu-id="833d1-112">El número de factura se asignará al registrar la factura.</span><span class="sxs-lookup"><span data-stu-id="833d1-112">The invoice number will be assigned when the invoice is posted.</span></span>
    * <span data-ttu-id="833d1-113">Si está usando las órdenes de SEPA (Zona Única de Pagos en Euros), la orden de débito directo se rellenará automáticamente cuando seleccione la cuenta de cliente.</span><span class="sxs-lookup"><span data-stu-id="833d1-113">If you're using Single Euro Payments Area (SEPA) mandates, the direct debit mandate is automatically entered when you select the customer account.</span></span>

4. <span data-ttu-id="833d1-114">En el campo **Descripción**, especifique un valor.</span><span class="sxs-lookup"><span data-stu-id="833d1-114">In the **Description** field, enter a value.</span></span>
5. <span data-ttu-id="833d1-115">En el campo **Cuenta principal**, especifique un número de cuenta sin dimensiones.</span><span class="sxs-lookup"><span data-stu-id="833d1-115">In the **Main account** field, specify an account number that doesn't have dimensions.</span></span> <span data-ttu-id="833d1-116">Especificará dimensiones más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="833d1-116">You will enter dimensions later in this topic.</span></span>

    <span data-ttu-id="833d1-117">También puede especificar uno o varios caracteres para la cuenta principal y usar la búsqueda para encontrar la cuenta.</span><span class="sxs-lookup"><span data-stu-id="833d1-117">You can also enter one or more characters for the main account, and use the lookup to find the account.</span></span>

6. <span data-ttu-id="833d1-118">Seleccione la ficha desplegable **Detalles de línea** para agregar dimensiones a la cuenta principal.</span><span class="sxs-lookup"><span data-stu-id="833d1-118">Select the **Line details** FastTab to add dimensions to the main account.</span></span>
7. <span data-ttu-id="833d1-119">Seleccione la pestaña **Línea de dimensiones financieras**.</span><span class="sxs-lookup"><span data-stu-id="833d1-119">Select the **Financial dimensions line** tab.</span></span>

    * <span data-ttu-id="833d1-120">Las dimensiones solo son para la línea seleccionada.</span><span class="sxs-lookup"><span data-stu-id="833d1-120">The dimensions are for the selected line only.</span></span>
    * <span data-ttu-id="833d1-121">El grupo de impuestos se obtiene del cliente.</span><span class="sxs-lookup"><span data-stu-id="833d1-121">The sales tax group is filled in from the customer.</span></span> <span data-ttu-id="833d1-122">Si el cliente no tiene un grupo de impuestos, se usará el grupo de impuestos de la cuenta principal.</span><span class="sxs-lookup"><span data-stu-id="833d1-122">If the customer doesn't have a sales tax group, the sales tax group from the main account is used.</span></span>
    * <span data-ttu-id="833d1-123">El grupo de impuestos de artículos se rellena desde la cuenta principal.</span><span class="sxs-lookup"><span data-stu-id="833d1-123">The items sales tax group is filled in from the main account.</span></span> <span data-ttu-id="833d1-124">Si la cuenta principal no tiene un grupo de impuestos de artículos, se usa el grupo de impuestos de artículos que se especifica en los parámetros de impuestos de contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="833d1-124">If the main account doesn't have an item sales tax group, the item sales tax group that is specified in the sales tax parameters in General ledger is used.</span></span>

8. <span data-ttu-id="833d1-125">Opcional: en el campo **Cantidad**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="833d1-125">Optional: In the **Quantity** field, enter a number.</span></span>
9. <span data-ttu-id="833d1-126">Opcional: en el campo **Precio unitario**, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="833d1-126">Optional: In the **Unit price** field, enter a number.</span></span>

    <span data-ttu-id="833d1-127">El importe se calcula como cantidad por el precio unitario.</span><span class="sxs-lookup"><span data-stu-id="833d1-127">The amount is calculated as the quantity times the unit price.</span></span> <span data-ttu-id="833d1-128">Sin embargo, puede reemplazar dicho cálculo especificando un importe.</span><span class="sxs-lookup"><span data-stu-id="833d1-128">However, you can override that calculation by entering an amount.</span></span>

10. <span data-ttu-id="833d1-129">Seleccione **Impuestos** para ver los impuestos calculados para la factura.</span><span class="sxs-lookup"><span data-stu-id="833d1-129">Select **Sales tax** to view the sales tax that is calculated for the invoice.</span></span>

    <span data-ttu-id="833d1-130">Puede ver los importes de los impuestos en esta página o reemplazar los importes en la ficha **Ajuste**.</span><span class="sxs-lookup"><span data-stu-id="833d1-130">You can view the sales tax amounts on this page, or you can override the amounts on the **Adjustment** tab.</span></span>

11. <span data-ttu-id="833d1-131">Seleccionar **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="833d1-131">Select **OK**.</span></span>
12. <span data-ttu-id="833d1-132">Seleccione **Gastos** para añadir un gasto a la factura.</span><span class="sxs-lookup"><span data-stu-id="833d1-132">Select **Charges** to add a charge to the invoice.</span></span>
13. <span data-ttu-id="833d1-133">En el campo **Código de gastos**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="833d1-133">In the **Charges code** field, enter a value.</span></span>
14. <span data-ttu-id="833d1-134">En el campo **Valor de gastos**, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="833d1-134">In the **Charges value** field, enter a number.</span></span>
15. <span data-ttu-id="833d1-135">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="833d1-135">Close the page.</span></span>
16. <span data-ttu-id="833d1-136">Seleccione **Totales** para ver los detalles y los totales resumidos de la factura.</span><span class="sxs-lookup"><span data-stu-id="833d1-136">Select **Totals** to view a summary of the invoice details and totals.</span></span>
17. <span data-ttu-id="833d1-137">Seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="833d1-137">Select **Close**.</span></span>
18. <span data-ttu-id="833d1-138">Seleccione **Registrar** para registrar la factura.</span><span class="sxs-lookup"><span data-stu-id="833d1-138">Select **Post** to post the invoice.</span></span> <span data-ttu-id="833d1-139">Todavía tendrá una oportunidad de cancelar antes de registrar realmente.</span><span class="sxs-lookup"><span data-stu-id="833d1-139">You will still have an opportunity to cancel before you actually post.</span></span>

    * <span data-ttu-id="833d1-140">Puede cambiar el control de tiempo de la impresión de facturas.</span><span class="sxs-lookup"><span data-stu-id="833d1-140">You can change the timing of invoice printing.</span></span> <span data-ttu-id="833d1-141">Seleccionar **Actual** para imprimir cada factura según se actualiza.</span><span class="sxs-lookup"><span data-stu-id="833d1-141">Select **Current** to print each invoice as it's updated.</span></span> <span data-ttu-id="833d1-142">Seleccione **Posterior** para imprimir cuando todas las facturas estén actualizadas.</span><span class="sxs-lookup"><span data-stu-id="833d1-142">Select **After** to print after all invoices have been updated.</span></span>
    * <span data-ttu-id="833d1-143">Para cambiar cómo se comprueba el límite de crédito del cliente antes de registrar la factura, cambie el valor en el campo **Tipo de límite de crédito**.</span><span class="sxs-lookup"><span data-stu-id="833d1-143">To change how the customer's credit limit is verified before the invoice is posted, change the value in the **Credit limit type** field.</span></span>
    * <span data-ttu-id="833d1-144">Para imprimir la factura, establezca la opción en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="833d1-144">To print the invoice, set the option to **Yes**.</span></span>
    * <span data-ttu-id="833d1-145">Para registrar la factura, establezca la opción en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="833d1-145">To post the invoice, set the option to **Yes**.</span></span> <span data-ttu-id="833d1-146">Puede imprimir la factura sin registrarla.</span><span class="sxs-lookup"><span data-stu-id="833d1-146">You can print the invoice without posting it.</span></span>

19. <span data-ttu-id="833d1-147">Seleccionar **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="833d1-147">Select **OK**.</span></span>

## <a name="copy-lines"></a><span data-ttu-id="833d1-148">Copiar líneas</span><span class="sxs-lookup"><span data-stu-id="833d1-148">Copy lines</span></span>
<span data-ttu-id="833d1-149">Para copiar líneas en una factura de servicios, seleccione una o varias líneas y, a continuación, haga clic en **Copiar líneas seleccionadas**.</span><span class="sxs-lookup"><span data-stu-id="833d1-149">To copy lines on a free text invoice, select one or more lines, and then select **Copy selected lines**.</span></span> <span data-ttu-id="833d1-150">Puede especificar el número de copias que desea realizar y también puede copiar notas y archivos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="833d1-150">You can specify the number of copies to make, and you can also copy notes and attachments.</span></span> <span data-ttu-id="833d1-151">Puede copiar las distribuciones o permitir que se vuelvan a crear al registrarlas.</span><span class="sxs-lookup"><span data-stu-id="833d1-151">You can either copy the distributions or let them be re-created when you post.</span></span>

<span data-ttu-id="833d1-152">Una vez que copie las líneas, puede editar la información según sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="833d1-152">After you copy lines, you can edit the information as you require.</span></span>

## <a name="create-a-free-text-invoice-from-a-template"></a><span data-ttu-id="833d1-153">Crear una factura de servicios a partir de una plantilla</span><span class="sxs-lookup"><span data-stu-id="833d1-153">Create a free text invoice from a template</span></span>
<span data-ttu-id="833d1-154">Puede crear una factura de servicios a partir de una plantilla.</span><span class="sxs-lookup"><span data-stu-id="833d1-154">You can create a free text invoice from a template.</span></span> <span data-ttu-id="833d1-155">Cuando seleccione **Nueva a partir de plantilla** desde la pestaña **Factura**, puede seleccionar un nombre de plantilla y la cuenta del cliente para la nueva factura de servicios.</span><span class="sxs-lookup"><span data-stu-id="833d1-155">When you select **New from template** on the **Invoice** tab, you can select a template name and the customer account for the new free text invoice.</span></span> <span data-ttu-id="833d1-156">Los valores predeterminados como las condiciones de pago y el método de pago se pueden rellenar automáticamente a partir del cliente o utilizar los valores que se guardaron en la plantilla.</span><span class="sxs-lookup"><span data-stu-id="833d1-156">Default values, such as the terms of payment and method of payment, can be automatically filled in from the customer, or you can use the values that were saved in the template.</span></span>

<span data-ttu-id="833d1-157">Se creará una nueva factura de servicios y puede editar los valores según sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="833d1-157">A new free text invoice is created, and you can edit the values as you require.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]