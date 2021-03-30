---
title: Crear una orden de domiciliación bancaria para un cliente
description: Esta guía de tarea muestra cómo crear una orden de domiciliación bancaria y cómo usarla en una factura.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, BankAccountTable, CustPaymMode, CustDirectDebitMandate, BankAccountTableLookUp, SrsReportViewerForm,  LogisticsAddressCityLookup, CustFreeInvoice, CustTableLookup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ef9beae6769c361680832d81ddda00e1237d3297
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5241643"
---
# <a name="create-a-direct-debit-mandate-for-a-customer"></a><span data-ttu-id="54757-103">Crear una orden de domiciliación bancaria para un cliente</span><span class="sxs-lookup"><span data-stu-id="54757-103">Create a direct debit mandate for a customer</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="54757-104">Esta guía de tarea muestra cómo crear una orden de domiciliación bancaria y cómo usarla en una factura.</span><span class="sxs-lookup"><span data-stu-id="54757-104">This task guide demonstrates how to create a direct debit mandate and use it on an invoice.</span></span>


## <a name="create-a-bank-account"></a><span data-ttu-id="54757-105">Creación de una cuenta bancaria</span><span class="sxs-lookup"><span data-stu-id="54757-105">Create a bank account</span></span>
1. <span data-ttu-id="54757-106">En el **Panel de exploración**, vaya a **Módulos > Clientes > Clientes > Todos los clientes**.</span><span class="sxs-lookup"><span data-stu-id="54757-106">In the **Navigation pane**, go to **Modules > Accounts receivable > Customers > All customers**.</span></span>
2. <span data-ttu-id="54757-107">En la lista, seleccione un registro.</span><span class="sxs-lookup"><span data-stu-id="54757-107">In the list, select a record.</span></span> <span data-ttu-id="54757-108">Por ejemplo, seleccione US-001.</span><span class="sxs-lookup"><span data-stu-id="54757-108">For example, select US-001</span></span>
3. <span data-ttu-id="54757-109">En el panel de acciones, haga clic en **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="54757-109">On the Action Pane, click **Customer**.</span></span>
4. <span data-ttu-id="54757-110">Haga clic en **Cuentas bancarias**.</span><span class="sxs-lookup"><span data-stu-id="54757-110">Click **Bank accounts**.</span></span>
5. <span data-ttu-id="54757-111">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="54757-111">Click **New**.</span></span>
6. <span data-ttu-id="54757-112">En el campo **Cuenta bancaria**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="54757-112">In the **Bank account** field, type a value.</span></span>
7. <span data-ttu-id="54757-113">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="54757-113">In the **Name** field, type a value.</span></span>
8. <span data-ttu-id="54757-114">Escriba un valor en el campo **IBAN**.</span><span class="sxs-lookup"><span data-stu-id="54757-114">In the **IBAN** field, type a value.</span></span>
9. <span data-ttu-id="54757-115">En el campo **Divisa**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="54757-115">In the **Currency** field, type a value.</span></span>
10. <span data-ttu-id="54757-116">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="54757-116">Click **Save**.</span></span>
11. <span data-ttu-id="54757-117">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="54757-117">Close the page.</span></span>
12. <span data-ttu-id="54757-118">En el **Panel de exploración**, vaya a **Módulos > Gestión de efectivo y bancos > Cuentas bancarias > Cuentas bancarias**.</span><span class="sxs-lookup"><span data-stu-id="54757-118">In the **Navigation pane**, go to **Modules > Cash and bank management > Bank accounts > Bank accounts**.</span></span>
13. <span data-ttu-id="54757-119">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="54757-119">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="54757-120">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="54757-120">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="54757-121">Haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="54757-121">Click **Edit**.</span></span>
16. <span data-ttu-id="54757-122">Expanda la ficha desplegable **Identificación adicional**.</span><span class="sxs-lookup"><span data-stu-id="54757-122">Expand the **Additional identification** fastTab.</span></span>
17. <span data-ttu-id="54757-123">En el campo **Id. de domiciliación bancaria**, especifique un valor.</span><span class="sxs-lookup"><span data-stu-id="54757-123">In the **Direct debit ID** field, type a value.</span></span>
18. <span data-ttu-id="54757-124">Escriba un valor en el campo **IBAN**.</span><span class="sxs-lookup"><span data-stu-id="54757-124">In the **IBAN** field, type a value.</span></span>
19. <span data-ttu-id="54757-125">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="54757-125">Close the page.</span></span>
20. <span data-ttu-id="54757-126">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="54757-126">Close the page.</span></span>

## <a name="define-the-electronic-payment-method"></a><span data-ttu-id="54757-127">Definición de la forma de pago electrónico</span><span class="sxs-lookup"><span data-stu-id="54757-127">Define the electronic payment method</span></span>
1. <span data-ttu-id="54757-128">En el **Panel de exploración**, vaya a **Módulos > Clientes > Configuración de pagos > Métodos de pago**.</span><span class="sxs-lookup"><span data-stu-id="54757-128">In the **Navigation pane**, go to **Modules > Accounts receivable > Payments setup > Methods of payment**.</span></span>
2. <span data-ttu-id="54757-129">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="54757-129">Click **New**.</span></span>
3. <span data-ttu-id="54757-130">En el campo **Método de pago**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="54757-130">In the **Method of payment** field, type a value.</span></span>
4. <span data-ttu-id="54757-131">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="54757-131">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="54757-132">En el campo **Tipo de pago**, seleccione "Pago electrónico".</span><span class="sxs-lookup"><span data-stu-id="54757-132">In the **Payment type** field, enter 'Electronic payment'.</span></span> <span data-ttu-id="54757-133">El tipo de pago para un método de pago de orden de domiciliación bancaria debe ser Pago electrónico.</span><span class="sxs-lookup"><span data-stu-id="54757-133">The payment type for a direct debit mandate method of payment must be Electronic payment.</span></span>
6. <span data-ttu-id="54757-134">Seleccione Sí en el campo **Requerir orden**.</span><span class="sxs-lookup"><span data-stu-id="54757-134">Select Yes in the **Require mandate** field.</span></span>
7. <span data-ttu-id="54757-135">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="54757-135">Close the page.</span></span>

## <a name="add-a-direct-debit-mandate-to-a-customer"></a><span data-ttu-id="54757-136">Agregue una orden de domiciliación bancaria a un cliente.</span><span class="sxs-lookup"><span data-stu-id="54757-136">Add a direct debit mandate to a customer.</span></span>
1. <span data-ttu-id="54757-137">En el **Panel de exploración**, vaya a **Módulos > Clientes > Clientes > Todos los clientes**.</span><span class="sxs-lookup"><span data-stu-id="54757-137">In the **Navigation pane**, go to **Modules > Accounts receivable > Customers > All customers**.</span></span>
2. <span data-ttu-id="54757-138">En la lista, seleccione un registro.</span><span class="sxs-lookup"><span data-stu-id="54757-138">In the list, select a record.</span></span> <span data-ttu-id="54757-139">Por ejemplo, seleccione US-001.</span><span class="sxs-lookup"><span data-stu-id="54757-139">For example, select US-001</span></span>
3. <span data-ttu-id="54757-140">Haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="54757-140">Click **Edit**.</span></span>
4. <span data-ttu-id="54757-141">Expanda la ficha desplegable **Valores predeterminados de pago**.</span><span class="sxs-lookup"><span data-stu-id="54757-141">Expand the **Payment defaults** fastTab.</span></span>
5. <span data-ttu-id="54757-142">En el campo **Método de pago**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="54757-142">In the **Method of payment** field, enter or select a value.</span></span>
6. <span data-ttu-id="54757-143">Expanda la ficha desplegable **Valores predeterminados de pago**.</span><span class="sxs-lookup"><span data-stu-id="54757-143">Expand the **Payment defaults** fastTab.</span></span>
7. <span data-ttu-id="54757-144">Expanda la ficha desplegable **Órdenes de domiciliación bancaria**.</span><span class="sxs-lookup"><span data-stu-id="54757-144">Expand the **Direct debit mandates** fastTab.</span></span>
8. <span data-ttu-id="54757-145">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="54757-145">Click **Add**.</span></span>
9. <span data-ttu-id="54757-146">En el campo **Cuenta bancaria**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="54757-146">In the **Bank account** field, enter or select a value.</span></span>
10. <span data-ttu-id="54757-147">En el campo **Cuenta bancaria de acreedor**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="54757-147">In the **Creditor bank account** field, enter or select a value.</span></span>
11. <span data-ttu-id="54757-148">En el campo **Frecuencia de pago**, especifique el número de pagos que se prevén para procesar esta orden.</span><span class="sxs-lookup"><span data-stu-id="54757-148">In the **Payment frequency** field, enter the number of payments that you expect to process for this mandate.</span></span>
12. <span data-ttu-id="54757-149">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="54757-149">Click **OK**.</span></span>
13. <span data-ttu-id="54757-150">Haga clic en **Imprimir**.</span><span class="sxs-lookup"><span data-stu-id="54757-150">Click **Print**.</span></span>
14. <span data-ttu-id="54757-151">Haga clic en **Informe de orden**.</span><span class="sxs-lookup"><span data-stu-id="54757-151">Click **Mandate report**.</span></span>
15. <span data-ttu-id="54757-152">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="54757-152">Close the page.</span></span>
16. <span data-ttu-id="54757-153">Haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="54757-153">Click **Edit**.</span></span>
17. <span data-ttu-id="54757-154">En el campo **Fecha de firma**, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="54757-154">In the **Signature date** field, enter a date.</span></span>
18. <span data-ttu-id="54757-155">Haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="54757-155">Click **Yes**.</span></span>
19. <span data-ttu-id="54757-156">Especifique la ubicación donde se firmó la orden.</span><span class="sxs-lookup"><span data-stu-id="54757-156">Enter the location where the mandate was signed.</span></span>
20. <span data-ttu-id="54757-157">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="54757-157">Click **OK**.</span></span>
21. <span data-ttu-id="54757-158">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="54757-158">Close the page.</span></span>

## <a name="create-a-free-text-invoice-with-mandate"></a><span data-ttu-id="54757-159">Creación de una factura de texto libre con una orden</span><span class="sxs-lookup"><span data-stu-id="54757-159">Create a free text invoice with mandate</span></span>
1. <span data-ttu-id="54757-160">En el **Panel de exploración**, vaya a **Módulos > Clientes > Facturas > Todas las facturas de servicios**.</span><span class="sxs-lookup"><span data-stu-id="54757-160">In the **Navigation pane**, go to **Modules > Accounts receivable > Invoices > All free text invoices**.</span></span>
2. <span data-ttu-id="54757-161">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="54757-161">Click **New**.</span></span>
3. <span data-ttu-id="54757-162">Seleccione el cliente al que haya agregado la orden.</span><span class="sxs-lookup"><span data-stu-id="54757-162">Select the customer that you added the mandate to.</span></span>
4. <span data-ttu-id="54757-163">En el campo **Id. de orden de domiciliación bancaria**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="54757-163">In the **Direct debit mandate ID** field, enter or select a value.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]