---
title: Informes financieros de saldo de comprobación
description: En este artículo se describen los informes predeterminados para los saldos de comprobación. También se describen los componentes asociados a estos informes y cómo puede modificar los informes para que se adapten a sus requisitos empresariales.
author: jinniew
ms.date: 05/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: roschlom
ms.custom: 12314
ms.assetid: 3b77d6f3-fd07-41a7-9ddb-1b22d1ae33fc
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 26ec03422315a280f7e779f992cf694eb5f845ea
ms.sourcegitcommit: 365092f735310990e82516110141d42aaf04e654
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2021
ms.locfileid: "6103667"
---
# <a name="trial-balance-financial-reports"></a><span data-ttu-id="50bfe-104">Informes financieros de saldo de comprobación</span><span class="sxs-lookup"><span data-stu-id="50bfe-104">Trial balance financial reports</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="50bfe-105">En este artículo se describen los informes predeterminados para los saldos de comprobación.</span><span class="sxs-lookup"><span data-stu-id="50bfe-105">This article describes the default reports for trial balances.</span></span> <span data-ttu-id="50bfe-106">También se describen los componentes asociados a estos informes y cómo puede modificar los informes para que se adapten a sus requisitos empresariales.</span><span class="sxs-lookup"><span data-stu-id="50bfe-106">It also describes the building blocks that are associated with these reports and how you can modify the reports to fit your business requirements.</span></span> 

## <a name="default-trial-balance-reports"></a><span data-ttu-id="50bfe-107">Informes de saldo de comprobación predeterminados</span><span class="sxs-lookup"><span data-stu-id="50bfe-107">Default trial balance reports</span></span>

<span data-ttu-id="50bfe-108">Hay tres informes de saldo de comprobación disponibles en Informes financieros.</span><span class="sxs-lookup"><span data-stu-id="50bfe-108">Three trial balance reports are available in Financial reporting.</span></span>

| <span data-ttu-id="50bfe-109">Informe predeterminado</span><span class="sxs-lookup"><span data-stu-id="50bfe-109">Default report</span></span>                                 | <span data-ttu-id="50bfe-110">Qué hace</span><span class="sxs-lookup"><span data-stu-id="50bfe-110">What it does</span></span>                                                                                                                                                                                        |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="50bfe-111">Saldo de comprobación detallado - predeterminado</span><span class="sxs-lookup"><span data-stu-id="50bfe-111">Detailed Trial Balance - Default</span></span>               | <span data-ttu-id="50bfe-112">Ofrece información de saldo para todas las cuentas e incluye saldos de débito y de crédito, y el neto de estos, junto con la fecha de transacción, el asiento y la descripción del diario.</span><span class="sxs-lookup"><span data-stu-id="50bfe-112">Provides balance information for all accounts, and includes debit and credit balances, and the net of these, together with the transaction date, voucher, and journal description.</span></span>                  |
| <span data-ttu-id="50bfe-113">Resumen de saldo de comprobación – predeterminado</span><span class="sxs-lookup"><span data-stu-id="50bfe-113">Summary Trial Balance – Default</span></span>                | <span data-ttu-id="50bfe-114">Ofrece información de saldo para todas las cuentas e incluye saldos de apertura y de cierre, y saldos de débito y crédito, junto con su diferencia neta.</span><span class="sxs-lookup"><span data-stu-id="50bfe-114">Provides balance information for all accounts, and includes opening and closing balances, and debit and credit balances, together with their net difference.</span></span>                                        |
| <span data-ttu-id="50bfe-115">Resumen de saldo de comprobación año por año – predeterminado</span><span class="sxs-lookup"><span data-stu-id="50bfe-115">Summary Trial Balance Year Over Year – Default</span></span> | <span data-ttu-id="50bfe-116">Ofrece información de saldo para todas las cuentas e incluye saldos de apertura y cierre, y saldos de débito y crédito, junto con su diferencia neta para el año actual y el anterior.</span><span class="sxs-lookup"><span data-stu-id="50bfe-116">Provides balance information for all accounts, and includes opening and closing balances, and debit and credit balances, together with their net difference for the current year and the past year.</span></span> |

## <a name="building-blocks"></a><span data-ttu-id="50bfe-117">Bloques de creación</span><span class="sxs-lookup"><span data-stu-id="50bfe-117">Building blocks</span></span>
<span data-ttu-id="50bfe-118">Los informes financieros del saldo de comprobación usan los siguientes bloques de creación.</span><span class="sxs-lookup"><span data-stu-id="50bfe-118">The trial balance financial reports use the following building blocks.</span></span>

| <span data-ttu-id="50bfe-119">Informe predeterminado</span><span class="sxs-lookup"><span data-stu-id="50bfe-119">Default report</span></span>                                 | <span data-ttu-id="50bfe-120">Definición de filas</span><span class="sxs-lookup"><span data-stu-id="50bfe-120">Row definition</span></span>          | <span data-ttu-id="50bfe-121">Definición de columnas</span><span class="sxs-lookup"><span data-stu-id="50bfe-121">Column definition</span></span>                              |
|------------------------------------------------|-------------------------|------------------------------------------------|
| <span data-ttu-id="50bfe-122">Saldo de comprobación detallado - predeterminado</span><span class="sxs-lookup"><span data-stu-id="50bfe-122">Detailed Trial Balance - Default</span></span>               | <span data-ttu-id="50bfe-123">Saldo de comprobación - predeterminado</span><span class="sxs-lookup"><span data-stu-id="50bfe-123">Trial Balance - Default</span></span> | <span data-ttu-id="50bfe-124">Saldo de comprobación detallado - predeterminado</span><span class="sxs-lookup"><span data-stu-id="50bfe-124">Detailed Trial Balance - Default</span></span>               |
| <span data-ttu-id="50bfe-125">Resumen de saldo de comprobación – predeterminado</span><span class="sxs-lookup"><span data-stu-id="50bfe-125">Summary Trial Balance – Default</span></span>                | <span data-ttu-id="50bfe-126">Saldo de comprobación - predeterminado</span><span class="sxs-lookup"><span data-stu-id="50bfe-126">Trial Balance - Default</span></span> | <span data-ttu-id="50bfe-127">Resumen de saldo de comprobación - predeterminado</span><span class="sxs-lookup"><span data-stu-id="50bfe-127">Summary Trial Balance - Default</span></span>                |
| <span data-ttu-id="50bfe-128">Resumen de saldo de comprobación año por año – predeterminado</span><span class="sxs-lookup"><span data-stu-id="50bfe-128">Summary Trial Balance Year Over Year – Default</span></span> | <span data-ttu-id="50bfe-129">Saldo de comprobación - predeterminado</span><span class="sxs-lookup"><span data-stu-id="50bfe-129">Trial Balance - Default</span></span> | <span data-ttu-id="50bfe-130">Resumen de saldo de comprobación año por año - predeterminado</span><span class="sxs-lookup"><span data-stu-id="50bfe-130">Summary Trial Balance Year Over Year - Default</span></span> |

> [!NOTE] 
> <span data-ttu-id="50bfe-131">Al ejecutar el informe **Saldo de comprobación** en Financial Reporting, asegúrese de seleccionar las casillas de verificación para **Mostrar filas sin importes** y **Mostrar informes sin filas activas** en la pestaña **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="50bfe-131">When running the **Trial Balance** report in Financial reporting, be sure to select the check boxes for **Display rows with no amounts** and **Display reports with no active rows** on the **Settings** tab.</span></span>

### <a name="row-definition"></a><span data-ttu-id="50bfe-132">Definición de filas</span><span class="sxs-lookup"><span data-stu-id="50bfe-132">Row definition</span></span>

<span data-ttu-id="50bfe-133">La definición de filas, Saldo de comprobación – Predeterminado, contiene una sola fila que extrae todas las cuentas principales.</span><span class="sxs-lookup"><span data-stu-id="50bfe-133">The row definition, Trial Balance – Default, contains a single row that pulls in all main accounts.</span></span> <span data-ttu-id="50bfe-134">Por tanto, cualquier persona puede generar el informe sin tener que realizar ninguna modificación.</span><span class="sxs-lookup"><span data-stu-id="50bfe-134">Therefore, anyone can generate the report without having to make any modifications.</span></span> <span data-ttu-id="50bfe-135">Cuando ve el informe, explora la fila única para ver los detalles acerca de cada cuenta.</span><span class="sxs-lookup"><span data-stu-id="50bfe-135">When you view the report, you drill into the single row to see details about each account.</span></span> <span data-ttu-id="50bfe-136">Puede modificar la definición de filas para que incluya más detalle.</span><span class="sxs-lookup"><span data-stu-id="50bfe-136">You can modify the row definition so that it includes more detail.</span></span> <span data-ttu-id="50bfe-137">Para modificar la definición de filas Saldo de comprobación - predeterminado para que incluya filas para todas las cuentas, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="50bfe-137">To modify the Trial Balance – Default row definition so that it includes rows for all accounts, follow these steps.</span></span>

1.  <span data-ttu-id="50bfe-138">Haga clic en **Editar** y, a continuación, en **Insertar filas de dimensiones**.</span><span class="sxs-lookup"><span data-stu-id="50bfe-138">Click **Edit**, and then click **Insert Rows from Dimensions**.</span></span> <span data-ttu-id="50bfe-139">El comando **Insertar filas de dimensiones** le permite elegir las dimensiones que desea tener en la definición de filas.</span><span class="sxs-lookup"><span data-stu-id="50bfe-139">The **Insert Rows from Dimensions** command lets you choose the dimensions that you want to have in your row definition.</span></span> <span data-ttu-id="50bfe-140">Para esta definición de filas, va a usar **Cuenta principal**.</span><span class="sxs-lookup"><span data-stu-id="50bfe-140">For this row definition, you're going to use **Main Account**.</span></span>
2.  <span data-ttu-id="50bfe-141">Asegúrese de que **Cuenta principal** contiene todos los ampersands (&) y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="50bfe-141">Make sure that **Main Account** contains all ampersands (&), and then click **OK**.</span></span>

<span data-ttu-id="50bfe-142">La definición de filas contiene ahora todas las cuentas principales para la entidad jurídica predeterminada.</span><span class="sxs-lookup"><span data-stu-id="50bfe-142">The row definition now contains all the main accounts for your default legal entity.</span></span>

### <a name="column-definition"></a><span data-ttu-id="50bfe-143">Definición de columnas</span><span class="sxs-lookup"><span data-stu-id="50bfe-143">Column definition</span></span>

<span data-ttu-id="50bfe-144">Cada informe de saldo de comprobación usa otra definición de columna.</span><span class="sxs-lookup"><span data-stu-id="50bfe-144">Each trial balance report uses a different column definition.</span></span> <span data-ttu-id="50bfe-145">Estas definiciones de columnas contienen diversos tipos de columnas para proporcionar distintos niveles de detalle y datos financieros.</span><span class="sxs-lookup"><span data-stu-id="50bfe-145">These column definitions contain different types of columns to provide different levels of detail and financial data.</span></span>

-   <span data-ttu-id="50bfe-146">**Tipos de columnas de Saldo de comprobación detallados – predeterminado:**</span><span class="sxs-lookup"><span data-stu-id="50bfe-146">**Detailed Trial Balance – Default column types:**</span></span>
    -   <span data-ttu-id="50bfe-147">**DESC** : la descripción de la definición de filas.</span><span class="sxs-lookup"><span data-stu-id="50bfe-147">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="50bfe-148">**ACCT**: códigos de cuenta</span><span class="sxs-lookup"><span data-stu-id="50bfe-148">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="50bfe-149">**ATTR (3)** atributos:</span><span class="sxs-lookup"><span data-stu-id="50bfe-149">**ATTR (3)** – Attributes:</span></span>
        -   <span data-ttu-id="50bfe-150">Fecha de la transacción</span><span class="sxs-lookup"><span data-stu-id="50bfe-150">Transaction Date</span></span>
        -   <span data-ttu-id="50bfe-151">Comprobante</span><span class="sxs-lookup"><span data-stu-id="50bfe-151">Voucher</span></span>
        -   <span data-ttu-id="50bfe-152">Descripción del diario</span><span class="sxs-lookup"><span data-stu-id="50bfe-152">Journal Description</span></span>
    -   <span data-ttu-id="50bfe-153">**FD**: los datos financieros que contienen solo débitos</span><span class="sxs-lookup"><span data-stu-id="50bfe-153">**FD** – Financial data that contains only debits</span></span>
    -   <span data-ttu-id="50bfe-154">**FD**: los datos financieros que contienen solo créditos</span><span class="sxs-lookup"><span data-stu-id="50bfe-154">**FD** – Financial data that contains only credits</span></span>
    -   <span data-ttu-id="50bfe-155">**CALC**: la diferencia neta</span><span class="sxs-lookup"><span data-stu-id="50bfe-155">**CALC** – The net difference</span></span>
-   <span data-ttu-id="50bfe-156">**Tipos de columnas de Resumen de saldo de comprobación - predeterminado:**</span><span class="sxs-lookup"><span data-stu-id="50bfe-156">**Summary Trial Balance – Default columns types:**</span></span>
    -   <span data-ttu-id="50bfe-157">**ACCT**: códigos de cuenta</span><span class="sxs-lookup"><span data-stu-id="50bfe-157">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="50bfe-158">**DESC** : la descripción de la definición de filas.</span><span class="sxs-lookup"><span data-stu-id="50bfe-158">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="50bfe-159">**ATTR**: un atributo:</span><span class="sxs-lookup"><span data-stu-id="50bfe-159">**ATTR** – An attribute:</span></span>
        -   <span data-ttu-id="50bfe-160">Comprobante</span><span class="sxs-lookup"><span data-stu-id="50bfe-160">Voucher</span></span>
    -   <span data-ttu-id="50bfe-161">**FD**: los datos financieros de saldo inicial</span><span class="sxs-lookup"><span data-stu-id="50bfe-161">**FD** – The beginning balance financial data</span></span>
    -   <span data-ttu-id="50bfe-162">**FD**: los datos financieros que contienen solo débitos</span><span class="sxs-lookup"><span data-stu-id="50bfe-162">**FD** – Financial data that contains only debits</span></span>
    -   <span data-ttu-id="50bfe-163">**FD**: los datos financieros que contienen solo créditos</span><span class="sxs-lookup"><span data-stu-id="50bfe-163">**FD** – Financial data that contains only credits</span></span>
    -   <span data-ttu-id="50bfe-164">**CALC**: la diferencia neta</span><span class="sxs-lookup"><span data-stu-id="50bfe-164">**CALC** – The net difference</span></span>
    -   <span data-ttu-id="50bfe-165">**CALC**: el saldo de cierre</span><span class="sxs-lookup"><span data-stu-id="50bfe-165">**CALC** – The closing balance</span></span>
-   <span data-ttu-id="50bfe-166">**Resumen de saldo de comprobación año por año - predeterminado:**</span><span class="sxs-lookup"><span data-stu-id="50bfe-166">**Summary Trial Balance Year Over Year – Default:**</span></span>
    -   <span data-ttu-id="50bfe-167">**ACCT**: códigos de cuenta</span><span class="sxs-lookup"><span data-stu-id="50bfe-167">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="50bfe-168">**DESC** : la descripción de la definición de filas.</span><span class="sxs-lookup"><span data-stu-id="50bfe-168">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="50bfe-169">**ATTR**: un atributo</span><span class="sxs-lookup"><span data-stu-id="50bfe-169">**ATTR** – An attribute</span></span>
        -   <span data-ttu-id="50bfe-170">Comprobante</span><span class="sxs-lookup"><span data-stu-id="50bfe-170">Voucher</span></span>
    -   <span data-ttu-id="50bfe-171">**FD**: datos financieros de saldo inicial para el año actual</span><span class="sxs-lookup"><span data-stu-id="50bfe-171">**FD** – The beginning balance financial data for the current year</span></span>
    -   <span data-ttu-id="50bfe-172">**FD**: los datos financieros que solo contienen débitos para el año actual</span><span class="sxs-lookup"><span data-stu-id="50bfe-172">**FD** – Financial data that contains only debits for the current year</span></span>
    -   <span data-ttu-id="50bfe-173">**FD**: los datos financieros que solo contienen créditos para el año actual</span><span class="sxs-lookup"><span data-stu-id="50bfe-173">**FD** – Financial data that contains only credits for the current year</span></span>
    -   <span data-ttu-id="50bfe-174">**CALC**: la diferencia neta</span><span class="sxs-lookup"><span data-stu-id="50bfe-174">**CALC** – The net difference</span></span>
    -   <span data-ttu-id="50bfe-175">**CALC**: el saldo de cierre</span><span class="sxs-lookup"><span data-stu-id="50bfe-175">**CALC** – The closing balance</span></span>
    -   <span data-ttu-id="50bfe-176">**FD**: los datos financieros que solo contienen débitos para el año pasado</span><span class="sxs-lookup"><span data-stu-id="50bfe-176">**FD** – Financial data that contains only debits for the last year</span></span>
    -   <span data-ttu-id="50bfe-177">**FD**: los datos financieros que solo contienen créditos para el año pasado</span><span class="sxs-lookup"><span data-stu-id="50bfe-177">**FD** – Financial data that contains only credits for the last year</span></span>

## <a name="additional-resources"></a><span data-ttu-id="50bfe-178">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="50bfe-178">Additional resources</span></span>

[<span data-ttu-id="50bfe-179">Visión general de informes financieros</span><span class="sxs-lookup"><span data-stu-id="50bfe-179">Financial reporting overview</span></span>](financial-reporting-getting-started.md)

[<span data-ttu-id="50bfe-180">Ver informes financieros</span><span class="sxs-lookup"><span data-stu-id="50bfe-180">View financial reports</span></span>](view-financial-reports.md)

[<span data-ttu-id="50bfe-181">Blog de informes financieros de Dynamics</span><span class="sxs-lookup"><span data-stu-id="50bfe-181">Dynamics Financial Reporting Blog</span></span>](https://blogs.msdn.com/b/dynamics_financial_reporting/)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
