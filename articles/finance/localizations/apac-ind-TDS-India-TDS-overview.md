---
title: Información general de impuestos deducidos en el origen (TDS) de la India
description: Este tema proporciona información detallada sobre el impuesto deducido en el origen (TDS) de la India. La documentación de TDS cubre la funcionalidad de esta capacidad.
author: kailiang
ms.date: 03/19/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 28ee843036e11bd37b97a065ce53d2eb860c79d9
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023581"
---
# <a name="indian-tax-deducted-at-source-tds-overview"></a><span data-ttu-id="7614c-104">Información general de impuestos deducidos en el origen (TDS) de la India</span><span class="sxs-lookup"><span data-stu-id="7614c-104">Indian Tax Deducted at Source (TDS) overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7614c-105">Este tema proporciona información detallada sobre el impuesto deducido en el origen (TDS) de la India.</span><span class="sxs-lookup"><span data-stu-id="7614c-105">This topic provides detailed information about Indian Tax Deducted at Source (TDS).</span></span>

<span data-ttu-id="7614c-106">La documentación de TDS cubre la funcionalidad de esta capacidad.</span><span class="sxs-lookup"><span data-stu-id="7614c-106">The TDS documentation covers the functionality of this capability.</span></span> <span data-ttu-id="7614c-107">También explica cómo realizar la configuración básica de TDS, calcular TDS en transacciones, completar el proceso de liquidación de TDS, registrar números de certificado de TDS y generar consultas de TDS, declaraciones de TDS y certificados de TDS.</span><span class="sxs-lookup"><span data-stu-id="7614c-107">It also explains how to do the basic setup for TDS, calculate TDS on transactions, complete the TDS settlement process, record TDS certificate numbers, and generate TDS inquiries, TDS statements, and TDS certificates.</span></span> <span data-ttu-id="7614c-108">La documentación incluye los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="7614c-108">The documentation includes the following topics:</span></span>

- [<span data-ttu-id="7614c-109">Configuración básica para TDS</span><span class="sxs-lookup"><span data-stu-id="7614c-109">Basic setup for TDS</span></span>](apac-ind-TDS-TDS-ledger-accounts-setup.md)
- [<span data-ttu-id="7614c-110">Diseñador de fórmulas y funcionalidad de límite de umbral utilizada para el cálculo de TDS</span><span class="sxs-lookup"><span data-stu-id="7614c-110">Formula designer and threshold limit functionality used for TDS calculation</span></span>](apac-ind-TDS-Formula-designer.md)
- [<span data-ttu-id="7614c-111">Cálculo de TDS en facturas, pagos, pagarés y transacciones entre empresas</span><span class="sxs-lookup"><span data-stu-id="7614c-111">Calculation of TDS on invoices, payments, promissory notes, and intercompany transactions</span></span>](apac-ind-TDS-Calculate-TDS-on-invoices-using-journals.md)
- [<span data-ttu-id="7614c-112">Proceso de liquidación periódica de TDS y liquidación de importes de TDS a proveedores de autoridad de TDS</span><span class="sxs-lookup"><span data-stu-id="7614c-112">Periodic TDS settlement process and settlement of TDS amounts to TDS authority vendors</span></span>](apac-ind-TDS-Run-the-periodic-TDS-settlement-process.md)
- [<span data-ttu-id="7614c-113">Registro y actualización de números y fechas de certificados TDS</span><span class="sxs-lookup"><span data-stu-id="7614c-113">Recording and updating TDS certificate numbers and dates</span></span>](apac-ind-TDS-Record-TDS-concession-certificate-numbers.md)

## <a name="introduction-to-tds"></a><span data-ttu-id="7614c-114">Introducción a TDS</span><span class="sxs-lookup"><span data-stu-id="7614c-114">Introduction to TDS</span></span>

<span data-ttu-id="7614c-115">De acuerdo con la Ley de impuestos sobre la renta de 1961, el receptor del servicio deduce el impuesto sobre la renta en el origen en el momento del pago anticipado o la contabilización del crédito, lo que ocurra primero.</span><span class="sxs-lookup"><span data-stu-id="7614c-115">Per the Income tax Act, 1961, income tax is deducted at the source by the receiver of the service at the time of advance payment or accounting of credit, whichever occurs first.</span></span> <span data-ttu-id="7614c-116">La persona que realiza el pago debe deducir el importe del impuesto y pagar solo el saldo neto al proveedor del servicio.</span><span class="sxs-lookup"><span data-stu-id="7614c-116">The person who makes the payment must deduct the tax amount and pay only the net balance to the provider of the service.</span></span> <span data-ttu-id="7614c-117">Los TDS se aplican a los servicios que especifica el gobierno y el impuesto se deduce utilizando las tasas que el gobierno especifica para un periodo.</span><span class="sxs-lookup"><span data-stu-id="7614c-117">TDS is applied on services that the government specifies, and the tax is deducted by using the rates that the government specifies for a period.</span></span> <span data-ttu-id="7614c-118">La tasa de deducción se basa en el estado de la entidad que recibe el pago o presta el servicio.</span><span class="sxs-lookup"><span data-stu-id="7614c-118">The rate of deduction is based on the status of the entity that receives the payment or provides the service.</span></span> <span data-ttu-id="7614c-119">Los estados incluyen **Individual**, **Familia indivisa hindú** (**HUF**), **Empresa**, **Firma**, **Asociación de personas** (**AOP**), **Cuerpo de individuos** (**BOI**) y **Autoridad local**.</span><span class="sxs-lookup"><span data-stu-id="7614c-119">Statuses include **Individual**, **Hindu Undivided Family** (**HUF**), **Company**, **Firm**, **Association of Persons** (**AOP**), **Body of Individuals** (**BOI**), and **Local authority**.</span></span>

<span data-ttu-id="7614c-120">Las siguientes secciones enumeran los servicios en los que se aplican los TDS, según lo especificado por el gobierno de la India.</span><span class="sxs-lookup"><span data-stu-id="7614c-120">The following sections list the services that TDS is applied on, as specified by the Government of India.</span></span>

<span data-ttu-id="7614c-121">**Residentes**</span><span class="sxs-lookup"><span data-stu-id="7614c-121">**Residents**</span></span>

- <span data-ttu-id="7614c-122">Ingresos por sueldos (según la sección 192)</span><span class="sxs-lookup"><span data-stu-id="7614c-122">Income from salaries (Under section 192)</span></span>
- <span data-ttu-id="7614c-123">Ingresos por intereses sobre valores (según la sección 193)</span><span class="sxs-lookup"><span data-stu-id="7614c-123">Income from interest on securities (Under section 193)</span></span>
- <span data-ttu-id="7614c-124">Ingresos por dividendo (según la sección 194)</span><span class="sxs-lookup"><span data-stu-id="7614c-124">Income from dividend (Under section 194)</span></span>
- <span data-ttu-id="7614c-125">Ingresos por interés (según la sección 194A)</span><span class="sxs-lookup"><span data-stu-id="7614c-125">Income from interest (Under section 194A)</span></span>
- <span data-ttu-id="7614c-126">Ingresos de loterías o juegos (según la sección 194B)</span><span class="sxs-lookup"><span data-stu-id="7614c-126">Income from lotteries or puzzles (Under section 194B)</span></span>
- <span data-ttu-id="7614c-127">Ganar en carreras de caballos, etc. (según la sección 194BB)</span><span class="sxs-lookup"><span data-stu-id="7614c-127">Winning from horse races etc. (Under section 194BB)</span></span>
- <span data-ttu-id="7614c-128">Contratistas y subcontratistas (según la sección 194C)</span><span class="sxs-lookup"><span data-stu-id="7614c-128">Contractors and sub-contractors (Under section 194C)</span></span>
- <span data-ttu-id="7614c-129">Comisión de seguros (según la sección 194D)</span><span class="sxs-lookup"><span data-stu-id="7614c-129">Insurance commission (Under section 194D)</span></span>
- <span data-ttu-id="7614c-130">Ingresos por depósito en el marco del plan de ahorro nacional (según la sección 194EE)</span><span class="sxs-lookup"><span data-stu-id="7614c-130">Income from deposit under national saving scheme (Under section 194EE)</span></span>
- <span data-ttu-id="7614c-131">Ingresos de fondos mutuos o UTI (según la sección 194F)</span><span class="sxs-lookup"><span data-stu-id="7614c-131">Income from mutual fund or UTI (Under section 194F)</span></span>
- <span data-ttu-id="7614c-132">Comisión, remuneración, premio, etc. en venta o lotería (según la sección 194G)</span><span class="sxs-lookup"><span data-stu-id="7614c-132">Commission, Remuneration, Prize etc., on sale or lottery (Under section 194G)</span></span>
- <span data-ttu-id="7614c-133">Pago de comisión o correduría (según la sección 194H)</span><span class="sxs-lookup"><span data-stu-id="7614c-133">Payment of Commission or brokerage (Under section 194H)</span></span>
- <span data-ttu-id="7614c-134">Alquiler (según la sección 194I)</span><span class="sxs-lookup"><span data-stu-id="7614c-134">Rent (Under section 194I)</span></span>
- <span data-ttu-id="7614c-135">Servicio profesional (según la sección 194J)</span><span class="sxs-lookup"><span data-stu-id="7614c-135">Professional service (Under section 194J)</span></span>
- <span data-ttu-id="7614c-136">Ingresos por unidades (según la sección 194K)</span><span class="sxs-lookup"><span data-stu-id="7614c-136">Income from Units (Under section 194K)</span></span>
- <span data-ttu-id="7614c-137">Pago de compensación por la adquisición de determinadas propiedades inmuebles (según la sección 194LA)</span><span class="sxs-lookup"><span data-stu-id="7614c-137">Payment of compensation on acquisition of certain immovable property (Under section 194LA)</span></span>

<span data-ttu-id="7614c-138">**No residentes**</span><span class="sxs-lookup"><span data-stu-id="7614c-138">**Non-residents**</span></span>

- <span data-ttu-id="7614c-139">Pagos a deportistas o asociaciones deportivas no residentes (según la sección 194E)</span><span class="sxs-lookup"><span data-stu-id="7614c-139">Payments to Non-resident sportsmen or sports association (Under section 194E)</span></span>
- <span data-ttu-id="7614c-140">Otras sumas (en la sección 195)</span><span class="sxs-lookup"><span data-stu-id="7614c-140">Other sums (Under section 195)</span></span>
- <span data-ttu-id="7614c-141">Ingresos por unidades de no residentes (según la sección 196A)</span><span class="sxs-lookup"><span data-stu-id="7614c-141">Income in respect of units of non-residents (Under section 196A)</span></span>

    - <span data-ttu-id="7614c-142">Ingresos de pólizas en divisa extranjera o acciones de una empresa india (según la sección 196C)</span><span class="sxs-lookup"><span data-stu-id="7614c-142">Income from foreign currency bonds or shares of Indian Company (Under section 196C)</span></span>
    - <span data-ttu-id="7614c-143">Ingresos de inversores institucionales extranjeros procedentes de valores (según la sección 196D)</span><span class="sxs-lookup"><span data-stu-id="7614c-143">Incomes of foreign institutional investors from securities (Under section 196D)</span></span>
    - <span data-ttu-id="7614c-144">Salario y todos los demás ingresos positivos en cualquier categoría de ingresos (sección 192)</span><span class="sxs-lookup"><span data-stu-id="7614c-144">Salary and all other positive incomes under any head on income (Section 192)</span></span>
    - <span data-ttu-id="7614c-145">Intereses sobre valores (sección 193)</span><span class="sxs-lookup"><span data-stu-id="7614c-145">Interest on securities (Section 193)</span></span>
    - <span data-ttu-id="7614c-146">Intereses distintos de los intereses sobre valores (sección 194A)</span><span class="sxs-lookup"><span data-stu-id="7614c-146">Interest other than interest on securities (Section 194A)</span></span>
    - <span data-ttu-id="7614c-147">Pagos a contratistas y subcontratistas (sección 194C)</span><span class="sxs-lookup"><span data-stu-id="7614c-147">Payments to contractors and sub-contractors (Section 194C)</span></span>
    - <span data-ttu-id="7614c-148">Ganancias de lotería o crucigramas (sección 194B)</span><span class="sxs-lookup"><span data-stu-id="7614c-148">Winnings from Lottery or crossword puzzles (Section 194B)</span></span>
    - <span data-ttu-id="7614c-149">Ganancias en carreras de caballos (sección 194BB)</span><span class="sxs-lookup"><span data-stu-id="7614c-149">Winnings from horse races (Section 194BB)</span></span>
    - <span data-ttu-id="7614c-150">Comisión de seguros que cubre todos los pagos para la adquisición de negocios de seguros (sección 194D)</span><span class="sxs-lookup"><span data-stu-id="7614c-150">Insurance Commission covering all payments for procuring Insurance business (Section 194D)</span></span>
    - <span data-ttu-id="7614c-151">Cualquier interés que no sea el interés sobre valores pagaderos a no residentes que no sean una empresa o una empresa extranjera (sección 195)</span><span class="sxs-lookup"><span data-stu-id="7614c-151">Any interest other than interest on securities payable to non-residents not being a company or to a foreign company (Section 195)</span></span>
    - <span data-ttu-id="7614c-152">Pago al deportista no residente incluido deportista, asociación o institución deportiva.</span><span class="sxs-lookup"><span data-stu-id="7614c-152">Payment to non-resident sportsman including athlete or sports association or institution.</span></span> <span data-ttu-id="7614c-153">En el caso de deportistas no residentes, se incluyen pagos con respecto a anuncios y artículos sobre cualquier juego o deporte en la India en periódicos, revistas, etc.</span><span class="sxs-lookup"><span data-stu-id="7614c-153">In case of non-resident sportsman, payments in respect of advertisements as well as articles on any game/sports in India in newspapers, magazines, and so.</span></span> <span data-ttu-id="7614c-154">(sección 194E)</span><span class="sxs-lookup"><span data-stu-id="7614c-154">is included (Section 194E)</span></span>
    - <span data-ttu-id="7614c-155">Pago con respecto a depósitos bajo NSS \[Plan nacional de ahorro\] (sección 194EE)</span><span class="sxs-lookup"><span data-stu-id="7614c-155">Payment in respect of deposits under NSS \[National Savings Scheme\] (Section 194EE)</span></span>
    - <span data-ttu-id="7614c-156">Pago a cuenta de recompra de Participaciones por Fondo Mutuo o UTI (Sección 194F)</span><span class="sxs-lookup"><span data-stu-id="7614c-156">Payment on account of repurchase of Units by Mutual Fund or UTI (Section 194F)</span></span>
    - <span data-ttu-id="7614c-157">Pago para comisión o correduría (sección 194H)</span><span class="sxs-lookup"><span data-stu-id="7614c-157">Payment for Commission or brokerage (Section 194H)</span></span>
    - <span data-ttu-id="7614c-158">Pago del alquiler (sección 194I)</span><span class="sxs-lookup"><span data-stu-id="7614c-158">Payment of rent (Section 194I)</span></span>
    - <span data-ttu-id="7614c-159">Pago de cuotas por servicios profesionales o técnicos (sección 194J)</span><span class="sxs-lookup"><span data-stu-id="7614c-159">Payment of fees for professional or technical services (Section 194J)</span></span>
    - <span data-ttu-id="7614c-160">Comisión a Stockiest, distribuidores, compradores y vendedores de boletos de lotería, incluida la remuneración o el premio de dichos boletos (sección 194G)</span><span class="sxs-lookup"><span data-stu-id="7614c-160">Commission to Stockiest, distributors, buyers and sellers of Lottery tickets including remuneration or prize on such tickets (Section 194G)</span></span>
    - <span data-ttu-id="7614c-161">Ingresos de unidades compradas en divisa extranjera o ganancias de capital a largo plazo que surjan de la transferencia de dichas unidades compradas en divisa extranjera (sección 196B)</span><span class="sxs-lookup"><span data-stu-id="7614c-161">Income from Units purchased in foreign currency or long-term capital gain arising from the transfer of such Units purchased in foreign currency (Section 196B)</span></span>
    - <span data-ttu-id="7614c-162">Pago de cualquier ingreso a no residentes con respecto a intereses o dividendos sobre pólizas y acciones (sección 196C)</span><span class="sxs-lookup"><span data-stu-id="7614c-162">Payment of any income to non-residents in respect of interest or dividend on bonds and shares (Section 196C)</span></span>

<span data-ttu-id="7614c-163">Los TDS se calculan sobre compras, ventas, devoluciones de ventas, notas de crédito, adquisiciones de activos fijos, pagos anticipados, pagos por adelantado, pagarés, impuestos sobre obras y transacciones entre empresas.</span><span class="sxs-lookup"><span data-stu-id="7614c-163">TDS is calculated on purchases, sales, sales returns, credit notes, fixed asset acquisitions, prepayments, advance payments, promissory notes, works tax, and intercompany transactions.</span></span>

> [!NOTE]
> <span data-ttu-id="7614c-164">En el escenario fiscal actual de la India, los TDS no se calculan sobre las transacciones de ventas.</span><span class="sxs-lookup"><span data-stu-id="7614c-164">In the current Indian tax scenario, TDS isn't calculated on sales transactions.</span></span> <span data-ttu-id="7614c-165">Sin embargo, el sistema incluye una provisión para calcular los TDS recuperables en transacciones de ventas, especialmente para transacciones entre empresas.</span><span class="sxs-lookup"><span data-stu-id="7614c-165">However, the system includes a provision to calculate TDS recoverable on sales transactions, especially for intercompany transactions.</span></span>

<span data-ttu-id="7614c-166">El cálculo de TDS siempre tiene en cuenta el umbral y el umbral de excepción que se definen para el componente TDS.</span><span class="sxs-lookup"><span data-stu-id="7614c-166">The calculation of TDS always considers the threshold and the exception threshold that are defined for the TDS component.</span></span>

<span data-ttu-id="7614c-167">Se debe ejecutar el proceso de liquidación periódica de TDS y los pagos de TDS deben liquidarse a los proveedores de la autoridad de TDS.</span><span class="sxs-lookup"><span data-stu-id="7614c-167">The periodic TDS settlement process must be run, and the TDS payments must be settled to TDS authority vendors.</span></span>

<span data-ttu-id="7614c-168">Los números de certificado y las fechas de los certificados TDS que se reciben de proveedores o clientes se pueden registrar y actualizar.</span><span class="sxs-lookup"><span data-stu-id="7614c-168">The certificate numbers and dates for TDS certificates that are received from vendors or customers can be recorded and updated.</span></span> <span data-ttu-id="7614c-169">Además, los extractos de cuenta trimestrales del formulario 26Q y del formulario 27Q, además del certificado del formulario 16A para TDS, se pueden generar en Finance.</span><span class="sxs-lookup"><span data-stu-id="7614c-169">Additionally, Form 26Q and Form 27Q quarterly statements, and the Form 16A certificate for TDS, can be generated in Finance.</span></span>

## <a name="setting-up-and-working-with-tds"></a><span data-ttu-id="7614c-170">Configurar y trabajar con TDS</span><span class="sxs-lookup"><span data-stu-id="7614c-170">Setting up and working with TDS</span></span>

<span data-ttu-id="7614c-171">Aquí hay una descripción general del proceso para configurar y trabajar con TDS:</span><span class="sxs-lookup"><span data-stu-id="7614c-171">Here is an overview of the process for setting up and working with TDS:</span></span>

1. <span data-ttu-id="7614c-172">**Configuración de TDS:**</span><span class="sxs-lookup"><span data-stu-id="7614c-172">**TDS setup:**</span></span>

    - <span data-ttu-id="7614c-173">Configuración de parámetros:</span><span class="sxs-lookup"><span data-stu-id="7614c-173">Parameter setup:</span></span>

        - <span data-ttu-id="7614c-174">En los parámetros de contabilidad general, active los parámetros relacionados con TDS.</span><span class="sxs-lookup"><span data-stu-id="7614c-174">In General ledger parameters, activate parameters that are related to TDS.</span></span>
        - <span data-ttu-id="7614c-175">En los parámetros de contabilidad general, configure la secuencia numérica para los pagos de retención de impuestos.</span><span class="sxs-lookup"><span data-stu-id="7614c-175">In General ledger parameters, set up the number sequence for withholding tax payments.</span></span>
        - <span data-ttu-id="7614c-176">Configure los parámetros en proveedores y clientes.</span><span class="sxs-lookup"><span data-stu-id="7614c-176">Set up parameters in Accounts payable and Accounts receivable.</span></span>

    - <span data-ttu-id="7614c-177">Configuración básica:</span><span class="sxs-lookup"><span data-stu-id="7614c-177">Basic setup:</span></span>

        - <span data-ttu-id="7614c-178">Configure los números de registro de TDS para una empresa, clientes y proveedores.</span><span class="sxs-lookup"><span data-stu-id="7614c-178">Set up TDS registration numbers for a company, customers, and vendors.</span></span>
        - <span data-ttu-id="7614c-179">Configure los grupos de componentes de TDS.</span><span class="sxs-lookup"><span data-stu-id="7614c-179">Set up TDS component groups.</span></span>
        - <span data-ttu-id="7614c-180">Configure los componentes de TDS, adjunte los grupos de componentes de TDS y defina el umbral y el umbral de excepción para los mismos.</span><span class="sxs-lookup"><span data-stu-id="7614c-180">Set up TDS components, attach TDS component groups to them, and define the threshold and exception threshold for them.</span></span>
        - <span data-ttu-id="7614c-181">Configure las autoridades de TDS.</span><span class="sxs-lookup"><span data-stu-id="7614c-181">Set up TDS authorities.</span></span>
        - <span data-ttu-id="7614c-182">Configure los periodos de liquidación de TDS.</span><span class="sxs-lookup"><span data-stu-id="7614c-182">Set up TDS settlement periods.</span></span>
        - <span data-ttu-id="7614c-183">Configure los códigos de impuestos de TDS y adjunte los componentes de TDS.</span><span class="sxs-lookup"><span data-stu-id="7614c-183">Set up TDS tax codes, and attach TDS components to them.</span></span>
        - <span data-ttu-id="7614c-184">Configure los grupos de impuestos de TDS y adjunte los códigos de impuestos de TDS.</span><span class="sxs-lookup"><span data-stu-id="7614c-184">Set up TDS tax groups, and attach TDS tax codes to them.</span></span>
        - <span data-ttu-id="7614c-185">En el diseñador de fórmulas, defina una fórmula para calcular TDS para un grupo de TDS.</span><span class="sxs-lookup"><span data-stu-id="7614c-185">In the formula designer, define a formula to calculate TDS for a TDS group.</span></span>
        - <span data-ttu-id="7614c-186">Registre los números de los certificados de concesión de TDS.</span><span class="sxs-lookup"><span data-stu-id="7614c-186">Record TDS concession certificate numbers.</span></span>

    - <span data-ttu-id="7614c-187">Cuenta contable y configuración de la empresa:</span><span class="sxs-lookup"><span data-stu-id="7614c-187">Ledger accounts and company setup:</span></span>

        - <span data-ttu-id="7614c-188">Configure cuentas de proveedor y cliente de TDS.</span><span class="sxs-lookup"><span data-stu-id="7614c-188">Set up TDS payable and receivable ledger accounts.</span></span>
        - <span data-ttu-id="7614c-189">Configure un número de cuenta de deducción y recaudación de impuestos (TAN) y una categoría de tipo de deductor para la empresa.</span><span class="sxs-lookup"><span data-stu-id="7614c-189">Set up a Tax Deduction and Collection Account Number (TAN) and a deductor type category for the company.</span></span>

    - <span data-ttu-id="7614c-190">Otra configuración:</span><span class="sxs-lookup"><span data-stu-id="7614c-190">Other setup:</span></span>

        - <span data-ttu-id="7614c-191">Configure una programación de pagos que incluya la asignación de TDS.</span><span class="sxs-lookup"><span data-stu-id="7614c-191">Set up a payment schedule that includes TDS allocation.</span></span>
        - <span data-ttu-id="7614c-192">Configure un tipo de cuota de pago para pagos a la autoridad de TDS.</span><span class="sxs-lookup"><span data-stu-id="7614c-192">Set up a payment fee type for payments to the TDS authority.</span></span>
        - <span data-ttu-id="7614c-193">Configure información sobre grupos de TDS, números de cuenta permanentes (PAN) y TAN para proveedores y clientes.</span><span class="sxs-lookup"><span data-stu-id="7614c-193">Set up information about TDS groups, permanent account numbers (PANs), and TANs for vendors and customers.</span></span>

2. <span data-ttu-id="7614c-194">**Cálculo de TDS en transacciones:**</span><span class="sxs-lookup"><span data-stu-id="7614c-194">**Calculation of TDS in transactions:**</span></span>

    - <span data-ttu-id="7614c-195">Facturas y pagos</span><span class="sxs-lookup"><span data-stu-id="7614c-195">Invoices and payments</span></span>
    - <span data-ttu-id="7614c-196">Pagarés</span><span class="sxs-lookup"><span data-stu-id="7614c-196">Promissory notes</span></span>
    - <span data-ttu-id="7614c-197">Anticipos</span><span class="sxs-lookup"><span data-stu-id="7614c-197">Advance payments</span></span>
    - <span data-ttu-id="7614c-198">Pagos por adelantado</span><span class="sxs-lookup"><span data-stu-id="7614c-198">Prepayments</span></span>

3. <span data-ttu-id="7614c-199">**Liquidación de TDS:**</span><span class="sxs-lookup"><span data-stu-id="7614c-199">**TDS settlement:**</span></span>

    - <span data-ttu-id="7614c-200">Proceso de liquidación periódica de TDS</span><span class="sxs-lookup"><span data-stu-id="7614c-200">Periodic TDS settlement process</span></span>
    - <span data-ttu-id="7614c-201">Liquidación de pagos de TDS a proveedores de autoridad de TDS y generación de challan de TDS</span><span class="sxs-lookup"><span data-stu-id="7614c-201">Settlement of TDS payments to TDS authority vendors and generation of TDS challan</span></span>

4. <span data-ttu-id="7614c-202">**Consultas, extractos y certificado de TDS:**</span><span class="sxs-lookup"><span data-stu-id="7614c-202">**TDS inquiries, statements, and certificate:**</span></span>

    - <span data-ttu-id="7614c-203">Registre y actualice los números y fechas de certificados TDS.</span><span class="sxs-lookup"><span data-stu-id="7614c-203">Record and update TDS certificate numbers and dates.</span></span>
    - <span data-ttu-id="7614c-204">Genere una consulta de TDS y una consulta de TDS registrada.</span><span class="sxs-lookup"><span data-stu-id="7614c-204">Generate a TDS inquiry and a posted TDS inquiry.</span></span>
    - <span data-ttu-id="7614c-205">Genere el formulario 27A, el formulario 26Q y el formulario 27Q TDS y extractos de cuenta trimestrales de e-TDS.</span><span class="sxs-lookup"><span data-stu-id="7614c-205">Generate Form 27A, Form 26Q, and Form 27Q TDS and e-TDS quarterly statements.</span></span>
    - <span data-ttu-id="7614c-206">Genere un certificado de TDS del formulario 16A.</span><span class="sxs-lookup"><span data-stu-id="7614c-206">Generate a Form 16A TDS certificate.</span></span>
