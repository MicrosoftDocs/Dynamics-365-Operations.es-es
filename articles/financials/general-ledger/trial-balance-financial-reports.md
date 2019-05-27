---
title: Informes financieros de saldo de comprobación
description: En este artículo se describen los informes predeterminados para los saldos de comprobación. También se describen los componentes asociados a estos informes y cómo puede modificar los informes para que se adapten a sus requisitos empresariales.
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 12314
ms.assetid: 3b77d6f3-fd07-41a7-9ddb-1b22d1ae33fc
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c9e8c16724364df4dd62150056299e818470aa63
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1553700"
---
# <a name="trial-balance-financial-reports"></a><span data-ttu-id="a0b07-104">Informes financieros de saldo de comprobación</span><span class="sxs-lookup"><span data-stu-id="a0b07-104">Trial balance financial reports</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a0b07-105">En este artículo se describen los informes predeterminados para los saldos de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a0b07-105">This article describes the default reports for trial balances.</span></span> <span data-ttu-id="a0b07-106">También se describen los componentes asociados a estos informes y cómo puede modificar los informes para que se adapten a sus requisitos empresariales.</span><span class="sxs-lookup"><span data-stu-id="a0b07-106">It also describes the building blocks that are associated with these reports and how you can modify the reports to fit your business requirements.</span></span> 

<a name="default-trial-balance-reports"></a><span data-ttu-id="a0b07-107">Informes de saldo de comprobación predeterminados</span><span class="sxs-lookup"><span data-stu-id="a0b07-107">Default trial balance reports</span></span>
-----------------------------

<span data-ttu-id="a0b07-108">Hay tres informes de saldo de comprobación disponibles en Informes financieros en Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a0b07-108">Three trial balance reports are available in Financial reporting in Microsoft Dynamics 365 for Finance and Operations.</span></span>

| <span data-ttu-id="a0b07-109">Informe predeterminado</span><span class="sxs-lookup"><span data-stu-id="a0b07-109">Default report</span></span>                                 | <span data-ttu-id="a0b07-110">Qué hace</span><span class="sxs-lookup"><span data-stu-id="a0b07-110">What it does</span></span>                                                                                                                                                                                        |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="a0b07-111">Saldo de comprobación detallado - predeterminado</span><span class="sxs-lookup"><span data-stu-id="a0b07-111">Detailed Trial Balance - Default</span></span>               | <span data-ttu-id="a0b07-112">Ofrece información de saldo para todas las cuentas e incluye saldos de débito y de crédito, y el neto de estos, junto con la fecha de transacción, el asiento y la descripción del diario.</span><span class="sxs-lookup"><span data-stu-id="a0b07-112">Provides balance information for all accounts, and includes debit and credit balances, and the net of these, together with the transaction date, voucher, and journal description.</span></span>                  |
| <span data-ttu-id="a0b07-113">Resumen de saldo de comprobación – predeterminado</span><span class="sxs-lookup"><span data-stu-id="a0b07-113">Summary Trial Balance – Default</span></span>                | <span data-ttu-id="a0b07-114">Ofrece información de saldo para todas las cuentas e incluye saldos de apertura y de cierre, y saldos de débito y crédito, junto con su diferencia neta.</span><span class="sxs-lookup"><span data-stu-id="a0b07-114">Provides balance information for all accounts, and includes opening and closing balances, and debit and credit balances, together with their net difference.</span></span>                                        |
| <span data-ttu-id="a0b07-115">Resumen de saldo de comprobación año por año – predeterminado</span><span class="sxs-lookup"><span data-stu-id="a0b07-115">Summary Trial Balance Year Over Year – Default</span></span> | <span data-ttu-id="a0b07-116">Ofrece información de saldo para todas las cuentas e incluye saldos de apertura y cierre, y saldos de débito y crédito, junto con su diferencia neta para el año actual y el anterior.</span><span class="sxs-lookup"><span data-stu-id="a0b07-116">Provides balance information for all accounts, and includes opening and closing balances, and debit and credit balances, together with their net difference for the current year and the past year.</span></span> |

## <a name="building-blocks"></a><span data-ttu-id="a0b07-117">Bloques de creación</span><span class="sxs-lookup"><span data-stu-id="a0b07-117">Building blocks</span></span>
<span data-ttu-id="a0b07-118">Los informes financieros del saldo de comprobación usan los siguientes bloques de creación.</span><span class="sxs-lookup"><span data-stu-id="a0b07-118">The trial balance financial reports use the following building blocks.</span></span>

| <span data-ttu-id="a0b07-119">Informe predeterminado</span><span class="sxs-lookup"><span data-stu-id="a0b07-119">Default report</span></span>                                 | <span data-ttu-id="a0b07-120">Definición de filas</span><span class="sxs-lookup"><span data-stu-id="a0b07-120">Row definition</span></span>          | <span data-ttu-id="a0b07-121">Definición de columnas</span><span class="sxs-lookup"><span data-stu-id="a0b07-121">Column definition</span></span>                              |
|------------------------------------------------|-------------------------|------------------------------------------------|
| <span data-ttu-id="a0b07-122">Saldo de comprobación detallado - predeterminado</span><span class="sxs-lookup"><span data-stu-id="a0b07-122">Detailed Trial Balance - Default</span></span>               | <span data-ttu-id="a0b07-123">Saldo de comprobación - predeterminado</span><span class="sxs-lookup"><span data-stu-id="a0b07-123">Trial Balance - Default</span></span> | <span data-ttu-id="a0b07-124">Saldo de comprobación detallado - predeterminado</span><span class="sxs-lookup"><span data-stu-id="a0b07-124">Detailed Trial Balance - Default</span></span>               |
| <span data-ttu-id="a0b07-125">Resumen de saldo de comprobación – predeterminado</span><span class="sxs-lookup"><span data-stu-id="a0b07-125">Summary Trial Balance – Default</span></span>                | <span data-ttu-id="a0b07-126">Saldo de comprobación - predeterminado</span><span class="sxs-lookup"><span data-stu-id="a0b07-126">Trial Balance - Default</span></span> | <span data-ttu-id="a0b07-127">Resumen de saldo de comprobación - predeterminado</span><span class="sxs-lookup"><span data-stu-id="a0b07-127">Summary Trial Balance - Default</span></span>                |
| <span data-ttu-id="a0b07-128">Resumen de saldo de comprobación año por año – predeterminado</span><span class="sxs-lookup"><span data-stu-id="a0b07-128">Summary Trial Balance Year Over Year – Default</span></span> | <span data-ttu-id="a0b07-129">Saldo de comprobación - predeterminado</span><span class="sxs-lookup"><span data-stu-id="a0b07-129">Trial Balance - Default</span></span> | <span data-ttu-id="a0b07-130">Resumen de saldo de comprobación año por año - predeterminado</span><span class="sxs-lookup"><span data-stu-id="a0b07-130">Summary Trial Balance Year Over Year - Default</span></span> |

### <a name="row-definition"></a><span data-ttu-id="a0b07-131">Definición de filas</span><span class="sxs-lookup"><span data-stu-id="a0b07-131">Row definition</span></span>

<span data-ttu-id="a0b07-132">La definición de filas, Saldo de comprobación – Predeterminado, contiene una sola fila que extrae todas las cuentas principales.</span><span class="sxs-lookup"><span data-stu-id="a0b07-132">The row definition, Trial Balance – Default, contains a single row that pulls in all main accounts.</span></span> <span data-ttu-id="a0b07-133">Por tanto, cualquier persona puede generar el informe sin tener que realizar ninguna modificación.</span><span class="sxs-lookup"><span data-stu-id="a0b07-133">Therefore, anyone can generate the report without having to make any modifications.</span></span> <span data-ttu-id="a0b07-134">Cuando ve el informe, explora la fila única para ver los detalles acerca de cada cuenta.</span><span class="sxs-lookup"><span data-stu-id="a0b07-134">When you view the report, you drill into the single row to see details about each account.</span></span> <span data-ttu-id="a0b07-135">Puede modificar la definición de filas para que incluya más detalle.</span><span class="sxs-lookup"><span data-stu-id="a0b07-135">You can modify the row definition so that it includes more detail.</span></span> <span data-ttu-id="a0b07-136">Para modificar la definición de filas Saldo de comprobación - predeterminado para que incluya filas para todas las cuentas, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a0b07-136">To modify the Trial Balance – Default row definition so that it includes rows for all accounts, follow these steps.</span></span>

1.  <span data-ttu-id="a0b07-137">Haga clic en **Editar** y, a continuación, en **Insertar filas de dimensiones**.</span><span class="sxs-lookup"><span data-stu-id="a0b07-137">Click **Edit**, and then click **Insert Rows from Dimensions**.</span></span> <span data-ttu-id="a0b07-138">El comando **Insertar filas de dimensiones** le permite elegir las dimensiones que desea tener en la definición de filas.</span><span class="sxs-lookup"><span data-stu-id="a0b07-138">The **Insert Rows from Dimensions** command lets you choose the dimensions that you want to have in your row definition.</span></span> <span data-ttu-id="a0b07-139">Para esta definición de filas, va a usar **Cuenta principal**.</span><span class="sxs-lookup"><span data-stu-id="a0b07-139">For this row definition, you're going to use **Main Account**.</span></span>
2.  <span data-ttu-id="a0b07-140">Asegúrese de que **Cuenta principal** contiene todos los ampersands (&) y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a0b07-140">Make sure that **Main Account** contains all ampersands (&), and then click **OK**.</span></span>

<span data-ttu-id="a0b07-141">La definición de filas contiene ahora todas las cuentas principales para la entidad jurídica predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a0b07-141">The row definition now contains all the main accounts for your default legal entity.</span></span>

### <a name="column-definition"></a><span data-ttu-id="a0b07-142">Definición de columnas</span><span class="sxs-lookup"><span data-stu-id="a0b07-142">Column definition</span></span>

<span data-ttu-id="a0b07-143">Cada informe de saldo de comprobación usa otra definición de columna.</span><span class="sxs-lookup"><span data-stu-id="a0b07-143">Each trial balance report uses a different column definition.</span></span> <span data-ttu-id="a0b07-144">Estas definiciones de columnas contienen diversos tipos de columnas para proporcionar distintos niveles de detalle y datos financieros.</span><span class="sxs-lookup"><span data-stu-id="a0b07-144">These column definitions contain different types of columns to provide different levels of detail and financial data.</span></span>

-   <span data-ttu-id="a0b07-145">**Tipos de columnas de Saldo de comprobación detallados – predeterminado:**</span><span class="sxs-lookup"><span data-stu-id="a0b07-145">**Detailed Trial Balance – Default column types:**</span></span>
    -   <span data-ttu-id="a0b07-146">**DESC** : la descripción de la definición de filas.</span><span class="sxs-lookup"><span data-stu-id="a0b07-146">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="a0b07-147">**ACCT**: códigos de cuenta</span><span class="sxs-lookup"><span data-stu-id="a0b07-147">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="a0b07-148">**ATTR (3)** atributos:</span><span class="sxs-lookup"><span data-stu-id="a0b07-148">**ATTR (3)** – Attributes:</span></span>
        -   <span data-ttu-id="a0b07-149">Fecha de la transacción</span><span class="sxs-lookup"><span data-stu-id="a0b07-149">Transaction Date</span></span>
        -   <span data-ttu-id="a0b07-150">Comprobante</span><span class="sxs-lookup"><span data-stu-id="a0b07-150">Voucher</span></span>
        -   <span data-ttu-id="a0b07-151">Descripción del diario</span><span class="sxs-lookup"><span data-stu-id="a0b07-151">Journal Description</span></span>
    -   <span data-ttu-id="a0b07-152">**FD**: los datos financieros que contienen solo débitos</span><span class="sxs-lookup"><span data-stu-id="a0b07-152">**FD** – Financial data that contains only debits</span></span>
    -   <span data-ttu-id="a0b07-153">**FD**: los datos financieros que contienen solo créditos</span><span class="sxs-lookup"><span data-stu-id="a0b07-153">**FD** – Financial data that contains only credits</span></span>
    -   <span data-ttu-id="a0b07-154">**CALC**: la diferencia neta</span><span class="sxs-lookup"><span data-stu-id="a0b07-154">**CALC** – The net difference</span></span>
-   <span data-ttu-id="a0b07-155">**Tipos de columnas de Resumen de saldo de comprobación - predeterminado:**</span><span class="sxs-lookup"><span data-stu-id="a0b07-155">**Summary Trial Balance – Default columns types:**</span></span>
    -   <span data-ttu-id="a0b07-156">**ACCT**: códigos de cuenta</span><span class="sxs-lookup"><span data-stu-id="a0b07-156">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="a0b07-157">**DESC** : la descripción de la definición de filas.</span><span class="sxs-lookup"><span data-stu-id="a0b07-157">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="a0b07-158">**ATTR**: un atributo:</span><span class="sxs-lookup"><span data-stu-id="a0b07-158">**ATTR** – An attribute:</span></span>
        -   <span data-ttu-id="a0b07-159">Comprobante</span><span class="sxs-lookup"><span data-stu-id="a0b07-159">Voucher</span></span>
    -   <span data-ttu-id="a0b07-160">**FD**: los datos financieros de saldo inicial</span><span class="sxs-lookup"><span data-stu-id="a0b07-160">**FD** – The beginning balance financial data</span></span>
    -   <span data-ttu-id="a0b07-161">**FD**: los datos financieros que contienen solo débitos</span><span class="sxs-lookup"><span data-stu-id="a0b07-161">**FD** – Financial data that contains only debits</span></span>
    -   <span data-ttu-id="a0b07-162">**FD**: los datos financieros que contienen solo créditos</span><span class="sxs-lookup"><span data-stu-id="a0b07-162">**FD** – Financial data that contains only credits</span></span>
    -   <span data-ttu-id="a0b07-163">**CALC**: la diferencia neta</span><span class="sxs-lookup"><span data-stu-id="a0b07-163">**CALC** – The net difference</span></span>
    -   <span data-ttu-id="a0b07-164">**CALC**: el saldo de cierre</span><span class="sxs-lookup"><span data-stu-id="a0b07-164">**CALC** – The closing balance</span></span>
-   <span data-ttu-id="a0b07-165">**Resumen de saldo de comprobación año por año - predeterminado:**</span><span class="sxs-lookup"><span data-stu-id="a0b07-165">**Summary Trial Balance Year Over Year – Default:**</span></span>
    -   <span data-ttu-id="a0b07-166">**ACCT**: códigos de cuenta</span><span class="sxs-lookup"><span data-stu-id="a0b07-166">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="a0b07-167">**DESC** : la descripción de la definición de filas.</span><span class="sxs-lookup"><span data-stu-id="a0b07-167">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="a0b07-168">**ATTR**: un atributo</span><span class="sxs-lookup"><span data-stu-id="a0b07-168">**ATTR** – An attribute</span></span>
        -   <span data-ttu-id="a0b07-169">Comprobante</span><span class="sxs-lookup"><span data-stu-id="a0b07-169">Voucher</span></span>
    -   <span data-ttu-id="a0b07-170">**FD**: datos financieros de saldo inicial para el año actual</span><span class="sxs-lookup"><span data-stu-id="a0b07-170">**FD** – The beginning balance financial data for the current year</span></span>
    -   <span data-ttu-id="a0b07-171">**FD**: los datos financieros que solo contienen débitos para el año actual</span><span class="sxs-lookup"><span data-stu-id="a0b07-171">**FD** – Financial data that contains only debits for the current year</span></span>
    -   <span data-ttu-id="a0b07-172">**FD**: los datos financieros que solo contienen créditos para el año actual</span><span class="sxs-lookup"><span data-stu-id="a0b07-172">**FD** – Financial data that contains only credits for the current year</span></span>
    -   <span data-ttu-id="a0b07-173">**CALC**: la diferencia neta</span><span class="sxs-lookup"><span data-stu-id="a0b07-173">**CALC** – The net difference</span></span>
    -   <span data-ttu-id="a0b07-174">**CALC**: el saldo de cierre</span><span class="sxs-lookup"><span data-stu-id="a0b07-174">**CALC** – The closing balance</span></span>
    -   <span data-ttu-id="a0b07-175">**FD**: los datos financieros que solo contienen débitos para el año pasado</span><span class="sxs-lookup"><span data-stu-id="a0b07-175">**FD** – Financial data that contains only debits for the last year</span></span>
    -   <span data-ttu-id="a0b07-176">**FD**: los datos financieros que solo contienen créditos para el año pasado</span><span class="sxs-lookup"><span data-stu-id="a0b07-176">**FD** – Financial data that contains only credits for the last year</span></span>



<a name="additional-resources"></a><span data-ttu-id="a0b07-177">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a0b07-177">Additional resources</span></span>
--------

[<span data-ttu-id="a0b07-178">Informes financieros</span><span class="sxs-lookup"><span data-stu-id="a0b07-178">Financial reporting</span></span>](financial-reporting-getting-started.md)

[<span data-ttu-id="a0b07-179">Ver informes financieros</span><span class="sxs-lookup"><span data-stu-id="a0b07-179">View financial reports</span></span>](view-financial-reports.md)

[<span data-ttu-id="a0b07-180">Blog de informes financieros de Dynamics</span><span class="sxs-lookup"><span data-stu-id="a0b07-180">Dynamics Financial Reporting Blog</span></span>](http://blogs.msdn.com/b/dynamics_financial_reporting/)



