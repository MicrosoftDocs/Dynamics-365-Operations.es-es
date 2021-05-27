---
title: Anticipos del cliente
description: Este tema explica cómo configurar y procesar los anticipos del cliente (también llamados depósitos del cliente).
author: roschlom
ms.date: 04/30/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, LedgerJournalTransCustPaym, CustParameters
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: ''
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c3314803b994aed40e5b04d8546a45bd305d48b6
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019429"
---
# <a name="customer-prepayments"></a><span data-ttu-id="ccc81-103">Anticipos del cliente</span><span class="sxs-lookup"><span data-stu-id="ccc81-103">Customer prepayments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ccc81-104">Los anticipos del cliente se utilizan cuando recibe un pago de un cliente, pero no hay ninguna factura con la que se pueda liquidar el pago.</span><span class="sxs-lookup"><span data-stu-id="ccc81-104">Customer prepayments are used when you receive a payment from a customer, but there is no invoice that the payment can be settled against.</span></span> <span data-ttu-id="ccc81-105">Estos tipos de pagos también se conocen como depósitos del cliente.</span><span class="sxs-lookup"><span data-stu-id="ccc81-105">These types of payments are also referred to as customer deposits.</span></span>

<span data-ttu-id="ccc81-106">El proceso de configuración y trabajo con anticipos de clientes consta de los siguientes pasos básicos.</span><span class="sxs-lookup"><span data-stu-id="ccc81-106">The process of setting up and working with customer prepayments consists of the following basic steps.</span></span>

1. <span data-ttu-id="ccc81-107">Cree un perfil de registro de cliente para anticipos.</span><span class="sxs-lookup"><span data-stu-id="ccc81-107">Create a customer posting profile for prepayments.</span></span>
2. <span data-ttu-id="ccc81-108">Elija el parámetro **Perfil de registro con asiento del diario de anticipos**.</span><span class="sxs-lookup"><span data-stu-id="ccc81-108">Set the **Posting profile with prepayment journal voucher** parameter.</span></span>
3. <span data-ttu-id="ccc81-109">Cree un diario de pagos del cliente y seleccione la casilla **Asiento del diario de anticipos** en cada línea.</span><span class="sxs-lookup"><span data-stu-id="ccc81-109">Create a customer payment journal, and select the **Prepayment journal voucher** check box on each line.</span></span>
4. <span data-ttu-id="ccc81-110">Registre el diario de pagos del cliente.</span><span class="sxs-lookup"><span data-stu-id="ccc81-110">Post the customer payment journal.</span></span>
5. <span data-ttu-id="ccc81-111">Una vez generada una factura, liquide el anticipo con ella mediante la página **Liquidar transacciones abiertas**.</span><span class="sxs-lookup"><span data-stu-id="ccc81-111">After an invoice is generated, settle the prepayment with it by using the **Settle open transactions** page.</span></span>

## <a name="create-a-customer-posting-profile-for-prepayments"></a><span data-ttu-id="ccc81-112">Crear un perfil de registro de cliente para anticipos</span><span class="sxs-lookup"><span data-stu-id="ccc81-112">Create a customer posting profile for prepayments</span></span>

<span data-ttu-id="ccc81-113">Por lo general, cuando acepta anticipos o depósitos de sus clientes antes de que se entreguen los bienes o servicios o antes de que exista una factura en su sistema, querrá registrar el efectivo como un pasivo en lugar de un activo en su plan de cuentas.</span><span class="sxs-lookup"><span data-stu-id="ccc81-113">Typically, when you accept prepayments or deposits from your customers before goods or services are delivered, or before an invoice exists in your system, you will want to record the cash as a liability instead of an asset in your chart of accounts.</span></span> <span data-ttu-id="ccc81-114">Sin embargo, los requisitos para registrar estos importes en su contabilidad general pueden diferir según su país o región.</span><span class="sxs-lookup"><span data-stu-id="ccc81-114">However, the requirements for recording these amounts in your general ledger might differ, depending on your country or region.</span></span> <span data-ttu-id="ccc81-115">Por lo tanto, asegúrese de consultar a sus contables sobre las regulaciones locales que se apliquen.</span><span class="sxs-lookup"><span data-stu-id="ccc81-115">Therefore, be sure to consult your accountants about any local regulations that apply.</span></span>

<span data-ttu-id="ccc81-116">En general, el proceso para crear un perfil de contabilización que se puede utilizar para anticipos es el mismo que el proceso para crear otros perfiles de contabilización.</span><span class="sxs-lookup"><span data-stu-id="ccc81-116">In general, the process for creating a posting profile that can be used for prepayments is the same as the process for creating other posting profiles.</span></span> <span data-ttu-id="ccc81-117">La principal diferencia es la cuenta principal que selecciona en el campo **Extracto de cuenta**.</span><span class="sxs-lookup"><span data-stu-id="ccc81-117">The primary difference is the main account that you select in the **Summary account** field.</span></span> <span data-ttu-id="ccc81-118">Para obtener más información, consulte [Perfiles de contabilización del cliente (formulario)](customer-posting-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="ccc81-118">For more information, see [Customer posting profiles](customer-posting-profiles.md).</span></span>

## <a name="define-parameters-for-customer-prepayments"></a><span data-ttu-id="ccc81-119">Definir parámetros para anticipos de clientes</span><span class="sxs-lookup"><span data-stu-id="ccc81-119">Define parameters for customer prepayments</span></span>

<span data-ttu-id="ccc81-120">Hay dos parámetros principales de clientes que debe tener en cuenta al configurar el sistema para anticipos de clientes.</span><span class="sxs-lookup"><span data-stu-id="ccc81-120">There are two main Accounts receivable parameters that you must consider when you configure the system for customer prepayments.</span></span> <span data-ttu-id="ccc81-121">Siga estos pasos para configurar los parámetros.</span><span class="sxs-lookup"><span data-stu-id="ccc81-121">Follow these steps to configure the parameters.</span></span>

1. <span data-ttu-id="ccc81-122">Vaya a **Clientes \> Configuración \> Parámetros de clientes**.</span><span class="sxs-lookup"><span data-stu-id="ccc81-122">Go to **Accounts receivable \> Setup \> Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="ccc81-123">Opcional: en la pestaña **Impuestos y contabilidad**, en la ficha desplegable **Pago**, establezca la opción **Impuestos sobre el asiento del diario de anticipos** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="ccc81-123">Optional: On the **Ledger and sales tax** tab, on the **Payment** FastTab, set the **Sales tax on prepayment journal voucher** option to **Yes**.</span></span>
3. <span data-ttu-id="ccc81-124">En el campo **Perfil de registro con asiento del diario de anticipos**, seleccione el perfil de contabilización del cliente que se utilizará cuando se registren los anticipos del cliente.</span><span class="sxs-lookup"><span data-stu-id="ccc81-124">In the **Posting profile with prepayment journal voucher** field, select the customer posting profile to use when customer prepayments are posted.</span></span>
4. <span data-ttu-id="ccc81-125">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ccc81-125">Close the page.</span></span>

## <a name="create-customer-prepayment-vouchers"></a><span data-ttu-id="ccc81-126">Crear asientos de anticipos de clientes</span><span class="sxs-lookup"><span data-stu-id="ccc81-126">Create customer prepayment vouchers</span></span>

<span data-ttu-id="ccc81-127">Cuando crea el diario de pagos del cliente, para cada anticipo debe establecer la opción **Asiento del diario de anticipos** a **Sí** en la página **Diario de pagos de clientes**.</span><span class="sxs-lookup"><span data-stu-id="ccc81-127">When you create the customer payment journal, for every prepayment, you must set the **Prepayment journal voucher** option to **Yes** on the **Customer payment journal** page.</span></span> <span data-ttu-id="ccc81-128">Para crear un anticipo de cliente, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ccc81-128">Follow these steps to create a customer prepayment.</span></span>

1. <span data-ttu-id="ccc81-129">Vaya a **Clientes \> Pagos \> Diario de pagos de clientes**.</span><span class="sxs-lookup"><span data-stu-id="ccc81-129">Go to **Accounts receivable \> Payments \> Customer payment journal**.</span></span>
2. <span data-ttu-id="ccc81-130">Seleccione **Nuevo** para crear un diario.</span><span class="sxs-lookup"><span data-stu-id="ccc81-130">Select **New** to create a journal.</span></span>
3. <span data-ttu-id="ccc81-131">En el campo **Nombre**, seleccione el nombre de diario que usar.</span><span class="sxs-lookup"><span data-stu-id="ccc81-131">In the **Name** field, select the journal name to use.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ccc81-132">Si estableció la opción **Impuestos sobre el asiento del diario de anticipos** a **Sí** en el procedimiento anterior, debe seleccionar un nombre de diario donde el parámetro **Importe incluye impuesto de venta** esté seleccionado.</span><span class="sxs-lookup"><span data-stu-id="ccc81-132">If you set the **Sales tax on prepayment journal voucher** option to **Yes** in the previous procedure, you must select a journal name where the **Amount includes sales tax** parameter is selected.</span></span> 

4. <span data-ttu-id="ccc81-133">Opcional: puede introducir una descripción detallada en el campo **Descripción**.</span><span class="sxs-lookup"><span data-stu-id="ccc81-133">Optional: In the **Description** field, enter a detailed description.</span></span>
5. <span data-ttu-id="ccc81-134">Seleccionar **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="ccc81-134">Select **Lines**.</span></span>
6. <span data-ttu-id="ccc81-135">Si no existe una línea en blanco, seleccione **Nuevo** para crear una línea.</span><span class="sxs-lookup"><span data-stu-id="ccc81-135">If a blank line doesn't exist, select **New** to create a line.</span></span>
7. <span data-ttu-id="ccc81-136">En el campo **Fecha**, introduzca la fecha en la que se debe publicar la entrada de anticipo.</span><span class="sxs-lookup"><span data-stu-id="ccc81-136">In the **Date** field, enter the date when the prepayment should be posted.</span></span>
8. <span data-ttu-id="ccc81-137">En el campo **Cuenta**, seleccione el cliente para el anticipo.</span><span class="sxs-lookup"><span data-stu-id="ccc81-137">In the **Account** field, select the customer for the prepayment.</span></span>
9. <span data-ttu-id="ccc81-138">Opcional: puede introducir una descripción detallada de la transacción en el campo **Descripción**.</span><span class="sxs-lookup"><span data-stu-id="ccc81-138">Optional: In the **Description** field, enter a detailed description of the transaction.</span></span>
10. <span data-ttu-id="ccc81-139">En el campo **Crédito**, especifique el importe del anticipo.</span><span class="sxs-lookup"><span data-stu-id="ccc81-139">In the **Credit** field, enter the amount of the prepayment.</span></span>
11. <span data-ttu-id="ccc81-140">En el campo **Cuenta de contrapartida**, seleccione la cuenta de contrapartida del pago.</span><span class="sxs-lookup"><span data-stu-id="ccc81-140">In the **Offset account** field, select the account to offset the payment to.</span></span> <span data-ttu-id="ccc81-141">Por ejemplo, seleccione el banco o la cuenta principal para registrar el pago.</span><span class="sxs-lookup"><span data-stu-id="ccc81-141">For example, select the bank or main account to post the payment to.</span></span>
12. <span data-ttu-id="ccc81-142">En el campo **Método de pago**, seleccione el método de pago del cliente.</span><span class="sxs-lookup"><span data-stu-id="ccc81-142">In the **Method of payment** field, select the customer's method of payment.</span></span>
13. <span data-ttu-id="ccc81-143">En la pestaña **Pago** , establezca la opción **Asiento del diario de anticipos** a **Sí**.</span><span class="sxs-lookup"><span data-stu-id="ccc81-143">On the **Payment** tab, set the **Prepayment journal voucher** option to **Yes**.</span></span>
14. <span data-ttu-id="ccc81-144">Repita los pasos del 7 al 13 para cada anticipo adicional que deba registrarse.</span><span class="sxs-lookup"><span data-stu-id="ccc81-144">Repeat steps 7 through 13 for each additional prepayment that must be posted.</span></span>
15. <span data-ttu-id="ccc81-145">Seleccione **Registrar** para terminar el diario.</span><span class="sxs-lookup"><span data-stu-id="ccc81-145">Select **Post** to finalize the journal.</span></span>

## <a name="settle-prepayments-with-invoices"></a><span data-ttu-id="ccc81-146">Liquidar anticipos con facturas</span><span class="sxs-lookup"><span data-stu-id="ccc81-146">Settle prepayments with invoices</span></span>

<span data-ttu-id="ccc81-147">Puedes usar el espacio de trabajo **Pagos de clientes** para encontrar y liquidar fácilmente los pagos que no se han liquidado por completo.</span><span class="sxs-lookup"><span data-stu-id="ccc81-147">You can use the **Customer payments** workspace to easily find and settle payments that haven't been fully settled.</span></span>

1. <span data-ttu-id="ccc81-148">En el panel **Inicio**, seleccione el icono **Pagos de clientes**.</span><span class="sxs-lookup"><span data-stu-id="ccc81-148">On the **Home** dashboard, select the **Customer payments** tile.</span></span>
2. <span data-ttu-id="ccc81-149">En la sección **Transacciones de clientes**, en la pestaña **Pagos no liquidados**, busque y seleccione el pago a liquidar.</span><span class="sxs-lookup"><span data-stu-id="ccc81-149">In the **Customer transactions** section, on the **Payments not settled** tab, search for and select the payment to settle.</span></span>
3. <span data-ttu-id="ccc81-150">Seleccione **Liquidar transacciones**.</span><span class="sxs-lookup"><span data-stu-id="ccc81-150">Select **Settle transactions**.</span></span>
4. <span data-ttu-id="ccc81-151">Selecciona la casilla **Marcar** para la factura y el pago que se liquidarán.</span><span class="sxs-lookup"><span data-stu-id="ccc81-151">Select the **Mark** check box for the invoice and the payment that will be settled.</span></span>
5. <span data-ttu-id="ccc81-152">Seleccione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="ccc81-152">Select **Post**.</span></span>

<span data-ttu-id="ccc81-153">Para obtener más información sobre cómo liquidar transacciones abiertas, consulte [Descripción de la liquidación](/cash-bank-management/settlement-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ccc81-153">For more information about how to settle open transactions, see [Settlement overview](/cash-bank-management/settlement-overview.md).</span></span>
