--- 
title: "Crear una orden de domiciliación bancaria para un cliente"
description: "Esta guía de tarea muestra cómo crear una orden de domiciliación bancaria y cómo usarla en una factura."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 10/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: d01c7c19925a3c7064ab3f845b92b610b162066c
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-direct-debit-mandate-for-a-customer"></a><span data-ttu-id="f8e69-103">Crear una orden de domiciliación bancaria para un cliente</span><span class="sxs-lookup"><span data-stu-id="f8e69-103">Create a direct debit mandate for a customer</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f8e69-104">Esta guía de tarea muestra cómo crear una orden de domiciliación bancaria y cómo usarla en una factura.</span><span class="sxs-lookup"><span data-stu-id="f8e69-104">This task guide demonstrates how to create a direct debit mandate and use it on an invoice.</span></span>


## <a name="create-a-bank-account"></a><span data-ttu-id="f8e69-105">Creación de una cuenta bancaria</span><span class="sxs-lookup"><span data-stu-id="f8e69-105">Create a bank account</span></span>
1. <span data-ttu-id="f8e69-106">Vaya a Clientes > Clientes > Todos los clientes.</span><span class="sxs-lookup"><span data-stu-id="f8e69-106">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="f8e69-107">Por ejemplo, seleccione US-001.</span><span class="sxs-lookup"><span data-stu-id="f8e69-107">For example, select US-001</span></span>
3. <span data-ttu-id="f8e69-108">En el panel de acciones, haga clic en Clientes.</span><span class="sxs-lookup"><span data-stu-id="f8e69-108">On the Action Pane, click Customer.</span></span>
4. <span data-ttu-id="f8e69-109">Haga clic en Cuentas bancarias.</span><span class="sxs-lookup"><span data-stu-id="f8e69-109">Click Bank accounts.</span></span>
5. <span data-ttu-id="f8e69-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="f8e69-110">Click New.</span></span>
6. <span data-ttu-id="f8e69-111">En el campo Cuenta bancaria, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f8e69-111">In the Bank account field, type a value.</span></span>
7. <span data-ttu-id="f8e69-112">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f8e69-112">In the Name field, type a value.</span></span>
8. <span data-ttu-id="f8e69-113">Escriba un valor en el campo IBAN.</span><span class="sxs-lookup"><span data-stu-id="f8e69-113">In the IBAN field, type a value.</span></span>
9. <span data-ttu-id="f8e69-114">En el campo Divisa, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f8e69-114">In the Currency field, type a value.</span></span>
10. <span data-ttu-id="f8e69-115">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="f8e69-115">Click Save.</span></span>
11. <span data-ttu-id="f8e69-116">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f8e69-116">Close the page.</span></span>
12. <span data-ttu-id="f8e69-117">Vaya a Gestión de efectivo y de banco > Cuentas bancarias > Cuentas bancarias.</span><span class="sxs-lookup"><span data-stu-id="f8e69-117">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
13. <span data-ttu-id="f8e69-118">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="f8e69-118">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="f8e69-119">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f8e69-119">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="f8e69-120">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="f8e69-120">Click Edit.</span></span>
16. <span data-ttu-id="f8e69-121">Expanda la sección Identificación adicional.</span><span class="sxs-lookup"><span data-stu-id="f8e69-121">Expand the Additional identification section.</span></span>
17. <span data-ttu-id="f8e69-122">En el campo Id. de domiciliación bancaria, especifique un valor.</span><span class="sxs-lookup"><span data-stu-id="f8e69-122">In the Direct debit ID field, type a value.</span></span>
18. <span data-ttu-id="f8e69-123">Escriba un valor en el campo IBAN.</span><span class="sxs-lookup"><span data-stu-id="f8e69-123">In the IBAN field, type a value.</span></span>
19. <span data-ttu-id="f8e69-124">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f8e69-124">Close the page.</span></span>
20. <span data-ttu-id="f8e69-125">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f8e69-125">Close the page.</span></span>

## <a name="define-the-electronic-payment-method"></a><span data-ttu-id="f8e69-126">Definición de la forma de pago electrónico</span><span class="sxs-lookup"><span data-stu-id="f8e69-126">Define the electronic payment method</span></span>
1. <span data-ttu-id="f8e69-127">Vaya a Clientes > Configuración de pagos > Formas de pago.</span><span class="sxs-lookup"><span data-stu-id="f8e69-127">Go to Accounts receivable > Payments setup > Methods of payment.</span></span>
2. <span data-ttu-id="f8e69-128">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="f8e69-128">Click New.</span></span>
3. <span data-ttu-id="f8e69-129">En el campo Forma de pago, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f8e69-129">In the Method of payment field, type a value.</span></span>
4. <span data-ttu-id="f8e69-130">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f8e69-130">In the Description field, type a value.</span></span>
5. <span data-ttu-id="f8e69-131">El tipo de pago para un método de pago de orden de domiciliación bancaria debe ser Pago electrónico.</span><span class="sxs-lookup"><span data-stu-id="f8e69-131">The payment type for a direct debit mandate method of payment must be Electronic payment.</span></span>
6. <span data-ttu-id="f8e69-132">Seleccione Sí en el campo Requerir orden.</span><span class="sxs-lookup"><span data-stu-id="f8e69-132">Select Yes in the Require mandate field.</span></span>
7. <span data-ttu-id="f8e69-133">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f8e69-133">Close the page.</span></span>

## <a name="add-a-direct-debit-mandate-to-a-customer"></a><span data-ttu-id="f8e69-134">Agregue una orden de domiciliación bancaria a un cliente.</span><span class="sxs-lookup"><span data-stu-id="f8e69-134">Add a direct debit mandate to a customer.</span></span>
1. <span data-ttu-id="f8e69-135">Vaya a Clientes > Clientes > Todos los clientes.</span><span class="sxs-lookup"><span data-stu-id="f8e69-135">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="f8e69-136">Por ejemplo, seleccione US-001.</span><span class="sxs-lookup"><span data-stu-id="f8e69-136">For example, select US-001</span></span>
3. <span data-ttu-id="f8e69-137">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="f8e69-137">Click Edit.</span></span>
4. <span data-ttu-id="f8e69-138">Expanda la sección Valores predeterminados de pago.</span><span class="sxs-lookup"><span data-stu-id="f8e69-138">Expand the Payment defaults section.</span></span>
5. <span data-ttu-id="f8e69-139">En el campo Método de pago, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f8e69-139">In the Method of payment field, enter or select a value.</span></span>
6. <span data-ttu-id="f8e69-140">Expanda la sección Valores predeterminados de pago.</span><span class="sxs-lookup"><span data-stu-id="f8e69-140">Expand the Payment defaults section.</span></span>
7. <span data-ttu-id="f8e69-141">Expanda la sección Órdenes de domiciliación bancaria.</span><span class="sxs-lookup"><span data-stu-id="f8e69-141">Expand the Direct debit mandates section.</span></span>
8. <span data-ttu-id="f8e69-142">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="f8e69-142">Click Add.</span></span>
9. <span data-ttu-id="f8e69-143">En el campo Cuenta bancaria, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f8e69-143">In the Bank account field, enter or select a value.</span></span>
10. <span data-ttu-id="f8e69-144">En el campo Cuenta bancaria de acreedor, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f8e69-144">In the Creditor bank account field, enter or select a value.</span></span>
11. <span data-ttu-id="f8e69-145">Especifique el número de pagos que se prevén para procesar esta orden.</span><span class="sxs-lookup"><span data-stu-id="f8e69-145">Enter the number of payments that you expect to process for this mandate.</span></span>
12. <span data-ttu-id="f8e69-146">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="f8e69-146">Click OK.</span></span>
13. <span data-ttu-id="f8e69-147">Haga clic en Imprimir.</span><span class="sxs-lookup"><span data-stu-id="f8e69-147">Click Print.</span></span>
14. <span data-ttu-id="f8e69-148">Haga clic en Informe de orden.</span><span class="sxs-lookup"><span data-stu-id="f8e69-148">Click Mandate report.</span></span>
15. <span data-ttu-id="f8e69-149">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f8e69-149">Close the page.</span></span>
16. <span data-ttu-id="f8e69-150">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="f8e69-150">Click Edit.</span></span>
17. <span data-ttu-id="f8e69-151">En el campo Fecha de firma, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="f8e69-151">In the Signature date field, enter a date.</span></span>
18. <span data-ttu-id="f8e69-152">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="f8e69-152">Click Yes.</span></span>
19. <span data-ttu-id="f8e69-153">Especifique la ubicación donde se firmó la orden.</span><span class="sxs-lookup"><span data-stu-id="f8e69-153">Enter the location where the mandate was signed.</span></span>
20. <span data-ttu-id="f8e69-154">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="f8e69-154">Click OK.</span></span>
21. <span data-ttu-id="f8e69-155">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f8e69-155">Close the page.</span></span>

## <a name="create-a-free-text-invoice-with-mandate"></a><span data-ttu-id="f8e69-156">Creación de una factura de texto libre con una orden</span><span class="sxs-lookup"><span data-stu-id="f8e69-156">Create a free text invoice with mandate</span></span>
1. <span data-ttu-id="f8e69-157">Vaya a Clientes > Facturas > Todas las facturas de servicios.</span><span class="sxs-lookup"><span data-stu-id="f8e69-157">Go to Accounts receivable > Invoices > All free text invoices.</span></span>
2. <span data-ttu-id="f8e69-158">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="f8e69-158">Click New.</span></span>
3. <span data-ttu-id="f8e69-159">Seleccione el cliente al que haya agregado la orden.</span><span class="sxs-lookup"><span data-stu-id="f8e69-159">Select the customer that you added the mandate to.</span></span>
4. <span data-ttu-id="f8e69-160">En el campo Id. de proyecto, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f8e69-160">In the Direct debit mandate ID field, enter or select a value.</span></span>


