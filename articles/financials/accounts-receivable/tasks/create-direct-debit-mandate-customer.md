---
title: Crear una orden de domiciliación bancaria para un cliente
description: Esta guía de tarea muestra cómo crear una orden de domiciliación bancaria y cómo usarla en una factura.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, BankAccountTable, CustPaymMode, CustDirectDebitMandate, BankAccountTableLookUp, SrsReportViewerForm,  LogisticsAddressCityLookup, CustFreeInvoice, CustTableLookup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7c93a1aba6ca32e783a6ed6f005c72aab3e06978
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1843010"
---
# <a name="create-a-direct-debit-mandate-for-a-customer"></a><span data-ttu-id="c3d9c-103">Crear una orden de domiciliación bancaria para un cliente</span><span class="sxs-lookup"><span data-stu-id="c3d9c-103">Create a direct debit mandate for a customer</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c3d9c-104">Esta guía de tarea muestra cómo crear una orden de domiciliación bancaria y cómo usarla en una factura.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-104">This task guide demonstrates how to create a direct debit mandate and use it on an invoice.</span></span>


## <a name="create-a-bank-account"></a><span data-ttu-id="c3d9c-105">Creación de una cuenta bancaria</span><span class="sxs-lookup"><span data-stu-id="c3d9c-105">Create a bank account</span></span>
1. <span data-ttu-id="c3d9c-106">Vaya a Clientes > Clientes > Todos los clientes.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-106">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="c3d9c-107">Por ejemplo, seleccione US-001.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-107">For example, select US-001</span></span>
3. <span data-ttu-id="c3d9c-108">En el panel de acciones, haga clic en Clientes.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-108">On the Action Pane, click Customer.</span></span>
4. <span data-ttu-id="c3d9c-109">Haga clic en Cuentas bancarias.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-109">Click Bank accounts.</span></span>
5. <span data-ttu-id="c3d9c-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-110">Click New.</span></span>
6. <span data-ttu-id="c3d9c-111">En el campo Cuenta bancaria, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-111">In the Bank account field, type a value.</span></span>
7. <span data-ttu-id="c3d9c-112">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-112">In the Name field, type a value.</span></span>
8. <span data-ttu-id="c3d9c-113">Escriba un valor en el campo IBAN.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-113">In the IBAN field, type a value.</span></span>
9. <span data-ttu-id="c3d9c-114">En el campo Divisa, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-114">In the Currency field, type a value.</span></span>
10. <span data-ttu-id="c3d9c-115">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-115">Click Save.</span></span>
11. <span data-ttu-id="c3d9c-116">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-116">Close the page.</span></span>
12. <span data-ttu-id="c3d9c-117">Vaya a Gestión de efectivo y de banco > Cuentas bancarias > Cuentas bancarias.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-117">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
13. <span data-ttu-id="c3d9c-118">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-118">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="c3d9c-119">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-119">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="c3d9c-120">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-120">Click Edit.</span></span>
16. <span data-ttu-id="c3d9c-121">Expanda la sección Identificación adicional.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-121">Expand the Additional identification section.</span></span>
17. <span data-ttu-id="c3d9c-122">En el campo Id. de domiciliación bancaria, especifique un valor.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-122">In the Direct debit ID field, type a value.</span></span>
18. <span data-ttu-id="c3d9c-123">Escriba un valor en el campo IBAN.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-123">In the IBAN field, type a value.</span></span>
19. <span data-ttu-id="c3d9c-124">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-124">Close the page.</span></span>
20. <span data-ttu-id="c3d9c-125">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-125">Close the page.</span></span>

## <a name="define-the-electronic-payment-method"></a><span data-ttu-id="c3d9c-126">Definición de la forma de pago electrónico</span><span class="sxs-lookup"><span data-stu-id="c3d9c-126">Define the electronic payment method</span></span>
1. <span data-ttu-id="c3d9c-127">Vaya a Clientes > Configuración de pagos > Formas de pago.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-127">Go to Accounts receivable > Payments setup > Methods of payment.</span></span>
2. <span data-ttu-id="c3d9c-128">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-128">Click New.</span></span>
3. <span data-ttu-id="c3d9c-129">En el campo Forma de pago, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-129">In the Method of payment field, type a value.</span></span>
4. <span data-ttu-id="c3d9c-130">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-130">In the Description field, type a value.</span></span>
5. <span data-ttu-id="c3d9c-131">El tipo de pago para un método de pago de orden de domiciliación bancaria debe ser Pago electrónico.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-131">The payment type for a direct debit mandate method of payment must be Electronic payment.</span></span>
6. <span data-ttu-id="c3d9c-132">Seleccione Sí en el campo Requerir orden.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-132">Select Yes in the Require mandate field.</span></span>
7. <span data-ttu-id="c3d9c-133">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-133">Close the page.</span></span>

## <a name="add-a-direct-debit-mandate-to-a-customer"></a><span data-ttu-id="c3d9c-134">Agregue una orden de domiciliación bancaria a un cliente.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-134">Add a direct debit mandate to a customer.</span></span>
1. <span data-ttu-id="c3d9c-135">Vaya a Clientes > Clientes > Todos los clientes.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-135">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="c3d9c-136">Por ejemplo, seleccione US-001.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-136">For example, select US-001</span></span>
3. <span data-ttu-id="c3d9c-137">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-137">Click Edit.</span></span>
4. <span data-ttu-id="c3d9c-138">Expanda la sección Valores predeterminados de pago.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-138">Expand the Payment defaults section.</span></span>
5. <span data-ttu-id="c3d9c-139">En el campo Método de pago, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-139">In the Method of payment field, enter or select a value.</span></span>
6. <span data-ttu-id="c3d9c-140">Expanda la sección Valores predeterminados de pago.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-140">Expand the Payment defaults section.</span></span>
7. <span data-ttu-id="c3d9c-141">Expanda la sección Órdenes de domiciliación bancaria.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-141">Expand the Direct debit mandates section.</span></span>
8. <span data-ttu-id="c3d9c-142">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-142">Click Add.</span></span>
9. <span data-ttu-id="c3d9c-143">En el campo Cuenta bancaria, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-143">In the Bank account field, enter or select a value.</span></span>
10. <span data-ttu-id="c3d9c-144">En el campo Cuenta bancaria de acreedor, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-144">In the Creditor bank account field, enter or select a value.</span></span>
11. <span data-ttu-id="c3d9c-145">Especifique el número de pagos que se prevén para procesar esta orden.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-145">Enter the number of payments that you expect to process for this mandate.</span></span>
12. <span data-ttu-id="c3d9c-146">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="c3d9c-146">Click OK.</span></span>
13. <span data-ttu-id="c3d9c-147">Haga clic en Imprimir.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-147">Click Print.</span></span>
14. <span data-ttu-id="c3d9c-148">Haga clic en Informe de orden.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-148">Click Mandate report.</span></span>
15. <span data-ttu-id="c3d9c-149">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-149">Close the page.</span></span>
16. <span data-ttu-id="c3d9c-150">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-150">Click Edit.</span></span>
17. <span data-ttu-id="c3d9c-151">En el campo Fecha de firma, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-151">In the Signature date field, enter a date.</span></span>
18. <span data-ttu-id="c3d9c-152">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-152">Click Yes.</span></span>
19. <span data-ttu-id="c3d9c-153">Especifique la ubicación donde se firmó la orden.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-153">Enter the location where the mandate was signed.</span></span>
20. <span data-ttu-id="c3d9c-154">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="c3d9c-154">Click OK.</span></span>
21. <span data-ttu-id="c3d9c-155">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-155">Close the page.</span></span>

## <a name="create-a-free-text-invoice-with-mandate"></a><span data-ttu-id="c3d9c-156">Creación de una factura de texto libre con una orden</span><span class="sxs-lookup"><span data-stu-id="c3d9c-156">Create a free text invoice with mandate</span></span>
1. <span data-ttu-id="c3d9c-157">Vaya a Clientes > Facturas > Todas las facturas de servicios.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-157">Go to Accounts receivable > Invoices > All free text invoices.</span></span>
2. <span data-ttu-id="c3d9c-158">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-158">Click New.</span></span>
3. <span data-ttu-id="c3d9c-159">Seleccione el cliente al que haya agregado la orden.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-159">Select the customer that you added the mandate to.</span></span>
4. <span data-ttu-id="c3d9c-160">En el campo Id. de proyecto, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c3d9c-160">In the Direct debit mandate ID field, enter or select a value.</span></span>

