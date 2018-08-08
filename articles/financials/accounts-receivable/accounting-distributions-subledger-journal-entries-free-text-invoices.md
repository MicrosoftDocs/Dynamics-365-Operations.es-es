---
title: Distribuciones contables y asientos del subdiario contable para las facturas de servicios
description: "Las distribuciones contables se usan para definir cómo se contabilizará un importe; por ejemplo, cómo se contabilizarán los ingresos, impuestos o gastos en una factura de servicios. Cada importe que se debe contabilizar cuando se registre la factura de servicios en el diario tendrá una o varias distribuciones contables."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 3141
ms.assetid: fecd17a2-d7b4-4a20-ac81-eb71abbfa9d1
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 5d1546e8537110daec5d6655f68d3328a58ca1cb
ms.contentlocale: es-es
ms.lasthandoff: 08/07/2018

---

# <a name="accounting-distributions-and-subledger-journal-entries-for-free-text-invoices"></a><span data-ttu-id="2ec0d-104">Distribuciones contables y asientos del subdiario contable para las facturas de servicios</span><span class="sxs-lookup"><span data-stu-id="2ec0d-104">Accounting distributions and subledger journal entries for free text invoices</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2ec0d-105">Las distribuciones contables se usan para definir cómo se contabilizará un importe; por ejemplo, cómo se contabilizarán los ingresos, impuestos o gastos en una factura de servicios.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-105">Accounting distributions are used to define how an amount will be accounted for, such as how the revenue, tax, or charges will be accounted for on a free text invoice.</span></span> <span data-ttu-id="2ec0d-106">Cada importe que se debe contabilizar cuando se registre la factura de servicios en el diario tendrá una o varias distribuciones contables.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-106">Every amount that must be accounted for when the free text invoice is journalized will have one or more accounting distributions.</span></span>

<a name="accounting-distributions"></a><span data-ttu-id="2ec0d-107">Distribuciones contables</span><span class="sxs-lookup"><span data-stu-id="2ec0d-107">Accounting distributions</span></span>
------------------------

<span data-ttu-id="2ec0d-108">Puede usar los siguientes botones de la página Factura de texto libre para ver y para modificar probablemente las distribuciones contables de cada importe de la factura de texto libre.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-108">You can use the following buttons in the Free text invoice page to view, and possibly change, the accounting distributions for each amount on the free text invoice.</span></span>

-   <span data-ttu-id="2ec0d-109">**Distribuir importes**: permite ver y cambiar las distribuciones contables de una línea individual y todas las líneas secundarias, como impuestos o gastos.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-109">**Distribute amounts**—View and change the accounting distributions for an individual line and any child lines, such as taxes or charges.</span></span> <span data-ttu-id="2ec0d-110">También puede ver y cambiar distribuciones contables para la línea secundaria directamente desde la página Transacciones de impuestos o la página Transacciones de gastos.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-110">You can also view and change the accounting distributions for the child line directly from the Sales tax transactions page or the Charges transactions page.</span></span>
    -   <span data-ttu-id="2ec0d-111">Permite cambiar importes de encabezado de factura de servicios, como gastos o importes de redondeo de divisa.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-111">Change free text invoice header amounts, such as charges or currency rounding amounts.</span></span>
    -   <span data-ttu-id="2ec0d-112">Cambie importes de líneas de facturas de texto libre.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-112">Change free text invoice line amounts.</span></span>
-   <span data-ttu-id="2ec0d-113">**Ver distribuciones**: permite ver las distribuciones contables para todas las líneas del documento.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-113">**View distributions**—View the accounting distributions for all lines on the document.</span></span> <span data-ttu-id="2ec0d-114">No se pueden cambiar las distribuciones contables desde esta vista.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-114">You can't change the accounting distributions from this view.</span></span>
    -   <span data-ttu-id="2ec0d-115">Permite ver los importes de línea y encabezado.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-115">View header and line amounts.</span></span>

## <a name="distributing-amounts"></a><span data-ttu-id="2ec0d-116">Distribución de importes</span><span class="sxs-lookup"><span data-stu-id="2ec0d-116">Distributing amounts</span></span>
<span data-ttu-id="2ec0d-117">Al introducir una factura de servicios, cada importe se va a distribuir de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-117">When you enter a free text invoice, each amount will be distributed as follows.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ec0d-118">Tipo de importe monetario</span><span class="sxs-lookup"><span data-stu-id="2ec0d-118">Type of monetary amount</span></span></th>
<th><span data-ttu-id="2ec0d-119">Desde dónde se muestra la cuenta principal</span><span class="sxs-lookup"><span data-stu-id="2ec0d-119">Where the main account is displayed from</span></span></th>
<th><span data-ttu-id="2ec0d-120">Orden de prioridad que determina que dimensión financiera se visualiza</span><span class="sxs-lookup"><span data-stu-id="2ec0d-120">Order of priority that determines which default financial dimension is displayed</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="2ec0d-121">Línea de factura de servicios</span><span class="sxs-lookup"><span data-stu-id="2ec0d-121">Free text invoice line</span></span></td>
<td><span data-ttu-id="2ec0d-122">La cuenta contable en la línea de factura de servicios.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-122">The ledger account on the free text invoice line.</span></span></td>
<td><ol>
<li><span data-ttu-id="2ec0d-123">Si la cuenta principal es una cuenta de asignación, use el valor predeterminado de la definición de cuenta de asignación.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-123">If the main account is an allocation account, use the default value from the allocation account definition.</span></span></li>
<li><span data-ttu-id="2ec0d-124">Si la cuenta principal no es una cuenta de asignación, use la plantilla predeterminada de dimensión financiera en la línea de factura de servicios.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-124">If the main account is not an allocation account, use the financial dimension default template on the free text invoice line.</span></span></li>
<li><span data-ttu-id="2ec0d-125">Use los valores de la dimensión financiera predeterminados en la línea de factura de servicios.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-125">Use the default financial dimension values on the free text invoice line.</span></span></li>
<li><span data-ttu-id="2ec0d-126">Use los valores de la dimensión financiera predeterminados de la cuenta contable en la página Plan de cuentas.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-126">Use the default financial dimension values from the ledger account in the Chart of accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2ec0d-127">Línea de factura de servicios para un número de activo fijo y una combinación de modelo de valor</span><span class="sxs-lookup"><span data-stu-id="2ec0d-127">Free text invoice line for a fixed asset number and value model combination</span></span>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><span data-ttu-id="2ec0d-128"><strong>Nota</strong></span><span class="sxs-lookup"><span data-stu-id="2ec0d-128"><strong>Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="2ec0d-129">La cuenta principal en la línea de factura de servicios será la primera cuenta de cancelación de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-129">The main account on the free text invoice line will be the fixed asset disposal account.</span></span></td>
</tr>
</tbody>
</table>
</div></td>
<td><span data-ttu-id="2ec0d-130">La cuenta contable en la línea de factura de servicios.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-130">The ledger account on the free text invoice line.</span></span></td>
<td><ol>
<li><span data-ttu-id="2ec0d-131">Use los valores de la dimensión financiera predeterminados en la línea de factura de servicios.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-131">Use the default financial dimension values on the free text invoice line.</span></span></li>
<li><span data-ttu-id="2ec0d-132">Use los valores de la dimensión financiera predeterminados de la cuenta contable en la página Plan de cuentas.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-132">Use the default financial dimension values from the ledger account in the Chart of accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="2ec0d-133">Importe de descuento de la factura de servicios</span><span class="sxs-lookup"><span data-stu-id="2ec0d-133">Free text invoice discount amount</span></span></td>
<td><span data-ttu-id="2ec0d-134">El campo Cuenta principal para descuentos de cliente en la página Descuentos por pronto pago.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-134">The Main account for customer discounts field in the Cash discounts page.</span></span></td>
<td><ol>
<li><span data-ttu-id="2ec0d-135">Si la cuenta principal es una cuenta de asignación, use el valor predeterminado de la definición de cuenta de asignación.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-135">If the main account is an allocation account, use the default value from the allocation account definition.</span></span></li>
<li><span data-ttu-id="2ec0d-136">Si la cuenta principal no es una cuenta de asignación, use la plantilla predeterminada de dimensión financiera en la línea de factura de servicios.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-136">If the main account is not an allocation account, use the financial dimension default template on the free text invoice line.</span></span></li>
<li><span data-ttu-id="2ec0d-137">Use los valores de la dimensión financiera predeterminados en la línea de factura de servicios.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-137">Use the default financial dimension values on the free text invoice line.</span></span></li>
<li><span data-ttu-id="2ec0d-138">Use los valores de la dimensión financiera predeterminados de la cuenta contable en la página Plan de cuentas.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-138">Use the default financial dimension values from the ledger account in the Chart of accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2ec0d-139">Importe de impuestos de la factura de servicios</span><span class="sxs-lookup"><span data-stu-id="2ec0d-139">Free text invoice sales tax amount</span></span></td>
<td><span data-ttu-id="2ec0d-140">El campo Impuestos repercutidos en la página Grupos de registro.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-140">The Sales tax payable field in the Ledger posting groups page.</span></span></td>
<td><ol>
<li><span data-ttu-id="2ec0d-141">Use las dimensiones financieras que se definen en el importe de línea de factura de servicios o las distribuciones del importe de la línea de gastos.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-141">Use the financial dimensions that are defined on the free text invoice line amount or the distributions for the charge line amount.</span></span></li>
<li><span data-ttu-id="2ec0d-142">Use los valores de la dimensión financiera predeterminados en la línea de factura de servicios.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-142">Use the default financial dimension values on the free text invoice line.</span></span></li>
<li><span data-ttu-id="2ec0d-143">Use los valores de la dimensión financiera predeterminados de la cuenta contable en la página Plan de cuentas.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-143">Use the default financial dimension values from the ledger account in the Chart of accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="2ec0d-144">Importe de línea de gastos de la factura de servicios</span><span class="sxs-lookup"><span data-stu-id="2ec0d-144">Free text invoice charge line amount</span></span></td>
<td><span data-ttu-id="2ec0d-145">El campo Cuenta de crédito en la página Código de gastos.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-145">The Credit account field in the Charges code page.</span></span></td>
<td><ol>
<li><span data-ttu-id="2ec0d-146">Si la cuenta principal es una cuenta de asignación, use el valor predeterminado de la definición de cuenta de asignación.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-146">If the main account is an allocation account, use the default value from the allocation account definition.</span></span></li>
<li><span data-ttu-id="2ec0d-147">Si la cuenta principal no es una cuenta de asignación, use la plantilla predeterminada de dimensión financiera en la línea de factura de servicios.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-147">If the main account is not an allocation account, use the financial dimension default template on the free text invoice line.</span></span></li>
<li><span data-ttu-id="2ec0d-148">Use los valores de la dimensión financiera predeterminados en la línea de factura de servicios.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-148">Use the default financial dimension values on the free text invoice line.</span></span></li>
<li><span data-ttu-id="2ec0d-149">Use los valores de la dimensión financiera predeterminados de la cuenta contable en la página Plan de cuentas.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-149">Use the default financial dimension values from the ledger account in the Chart of accounts page.</span></span></li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="distributing-taxes"></a><span data-ttu-id="2ec0d-150">Distribución de impuestos</span><span class="sxs-lookup"><span data-stu-id="2ec0d-150">Distributing taxes</span></span>
<span data-ttu-id="2ec0d-151">Las distribuciones contables para los impuestos no se pueden crear hasta que se calculen los impuestos.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-151">Accounting distributions for taxes cannot be created until taxes are calculated.</span></span> <span data-ttu-id="2ec0d-152">Para calcular los impuestos, debe completar una de las tareas que se describen a continuación en el formulario Factura de texto libre:</span><span class="sxs-lookup"><span data-stu-id="2ec0d-152">To calculate sales taxes, you must complete one of the following tasks in the Free text invoice form:</span></span>
-   <span data-ttu-id="2ec0d-153">Ver los impuestos.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-153">View the sales tax.</span></span>
-   <span data-ttu-id="2ec0d-154">Ver el total de la factura.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-154">View the invoice total.</span></span>
-   <span data-ttu-id="2ec0d-155">Ver el flujo de efectivo.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-155">View the cash flow.</span></span>
-   <span data-ttu-id="2ec0d-156">Ver las distribuciones contables de toda la factura de servicios.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-156">View accounting distributions for the whole free text invoice.</span></span>
-   <span data-ttu-id="2ec0d-157">Ver el subdiario contable.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-157">View the subledger journal.</span></span>

## <a name="subledger-journals-for-free-text-invoices"></a><span data-ttu-id="2ec0d-158">Subdiarios contables para facturas de servicios</span><span class="sxs-lookup"><span data-stu-id="2ec0d-158">Subledger journals for free text invoices</span></span>
<span data-ttu-id="2ec0d-159">Antes de registrar una factura de servicios, se debe visualizar el asiento contable completo de la factura, que incluye débitos y créditos, para verificar que la factura se está registrando en las cuentas correctas.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-159">Before you post a free text invoice, you can view the full accounting entry of the invoice, which includes debits and credits, to verify that the invoice is being posted to the correct accounts.</span></span> <span data-ttu-id="2ec0d-160">Esta visualización del asiento contable completo se denomina subdiario contable.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-160">This view of the full accounting entry is called a subledger journal.</span></span> <span data-ttu-id="2ec0d-161">Si el asiento del subdiario contable es incorrecto cuando se obtiene una vista previa antes de registrar la factura de servicios en el diario, no se puede cambiar el asiento del subdiario contable.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-161">If the subledger journal entry is incorrect when you preview it before you journalize the free text invoice, you can't change the subledger journal entry.</span></span> <span data-ttu-id="2ec0d-162">En lugar de ello, se deben cambiar las distribuciones contables o el perfil de registro.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-162">Instead, you must change the accounting distributions or the posting profile.</span></span> <span data-ttu-id="2ec0d-163">Las distribuciones contables se usan para definir un lado del asiento contable, el débito o el crédito.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-163">The accounting distributions are used to define one side of the accounting entry, the debit or the credit.</span></span> <span data-ttu-id="2ec0d-164">El asiento contable del subdiario contable se crea a partir de los perfiles de registro, como por ejemplo, desde la cuenta de cliente o los impuestos.</span><span class="sxs-lookup"><span data-stu-id="2ec0d-164">The offsetting subledger journal account entry is created from the posting profiles, such as from the customer account or the tax.</span></span>




