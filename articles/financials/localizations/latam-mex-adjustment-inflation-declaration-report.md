---
title: "Informe de la declaración de inflación de ajuste"
description: "Los usuarios de Microsoft Dynamics 365 Finance and for Operations Enterprise Edition pueden procesar ajustes de inflación mediante coeficientes de INPC, distintos métodos (como saldos de apertura, saldo, saldo mensual y fecha de transacción) y diversas dimensiones."
author: sndray
manager: AnnBe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InflationAdjJournal_MX, InpcRateTable_MX, LedgerParameters, MainAccount
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 9391
ms.assetid: 9076bf16-0021-47ad-a3b9-1bab75c583ec
ms.search.region: Mexico
ms.author: sndray
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 49782b5d66bf51ab99ed3fbb60c6e7dfb3193f2d
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="adjustment-inflation-declaration-report"></a><span data-ttu-id="97428-103">Informe de la declaración de inflación de ajuste</span><span class="sxs-lookup"><span data-stu-id="97428-103">Adjustment inflation declaration report</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="97428-104">Los usuarios de Finance and Operations pueden procesar ajustes de inflación mediante coeficientes de INPC, distintos métodos (como saldos de apertura, saldo, saldo mensual y fecha de transacción) y diversas dimensiones.</span><span class="sxs-lookup"><span data-stu-id="97428-104">Finance and Operations users can process inflation adjustments by using INPC rates, various methods (such as opening balance, balance, monthly balance, and transaction date), and various dimensions.</span></span>

<span data-ttu-id="97428-105">Todas las empresas de México deben aplicar el proceso de NIF B-10 para reconocimiento de inflación en informes financieros si la tasa de inflación acumulativa durante los tres últimos años es igual o supera el 26 por ciento.</span><span class="sxs-lookup"><span data-stu-id="97428-105">All companies in Mexico are required to apply the NIF B-10 process to inflation recognition in financial statements if the cumulative inflation rate during the last three years equals or exceeds 26 percent.</span></span> <span data-ttu-id="97428-106">Al usar las tasas de índice del Índice Nacional de Precios al Consumidor (INPC) cada mes, puede expresar los valores de transacción en la fecha de cierre de la hoja del saldo general.</span><span class="sxs-lookup"><span data-stu-id="97428-106">By using the Índice Nacional de Precios al Consumidor (INPC) index rates every month, you can express the transaction values at the closing date of the general balance sheet.</span></span> <span data-ttu-id="97428-107">Cuando se ejecuta el proceso de ajuste de inflación, se ajustan los saldos contables y las entradas de asiento se registran de acuerdo con los coeficientes de INPC.</span><span class="sxs-lookup"><span data-stu-id="97428-107">When the inflation adjustment process is run, the ledger balances are adjusted, and voucher entries are posted according to the INPC rates.</span></span> <span data-ttu-id="97428-108">Se definen los métodos de ajuste y puede ver el efecto del ajuste de inflación generando informes de simulación antes de ejecutar el proceso real.</span><span class="sxs-lookup"><span data-stu-id="97428-108">Adjustment methods are defined, and you can view the effect of the inflation adjustment by generating simulation reports before you run the actual process.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="97428-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="97428-109">Prerequisites</span></span>
<span data-ttu-id="97428-110">La tabla siguiente muestra la configuración que debe existir antes de comenzar el registro de efectos inflacionistas en la contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="97428-110">The following table lists the configuration that must be in place before you start registration of inflationary effects in your general ledger.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="97428-111">Instalación</span><span class="sxs-lookup"><span data-stu-id="97428-111">Setup</span></span></th>
<th><span data-ttu-id="97428-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="97428-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="97428-113">Coeficientes de INPC</span><span class="sxs-lookup"><span data-stu-id="97428-113">INPC rates</span></span></td>
<td><span data-ttu-id="97428-114">Cree o edite la tabla de coeficiente de INPC para registrar la tasa de inflación por año y mes para calcular los importes de ajuste de inflación.</span><span class="sxs-lookup"><span data-stu-id="97428-114">Create or edit the INPC rate table to register the inflation rate per year and month to calculate the inflation adjustment amounts.</span></span> <span data-ttu-id="97428-115">Solo puede cambiar los importes si no hay ningún ajuste de inflación para el ejercicio y el mes concretos, y cuando se abre y se invierte el estado del proceso de ajuste de inflación.</span><span class="sxs-lookup"><span data-stu-id="97428-115">You can change the amounts only when there is no adjustment inflation for the particular year and month, and when the status of the inflation adjustment process is open and reversed.</span></span> <span data-ttu-id="97428-116">Esta tabla está disponible en el sitio del gobierno (SAT).</span><span class="sxs-lookup"><span data-stu-id="97428-116">This table is available on the government site (SAT).</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="97428-117">Parámetros de inflación</span><span class="sxs-lookup"><span data-stu-id="97428-117">Inflation parameters</span></span></td>
<td><span data-ttu-id="97428-118">En los parámetros de contabilidad general, debe configurar la cuenta principal en la que se registra el resultado de la posición monetaria.</span><span class="sxs-lookup"><span data-stu-id="97428-118">In the general ledger parameters, you must set up the main account where the result of monetary position is posted.</span></span>
<ul>
<li><span data-ttu-id="97428-119"><strong>Cuenta REPOMO para la corrección de la inflación:</strong> Esta es la cuenta principal que se usa para registrar la inflación de ajuste.</span><span class="sxs-lookup"><span data-stu-id="97428-119"><strong>REPOMO account for inflation correction:</strong> This is the main account that is used to post the adjustment inflation.</span></span> <span data-ttu-id="97428-120">Use esta cuenta para registrar el importe que se recibe para las cuentas de resultado en cuentas de Resultado por Posición Monetaria (REPOMO).</span><span class="sxs-lookup"><span data-stu-id="97428-120">Use this account to post the amount that is received for the Result on Exchange Rate Position (REPOMO) accounts.</span></span> <span data-ttu-id="97428-121">Esta cuenta debe ser siempre del tipo pérdidas y ganancias, ingresos o gastos.</span><span class="sxs-lookup"><span data-stu-id="97428-121">This account must always of the profit and loss, revenue, or expense type.</span></span></li>
<li><span data-ttu-id="97428-122"><strong>Cuenta principal de contrapartida:</strong> La cuenta principal de contrapartida que se usa para las transacciones de ajuste de inflación.</span><span class="sxs-lookup"><span data-stu-id="97428-122"><strong>Offset main account:</strong> The offset main account that is used for inflation adjustment transactions.</span></span></li>
<li><span data-ttu-id="97428-123"><strong>Números de serie:</strong> debe especificar un número de serie para <strong>Asiento de ajuste de inflación</strong> y<strong> Asiento de inversión de ajuste de inflación</strong>.</span><span class="sxs-lookup"><span data-stu-id="97428-123"><strong>Sequence numbers:</strong> You must specify a sequence number for <strong>Inflation adjustment vouchers</strong> and <strong>Inflation adjustment reversal voucher</strong>.</span></span> <span data-ttu-id="97428-124">Estos asientos se usan para generar las transacciones de ajuste y las transacciones de ajuste de inversión cuando se invierten las transacciones de ajuste de inflación.</span><span class="sxs-lookup"><span data-stu-id="97428-124">These vouchers are used to generate the adjustment transactions and the reversal adjustment transactions when the inflation adjustment transactions are reversed.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="97428-125">Cuentas principales</span><span class="sxs-lookup"><span data-stu-id="97428-125">Main accounts</span></span></td>
<td><span data-ttu-id="97428-126">Debe configurar parámetros específicos por cuenta principal para habilitar la generación de transacciones de inflación de ajuste.</span><span class="sxs-lookup"><span data-stu-id="97428-126">You must configure specific parameters per main account to enable the generation of adjustment inflation transactions.</span></span>
<ul>
<li><span data-ttu-id="97428-127"><strong>Ajuste de B-10:</strong> seleccione <strong>Sí</strong> si desea revalorizar esta cuenta durante el proceso de ajuste de inflación.</span><span class="sxs-lookup"><span data-stu-id="97428-127"><strong>B-10 adjustment:</strong> Select <strong>Yes</strong> if you want to revaluate this account during the inflation adjustment process.</span></span></li>
<li><span data-ttu-id="97428-128"><strong>Tipo de REPOMO:</strong> si esta cuenta principal es parte del cálculo de REPOMO, debe indicar el tipo: <strong>Activo</strong> o <strong>Pasivo</strong>.</span><span class="sxs-lookup"><span data-stu-id="97428-128"><strong>REPOMO type:</strong> If this main account is part of REPOMO calculation, you must indicate the type: <strong>Asset</strong> or <strong>Liability</strong>.</span></span> <span data-ttu-id="97428-129"><strong>No aplicable</strong> se selecciona cuando la cuenta principal no forma parte del cálculo de REPOMO.</span><span class="sxs-lookup"><span data-stu-id="97428-129"><strong>Not applicable</strong> is selected when the main account is not part of REPOMO calculation.</span></span></li>
<li><span data-ttu-id="97428-130"><strong>Método de ajuste:</strong> seleccione el método de ajuste que se usará cuando se ejecute el proceso de inflación de ajuste.</span><span class="sxs-lookup"><span data-stu-id="97428-130"><strong>Adjustment method:</strong> Select the adjustment method to use when the adjustment inflation process is run.</span></span> <span data-ttu-id="97428-131">Solo se usan las cuentas contables activas cuando se ejecuta el proceso de inflación de ajuste.</span><span class="sxs-lookup"><span data-stu-id="97428-131">Only the active ledger accounts are used when the adjustment inflation process is run.</span></span>
<ul>
<li><span data-ttu-id="97428-132">Ninguna</span><span class="sxs-lookup"><span data-stu-id="97428-132">None</span></span></li>
<li><span data-ttu-id="97428-133">Fecha de la transacción</span><span class="sxs-lookup"><span data-stu-id="97428-133">Transaction date</span></span></li>
<li><span data-ttu-id="97428-134">Saldo de apertura</span><span class="sxs-lookup"><span data-stu-id="97428-134">Opening balance</span></span></li>
<li><span data-ttu-id="97428-135">Saldo mensual</span><span class="sxs-lookup"><span data-stu-id="97428-135">Monthly balance</span></span></li>
<li><span data-ttu-id="97428-136">Saldo</span><span class="sxs-lookup"><span data-stu-id="97428-136">Balance</span></span></li>
</ul></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="start-the-adjustment-inflation-process"></a><span data-ttu-id="97428-137">Iniciar el proceso de inflación de ajuste</span><span class="sxs-lookup"><span data-stu-id="97428-137">Start the adjustment inflation process</span></span>
<span data-ttu-id="97428-138">Para iniciar el proceso, haga clic en **Contabilidad general** &gt; **Tareas de período** &gt; **Ajuste de inflación B-10**.</span><span class="sxs-lookup"><span data-stu-id="97428-138">To start the process, click **General ledger** &gt; **Period tasks** &gt; **Inflation adjustment B-10**.</span></span> <span data-ttu-id="97428-139">Puede** **crear la entrada para un período específico e incluir las fechas inicial y final.</span><span class="sxs-lookup"><span data-stu-id="97428-139">You can** **create the entry for a specific period, and include the from and to dates.</span></span> <span data-ttu-id="97428-140">El estado predeterminado para la entrada es **Abierto**.</span><span class="sxs-lookup"><span data-stu-id="97428-140">The default status for this entry is **Open**.</span></span> <span data-ttu-id="97428-141">También puede incluir notas adicionales acerca del proceso de ajuste de inflación.</span><span class="sxs-lookup"><span data-stu-id="97428-141">You also can include additional notes about the inflation adjustment process.</span></span> <span data-ttu-id="97428-142">Hay diversas maneras de ejecutar el proceso:</span><span class="sxs-lookup"><span data-stu-id="97428-142">There are various ways to run the process:</span></span>

-   <span data-ttu-id="97428-143">**Simular**: antes de ejecutar el proceso de ajuste de inflación, puede ejecutar una simulación de los efectos generales de ejecutar el ajuste de inflación.</span><span class="sxs-lookup"><span data-stu-id="97428-143">**Simulate** – Before you run the inflation adjustment process, you can run a simulation of the overall effects of running the inflation adjustment.</span></span> <span data-ttu-id="97428-144">Si se encuentran diferencias en el informe **Simulación**, puede cambiar solo los campos **Capa de registro** y **Notas** en la página **Ajuste por inflación B-10**.</span><span class="sxs-lookup"><span data-stu-id="97428-144">If differences are found in the **Simulation** report, you can change only the **Posting layer** field and the **Notes** field on the **Inflation adjustment B-10** page.</span></span> <span data-ttu-id="97428-145">El proceso de simulación no registra las transacciones contables de ajuste de inflación.</span><span class="sxs-lookup"><span data-stu-id="97428-145">The simulation process does not post the inflation adjustment ledgers transactions.</span></span> <span data-ttu-id="97428-146">El proceso genera un informe que muestra las transacciones contables de ajuste de inflación generadas por el sistema.</span><span class="sxs-lookup"><span data-stu-id="97428-146">The process generates a report that shows the inflation adjustment ledger transactions that are generated by the system.</span></span>
-   <span data-ttu-id="97428-147">**Registrar**: puede registrar definitivamente el ajuste de inflación para generar los asientos de inflación de ajuste relacionados.</span><span class="sxs-lookup"><span data-stu-id="97428-147">**Post**  – You can definitively post the adjustment inflation to generate the related adjustment inflation vouchers.</span></span> <span data-ttu-id="97428-148">También puede especificar la capa de registro donde se generan las transacciones.</span><span class="sxs-lookup"><span data-stu-id="97428-148">You can also specify the posting layer where the transactions are generated.</span></span> <span data-ttu-id="97428-149">La entrada de inflación de ajuste tiene un estado de **Registrado**.</span><span class="sxs-lookup"><span data-stu-id="97428-149">The adjustment inflation entry has a status of **Posted**.</span></span>
-   <span data-ttu-id="97428-150">**Invertir**: puede invertir las transacciones de ajuste de inflación que se han registrado y ejecutar el proceso de nuevo si es necesario.</span><span class="sxs-lookup"><span data-stu-id="97428-150">**Reverse** – You can reverse inflation adjustment transactions that have been posted and run the process again if you must.</span></span> <span data-ttu-id="97428-151">Tras la inversión, el estado del proceso de inflación de ajuste se cambia a **Invertido**.</span><span class="sxs-lookup"><span data-stu-id="97428-151">After the reversal, the status of the adjustment inflation process is changed to **Reversed**.</span></span>

## <a name="available-report-types"></a><span data-ttu-id="97428-152">Tipos de informes disponibles</span><span class="sxs-lookup"><span data-stu-id="97428-152">Available report types</span></span>
<span data-ttu-id="97428-153">Hay varios tipos de informes de inflación de ajuste disponibles para fines de control cuando la entrada de inflación de ajuste tiene un estado de **Registrado**.</span><span class="sxs-lookup"><span data-stu-id="97428-153">Various types of adjustment inflation reports are available for control purposes when the adjustment inflation entry has a status of **Posted**.</span></span>

### <a name="repomo-report"></a><span data-ttu-id="97428-154">Informe REPOMO</span><span class="sxs-lookup"><span data-stu-id="97428-154">REPOMO report</span></span>

<span data-ttu-id="97428-155">Este informe se basa en los siguientes valores de parámetros:</span><span class="sxs-lookup"><span data-stu-id="97428-155">This report is based on the following parameter values:</span></span>

-   <span data-ttu-id="97428-156">El control deslizante **Ajuste de B-10** se encuentra para la cuenta principal.</span><span class="sxs-lookup"><span data-stu-id="97428-156">The **B-10 adjustment** slider is on for the main account.</span></span>
-   <span data-ttu-id="97428-157">El tipo de cuenta para la cuenta principal es **Activo**, **Pasivo** o **Balance**.</span><span class="sxs-lookup"><span data-stu-id="97428-157">The account type for the main account is **Asset**, **Liability**, or **Balance**.</span></span>
-   <span data-ttu-id="97428-158">El tipo REPOMO para la cuenta principal es **Activo** o **Pasivo**.</span><span class="sxs-lookup"><span data-stu-id="97428-158">The REPOMO type for the main account is **Asset** or **Liability**.</span></span>
-   <span data-ttu-id="97428-159">El tipo de ajuste de la cuenta principal es **Saldo de** **apertura**.</span><span class="sxs-lookup"><span data-stu-id="97428-159">The adjustment type of the main account is **Opening** **balance**.</span></span>

### <a name="profit-and-loss-report"></a><span data-ttu-id="97428-160">Informe de pérdidas y ganancias</span><span class="sxs-lookup"><span data-stu-id="97428-160">Profit and loss report</span></span>

<span data-ttu-id="97428-161">Este informe muestra el cálculo del ajuste de inflación de pérdidas y ganancias para el intervalo del período seleccionado.</span><span class="sxs-lookup"><span data-stu-id="97428-161">This report shows the calculation of the profit and loss inflation adjustment for the selected period range.</span></span> <span data-ttu-id="97428-162">Muestra los detalles de todas las cuentas principales que tienen los siguientes valores de parámetros:</span><span class="sxs-lookup"><span data-stu-id="97428-162">It shows the details of all main accounts that have the following parameter values:</span></span>

-   <span data-ttu-id="97428-163">El control deslizante **Ajuste de B-10** se encuentra para la cuenta principal.</span><span class="sxs-lookup"><span data-stu-id="97428-163">The **B-10 adjustment** slider is on for the main account.</span></span>
-   <span data-ttu-id="97428-164">El tipo de cuenta para la cuenta principal es **Pérdidas y ganancias**, **Ingresos** o **Gasto**.</span><span class="sxs-lookup"><span data-stu-id="97428-164">The account type for the main account is **Profit and loss**, **Revenue**, or **Expense**.</span></span>
-   <span data-ttu-id="97428-165">El tipo de ajuste de la cuenta principal es **Saldo** **mensual**.</span><span class="sxs-lookup"><span data-stu-id="97428-165">The adjustment type of the main account is **Monthly** **Balance**.</span></span>

### <a name="inventory-report"></a><span data-ttu-id="97428-166">Informe de inventario</span><span class="sxs-lookup"><span data-stu-id="97428-166">Inventory report</span></span>

<span data-ttu-id="97428-167">Este informe muestra el cálculo del ajuste de inflación del código de cuenta de inventario para el período seleccionado.</span><span class="sxs-lookup"><span data-stu-id="97428-167">This report shows the calculation of the inventory account code inflation adjustment for the selected period.</span></span> <span data-ttu-id="97428-168">Debe mostrar todas las cuentas principales que tiene los siguientes valores de parámetros:</span><span class="sxs-lookup"><span data-stu-id="97428-168">It must show all main accounts that have the following parameter values:</span></span>

-   <span data-ttu-id="97428-169">El control deslizante **Ajuste de B-10** se encuentra para la cuenta principal.</span><span class="sxs-lookup"><span data-stu-id="97428-169">The **B-10 adjustment** slider is on for the main account.</span></span>
-   <span data-ttu-id="97428-170">El tipo de ajuste de la cuenta principal es **Saldo**</span><span class="sxs-lookup"><span data-stu-id="97428-170">The adjustment type of the main account is **Balance**.</span></span>

### <a name="capital-and-result-report"></a><span data-ttu-id="97428-171">Informe de capital y resultado</span><span class="sxs-lookup"><span data-stu-id="97428-171">Capital and result report</span></span>

<span data-ttu-id="97428-172">Este informe muestra el cálculo del ajuste de inflación del código de cuenta de capital y resultado para el período seleccionado.</span><span class="sxs-lookup"><span data-stu-id="97428-172">This report shows the calculation of the capital and result account code inflation adjustment for the selected period.</span></span> <span data-ttu-id="97428-173">Debe mostrar todas las cuentas principales que tiene los siguientes valores de parámetros:</span><span class="sxs-lookup"><span data-stu-id="97428-173">It must show all main accounts that have the following parameter values:</span></span>

-   <span data-ttu-id="97428-174">El control deslizante **Ajuste de B-10** se encuentra para la cuenta principal.</span><span class="sxs-lookup"><span data-stu-id="97428-174">The **B-10 adjustment** slider is on for the main account.</span></span>
-   <span data-ttu-id="97428-175">El tipo de cuenta para la cuenta principal es **Balance** **de situación**, **Activo**, **Pasivo** o **Recursos propios**.</span><span class="sxs-lookup"><span data-stu-id="97428-175">The account type for the main account is **Balance** **sheet**, **Asset**, **Liability**, or **Equity**.</span></span>
-   <span data-ttu-id="97428-176">El tipo de ajuste de la cuenta principal es **Fecha** **de la transacción**.</span><span class="sxs-lookup"><span data-stu-id="97428-176">The adjustment type of the main account is **Transaction** **date**.</span></span>





