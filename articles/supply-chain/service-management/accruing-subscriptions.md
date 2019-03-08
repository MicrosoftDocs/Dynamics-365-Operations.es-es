---
title: Acumulación de suscripciones
description: Con las suscripciones de servicios, puede acumular ingresos manualmente en los períodos siguientes a la fecha de facturación de una transacción de gastos.
author: ShylaThompson
manager: AnnBe
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMASubscriptionGroup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a183e17749c04b407eb17155ecb1363e96ade18a
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "317186"
---
# <a name="accruing-subscriptions"></a><span data-ttu-id="adae2-103">Acumulación de suscripciones</span><span class="sxs-lookup"><span data-stu-id="adae2-103">Accruing subscriptions</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="adae2-104">Con las suscripciones de servicios, puede acumular ingresos manualmente en los períodos siguientes a la fecha de facturación de una transacción de gastos.</span><span class="sxs-lookup"><span data-stu-id="adae2-104">With service subscriptions, you manually accrue revenue in the periods following the date when you invoiced a fee transaction.</span></span>

<span data-ttu-id="adae2-105">Los períodos de acumulación se crean para el período de factura que configure para la cuota de suscripción y los períodos de acumulación se basan en el código de período de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="adae2-105">Accrual periods are created for the invoice period that you set up for the subscription fee, and the accrual periods are based on the period code of the subscription.</span></span>

<span data-ttu-id="adae2-106">Puede acumular e invertir ingresos acumulados.</span><span class="sxs-lookup"><span data-stu-id="adae2-106">You can accrue and reverse accrued revenue.</span></span>

## <a name="reverse-accruals-of-credit-amounts"></a><span data-ttu-id="adae2-107">Invertir las provisiones de importes de crédito</span><span class="sxs-lookup"><span data-stu-id="adae2-107">Reverse accruals of credit amounts</span></span>

<span data-ttu-id="adae2-108">Si abona importes de suscripción facturados, puede usar dos métodos diferentes para invertir los importes de acumulación:</span><span class="sxs-lookup"><span data-stu-id="adae2-108">If you credit invoiced subscription amounts, you can use two methods to reverse the accrual amounts:</span></span>

  - <span data-ttu-id="adae2-109">puede invertir cada transacción de ingreso acumulado individualmente antes de crear la propuesta de nota de abono para la transacción.</span><span class="sxs-lookup"><span data-stu-id="adae2-109">You can reverse each accrued revenue transaction individually before you create the credit note proposal for the transaction.</span></span> <span data-ttu-id="adae2-110">Este es el método manual.</span><span class="sxs-lookup"><span data-stu-id="adae2-110">This is the manual method.</span></span> <span data-ttu-id="adae2-111">(manual)</span><span class="sxs-lookup"><span data-stu-id="adae2-111">(manual)</span></span>

  - <span data-ttu-id="adae2-112">Puede tener los importes acumulados invertidos en la fecha en la que la nota de abono se registra o en la fecha de registro original de acumulación.</span><span class="sxs-lookup"><span data-stu-id="adae2-112">You can have the accrued amounts reversed on the date where the credit note is posted or on the original posting date of the accrual.</span></span>

<span data-ttu-id="adae2-113">Para obtener más información, consulte [Parámetros de suscripción (formulario)](https://technet.microsoft.com/en-us/library/aa619615.aspx).</span><span class="sxs-lookup"><span data-stu-id="adae2-113">For more information, see [Subscription parameters (form)](https://technet.microsoft.com/en-us/library/aa619615.aspx).</span></span>

## <a name="setup-requirements"></a><span data-ttu-id="adae2-114">Configurar requisitos</span><span class="sxs-lookup"><span data-stu-id="adae2-114">Setup requirements</span></span>

<span data-ttu-id="adae2-115">Para acumular ingresos, asegúrese de que se cumplen los siguientes requisitos de datos:</span><span class="sxs-lookup"><span data-stu-id="adae2-115">To accrue revenue, make sure that the following data requirements are met:</span></span>

## <a name="account-setup"></a><span data-ttu-id="adae2-116">Configuración de cuenta</span><span class="sxs-lookup"><span data-stu-id="adae2-116">Account setup</span></span>

<span data-ttu-id="adae2-117">Las cuentas **Trabajo en proceso - suscripción** y **Ingresos acumulados - suscripción** deben configurarse en el módulo **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="adae2-117">The **WIP - subscription** and the **Accrued revenue - subscription** accounts must be set up in the **Project** module.</span></span>

<span data-ttu-id="adae2-118">Al registrar el ingreso acumulado, se carga en la cuenta **Trabajo en proceso - suscripción** el importe de acumulación y se abona el importe a acumulación en la cuenta **Ingresos acumulados - suscripción**.</span><span class="sxs-lookup"><span data-stu-id="adae2-118">When you post accrued revenue, the **WIP - subscription** account is debited with the accrual amount, and the **Accrued revenue - subscription** account is credited with the accrual amount.</span></span>

## <a name="set-up-accounts-for-accrual-of-subscription-revenue"></a><span data-ttu-id="adae2-119">Configuración de cuentas para la acumulación de ingresos de suscripción</span><span class="sxs-lookup"><span data-stu-id="adae2-119">Set up accounts for accrual of subscription revenue</span></span>

1.  <span data-ttu-id="adae2-120">Haga clic en **Administración de proyectos y contabilidad** \> **Configurar** \> **Registrar** \> **Configuración de registro**.</span><span class="sxs-lookup"><span data-stu-id="adae2-120">Click **Project management and accounting** \> **Setup** \> **Posting** \> **Ledger posting setup**.</span></span>

2.  <span data-ttu-id="adae2-121">Haga clic en la pestaña **Cuentas de ingresos** , y seleccione **Trabajo en curso - Suscripción** o **Ingresos acumulados - Suscripción** para configurar las cuentas.</span><span class="sxs-lookup"><span data-stu-id="adae2-121">Click the **Revenue accounts** tab, and select **WIP - subscription** or **Accrued revenue - subscription** to set up the accounts.</span></span>

## <a name="subscription-group-setup"></a><span data-ttu-id="adae2-122">Configuración del grupo de suscripciones</span><span class="sxs-lookup"><span data-stu-id="adae2-122">Subscription group setup</span></span>

<span data-ttu-id="adae2-123">Para poder acumular ingresos para suscripciones, debe activarse la casilla **Acumular ingresos**.</span><span class="sxs-lookup"><span data-stu-id="adae2-123">To be able to accrue revenue for subscriptions, the **Accrue revenue** check box must be selected.</span></span> <span data-ttu-id="adae2-124">Esto se encuentra en el formulario **Grupos de suscripción** para el grupo vinculado a la suscripción.</span><span class="sxs-lookup"><span data-stu-id="adae2-124">This is found on the **Subscription groups** form for the group that is attached to the subscription.</span></span> <span data-ttu-id="adae2-125">Haga clic en **Gestión de servicio** \> **Configuración** \> **Suscripciones de servicio** \> **Grupos de suscripciones**.</span><span class="sxs-lookup"><span data-stu-id="adae2-125">Click **Service management** \> **Setup** \> **Service subscriptions** \> **Subscription groups**.</span></span>

## <a name="enable-revenue-accrual-on-a-subscription-group"></a><span data-ttu-id="adae2-126">Habilitar acumulación de ingresos en un grupo de suscripciones</span><span class="sxs-lookup"><span data-stu-id="adae2-126">Enable revenue accrual on a subscription group</span></span>

1.  <span data-ttu-id="adae2-127">Haga clic en **Gestión de servicio** \> **Configuración** \> **Suscripciones de servicio** \> **Grupos de suscripciones**.</span><span class="sxs-lookup"><span data-stu-id="adae2-127">Click **Service management** \> **Setup** \> **Service subscriptions** \> **Subscription groups**.</span></span>

## <a name="periods"></a><span data-ttu-id="adae2-128">Períodos</span><span class="sxs-lookup"><span data-stu-id="adae2-128">Periods</span></span>

<span data-ttu-id="adae2-129">Debe configurar un código de período de facturación.</span><span class="sxs-lookup"><span data-stu-id="adae2-129">You must set up an invoicing period code.</span></span> <span data-ttu-id="adae2-130">A menos que desee acumular ingresos dentro de los mismos intervalos de tiempo que utiliza para la facturación, también deberá configurar un período de acumulación.</span><span class="sxs-lookup"><span data-stu-id="adae2-130">Unless you want to accrue revenue in the same time intervals as you use for invoicing, you must also set up an accrual period.</span></span>

<span data-ttu-id="adae2-131">La tabla siguiente proporciona una visión general de los períodos de acumulación que se pueden configurar para cada período de facturación:</span><span class="sxs-lookup"><span data-stu-id="adae2-131">The following table provides an overview of which accrual periods can be set up for each invoicing period:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="adae2-132">Período de facturación</span><span class="sxs-lookup"><span data-stu-id="adae2-132">Invoicing period</span></span></p></th>
<th><p><span data-ttu-id="adae2-133">Período de acumulación</span><span class="sxs-lookup"><span data-stu-id="adae2-133">Accrual period</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="adae2-134"><strong>Años</strong></span><span class="sxs-lookup"><span data-stu-id="adae2-134"><strong>Years</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="adae2-135"><strong>Años</strong></span><span class="sxs-lookup"><span data-stu-id="adae2-135"><strong>Years</strong></span></span></p></li>
<li><p><span data-ttu-id="adae2-136"><strong>Trimestre</strong></span><span class="sxs-lookup"><span data-stu-id="adae2-136"><strong>Quarter</strong></span></span></p></li>
<li><p><span data-ttu-id="adae2-137"><strong>Mes</strong></span><span class="sxs-lookup"><span data-stu-id="adae2-137"><strong>Month</strong></span></span></p></li>
<li><p><span data-ttu-id="adae2-138"><strong>Día</strong></span><span class="sxs-lookup"><span data-stu-id="adae2-138"><strong>Day</strong></span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adae2-139"><strong>Trimestre</strong></span><span class="sxs-lookup"><span data-stu-id="adae2-139"><strong>Quarter</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="adae2-140"><strong>Trimestre</strong></span><span class="sxs-lookup"><span data-stu-id="adae2-140"><strong>Quarter</strong></span></span></p></li>
<li><p><span data-ttu-id="adae2-141"><strong>Mes</strong></span><span class="sxs-lookup"><span data-stu-id="adae2-141"><strong>Month</strong></span></span></p></li>
<li><p><span data-ttu-id="adae2-142"><strong>Día</strong></span><span class="sxs-lookup"><span data-stu-id="adae2-142"><strong>Day</strong></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="adae2-143"><strong>Mes</strong></span><span class="sxs-lookup"><span data-stu-id="adae2-143"><strong>Month</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="adae2-144"><strong>Mes</strong></span><span class="sxs-lookup"><span data-stu-id="adae2-144"><strong>Month</strong></span></span></p></li>
<li><p><span data-ttu-id="adae2-145"><strong>Día</strong></span><span class="sxs-lookup"><span data-stu-id="adae2-145"><strong>Day</strong></span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adae2-146"><strong>Semana</strong></span><span class="sxs-lookup"><span data-stu-id="adae2-146"><strong>Week</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="adae2-147"><strong>Día</strong></span><span class="sxs-lookup"><span data-stu-id="adae2-147"><strong>Day</strong></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="adae2-148"><strong>Día</strong></span><span class="sxs-lookup"><span data-stu-id="adae2-148"><strong>Day</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="adae2-149"><strong>Día</strong></span><span class="sxs-lookup"><span data-stu-id="adae2-149"><strong>Day</strong></span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="adae2-150">La configuración del período de facturación es una parte obligatoria de toda la configuración del grupo de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="adae2-150">Setting up the invoicing period is a mandatory part of the overall subscription group setup.</span></span> <span data-ttu-id="adae2-151">Puede decidir si también configurar un período de acumulación para el grupo de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="adae2-151">You can decide whether to also set up an accrual period for the subscription group.</span></span> <span data-ttu-id="adae2-152">Si lo hace, se sugiere este período en el campo **Código del período**.</span><span class="sxs-lookup"><span data-stu-id="adae2-152">If you set up an accrual period for the subscription group, this period is suggested in the **Period code** field.</span></span> <span data-ttu-id="adae2-153">Este campo se encuentra en el formulario **Acumular ingresos de suscripción**, cuando se acumulan ingresos de suscripción.</span><span class="sxs-lookup"><span data-stu-id="adae2-153">This field is found in the **Accrue subscription revenue** form, when you accrue subscription revenue.</span></span> <span data-ttu-id="adae2-154">Sin embargo, el período de acumulación es información opcional acerca del grupo de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="adae2-154">However, the accrual period is optional information about the subscription group.</span></span>


> [!NOTE]
> <P><span data-ttu-id="adae2-155">Use la siguiente ruta para abrir el formulario <STRONG>Acumular ingresos de suscripción</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="adae2-155">Use the following path to open the <STRONG>Accrue subscription revenue</STRONG> form.</span></span> <span data-ttu-id="adae2-156">Haga clic en <STRONG>Gestión de servicio</STRONG> &gt; <STRONG>Periódica</STRONG> &gt; <STRONG>Suscripciones de servicio</STRONG> &gt; <STRONG>Acumular ingresos de suscripción</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="adae2-156">Click <STRONG>Service management</STRONG> &gt; <STRONG>Periodic</STRONG> &gt; <STRONG>Service subscriptions</STRONG> &gt; <STRONG>Accrue subscription revenue</STRONG>.</span></span></P>


## <a name="transactions"></a><span data-ttu-id="adae2-157">Transacciones</span><span class="sxs-lookup"><span data-stu-id="adae2-157">Transactions</span></span>

<span data-ttu-id="adae2-158">Puede controlar el número de transacciones contables que se crean al registrar ingresos acumulados.</span><span class="sxs-lookup"><span data-stu-id="adae2-158">You can control the number of ledger transactions that are created when you post accrued revenue.</span></span> <span data-ttu-id="adae2-159">En las suscripciones, defina si las transacciones contables se deben crear como total o por línea.</span><span class="sxs-lookup"><span data-stu-id="adae2-159">On subscriptions, define if the ledger transactions should be created as a total or per line.</span></span>

## <a name="specify-the-level-of-posting-details-to-display-for-accrued-transactions"></a><span data-ttu-id="adae2-160">Especificar el nivel de detalles de registro que se muestra para transacciones acumuladas</span><span class="sxs-lookup"><span data-stu-id="adae2-160">Specify the level of posting details to display for accrued transactions</span></span>

1.  <span data-ttu-id="adae2-161">Haga clic en **Gestión de proyectos y contabilidad** \> **Configurar** \> **Parámetros de gestión de proyectos y contabilidad**.</span><span class="sxs-lookup"><span data-stu-id="adae2-161">Click **Project management and accounting** \> **Setup** \> **Project management and accounting parameters**.</span></span>

2.  <span data-ttu-id="adae2-162">En la ficha **Financiero**, en el campo **Factura**, seleccione **Total** o **Línea**.</span><span class="sxs-lookup"><span data-stu-id="adae2-162">On the **Financial** tab, in the **Invoice** field, select **Total** or **Line**.</span></span>


## <a name="see-also"></a><span data-ttu-id="adae2-163">Consulte también</span><span class="sxs-lookup"><span data-stu-id="adae2-163">See also</span></span>

[<span data-ttu-id="adae2-164">Acumular ingresos de suscripción</span><span class="sxs-lookup"><span data-stu-id="adae2-164">Accrue subscription revenue</span></span>](accrue-subscription-revenue.md)

  


