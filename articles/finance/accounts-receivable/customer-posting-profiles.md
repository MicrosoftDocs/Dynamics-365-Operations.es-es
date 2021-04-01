---
title: Perfiles de contabilización del cliente
description: Los perfiles de contabilización del cliente controlan el registro de transacciones del cliente en la contabilidad general.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, CustVendExternalItem
audience: Application User
ms.reviewer: roschlom
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 75e1dae853ca4b0f3306c6c8d4c5b1f515732872
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5236923"
---
# <a name="customer-posting-profiles"></a><span data-ttu-id="1c6fb-103">Perfiles de contabilización del cliente</span><span class="sxs-lookup"><span data-stu-id="1c6fb-103">Customer posting profiles</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1c6fb-104">Los perfiles de contabilización del cliente controlan el registro de transacciones del cliente en la contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-104">Customer posting profiles control the posting of customer transactions to the general ledger.</span></span>

<a name="customer-posting-profiles"></a><span data-ttu-id="1c6fb-105">Perfiles de contabilización del cliente</span><span class="sxs-lookup"><span data-stu-id="1c6fb-105">Customer posting profiles</span></span>
-------------------------

<span data-ttu-id="1c6fb-106">Los perfiles de registro de cliente le permiten asignar cuentas de contabilidad general y configuración de documentos a todos los clientes, un grupo de clientes o un único cliente.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-106">Customer posting profiles enable you to assign general ledger accounts and document settings to all customers, a group of customers or a single customer.</span></span> <span data-ttu-id="1c6fb-107">Esta configuración se usará al crear pedidos de venta, facturas de servicios, pagos en efectivo, cartas de cobro y notas de interés.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-107">These settings will be used when you create sales orders, free text invoices, cash payments, collection letters, and interest notes.</span></span> <span data-ttu-id="1c6fb-108">Para algunas transacciones, cuando seleccione un perfil de registro diferente de los perfiles de registro configurados para las transacciones de esta página y que tenga precedencia sobre los mismos.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-108">For some transactions, you can select a posting profile that differs from and takes precedence over the posting profiles that are set up for transactions in this page.</span></span> 

<span data-ttu-id="1c6fb-109">El perfil de contabilización predeterminado se define en la ficha desplegable Impuestos y contabilidad en la página Parámetros de clientes.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-109">The default posting profile is defined in the Ledger and Sales Tax fasttab on the Accounts receivable parameters page.</span></span> <span data-ttu-id="1c6fb-110">El perfil de contabilización predeterminado se incluye automáticamente en el encabezado de los documentos nuevos donde puede cambiarlo a otro perfil de contabilización si es necesario.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-110">The default posting profile is then included automatically on the header of new documents where you can change it to a different posting profile if needed.</span></span>

<span data-ttu-id="1c6fb-111">También puede asociar las definiciones de contabilización a los tipos de registro de transacción en la página Definiciones de contabilización de transacción.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-111">You can also associate posting definitions with transaction posting types in the Transaction posting definitions page.</span></span> <span data-ttu-id="1c6fb-112">Permite configurar los perfiles de registro que controlan el registro de transacciones de clientes en la contabilidad general en vez de los perfiles de registro.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-112">Posting definitions control the posting of customer transactions to the general ledger instead of posting profiles.</span></span>

## <a name="creating-a-posting-profile"></a><span data-ttu-id="1c6fb-113">Creación de un perfil de registro</span><span class="sxs-lookup"><span data-stu-id="1c6fb-113">Creating a posting profile</span></span>
<span data-ttu-id="1c6fb-114">Especifique las cuentas contables que se utilizan en el registro de las transacciones con el perfil de contabilización seleccionado.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-114">Specify the ledger accounts that are used in the posting of transactions that use the selected posting profile.</span></span> <span data-ttu-id="1c6fb-115">Seleccione un código de cuenta y, siempre que sea posible, una cuenta o número de grupo para el perfil de registro seleccionado.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-115">Select an account code and, whenever possible, an account or group number for the selected posting profile.</span></span> <span data-ttu-id="1c6fb-116">En el proceso de registro, para buscar el perfil de contabilización más adecuado para cada transacción busque el código de cuenta, el número de cuenta, o el grupo más específico, así como la combinación de números en el siguiente orden:</span><span class="sxs-lookup"><span data-stu-id="1c6fb-116">In the posting process, the most appropriate posting profile for each transaction is located by searching for the most specific account code, account number, or group and number combination in the following priority:</span></span>

| <span data-ttu-id="1c6fb-117">Valor del campo **Código de cuenta**</span><span class="sxs-lookup"><span data-stu-id="1c6fb-117">**Account code** field value</span></span> | <span data-ttu-id="1c6fb-118">Valor del campo **Número de grupo/cuenta**</span><span class="sxs-lookup"><span data-stu-id="1c6fb-118">**Account/Group number** field value</span></span>            | <span data-ttu-id="1c6fb-119">Prioridad de búsqueda</span><span class="sxs-lookup"><span data-stu-id="1c6fb-119">Search priority</span></span> |
|------------------------------|-------------------------------------------------|-----------------|
| <span data-ttu-id="1c6fb-120">**Tabla**</span><span class="sxs-lookup"><span data-stu-id="1c6fb-120">**Table**</span></span>                    | <span data-ttu-id="1c6fb-121">Cuenta de cliente específica</span><span class="sxs-lookup"><span data-stu-id="1c6fb-121">Specific customer account</span></span>                       | <span data-ttu-id="1c6fb-122">1</span><span class="sxs-lookup"><span data-stu-id="1c6fb-122">1</span></span>               |
| <span data-ttu-id="1c6fb-123">**Grupo**</span><span class="sxs-lookup"><span data-stu-id="1c6fb-123">**Group**</span></span>                    | <span data-ttu-id="1c6fb-124">Grupo de clientes asignado al cliente</span><span class="sxs-lookup"><span data-stu-id="1c6fb-124">Customer group that is assigned to the customer</span></span> | <span data-ttu-id="1c6fb-125">2</span><span class="sxs-lookup"><span data-stu-id="1c6fb-125">2</span></span>               |
| <span data-ttu-id="1c6fb-126">**Todas**</span><span class="sxs-lookup"><span data-stu-id="1c6fb-126">**All**</span></span>                      | <span data-ttu-id="1c6fb-127">En blanco</span><span class="sxs-lookup"><span data-stu-id="1c6fb-127">Blank</span></span>                                           | <span data-ttu-id="1c6fb-128">3</span><span class="sxs-lookup"><span data-stu-id="1c6fb-128">3</span></span>               |

<span data-ttu-id="1c6fb-129">Si desea que todas las transacciones de clientes tengan el mismo perfil de contabilización, configure solo un perfil de contabilización con valor Todas en el campo Código de cuenta.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-129">If you want all customer transactions to have the same posting profile, set up only one posting profile with All in the Account code field.</span></span> <span data-ttu-id="1c6fb-130">Especifique los valores siguientes para configurar su perfil de contabilización:</span><span class="sxs-lookup"><span data-stu-id="1c6fb-130">Specify the following values to set up your posting profile:</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="1c6fb-131">Campo</span><span class="sxs-lookup"><span data-stu-id="1c6fb-131">Field</span></span></th>
<th><span data-ttu-id="1c6fb-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="1c6fb-132">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="1c6fb-133"><strong>Perfil de contabilización</strong></span><span class="sxs-lookup"><span data-stu-id="1c6fb-133"><strong>Posting profile</strong></span></span></td>
<td><span data-ttu-id="1c6fb-134">Permite especificar un código para el perfil de contabilización.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-134">Enter a code for the posting profile.</span></span> <span data-ttu-id="1c6fb-135">Por ejemplo, podría crear dos perfiles de registro para obtener una cuenta para saldos de clientes en la divisa nacional y otra para saldos de clientes en una divisa extranjera.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-135">For example, you could create two posting profiles to obtain one account for customer balances in the national currency and another for customer balances in a foreign currency.</span></span> <span data-ttu-id="1c6fb-136">Podría llamar a una cuenta Nacional y a otra Extranjera.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-136">You could call one account National and the other Foreign.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="1c6fb-137"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="1c6fb-137"><strong>Description</strong></span></span></td>
<td><span data-ttu-id="1c6fb-138">Permite especificar una descripción del perfil de registro.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-138">Enter a description of the posting profile.</span></span> <span data-ttu-id="1c6fb-139">Esto solo se usa para identificar mejor el perfil de contabilización cuando lo ve en esta página.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-139">This is only used to better identify the posting profile when you view it in this page.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="1c6fb-140"><strong>Código de cuenta</strong></span><span class="sxs-lookup"><span data-stu-id="1c6fb-140"><strong>Account code</strong></span></span></td>
<td><span data-ttu-id="1c6fb-141">Permite especificar si el perfil de registro se aplica a un solo cliente, a un grupo de clientes o a todos los clientes:</span><span class="sxs-lookup"><span data-stu-id="1c6fb-141">Specify whether the posting profile applies to a single customer, a group of customers, or all customers:</span></span>
<ul>
<li><span data-ttu-id="1c6fb-142"><strong>Tabla</strong>: el perfil de registro se aplica a un único cliente.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-142"><strong>Table</strong> – The posting profile applies to a single customer.</span></span> <span data-ttu-id="1c6fb-143">Seleccione la cuenta de cliente en el campo Número de grupo/cuenta.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-143">Select the customer account in the Account/Group number field.</span></span></li>
<li><span data-ttu-id="1c6fb-144"><strong>Grupo</strong>: el perfil de registro se aplica a un grupo de clientes.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-144"><strong>Group</strong> – The posting profile applies to a customer group.</span></span> <span data-ttu-id="1c6fb-145">Seleccione el grupo de clientes en el campo Número de grupo/cuenta.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-145">Select the customer group in the Account/Group number field.</span></span></li>
<li><span data-ttu-id="1c6fb-146"><strong>Todos</strong>: el perfil de registro se aplica a todos los clientes.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-146"><strong>All</strong> – The posting profile applies to all customers.</span></span> <span data-ttu-id="1c6fb-147">Deje en blanco el campo Número de grupo/cuenta.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-147">Leave the Account/Group number field blank.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="1c6fb-148"><strong>Número de grupo/cuenta</strong></span><span class="sxs-lookup"><span data-stu-id="1c6fb-148"><strong>Account/Group number</strong></span></span></td>
<td><span data-ttu-id="1c6fb-149">Si Tabla está seleccionada en el campo Código de cuenta, seleccione el número de cuenta del cliente asociado al perfil de registro.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-149">If Table is selected in the Account code field, select the account number of the customer who is associated with the posting profile.</span></span> <span data-ttu-id="1c6fb-150">Si ha seleccionado Grupo, seleccione el grupo de clientes.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-150">If Group is selected, select the customer group.</span></span> <span data-ttu-id="1c6fb-151">Si Todos está seleccionado, deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-151">If All is selected, leave this field blank.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="1c6fb-152"><strong>Extracto de cuenta</strong></span><span class="sxs-lookup"><span data-stu-id="1c6fb-152"><strong>Summary account</strong></span></span></td>
<td><span data-ttu-id="1c6fb-153">Seleccione la cuenta contable que se utilizará como la cuenta de resumen de cliente para los clientes se asocian al perfil de registro.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-153">Select the ledger account that will be used as the customer summary account for the customers who are associated with the posting profile.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="1c6fb-154"><strong>Liquidar cuenta</strong></span><span class="sxs-lookup"><span data-stu-id="1c6fb-154"><strong>Settle account</strong></span></span></td>
<td><span data-ttu-id="1c6fb-155">Permite seleccionar la cuenta contable de liquidez que se usa para previsiones de flujo de efectivo.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-155">Select the liquidity ledger account that is used for cash flow forecasts.</span></span> <span data-ttu-id="1c6fb-156">Este campo solo aparecerá si se habilitan las previsiones de flujo de efectivo.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-156">This field will only appear if cash flow forecasts are enabled.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="1c6fb-157"><strong>Pagos de impuestos por adelantado</strong></span><span class="sxs-lookup"><span data-stu-id="1c6fb-157"><strong>Sales tax prepayments</strong></span></span></td>
<td><span data-ttu-id="1c6fb-158">Permite seleccionar la cuenta para los impuestos de pagos que se reciben por adelantado.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-158">Select the account for sales tax for payments that are received in advance.</span></span>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Billete" alt="Note" id="alert_note" class="cl_IC101471" /><span data-ttu-id="1c6fb-160"><strong>Nota</strong></span><span class="sxs-lookup"><span data-stu-id="1c6fb-160"><strong>Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="1c6fb-161">Use la página Parámetros de clientes para especificar el perfil de registro que se usará cuando un pago se marque como anticipo.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-161">Use the Accounts receivable parameters page to specify the posting profile to use when a payment is marked as a prepayment.</span></span></td>
</tr>
</tbody>
</table>
</div></td>
</tr>
<tr class="even">
<td><span data-ttu-id="1c6fb-162"><strong>Deudas por efectos descontados</strong></span><span class="sxs-lookup"><span data-stu-id="1c6fb-162"><strong>Liabilities for discount account</strong></span></span></td>
<td><span data-ttu-id="1c6fb-163">Permite seleccionar la cuenta contable para las deudas por efectos descontados.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-163">Select the ledger account for liabilities of discount.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="1c6fb-164"><strong>Secuencia de la carta de cobro</strong></span><span class="sxs-lookup"><span data-stu-id="1c6fb-164"><strong>Collection letter sequence</strong></span></span></td>
<td><span data-ttu-id="1c6fb-165">Permite seleccionar el identificador de secuencia de la carta de cobro para los clientes a los que se asigna el perfil de registro.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-165">Select the identifier of the collection letter sequence to use for customers to whom the posting profile is assigned.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="1c6fb-166"><strong>Código del interés</strong></span><span class="sxs-lookup"><span data-stu-id="1c6fb-166"><strong>Interest code</strong></span></span></td>
<td><span data-ttu-id="1c6fb-167">Permite seleccionar el código de interés para el cálculo del interés para los clientes a los que se asigna el perfil de contabilización.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-167">Select the interest code to use for the calculation of interest for customers to whom the posting profile is assigned.</span></span></td>
</tr>
</tbody>
</table>

### 

### <a name="table-restrictions"></a><span data-ttu-id="1c6fb-168">**Restricciones de tablas**</span><span class="sxs-lookup"><span data-stu-id="1c6fb-168">**Table restrictions**</span></span>

<span data-ttu-id="1c6fb-169">Para las transacciones que tienen seleccionado el perfil de registro, especifique si las transacciones se liquidarán automáticamente, se calculará el interés y, las cartas de cobro se emitirán.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-169">For transactions that have the selected posting profile, specify whether transactions will be settled automatically, interest will be calculated, and collection letters will be issued.</span></span> <span data-ttu-id="1c6fb-170">También puede seleccionar la cuenta que se usa al cerrar las transacciones que tienen el perfil de contabilización seleccionado.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-170">You can also select the account that is used when transactions that have the selected posting profile are closed.</span></span>

<span data-ttu-id="1c6fb-171">Especifique los valores siguientes para configurar su perfil de contabilización:</span><span class="sxs-lookup"><span data-stu-id="1c6fb-171">Specify the following values to set up your posting profile:</span></span>

| <span data-ttu-id="1c6fb-172">Campo</span><span class="sxs-lookup"><span data-stu-id="1c6fb-172">Field</span></span>                 | <span data-ttu-id="1c6fb-173">Descripción</span><span class="sxs-lookup"><span data-stu-id="1c6fb-173">Description</span></span>                                                                                                                                                                                                                                        |
|-----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="1c6fb-174">**Liquidación**</span><span class="sxs-lookup"><span data-stu-id="1c6fb-174">**Settlement**</span></span>        | <span data-ttu-id="1c6fb-175">Seleccione esta opción para habilitar la liquidación automática de las transacciones que tienen este perfil de registro.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-175">Select this toggle to enable automatic settlement of transactions that have this posting profile.</span></span> <span data-ttu-id="1c6fb-176">Si esta opción está desactivada, debe liquidar manualmente las transacciones mediante la página Liquidar transacciones abiertas o la página Introducir pagos de cliente.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-176">If this toggle is cleared, you must manually settle transactions by using the Settle open transactions page or the Enter customer payments page.</span></span> |
| <span data-ttu-id="1c6fb-177">**Aficiones**</span><span class="sxs-lookup"><span data-stu-id="1c6fb-177">**Interest**</span></span>          | <span data-ttu-id="1c6fb-178">Active esta opción si el interés se calcula en los saldos pendientes para las cuentas de los clientes que usan este perfil.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-178">Select this toggle if interest should be calculated on outstanding balances for customer accounts that use this profile.</span></span> <span data-ttu-id="1c6fb-179">Si se desactiva esta opción, no se calculará el interés para dichos clientes.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-179">If this toggle is cleared, interest will not be calculated for these customers.</span></span>                                           |
| <span data-ttu-id="1c6fb-180">**Carta de cobro**</span><span class="sxs-lookup"><span data-stu-id="1c6fb-180">**Collection letter**</span></span> | <span data-ttu-id="1c6fb-181">Active esta opción si las cartas de cobro se deben generar para cuentas de clientes que usan este perfil.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-181">Select this toggle if collection letters should be generated for customer accounts that use this profile.</span></span> <span data-ttu-id="1c6fb-182">Si se desactiva esta opción, las cartas de cobro no se generarán para estos clientes.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-182">If this toggle is cleared, collection letters will not be generated for these customers.</span></span>                                                 |
| <span data-ttu-id="1c6fb-183">**Cerrar**</span><span class="sxs-lookup"><span data-stu-id="1c6fb-183">**Close**</span></span>             | <span data-ttu-id="1c6fb-184">Seleccionar un perfil de registro al que desee cambiar cuando se cierren las transacciones con este perfil de registro.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-184">Select a posting profile to change to when transactions that have this posting profile are closed.</span></span> <span data-ttu-id="1c6fb-185">Una transacción se considera como cerrada cuando se ha liquidado completamente.</span><span class="sxs-lookup"><span data-stu-id="1c6fb-185">A transaction is regarded as closed when it has been settled in full.</span></span>                                                                           |



<span data-ttu-id="1c6fb-186">Para obtener más información, consulte [Resumen de pagos del cliente](../cash-bank-management/tasks/customer-payment-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1c6fb-186">For more information, see [Customer payment overview](../cash-bank-management/tasks/customer-payment-overview.md).</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]