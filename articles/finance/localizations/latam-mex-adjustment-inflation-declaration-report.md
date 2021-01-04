---
title: Informe de la declaración de inflación de ajuste
description: Los usuarios de Microsoft Dynamics 365 Finance pueden procesar ajustes de inflación mediante coeficientes de INPC, distintos métodos (como saldos de apertura, saldo, saldo mensual y fecha de transacción) y diversas dimensiones.
author: sndray
manager: AnnBe
ms.date: 10/31/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InflationAdjJournal_MX, InpcRateTable_MX, LedgerParameters, MainAccount
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 9391
ms.assetid: 9076bf16-0021-47ad-a3b9-1bab75c583ec
ms.search.region: Mexico
ms.author: sndray
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bf8ebc17845ba1e15d5e0fb7e1b22907beebe460
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4407787"
---
# <a name="adjustment-inflation-declaration-report"></a><span data-ttu-id="f8104-103">Informe de la declaración de inflación de ajuste</span><span class="sxs-lookup"><span data-stu-id="f8104-103">Adjustment inflation declaration report</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f8104-104">Puede procesar ajustes de inflación mediante coeficientes de INPC, distintos métodos (como saldos de apertura, saldo, saldo mensual y fecha de transacción) y diversas dimensiones.</span><span class="sxs-lookup"><span data-stu-id="f8104-104">You can process inflation adjustments by using INPC rates, various methods (such as opening balance, balance, monthly balance, and transaction date), and various dimensions.</span></span>

<span data-ttu-id="f8104-105">Todas las empresas de México deben aplicar el proceso de NIF B-10 para reconocimiento de inflación en informes financieros si la tasa de inflación acumulativa durante los tres últimos años es igual o supera el 26 por ciento.</span><span class="sxs-lookup"><span data-stu-id="f8104-105">All companies in Mexico are required to apply the NIF B-10 process to inflation recognition in financial statements if the cumulative inflation rate during the last three years equals or exceeds 26 percent.</span></span> <span data-ttu-id="f8104-106">Al usar las tasas de índice del Índice Nacional de Precios al Consumidor (INPC) cada mes, puede expresar los valores de transacción en la fecha de cierre de la hoja del saldo general.</span><span class="sxs-lookup"><span data-stu-id="f8104-106">By using the Índice Nacional de Precios al Consumidor (INPC) index rates every month, you can express the transaction values at the closing date of the general balance sheet.</span></span> <span data-ttu-id="f8104-107">Cuando se ejecuta el proceso de ajuste de inflación, se ajustan los saldos contables y las entradas de asiento se registran de acuerdo con los coeficientes de INPC.</span><span class="sxs-lookup"><span data-stu-id="f8104-107">When the inflation adjustment process is run, the ledger balances are adjusted, and voucher entries are posted according to the INPC rates.</span></span> <span data-ttu-id="f8104-108">Se definen los métodos de ajuste y puede ver el efecto del ajuste de inflación generando informes de simulación antes de ejecutar el proceso real.</span><span class="sxs-lookup"><span data-stu-id="f8104-108">Adjustment methods are defined, and you can view the effect of the inflation adjustment by generating simulation reports before you run the actual process.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f8104-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f8104-109">Prerequisites</span></span>
<span data-ttu-id="f8104-110">La tabla siguiente muestra la configuración que debe existir antes de comenzar el registro de efectos inflacionistas en la contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="f8104-110">The following table lists the configuration that must be in place before you start registration of inflationary effects in your general ledger.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f8104-111">Instalación</span><span class="sxs-lookup"><span data-stu-id="f8104-111">Setup</span></span></th>
<th><span data-ttu-id="f8104-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f8104-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f8104-113">Coeficientes de INPC</span><span class="sxs-lookup"><span data-stu-id="f8104-113">INPC rates</span></span></td>
<td><span data-ttu-id="f8104-114">Cree o edite la tabla de coeficiente de INPC para registrar la tasa de inflación por año y mes para calcular los importes de ajuste de inflación.</span><span class="sxs-lookup"><span data-stu-id="f8104-114">Create or edit the INPC rate table to register the inflation rate per year and month to calculate the inflation adjustment amounts.</span></span> <span data-ttu-id="f8104-115">Solo puede cambiar los importes si no hay ningún ajuste de inflación para el ejercicio y el mes concretos, y cuando se abre y se invierte el estado del proceso de ajuste de inflación.</span><span class="sxs-lookup"><span data-stu-id="f8104-115">You can change the amounts only when there is no adjustment inflation for the particular year and month, and when the status of the inflation adjustment process is open and reversed.</span></span> <span data-ttu-id="f8104-116">Esta tabla está disponible en el sitio del gobierno (SAT).</span><span class="sxs-lookup"><span data-stu-id="f8104-116">This table is available on the government site (SAT).</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f8104-117">Parámetros de inflación</span><span class="sxs-lookup"><span data-stu-id="f8104-117">Inflation parameters</span></span></td>
<td><span data-ttu-id="f8104-118">En los parámetros de contabilidad general, debe configurar la cuenta principal en la que se registra el resultado de la posición monetaria.</span><span class="sxs-lookup"><span data-stu-id="f8104-118">In the general ledger parameters, you must set up the main account where the result of monetary position is posted.</span></span>
<ul>
<li><span data-ttu-id="f8104-119"><strong>Cuenta REPOMO para la corrección de la inflación:</strong> Esta es la cuenta principal que se usa para registrar la inflación de ajuste.</span><span class="sxs-lookup"><span data-stu-id="f8104-119"><strong>REPOMO account for inflation correction:</strong> This is the main account that is used to post the adjustment inflation.</span></span> <span data-ttu-id="f8104-120">Use esta cuenta para registrar el importe que se recibe para las cuentas de resultado en cuentas de Resultado por Posición Monetaria (REPOMO).</span><span class="sxs-lookup"><span data-stu-id="f8104-120">Use this account to post the amount that is received for the Result on Exchange Rate Position (REPOMO) accounts.</span></span> <span data-ttu-id="f8104-121">Esta cuenta debe ser siempre del tipo pérdidas y ganancias, ingresos o gastos.</span><span class="sxs-lookup"><span data-stu-id="f8104-121">This account must always of the profit and loss, revenue, or expense type.</span></span></li>
<li><span data-ttu-id="f8104-122"><strong>Cuenta principal de contrapartida:</strong> La cuenta principal de contrapartida que se usa para las transacciones de ajuste de inflación.</span><span class="sxs-lookup"><span data-stu-id="f8104-122"><strong>Offset main account:</strong> The offset main account that is used for inflation adjustment transactions.</span></span></li>
<li><span data-ttu-id="f8104-123"><strong>Números de serie:</strong> debe especificar un número de serie para <strong>Asiento de ajuste de inflación</strong> y<strong> Asiento de inversión de ajuste de inflación</strong>.</span><span class="sxs-lookup"><span data-stu-id="f8104-123"><strong>Sequence numbers:</strong> You must specify a sequence number for <strong>Inflation adjustment vouchers</strong> and <strong>Inflation adjustment reversal voucher</strong>.</span></span> <span data-ttu-id="f8104-124">Estos asientos se usan para generar las transacciones de ajuste y las transacciones de ajuste de inversión cuando se invierten las transacciones de ajuste de inflación.</span><span class="sxs-lookup"><span data-stu-id="f8104-124">These vouchers are used to generate the adjustment transactions and the reversal adjustment transactions when the inflation adjustment transactions are reversed.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f8104-125">Cuentas principales</span><span class="sxs-lookup"><span data-stu-id="f8104-125">Main accounts</span></span></td>
<td><span data-ttu-id="f8104-126">Debe configurar parámetros específicos por cuenta principal para habilitar la generación de transacciones de inflación de ajuste.</span><span class="sxs-lookup"><span data-stu-id="f8104-126">You must configure specific parameters per main account to enable the generation of adjustment inflation transactions.</span></span>
<ul>
<li><span data-ttu-id="f8104-127"><strong>Ajuste de B-10:</strong> seleccione <strong>Sí</strong> si desea revalorizar esta cuenta durante el proceso de ajuste de inflación.</span><span class="sxs-lookup"><span data-stu-id="f8104-127"><strong>B-10 adjustment:</strong> Select <strong>Yes</strong> if you want to revaluate this account during the inflation adjustment process.</span></span></li>
<li><span data-ttu-id="f8104-128"><strong>Tipo de REPOMO:</strong> si esta cuenta principal es parte del cálculo de REPOMO, debe indicar el tipo: <strong>Activo</strong> o <strong>Pasivo</strong>.</span><span class="sxs-lookup"><span data-stu-id="f8104-128"><strong>REPOMO type:</strong> If this main account is part of REPOMO calculation, you must indicate the type: <strong>Asset</strong> or <strong>Liability</strong>.</span></span> <span data-ttu-id="f8104-129"><strong>No aplicable</strong> se selecciona cuando la cuenta principal no forma parte del cálculo de REPOMO.</span><span class="sxs-lookup"><span data-stu-id="f8104-129"><strong>Not applicable</strong> is selected when the main account is not part of REPOMO calculation.</span></span></li>
<li><span data-ttu-id="f8104-130"><strong>Método de ajuste:</strong> seleccione el método de ajuste que se usará cuando se ejecute el proceso de inflación de ajuste.</span><span class="sxs-lookup"><span data-stu-id="f8104-130"><strong>Adjustment method:</strong> Select the adjustment method to use when the adjustment inflation process is run.</span></span> <span data-ttu-id="f8104-131">Solo se usan las cuentas contables activas cuando se ejecuta el proceso de inflación de ajuste.</span><span class="sxs-lookup"><span data-stu-id="f8104-131">Only the active ledger accounts are used when the adjustment inflation process is run.</span></span>
<ul>
<li><span data-ttu-id="f8104-132">Ninguna</span><span class="sxs-lookup"><span data-stu-id="f8104-132">None</span></span></li>
<li><span data-ttu-id="f8104-133">Fecha de la transacción</span><span class="sxs-lookup"><span data-stu-id="f8104-133">Transaction date</span></span></li>
<li><span data-ttu-id="f8104-134">Saldo de apertura</span><span class="sxs-lookup"><span data-stu-id="f8104-134">Opening balance</span></span></li>
<li><span data-ttu-id="f8104-135">Saldo mensual</span><span class="sxs-lookup"><span data-stu-id="f8104-135">Monthly balance</span></span></li>
<li><span data-ttu-id="f8104-136">Saldo</span><span class="sxs-lookup"><span data-stu-id="f8104-136">Balance</span></span></li>
</ul></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="start-the-adjustment-inflation-process"></a><span data-ttu-id="f8104-137">Iniciar el proceso de inflación de ajuste</span><span class="sxs-lookup"><span data-stu-id="f8104-137">Start the adjustment inflation process</span></span>
<span data-ttu-id="f8104-138">Para iniciar el proceso, haga clic en <strong>Contabilidad general</strong> &gt; <strong>Tareas de período</strong> &gt; <strong>Ajuste de inflación B-10</strong>.</span><span class="sxs-lookup"><span data-stu-id="f8104-138">To start the process, click <strong>General ledger</strong> &gt; <strong>Period tasks</strong> &gt; <strong>Inflation adjustment B-10</strong>.</span></span> <span data-ttu-id="f8104-139">Puede\*\* <strong>crear la entrada de un período específico e incluir la fecha inicial y final. El estado predeterminado para la entrada es \*\*Abierto</strong>.</span><span class="sxs-lookup"><span data-stu-id="f8104-139">You can\*\* <strong>create the entry for a specific period, and include the from and to dates. The default status for this entry is \*\*Open</strong>.</span></span> <span data-ttu-id="f8104-140">También puede incluir notas adicionales acerca del proceso de ajuste de inflación.</span><span class="sxs-lookup"><span data-stu-id="f8104-140">You also can include additional notes about the inflation adjustment process.</span></span> <span data-ttu-id="f8104-141">Hay diversas maneras de ejecutar el proceso:</span><span class="sxs-lookup"><span data-stu-id="f8104-141">There are various ways to run the process:</span></span>

-   <span data-ttu-id="f8104-142">**Simular**: antes de ejecutar el proceso de ajuste de inflación, puede ejecutar una simulación de los efectos generales de ejecutar el ajuste de inflación.</span><span class="sxs-lookup"><span data-stu-id="f8104-142">**Simulate** – Before you run the inflation adjustment process, you can run a simulation of the overall effects of running the inflation adjustment.</span></span> <span data-ttu-id="f8104-143">Si se encuentran diferencias en el informe **Simulación**, puede cambiar solo los campos **Capa de registro** y **Notas** en la página **Ajuste por inflación B-10**.</span><span class="sxs-lookup"><span data-stu-id="f8104-143">If differences are found in the **Simulation** report, you can change only the **Posting layer** field and the **Notes** field on the **Inflation adjustment B-10** page.</span></span> <span data-ttu-id="f8104-144">El proceso de simulación no registra las transacciones contables de ajuste de inflación.</span><span class="sxs-lookup"><span data-stu-id="f8104-144">The simulation process does not post the inflation adjustment ledgers transactions.</span></span> <span data-ttu-id="f8104-145">El proceso genera un informe que muestra las transacciones contables de ajuste de inflación generadas por el sistema.</span><span class="sxs-lookup"><span data-stu-id="f8104-145">The process generates a report that shows the inflation adjustment ledger transactions that are generated by the system.</span></span>
-   <span data-ttu-id="f8104-146">**Registrar**: puede registrar definitivamente el ajuste de inflación para generar los asientos de inflación de ajuste relacionados.</span><span class="sxs-lookup"><span data-stu-id="f8104-146">**Post**  – You can definitively post the adjustment inflation to generate the related adjustment inflation vouchers.</span></span> <span data-ttu-id="f8104-147">También puede especificar la capa de registro donde se generan las transacciones.</span><span class="sxs-lookup"><span data-stu-id="f8104-147">You can also specify the posting layer where the transactions are generated.</span></span> <span data-ttu-id="f8104-148">La entrada de inflación de ajuste tiene un estado de **Registrado**.</span><span class="sxs-lookup"><span data-stu-id="f8104-148">The adjustment inflation entry has a status of **Posted**.</span></span>
-   <span data-ttu-id="f8104-149">**Invertir**: puede invertir las transacciones de ajuste de inflación que se han registrado y ejecutar el proceso de nuevo si es necesario.</span><span class="sxs-lookup"><span data-stu-id="f8104-149">**Reverse** – You can reverse inflation adjustment transactions that have been posted and run the process again if you must.</span></span> <span data-ttu-id="f8104-150">Tras la inversión, el estado del proceso de inflación de ajuste se cambia a **Invertido**.</span><span class="sxs-lookup"><span data-stu-id="f8104-150">After the reversal, the status of the adjustment inflation process is changed to **Reversed**.</span></span>

## <a name="available-report-types"></a><span data-ttu-id="f8104-151">Tipos de informes disponibles</span><span class="sxs-lookup"><span data-stu-id="f8104-151">Available report types</span></span>
<span data-ttu-id="f8104-152">Hay varios tipos de informes de inflación de ajuste disponibles para fines de control cuando la entrada de inflación de ajuste tiene un estado de **Registrado**.</span><span class="sxs-lookup"><span data-stu-id="f8104-152">Various types of adjustment inflation reports are available for control purposes when the adjustment inflation entry has a status of **Posted**.</span></span>

### <a name="repomo-report"></a><span data-ttu-id="f8104-153">Informe REPOMO</span><span class="sxs-lookup"><span data-stu-id="f8104-153">REPOMO report</span></span>

<span data-ttu-id="f8104-154">Este informe se basa en los siguientes valores de parámetros:</span><span class="sxs-lookup"><span data-stu-id="f8104-154">This report is based on the following parameter values:</span></span>

-   <span data-ttu-id="f8104-155">El control deslizante **Ajuste de B-10** se encuentra para la cuenta principal.</span><span class="sxs-lookup"><span data-stu-id="f8104-155">The **B-10 adjustment** slider is on for the main account.</span></span>
-   <span data-ttu-id="f8104-156">El tipo de cuenta para la cuenta principal es **Activo**, **Pasivo** o **Balance**.</span><span class="sxs-lookup"><span data-stu-id="f8104-156">The account type for the main account is **Asset**, **Liability**, or **Balance**.</span></span>
-   <span data-ttu-id="f8104-157">El tipo REPOMO para la cuenta principal es **Activo** o **Pasivo**.</span><span class="sxs-lookup"><span data-stu-id="f8104-157">The REPOMO type for the main account is **Asset** or **Liability**.</span></span>
-   <span data-ttu-id="f8104-158">El tipo de ajuste de la cuenta principal es **Saldo de** **apertura**.</span><span class="sxs-lookup"><span data-stu-id="f8104-158">The adjustment type of the main account is **Opening** **balance**.</span></span>

### <a name="profit-and-loss-report"></a><span data-ttu-id="f8104-159">Informe de pérdidas y ganancias</span><span class="sxs-lookup"><span data-stu-id="f8104-159">Profit and loss report</span></span>

<span data-ttu-id="f8104-160">Este informe muestra el cálculo del ajuste de inflación de pérdidas y ganancias para el intervalo del período seleccionado.</span><span class="sxs-lookup"><span data-stu-id="f8104-160">This report shows the calculation of the profit and loss inflation adjustment for the selected period range.</span></span> <span data-ttu-id="f8104-161">Muestra los detalles de todas las cuentas principales que tienen los siguientes valores de parámetros:</span><span class="sxs-lookup"><span data-stu-id="f8104-161">It shows the details of all main accounts that have the following parameter values:</span></span>

-   <span data-ttu-id="f8104-162">El control deslizante **Ajuste de B-10** se encuentra para la cuenta principal.</span><span class="sxs-lookup"><span data-stu-id="f8104-162">The **B-10 adjustment** slider is on for the main account.</span></span>
-   <span data-ttu-id="f8104-163">El tipo de cuenta para la cuenta principal es **Pérdidas y ganancias**, **Ingresos** o **Gasto**.</span><span class="sxs-lookup"><span data-stu-id="f8104-163">The account type for the main account is **Profit and loss**, **Revenue**, or **Expense**.</span></span>
-   <span data-ttu-id="f8104-164">El tipo de ajuste de la cuenta principal es **Saldo** **mensual**.</span><span class="sxs-lookup"><span data-stu-id="f8104-164">The adjustment type of the main account is **Monthly** **Balance**.</span></span>

### <a name="inventory-report"></a><span data-ttu-id="f8104-165">Informe de inventario</span><span class="sxs-lookup"><span data-stu-id="f8104-165">Inventory report</span></span>

<span data-ttu-id="f8104-166">Este informe muestra el cálculo del ajuste de inflación del código de cuenta de inventario para el período seleccionado.</span><span class="sxs-lookup"><span data-stu-id="f8104-166">This report shows the calculation of the inventory account code inflation adjustment for the selected period.</span></span> <span data-ttu-id="f8104-167">Debe mostrar todas las cuentas principales que tiene los siguientes valores de parámetros:</span><span class="sxs-lookup"><span data-stu-id="f8104-167">It must show all main accounts that have the following parameter values:</span></span>

-   <span data-ttu-id="f8104-168">El control deslizante **Ajuste de B-10** se encuentra para la cuenta principal.</span><span class="sxs-lookup"><span data-stu-id="f8104-168">The **B-10 adjustment** slider is on for the main account.</span></span>
-   <span data-ttu-id="f8104-169">El tipo de ajuste de la cuenta principal es **Saldo**</span><span class="sxs-lookup"><span data-stu-id="f8104-169">The adjustment type of the main account is **Balance**.</span></span>

### <a name="capital-and-result-report"></a><span data-ttu-id="f8104-170">Informe de capital y resultado</span><span class="sxs-lookup"><span data-stu-id="f8104-170">Capital and result report</span></span>

<span data-ttu-id="f8104-171">Este informe muestra el cálculo del ajuste de inflación del código de cuenta de capital y resultado para el período seleccionado.</span><span class="sxs-lookup"><span data-stu-id="f8104-171">This report shows the calculation of the capital and result account code inflation adjustment for the selected period.</span></span> <span data-ttu-id="f8104-172">Debe mostrar todas las cuentas principales que tiene los siguientes valores de parámetros:</span><span class="sxs-lookup"><span data-stu-id="f8104-172">It must show all main accounts that have the following parameter values:</span></span>

-   <span data-ttu-id="f8104-173">El control deslizante **Ajuste de B-10** se encuentra para la cuenta principal.</span><span class="sxs-lookup"><span data-stu-id="f8104-173">The **B-10 adjustment** slider is on for the main account.</span></span>
-   <span data-ttu-id="f8104-174">El tipo de cuenta para la cuenta principal es **Balance** **de situación**, **Activo**, **Pasivo** o **Recursos propios**.</span><span class="sxs-lookup"><span data-stu-id="f8104-174">The account type for the main account is **Balance** **sheet**, **Asset**, **Liability**, or **Equity**.</span></span>
-   <span data-ttu-id="f8104-175">El tipo de ajuste de la cuenta principal es **Fecha** **de la transacción**.</span><span class="sxs-lookup"><span data-stu-id="f8104-175">The adjustment type of the main account is **Transaction** **date**.</span></span>




