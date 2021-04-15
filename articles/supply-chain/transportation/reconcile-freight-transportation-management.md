---
title: Conciliar el flete en la administración del transporte
description: En este tema se describe el proceso de conciliación de flete.
author: MarkusFogelberg
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSAuditMaster, TMSFreightBillInvoiceReconcile, TMSFreightBillSummary, TMSFreightBillType, TMSFreightMatchReason, TMSFBDetailReconcile, TMSInvoiceTable,TMSInvoiceLineReconcile,TMSReconcileInvoice, TMSFreightBillDetail, TMSFreightBillTypeAssignment, TMSRejectInvoiceLine, TMSMiscellaneousCharge
audience: Application User
ms.reviewer: kamaybac
ms.custom: 89983
ms.assetid: bc34a9b1-0c11-4797-b463-25409cf98ca8
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d523af235d645bd282af07d6a1f617bca5fba2dc
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809095"
---
# <a name="reconcile-freight-in-transportation-management"></a><span data-ttu-id="0a65a-103">Conciliar el flete en la administración del transporte</span><span class="sxs-lookup"><span data-stu-id="0a65a-103">Reconcile freight in transportation management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0a65a-104">En este tema se describe el proceso de conciliación de flete.</span><span class="sxs-lookup"><span data-stu-id="0a65a-104">This topic describes the freight reconciliation process.</span></span>

<span data-ttu-id="0a65a-105">La conciliación de flete se puede realizar manualmente o se puede configurar para que se produzca automáticamente.</span><span class="sxs-lookup"><span data-stu-id="0a65a-105">Freight reconciliation can be done manually, or it can be set up to occur automatically.</span></span> <span data-ttu-id="0a65a-106">Para usar la conciliación de flete automático, debe configurar un maestro de auditoría donde pueda definir los criterios que determinan qué albaranes de flete se concilian automáticamente.</span><span class="sxs-lookup"><span data-stu-id="0a65a-106">To use automatic freight reconciliation, you must set up an audit master where you can define criteria that determine which freight bills are matched automatically.</span></span>

## <a name="the-freight-reconciliation-process"></a><span data-ttu-id="0a65a-107">El proceso de conciliación de flete</span><span class="sxs-lookup"><span data-stu-id="0a65a-107">The freight reconciliation process</span></span>

<span data-ttu-id="0a65a-108">Las tasas de flete se calculan por el motor de velocidad que está asociado al transportista de envío pertinente.</span><span class="sxs-lookup"><span data-stu-id="0a65a-108">Freight rates are calculated by the rate engine that is associated with the relevant shipping carrier.</span></span> <span data-ttu-id="0a65a-109">Cuando se confirma una carga, se genera un albarán de flete y las tasas de flete se transfieren a él.</span><span class="sxs-lookup"><span data-stu-id="0a65a-109">When a load is confirmed, a freight bill is generated, and the freight rates are transferred to it.</span></span> <span data-ttu-id="0a65a-110">Las tasas de flete se distribuyen como gastos varios al documento de origen pertinente (pedido de compra, pedido de ventas o pedido de transferencia), en función de la configuración que se utiliza para el proceso de facturación normal.</span><span class="sxs-lookup"><span data-stu-id="0a65a-110">The freight rates are apportioned as miscellaneous charges to the relevant source document (purchase order, sales order, and/or transfer order), depending on the setup that is used for the regular billing process.</span></span> <span data-ttu-id="0a65a-111">El proceso de conciliación de flete (que también se conoce como el proceso de conciliación) puede iniciarse tan pronto como llega la factura de flete del transportista de envío.</span><span class="sxs-lookup"><span data-stu-id="0a65a-111">The freight reconciliation process (which is also known as the matching process) can start as soon as the freight invoice arrives from the shipping carrier.</span></span> <span data-ttu-id="0a65a-112">La factura se puede recibir de manera electrónica o en papel.</span><span class="sxs-lookup"><span data-stu-id="0a65a-112">The invoice can be received electronically or on paper.</span></span> <span data-ttu-id="0a65a-113">Si la factura en papel se recibe, puede generar una factura electrónica mediante el albarán de flete como plantilla.</span><span class="sxs-lookup"><span data-stu-id="0a65a-113">If the invoice is received on paper, you can generate an electronic invoice by using the freight bill as a template.</span></span>

<span data-ttu-id="0a65a-114">[![Proceso de conciliación de flete](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)</span><span class="sxs-lookup"><span data-stu-id="0a65a-114">[![Freight reconciliation process](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)</span></span>

## <a name="manual-reconciliation"></a><span data-ttu-id="0a65a-115">Conciliación manual</span><span class="sxs-lookup"><span data-stu-id="0a65a-115">Manual reconciliation</span></span>

<span data-ttu-id="0a65a-116">Si está conciliando el flete manualmente, deben conciliar cada línea de factura con la línea o líneas del albarán de flete para la carga que se factura.</span><span class="sxs-lookup"><span data-stu-id="0a65a-116">If you're reconciling freight manually, you must match each invoice line with the freight bill line or lines for the load that is being invoiced.</span></span> <span data-ttu-id="0a65a-117">Esto se hace conciliando en la página **Conciliación de albaranes de flete y facturas**.</span><span class="sxs-lookup"><span data-stu-id="0a65a-117">You do this matching on the **Freight bill and invoice matching** page.</span></span> <span data-ttu-id="0a65a-118">Si el importe de la línea de factura no coincide con el importe del albarán de flete, debe seleccionar un motivo de conciliación para la diferencia.</span><span class="sxs-lookup"><span data-stu-id="0a65a-118">If the amount on the invoice line doesn’t match the freight bill amount, you must select a reconciliation reason for the difference.</span></span> <span data-ttu-id="0a65a-119">Si hay varios motivos para la conciliación, puede dividir el importe no conciliado entre ellos.</span><span class="sxs-lookup"><span data-stu-id="0a65a-119">If there are multiple reasons for reconciliation, you can split the unmatched amount across them.</span></span> <span data-ttu-id="0a65a-120">El motivo de conciliación determina cómo se registran los importes de diferencia en la contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="0a65a-120">The reconciliation reason determines how the difference amounts are posted in the general ledger.</span></span> <span data-ttu-id="0a65a-121">Cuando se contabiliza la conciliación de todo el importe de la factura, se envía para aprobación y, a continuación, se registra el diario.</span><span class="sxs-lookup"><span data-stu-id="0a65a-121">When the reconciliation of the whole invoice amount is accounted for, it's submitted for approval, and then the journal is posted.</span></span> <span data-ttu-id="0a65a-122">En la ilustración siguiente se muestra cómo generar una factura de flete y realizar la conciliación de flete.</span><span class="sxs-lookup"><span data-stu-id="0a65a-122">The following illustration shows how to generate a freight invoice and do freight reconciliation.</span></span>

<span data-ttu-id="0a65a-123">[![Tareas de conciliación de flete](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)</span><span class="sxs-lookup"><span data-stu-id="0a65a-123">[![Freight reconciliation tasks](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)</span></span>

## <a name="automatic-reconciliation"></a><span data-ttu-id="0a65a-124">Conciliación automática</span><span class="sxs-lookup"><span data-stu-id="0a65a-124">Automatic reconciliation</span></span>

<span data-ttu-id="0a65a-125">Para utilizar la conciliación automática, debe especificar la programación de conciliación y las facturas y los transportistas de envío que se utilizarán.</span><span class="sxs-lookup"><span data-stu-id="0a65a-125">To use automatic reconciliation, you must specify the schedule for reconciliation, and the invoices and shipping carriers to use.</span></span> <span data-ttu-id="0a65a-126">La conciliación de las líneas de factura y los albaranes de flete se realiza según la configuración del tipo de albarán de flete y el maestro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="0a65a-126">The matching of the invoice lines and freight bills is done according to the setup of the audit master and freight bill type.</span></span> <span data-ttu-id="0a65a-127">Tras la ejecución de la conciliación automática, debe controlar todas las facturas que el sistema no puede conciliar.</span><span class="sxs-lookup"><span data-stu-id="0a65a-127">After you run the automatic reconciliation, you must handle any invoices that the system can't match.</span></span> <span data-ttu-id="0a65a-128">A continuación, debe procesar estas facturas manualmente para poder registrar todas las facturas para el pago.</span><span class="sxs-lookup"><span data-stu-id="0a65a-128">You must then process these invoices manually before you can post all the invoices for payment.</span></span>

## <a name="match-freight-bills-with-freight-invoices-using-automatic-or-manual-reconciliation"></a><span data-ttu-id="0a65a-129">Haga coincidir las facturas de flete con las facturas de flete mediante la conciliación automática o manual</span><span class="sxs-lookup"><span data-stu-id="0a65a-129">Match freight bills with freight invoices using automatic or manual reconciliation</span></span>

<span data-ttu-id="0a65a-130">*Matching* es el proceso de encontrar las facturas de flete que corresponden a cada factura de flete.</span><span class="sxs-lookup"><span data-stu-id="0a65a-130">*Matching* is the process of finding the freight bills that correspond to each freight invoice.</span></span> <span data-ttu-id="0a65a-131">Esto se puede hacer haciendo coincidir las líneas de la factura una por una (comparación manual) o haciendo coincidir todas las facturas disponibles a la vez (coincidencia automática).</span><span class="sxs-lookup"><span data-stu-id="0a65a-131">This can be done by matching the invoice lines one-by-one (manual matching), or by matching all available invoices at once (auto matching).</span></span>

### <a name="auto-matching"></a><span data-ttu-id="0a65a-132">Coincidencia automática</span><span class="sxs-lookup"><span data-stu-id="0a65a-132">Auto matching</span></span>

<span data-ttu-id="0a65a-133">Al hacer coincidir varias facturas de flete con la misma factura de flete, el proceso de coincidencia automática funciona de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="0a65a-133">When matching multiple freight invoices to the same freight bill, the process for auto matching works as follows:</span></span>

1. <span data-ttu-id="0a65a-134">Todas las facturas de flete no igualadas se clasifican por monto, con el monto mayor primero.</span><span class="sxs-lookup"><span data-stu-id="0a65a-134">All freight invoices not matched are sorted by amount, with largest amount first.</span></span>
1. <span data-ttu-id="0a65a-135">Las facturas de flete se comparan una por una, hasta que la factura de flete no tenga un monto positivo restante.</span><span class="sxs-lookup"><span data-stu-id="0a65a-135">The freight invoices are matched one-by-one, until the freight bill has no positive amount remaining.</span></span>
1. <span data-ttu-id="0a65a-136">Según la configuración del maestro de auditoría y el monto restante en las facturas de flete, se establece el monto restante.</span><span class="sxs-lookup"><span data-stu-id="0a65a-136">Depending on the setup of the audit master and the remaining amount on the freight invoices, the remaining amount is set.</span></span>

### <a name="manual-matching"></a><span data-ttu-id="0a65a-137">Conciliación manual</span><span class="sxs-lookup"><span data-stu-id="0a65a-137">Manual matching</span></span>

<span data-ttu-id="0a65a-138">Todas las facturas de flete con montos positivos estarán disponibles para coincidir.</span><span class="sxs-lookup"><span data-stu-id="0a65a-138">All freight bills with positive amounts will be available for matching.</span></span> <span data-ttu-id="0a65a-139">De forma similar a la comparación automática, el usuario solo podrá hacer coincidir las facturas de flete con montos negativos con las facturas de flete que no coincidan completamente.</span><span class="sxs-lookup"><span data-stu-id="0a65a-139">Similar to auto matching, the user will only be able to match freight invoices with negative amounts to freight bills not fully matched.</span></span>

### <a name="example"></a><span data-ttu-id="0a65a-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0a65a-140">Example</span></span>

<span data-ttu-id="0a65a-141">Suponga que tiene una factura de flete (FB) por un monto de 1500 y ha creado tres facturas de flete para la factura de flete con una línea de factura para cada factura con las siguientes configuraciones:</span><span class="sxs-lookup"><span data-stu-id="0a65a-141">Suppose that you have a freight bill (FB) for an amount of 1500 and you have created three freight invoices for the freight bill with one invoice line for each invoice with following settings:</span></span>

- <span data-ttu-id="0a65a-142">Factura de flete original (FB): Monto 1500</span><span class="sxs-lookup"><span data-stu-id="0a65a-142">Original freight bill (FB): Amount 1500</span></span>
- <span data-ttu-id="0a65a-143">Factura 1 (Inv1): Importe 1000</span><span class="sxs-lookup"><span data-stu-id="0a65a-143">Invoice 1 (Inv1): Amount 1000</span></span>
- <span data-ttu-id="0a65a-144">Factura 2 (Inv2): Importe 600</span><span class="sxs-lookup"><span data-stu-id="0a65a-144">Invoice 2 (Inv2): Amount 600</span></span>
- <span data-ttu-id="0a65a-145">Factura 3 (Inv3): Importe -100</span><span class="sxs-lookup"><span data-stu-id="0a65a-145">Invoice 3 (Inv3): Amount -100</span></span>

#### <a name="automatic-matching-result"></a><span data-ttu-id="0a65a-146">Resultado de coincidencia automático</span><span class="sxs-lookup"><span data-stu-id="0a65a-146">Automatic matching result</span></span>

<span data-ttu-id="0a65a-147">La coincidencia automática se ejecutará en el siguiente orden:</span><span class="sxs-lookup"><span data-stu-id="0a65a-147">Auto matching will execute in following order:</span></span>

1. <span data-ttu-id="0a65a-148">Ordene todas las facturas de flete descendiendo por monto: Inv1 -> Inv2 -> Inv3.</span><span class="sxs-lookup"><span data-stu-id="0a65a-148">Sort all freight invoices descending by amount: Inv1 -> Inv2 -> Inv3.</span></span>
1. <span data-ttu-id="0a65a-149">Haga coincidir Inv1 con FB.</span><span class="sxs-lookup"><span data-stu-id="0a65a-149">Match Inv1 with FB.</span></span> <span data-ttu-id="0a65a-150">Inv1 tiene 1000 coincidente y FB tiene 500 como importe restante, por lo que el estado se establece en *Parcialmente emparejado*.</span><span class="sxs-lookup"><span data-stu-id="0a65a-150">Inv1 has 1000 matched and FB has 500 amount remaining, so the status is set to *Partially matched*.</span></span>
1. <span data-ttu-id="0a65a-151">Haga coincidir Inv2 con FB.</span><span class="sxs-lookup"><span data-stu-id="0a65a-151">Match Inv2 with FB.</span></span> <span data-ttu-id="0a65a-152">Inv2 tiene 500 coincidente y FB tiene 0 como importe restante, por lo que el estado se establece en *Completamente emparejado*.</span><span class="sxs-lookup"><span data-stu-id="0a65a-152">Inv2 has 500 matched and FB has 0 remaining, so the status is set to *Fully matched*.</span></span>
1. <span data-ttu-id="0a65a-153">Debido a que FB ahora está completamente emparejado, Inv3 no se procesará.</span><span class="sxs-lookup"><span data-stu-id="0a65a-153">Because FB is now fully matched, Inv3 won't be processed.</span></span>

#### <a name="manual-matching-result"></a><span data-ttu-id="0a65a-154">Resultado de coincidencia manual</span><span class="sxs-lookup"><span data-stu-id="0a65a-154">Manual matching result</span></span>

<span data-ttu-id="0a65a-155">Para la coincidencia manual, los resultados varían según el orden de la coincidencia, como se ilustra en los siguientes casos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0a65a-155">For manual matching, the results vary depending on the order of the matching, as illustrated in the following example cases.</span></span>

##### <a name="manual-matching-case-1"></a><span data-ttu-id="0a65a-156">Caso de correspondencia manual 1</span><span class="sxs-lookup"><span data-stu-id="0a65a-156">Manual matching case 1</span></span>

<span data-ttu-id="0a65a-157">Una forma de hacer la coincidencia manual para este ejemplo es proceder de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="0a65a-157">One way to do manual matching for this example is to proceed as follows:</span></span>

1. <span data-ttu-id="0a65a-158">Haga coincidir FB con Inv1.</span><span class="sxs-lookup"><span data-stu-id="0a65a-158">Match FB with Inv1.</span></span> <span data-ttu-id="0a65a-159">FB tiene un importe de 500 restante, por lo que el estado se establece en *Parcialmente emparejado*.</span><span class="sxs-lookup"><span data-stu-id="0a65a-159">FB has 500 amount remaining, so the status set to *Partially matched*.</span></span>
1. <span data-ttu-id="0a65a-160">Haga coincidir Inv2 con FB.</span><span class="sxs-lookup"><span data-stu-id="0a65a-160">Match Inv2 with FB.</span></span> <span data-ttu-id="0a65a-161">Inv2 tiene 500 coincidente y FB tiene 0 como importe restante, por lo que el estado se establece en *Completamente emparejado*.</span><span class="sxs-lookup"><span data-stu-id="0a65a-161">Inv2 has 500 matched and FB has 0 remaining, so the status is set to *Fully matched*.</span></span>
1. <span data-ttu-id="0a65a-162">Cuando haga coincidir Inv3 manualmente, no encontrará facturas de flete incomparables.</span><span class="sxs-lookup"><span data-stu-id="0a65a-162">When manually matching Inv3, you won't find any unmatched freight bills.</span></span>

<span data-ttu-id="0a65a-163">Este caso es esencialmente el mismo que la coincidencia automática</span><span class="sxs-lookup"><span data-stu-id="0a65a-163">This case is essentially the same as auto matching</span></span>

##### <a name="manual-matching-case-2"></a><span data-ttu-id="0a65a-164">Caso de correspondencia manual 2</span><span class="sxs-lookup"><span data-stu-id="0a65a-164">Manual matching case 2</span></span>

<span data-ttu-id="0a65a-165">Otra forma de hacer la coincidencia manual para este ejemplo es proceder de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="0a65a-165">Another way to do manual matching for this example is to proceed as follows:</span></span>

1. <span data-ttu-id="0a65a-166">Haga coincidir Inv3 con FB.</span><span class="sxs-lookup"><span data-stu-id="0a65a-166">Match Inv3 with FB.</span></span> <span data-ttu-id="0a65a-167">Ahora FB tiene una cantidad restante de 1600, que es lo mismo que restar 100 negativo sobre 1500.</span><span class="sxs-lookup"><span data-stu-id="0a65a-167">Now FB has amount remaining 1600, which is the same as subtracting negative 100 on top of 1500.</span></span> <span data-ttu-id="0a65a-168">Tanto FB como Inv3 tienen una cantidad equivalente de -100.</span><span class="sxs-lookup"><span data-stu-id="0a65a-168">Both FB and Inv3 have a matched quantity of -100.</span></span>
1. <span data-ttu-id="0a65a-169">Haga coincidir Inv1 e Inv 2 con FB uno tras otro.</span><span class="sxs-lookup"><span data-stu-id="0a65a-169">Match Inv1 and Inv 2 with FB one after another.</span></span> <span data-ttu-id="0a65a-170">FB está completamente coincidente.</span><span class="sxs-lookup"><span data-stu-id="0a65a-170">FB is fully matched.</span></span>

<span data-ttu-id="0a65a-171">Como muestra este ejemplo, las facturas de flete coincidentes con importes negativos solo deben realizarse manualmente.</span><span class="sxs-lookup"><span data-stu-id="0a65a-171">As this example shows, matching freight invoices with negative amounts should only be done manually.</span></span> <span data-ttu-id="0a65a-172">Esto garantizará que siempre sea posible hacer coincidir las facturas de flete con importes negativos con una factura de flete que no coincida completamente porque eso le permite controlar la secuencia de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="0a65a-172">This will ensure that it is always possible to match the freight invoices with negative amounts to a freight bill not fully matched because that enables you to control the matching sequence.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]