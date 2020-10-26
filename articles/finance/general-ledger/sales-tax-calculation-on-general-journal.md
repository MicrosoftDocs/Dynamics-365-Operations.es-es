---
title: Cálculo de impuestos en líneas de diario generales
description: Este tema explica cómo se calculan los impuestos para distintos tipos de cuentas (proveedor, cliente, contabilidad, y proyecto) en las líneas del diario general.
author: EricWang
manager: Ann Beebe
ms.date: 08/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 51d43c8e6d16201e1f8c392c13ead20287782dcc
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "3983606"
---
# <a name="sales-tax-calculation-on-general-journal-lines"></a><span data-ttu-id="30f94-103">Cálculo de impuestos en líneas de diario generales</span><span class="sxs-lookup"><span data-stu-id="30f94-103">Sales tax calculation on general journal lines</span></span>
[!include [banner](../includes/banner.md)]

<span data-ttu-id="30f94-104">Este tema explica cómo se calculan los impuestos para distintos tipos de cuentas (proveedor, cliente, contabilidad, y proyecto) en las líneas del diario general.</span><span class="sxs-lookup"><span data-stu-id="30f94-104">This topic explains how sales taxes are calculated for different types of accounts (vendor, customer, ledger, and project) on general journal lines.</span></span>

<span data-ttu-id="30f94-105">El proceso se puede dividir en tres pasos:</span><span class="sxs-lookup"><span data-stu-id="30f94-105">The process can be divided into three steps:</span></span>

- <span data-ttu-id="30f94-106">Determine la dirección de impuestos.</span><span class="sxs-lookup"><span data-stu-id="30f94-106">Determine the sales tax direction.</span></span>

- <span data-ttu-id="30f94-107">Determine el importe de impuestos que se guardará una tabla temporal de impuestos.</span><span class="sxs-lookup"><span data-stu-id="30f94-107">Determine the sales tax amount that will be stored a temporary sales tax table.</span></span>

- <span data-ttu-id="30f94-108">Determine el importe de los impuestos y en el asiento.</span><span class="sxs-lookup"><span data-stu-id="30f94-108">Determine the sales tax amount and account on the voucher.</span></span>

## <a name="determine-the-sales-tax-direction"></a><span data-ttu-id="30f94-109">Determine la dirección de impuestos</span><span class="sxs-lookup"><span data-stu-id="30f94-109">Determine the sales tax direction</span></span>

<span data-ttu-id="30f94-110">La forma en que determinan la dirección de impuestos depende del tipo de cuenta en el asiento.</span><span class="sxs-lookup"><span data-stu-id="30f94-110">The way that the sales tax direction is determined depends on the type of account in the voucher.</span></span> <span data-ttu-id="30f94-111">La dirección de impuestos la determina la combinación del tipo de cuentas y el código de impuestos.</span><span class="sxs-lookup"><span data-stu-id="30f94-111">The sales tax direction is determined by the combination of account type and sales tax code.</span></span> <span data-ttu-id="30f94-112">Las secciones siguientes listan las posibilidades con más detalle.</span><span class="sxs-lookup"><span data-stu-id="30f94-112">The following sections the possibilities in more detail.</span></span> 

### <a name="account-type-is-project"></a><span data-ttu-id="30f94-113">Tipo de cuenta es Proyecto</span><span class="sxs-lookup"><span data-stu-id="30f94-113">Account type is Project</span></span>

<span data-ttu-id="30f94-114">Si tiene un asiento línea de diario en el que tipo de cuenta es **Proyecto**, todas las líneas de diario en el asiento aplicarán la misma dirección de impuestos.</span><span class="sxs-lookup"><span data-stu-id="30f94-114">If a voucher has journal line where the account type is **Project**, all the journal lines in the voucher apply the same tax direction.</span></span> <span data-ttu-id="30f94-115">La siguiente ilustración muestra la regla.</span><span class="sxs-lookup"><span data-stu-id="30f94-115">The following illustration shows the rule.</span></span> <span data-ttu-id="30f94-116">Los puntos siguientes muestran direcciones posibles de impuestos para las cuentas del proyecto.</span><span class="sxs-lookup"><span data-stu-id="30f94-116">The following points show the possible tax directions for project accounts.</span></span>

<span data-ttu-id="30f94-117">•   Si el código de impuestos es IVA de importación, la dirección de impuestos es IVA de importación.</span><span class="sxs-lookup"><span data-stu-id="30f94-117">•   If the sales tax code is use tax, then sales tax direction is Use Tax.</span></span>

<span data-ttu-id="30f94-118">•   Si el código de impuestos es exención de impuestos, la dirección de impuestos es Compra libre de impuestos.</span><span class="sxs-lookup"><span data-stu-id="30f94-118">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="30f94-119">•   Si el código de impuestos es IVA intracomunitario, la dirección de impuestos es Impuestos repercutidos.</span><span class="sxs-lookup"><span data-stu-id="30f94-119">•   If the sales tax code is intracom VAT, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="30f94-120">•   Si el código de impuestos es cargo invertido, la dirección de impuestos es Impuestos repercutidos.</span><span class="sxs-lookup"><span data-stu-id="30f94-120">•   If the sales tax code is reverse charge, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="30f94-121">De lo contrario, la dirección de impuestos es un impuesto soportados.</span><span class="sxs-lookup"><span data-stu-id="30f94-121">Otherwise, sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="30f94-122">El siguiente diagrama muestra gráficamente la regla.</span><span class="sxs-lookup"><span data-stu-id="30f94-122">The following diagram illustrates the rule graphically.</span></span>

![Posibilidades de la dirección de impuestos de cuentas del proyecto](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-vendor"></a><span data-ttu-id="30f94-124">El tipo de cuenta es proveedor</span><span class="sxs-lookup"><span data-stu-id="30f94-124">Account type is Vendor</span></span>

<span data-ttu-id="30f94-125">Si tiene un asiento línea de diario en el que tipo de cuenta es **Proveedor**, todas las líneas de diario en el asiento aplicarán la misma dirección de impuestos.</span><span class="sxs-lookup"><span data-stu-id="30f94-125">If a voucher has journal line where the account type is **Vendor**, all the journal lines in the voucher apply the same tax direction.</span></span> <span data-ttu-id="30f94-126">Los puntos siguientes muestran direcciones posibles de impuestos para las cuentas del proveedor.</span><span class="sxs-lookup"><span data-stu-id="30f94-126">The following points show the possible tax directions for vendor accounts.</span></span> 

<span data-ttu-id="30f94-127">•   Si el código de impuestos es IVA de importación, la dirección de impuestos es IVA de importación.</span><span class="sxs-lookup"><span data-stu-id="30f94-127">•   If the sales tax code is use tax, then sales tax direction is Use Tax.</span></span>

<span data-ttu-id="30f94-128">•   Si el código de impuestos es exención de impuestos, la dirección de impuestos es Compra libre de impuestos.</span><span class="sxs-lookup"><span data-stu-id="30f94-128">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="30f94-129">•   Si el código de impuestos es IVA intracomunitario, la dirección de impuestos es Impuestos repercutidos.</span><span class="sxs-lookup"><span data-stu-id="30f94-129">•   If the sales tax code is intracom VAT, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="30f94-130">•   Si el código de impuestos es cargo invertido, la dirección de impuestos es Impuestos repercutidos.</span><span class="sxs-lookup"><span data-stu-id="30f94-130">•   If the sales tax code is reverse charge, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="30f94-131">De lo contrario, la dirección de impuestos es un impuesto soportados.</span><span class="sxs-lookup"><span data-stu-id="30f94-131">Otherwise, sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="30f94-132">El siguiente diagrama muestra gráficamente la regla.</span><span class="sxs-lookup"><span data-stu-id="30f94-132">The following diagram illustrates the rule graphically.</span></span>

![Posibilidades de la dirección de impuestos de cuentas de proveedor](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-customer"></a><span data-ttu-id="30f94-134">El tipo de cuenta es Cliente</span><span class="sxs-lookup"><span data-stu-id="30f94-134">Account type is Customer</span></span>

<span data-ttu-id="30f94-135">Si tiene un asiento línea de diario en el que tipo de cuenta es **Cliente**, todas las líneas de diario en el asiento aplicarán la misma dirección de impuestos.</span><span class="sxs-lookup"><span data-stu-id="30f94-135">If a voucher has journal line where the account type is **Customer**, all the journal lines in the voucher apply the same tax direction.</span></span> <span data-ttu-id="30f94-136">Los puntos siguientes muestran direcciones posibles de impuestos para las cuentas de cliente.</span><span class="sxs-lookup"><span data-stu-id="30f94-136">The following points show the possible tax directions for customer accounts.</span></span>

<span data-ttu-id="30f94-137">•   Si el código de impuestos es exención de impuestos, la dirección de impuestos es Compra libre de impuestos.</span><span class="sxs-lookup"><span data-stu-id="30f94-137">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="30f94-138">•   Si el código de impuestos es IVA intracomunitario, la dirección de impuestos es Impuestos soportados.</span><span class="sxs-lookup"><span data-stu-id="30f94-138">•   If the sales tax code is intracom VAT, then sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="30f94-139">•   Si el código de impuestos es cargo invertido, la dirección de impuestos es Impuestos soportados.</span><span class="sxs-lookup"><span data-stu-id="30f94-139">•   If the sales tax code is reverse charge, then sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="30f94-140">De lo contrario, la dirección de impuestos es un impuesto repercutidos.</span><span class="sxs-lookup"><span data-stu-id="30f94-140">Otherwise, sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="30f94-141">El siguiente diagrama muestra gráficamente la regla.</span><span class="sxs-lookup"><span data-stu-id="30f94-141">The following diagram illustrates the rule graphically.</span></span>

![Posibilidades de la dirección de impuestos de cuentas de cliente](media/Sales-Tax-Direction-Customer.jpg)

### <a name="account-type-is-ledger"></a><span data-ttu-id="30f94-143">El tipo de cuenta es Libro mayor</span><span class="sxs-lookup"><span data-stu-id="30f94-143">Account type is Ledger</span></span>

<span data-ttu-id="30f94-144">La ilustración siguiente muestra la regla que se aplica cuando un asiento sólo tiene líneas de diario donde el tipo de cuenta es **Libro mayor**.</span><span class="sxs-lookup"><span data-stu-id="30f94-144">The following illustration shows the rule that applies when a voucher has only journal lines where the account type is **Ledger**.</span></span> <span data-ttu-id="30f94-145">Los puntos siguientes muestran direcciones posibles de impuestos para las cuentas de libro mayor.</span><span class="sxs-lookup"><span data-stu-id="30f94-145">The following points show the possible tax directions for ledger accounts.</span></span>

<span data-ttu-id="30f94-146">•   Si el código de impuestos es IVA de importación, la dirección de impuestos es IVA de importación.</span><span class="sxs-lookup"><span data-stu-id="30f94-146">•   If the sales tax code is use tax, then sales tax direction is Use Tax.</span></span>

<span data-ttu-id="30f94-147">•   Si el código de impuestos es exención de impuestos, la dirección de impuestos es Compra libre de impuestos.</span><span class="sxs-lookup"><span data-stu-id="30f94-147">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="30f94-148">De lo contrario, si el importe del diario es debe (positivo), la dirección de impuestos es Impuesto soportado; si el importe del diario es de crédito (negativo), la dirección de impuestos Impuesto repercutido.</span><span class="sxs-lookup"><span data-stu-id="30f94-148">Otherwise, if the journal amount is debit (positive) ,sales tax direction is Sales Tax Receivable; if the journal amount is credit (negative) ,sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="30f94-149">El siguiente diagrama muestra gráficamente la regla.</span><span class="sxs-lookup"><span data-stu-id="30f94-149">The following diagram illustrates the rule graphically.</span></span>

![Posibilidades de la dirección de impuestos de cuentas de libro mayor](media/Sales-Tax-Direction-Ledger.jpg)

#### <a name="override-the-sales-tax-direction"></a><span data-ttu-id="30f94-151">Anular la dirección de impuestos</span><span class="sxs-lookup"><span data-stu-id="30f94-151">Override the sales tax direction</span></span>

<span data-ttu-id="30f94-152">Puede anular la dirección de impuestos cuando el asiento sólo contiene líneas que en la que el tipo de cuenta es **Libro mayor**.</span><span class="sxs-lookup"><span data-stu-id="30f94-152">You can override the sales tax direction when the voucher contains only lines where the account type is **Ledger**.</span></span>

<span data-ttu-id="30f94-153">Vaya a **Contabilidad general \> Plan de cuentas \> Cuentas \> Cuentas principales**, y seleccione la ficha desplegable **Anular entidad jurídica**.</span><span class="sxs-lookup"><span data-stu-id="30f94-153">Go to **General ledger \> Chart of accounts \> Accounts \> Main accounts**, and select the **Legal entity overrides** FastTab.</span></span>

## <a name="determine-the-sales-tax-amount"></a><span data-ttu-id="30f94-154">Determine la cantidad de impuestos</span><span class="sxs-lookup"><span data-stu-id="30f94-154">Determine the sales tax amount</span></span>

<span data-ttu-id="30f94-155">Esta sección describe cómo se calcula el signo del importe de impuestos.</span><span class="sxs-lookup"><span data-stu-id="30f94-155">This section describes how the sales tax amount sign is calculated.</span></span>

![Página de transacciones de impuestos](media/sales-tax-amount-sign.jpg)

<span data-ttu-id="30f94-157">En la tabla siguiente se muestra la regla genérica para determinar el signo de los importes de impuestos en la tabla temporal de impuestos.</span><span class="sxs-lookup"><span data-stu-id="30f94-157">The following table shows the generic rule for determining the sign of sales tax amounts in the temporary sales tax table.</span></span>

| <span data-ttu-id="30f94-158">Cantidad de línea del diario</span><span class="sxs-lookup"><span data-stu-id="30f94-158">Journal line amount</span></span> | <span data-ttu-id="30f94-159">Dirección del impuesto</span><span class="sxs-lookup"><span data-stu-id="30f94-159">Sales tax direction</span></span>  | <span data-ttu-id="30f94-160">Signo de importe de impuestos</span><span class="sxs-lookup"><span data-stu-id="30f94-160">Sales tax amount sign</span></span> |
|---------------------|----------------------|-----------------------|
| <span data-ttu-id="30f94-161">Positivo</span><span class="sxs-lookup"><span data-stu-id="30f94-161">Positive</span></span>            | <span data-ttu-id="30f94-162">Impuestos soportados</span><span class="sxs-lookup"><span data-stu-id="30f94-162">Sales Tax Receivable</span></span> | <span data-ttu-id="30f94-163">Positivo</span><span class="sxs-lookup"><span data-stu-id="30f94-163">Positive</span></span>              |
| <span data-ttu-id="30f94-164">Positivo</span><span class="sxs-lookup"><span data-stu-id="30f94-164">Positive</span></span>            | <span data-ttu-id="30f94-165">Impuestos repercutidos</span><span class="sxs-lookup"><span data-stu-id="30f94-165">Sales Tax Payable</span></span>    | <span data-ttu-id="30f94-166">Negativo</span><span class="sxs-lookup"><span data-stu-id="30f94-166">Negative</span></span>              |
| <span data-ttu-id="30f94-167">Negativo</span><span class="sxs-lookup"><span data-stu-id="30f94-167">Negative</span></span>            | <span data-ttu-id="30f94-168">Impuestos soportados</span><span class="sxs-lookup"><span data-stu-id="30f94-168">Sales Tax Receivable</span></span> | <span data-ttu-id="30f94-169">Negativo</span><span class="sxs-lookup"><span data-stu-id="30f94-169">Negative</span></span>              |
| <span data-ttu-id="30f94-170">Negativo</span><span class="sxs-lookup"><span data-stu-id="30f94-170">Negative</span></span>            | <span data-ttu-id="30f94-171">Impuestos repercutidos</span><span class="sxs-lookup"><span data-stu-id="30f94-171">Sales Tax Payable</span></span>    | <span data-ttu-id="30f94-172">Positivo</span><span class="sxs-lookup"><span data-stu-id="30f94-172">Positive</span></span>              |

<span data-ttu-id="30f94-173">Hay una regla especial para los asientos con líneas sólo **Proyecto** o **Libro mayor** , cuando se selecciona un grupo de impuestos o grupo de impuestos en la línea **Libro mayor**.</span><span class="sxs-lookup"><span data-stu-id="30f94-173">There is a special rule for vouchers that have only **Project** or **Ledger** lines, when a sales tax group or item sales tax group is selected on the **Ledger** line.</span></span> <span data-ttu-id="30f94-174">Esta regla se controla mediante la función Habilitar cálculo independiente de impuestos para los diarios generales.</span><span class="sxs-lookup"><span data-stu-id="30f94-174">This rule is controlled by Enable independent sales tax calculation feature for general journals.</span></span> <span data-ttu-id="30f94-175">Cuando se desactiva esta función, el importe de impuestos de los usos en línea **Libro mayor** usan la línea de débito/crédito de la línea **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="30f94-175">When this feature is turned off, the tax amount of the **Ledger** line uses the debit/credit direction of the **Project** line.</span></span> <span data-ttu-id="30f94-176">Cuando se activa esta función, el importe de impuestos en la línea **Libro mayor** usa su propia dirección de crédito/débito.</span><span class="sxs-lookup"><span data-stu-id="30f94-176">When the feature is turned on, the tax amount of the **Ledger** line uses its own debit/credit direction.</span></span> <span data-ttu-id="30f94-177">En las siguientes tablas se muestra la regla para cada escenario.</span><span class="sxs-lookup"><span data-stu-id="30f94-177">The following tables show the rule for each scenario.</span></span> 

<span data-ttu-id="30f94-178">**Regla cuando se activa la función**</span><span class="sxs-lookup"><span data-stu-id="30f94-178">**Rule when the feature is turned on**</span></span>

| <span data-ttu-id="30f94-179">Línea cantidad del proyecto del diario</span><span class="sxs-lookup"><span data-stu-id="30f94-179">Journal line amount of project</span></span> | <span data-ttu-id="30f94-180">Dirección del impuesto</span><span class="sxs-lookup"><span data-stu-id="30f94-180">Sales tax direction</span></span>  | <span data-ttu-id="30f94-181">Signo de importe de impuestos</span><span class="sxs-lookup"><span data-stu-id="30f94-181">Sales tax amount sign</span></span> |
|--------------------------------|----------------------|-----------------------|
| <span data-ttu-id="30f94-182">Positivo</span><span class="sxs-lookup"><span data-stu-id="30f94-182">Positive</span></span>                       | <span data-ttu-id="30f94-183">Impuestos soportados</span><span class="sxs-lookup"><span data-stu-id="30f94-183">Sales Tax Receivable</span></span> | <span data-ttu-id="30f94-184">Positivo</span><span class="sxs-lookup"><span data-stu-id="30f94-184">Positive</span></span>              |
| <span data-ttu-id="30f94-185">Negativo</span><span class="sxs-lookup"><span data-stu-id="30f94-185">Negative</span></span>                       | <span data-ttu-id="30f94-186">Impuestos soportados</span><span class="sxs-lookup"><span data-stu-id="30f94-186">Sales Tax Receivable</span></span> | <span data-ttu-id="30f94-187">Negativo</span><span class="sxs-lookup"><span data-stu-id="30f94-187">Negative</span></span>              |

<span data-ttu-id="30f94-188">**Regla cuando se desactiva la función**</span><span class="sxs-lookup"><span data-stu-id="30f94-188">**Rule when the feature is turned off**</span></span>

| <span data-ttu-id="30f94-189">Línea cantidad del libro mayor</span><span class="sxs-lookup"><span data-stu-id="30f94-189">Journal line amount of ledger</span></span>  | <span data-ttu-id="30f94-190">Dirección del impuesto</span><span class="sxs-lookup"><span data-stu-id="30f94-190">Sales tax direction</span></span>  | <span data-ttu-id="30f94-191">Signo de importe de impuestos</span><span class="sxs-lookup"><span data-stu-id="30f94-191">Sales tax amount sign</span></span> |
|--------------------------------|----------------------|-----------------------|
| <span data-ttu-id="30f94-192">Positivo</span><span class="sxs-lookup"><span data-stu-id="30f94-192">Positive</span></span>                       | <span data-ttu-id="30f94-193">Impuestos soportados</span><span class="sxs-lookup"><span data-stu-id="30f94-193">Sales Tax Receivable</span></span> | <span data-ttu-id="30f94-194">Positivo</span><span class="sxs-lookup"><span data-stu-id="30f94-194">Positive</span></span>              |
| <span data-ttu-id="30f94-195">Negativo</span><span class="sxs-lookup"><span data-stu-id="30f94-195">Negative</span></span>                       | <span data-ttu-id="30f94-196">Impuestos soportados</span><span class="sxs-lookup"><span data-stu-id="30f94-196">Sales Tax Receivable</span></span> | <span data-ttu-id="30f94-197">Negativo</span><span class="sxs-lookup"><span data-stu-id="30f94-197">Negative</span></span>              |

## <a name="determine-the-sales-tax-amount-and-account-on-the-voucher"></a><span data-ttu-id="30f94-198">Determine el importe de los impuestos y en el asiento</span><span class="sxs-lookup"><span data-stu-id="30f94-198">Determine the sales tax amount and account on the voucher</span></span>

<span data-ttu-id="30f94-199">Al registrar impuestos, la cuenta principal se recupera del perfil del grupo de registro.</span><span class="sxs-lookup"><span data-stu-id="30f94-199">When you post sales taxes, the main account is retrieved from the ledger posting group profile.</span></span> <span data-ttu-id="30f94-200">Cuando los impuestos son soportados, el sistema utiliza la cuenta de impuestos soportados que se especifica en el perfil.</span><span class="sxs-lookup"><span data-stu-id="30f94-200">When sales taxes are receivable, the system uses the Sales Tax Receivable account that is specified in the profile.</span></span> <span data-ttu-id="30f94-201">Para los impuestos repercutidos, el sistema utiliza la cuenta de impuestos repercutidos que se especifica en el perfil.</span><span class="sxs-lookup"><span data-stu-id="30f94-201">For sales taxes that are payable, the system uses Sales Tax Payable account that is specified in the profile.</span></span>

<span data-ttu-id="30f94-202">La tabla siguiente muestra la regla genérica.</span><span class="sxs-lookup"><span data-stu-id="30f94-202">The following table shows the generic rule.</span></span>

| <span data-ttu-id="30f94-203">Dirección del impuesto</span><span class="sxs-lookup"><span data-stu-id="30f94-203">Sales tax direction</span></span>  | <span data-ttu-id="30f94-204">Signo de importe de impuestos</span><span class="sxs-lookup"><span data-stu-id="30f94-204">Sales tax amount sign</span></span> | <span data-ttu-id="30f94-205">Cuenta de impuestos</span><span class="sxs-lookup"><span data-stu-id="30f94-205">Sales tax account</span></span>      | <span data-ttu-id="30f94-206">Importe del asiento</span><span class="sxs-lookup"><span data-stu-id="30f94-206">Amount on voucher</span></span> |
|----------------------|-----------------------|------------------------|-------------------|
| <span data-ttu-id="30f94-207">Impuestos soportados</span><span class="sxs-lookup"><span data-stu-id="30f94-207">Sales Tax Receivable</span></span> | <span data-ttu-id="30f94-208">Positivo</span><span class="sxs-lookup"><span data-stu-id="30f94-208">Positive</span></span>              | <span data-ttu-id="30f94-209">Cuenta Impuestos soportados</span><span class="sxs-lookup"><span data-stu-id="30f94-209">Tax Receivable Account</span></span> | <span data-ttu-id="30f94-210">Positivo (Débito)</span><span class="sxs-lookup"><span data-stu-id="30f94-210">Positive (Debit)</span></span>  |
| <span data-ttu-id="30f94-211">Impuestos soportados</span><span class="sxs-lookup"><span data-stu-id="30f94-211">Sales Tax Receivable</span></span> | <span data-ttu-id="30f94-212">Negativo</span><span class="sxs-lookup"><span data-stu-id="30f94-212">Negative</span></span>              | <span data-ttu-id="30f94-213">Cuenta Impuestos soportados</span><span class="sxs-lookup"><span data-stu-id="30f94-213">Tax Receivable Account</span></span> | <span data-ttu-id="30f94-214">Negativo (Crédito)</span><span class="sxs-lookup"><span data-stu-id="30f94-214">Negative(Credit)</span></span>  |
| <span data-ttu-id="30f94-215">Impuestos repercutidos</span><span class="sxs-lookup"><span data-stu-id="30f94-215">Sales Tax Payable</span></span>    | <span data-ttu-id="30f94-216">Positivo</span><span class="sxs-lookup"><span data-stu-id="30f94-216">Positive</span></span>              | <span data-ttu-id="30f94-217">Cuenta Impuestos repercutidos</span><span class="sxs-lookup"><span data-stu-id="30f94-217">Tax Payable Account</span></span>    | <span data-ttu-id="30f94-218">Negativo (Crédito)</span><span class="sxs-lookup"><span data-stu-id="30f94-218">Negative(Credit)</span></span>  |
| <span data-ttu-id="30f94-219">Impuestos repercutidos</span><span class="sxs-lookup"><span data-stu-id="30f94-219">Sales Tax Payable</span></span>    | <span data-ttu-id="30f94-220">Negativo</span><span class="sxs-lookup"><span data-stu-id="30f94-220">Negative</span></span>              | <span data-ttu-id="30f94-221">Cuenta Impuestos repercutidos</span><span class="sxs-lookup"><span data-stu-id="30f94-221">Tax Payable Account</span></span>    | <span data-ttu-id="30f94-222">Positivo (Débito)</span><span class="sxs-lookup"><span data-stu-id="30f94-222">Positive (Debit)</span></span>  |
