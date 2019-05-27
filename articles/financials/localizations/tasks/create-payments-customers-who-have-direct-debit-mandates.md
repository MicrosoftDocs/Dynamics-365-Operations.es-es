---
title: Crear pagos para un cliente con órdenes de domiciliación bancaria
description: Este procedimiento muestra cómo generar un archivo de pago por domiciliación bancaria ISO20022 para un cliente que tiene la domiciliación bancaria configurada y una factura que debe pagarse.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustFreeInvoice, CustTableLookup, CustPostInvoiceJob, LedgerJournalTable, LedgerJournalTransCustPaym, SysQueryForm, CustPaymProposalEdit, BankAccountTableLookUp
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6781ac38fff6344bfc9546c3ffd2253fb3ef712c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1570039"
---
# <a name="create-payments-for-a-customer-who-have-direct-debit-mandates"></a><span data-ttu-id="50996-103">Crear pagos para un cliente con órdenes de domiciliación bancaria</span><span class="sxs-lookup"><span data-stu-id="50996-103">Create payments for a customer who have direct debit mandates</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="50996-104">Este procedimiento muestra cómo generar un archivo de pago por domiciliación bancaria ISO20022 para un cliente que tiene la domiciliación bancaria configurada y una factura que debe pagarse.</span><span class="sxs-lookup"><span data-stu-id="50996-104">This procedure shows how to generate an ISO20022 direct debit payment file for a customer who has direct debit configured and an invoice to be paid.</span></span> <span data-ttu-id="50996-105">Crear y enviar una factura es opcional.</span><span class="sxs-lookup"><span data-stu-id="50996-105">Creating and posting an invoice is optional.</span></span> <span data-ttu-id="50996-106">En lugar de tener una factura a pagar puede seleccionar una orden en un diario antes de generar un archivo de pago para admitir una situación de pago por adelantado del cliente.</span><span class="sxs-lookup"><span data-stu-id="50996-106">Instead of having an invoice to be paid you can select a mandate in a journal prior to generating a payment file, to support a customer prepayment scenario.</span></span>



<span data-ttu-id="50996-107">La empresa de datos de demostración utilizada para crear este procedimiento es DEMF.</span><span class="sxs-lookup"><span data-stu-id="50996-107">The demo data company used to create this procedure is DEMF.</span></span>



<span data-ttu-id="50996-108">Este es el quinto de cinco procedimientos que muestra el proceso de pago del cliente mediante las configuraciones de informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="50996-108">This is the fifth of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span> <span data-ttu-id="50996-109">Debe completar todas las tareas previas antes de poder completar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="50996-109">Before you can complete this task, you must complete the earlier tasks.</span></span> <span data-ttu-id="50996-110">Primero debe importar las configuraciones de informes electrónicos de pagos de cliente, configurar el método de pago y la información de su empresa y de los clientes.</span><span class="sxs-lookup"><span data-stu-id="50996-110">You must first import customer payment electronic reporting configurations, configure method of payments, and set up your company and customer information.</span></span> 


## <a name="post-a-free-text-invoice-with-direct-debit-information"></a><span data-ttu-id="50996-111">Registrar una factura de servicios con información de orden de domiciliación bancaria</span><span class="sxs-lookup"><span data-stu-id="50996-111">Post a free text invoice with direct debit information</span></span>
1. <span data-ttu-id="50996-112">Vaya a Clientes > Facturas > Todas las facturas de servicios.</span><span class="sxs-lookup"><span data-stu-id="50996-112">Go to Accounts receivable > Invoices > All free text invoices.</span></span>
2. <span data-ttu-id="50996-113">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="50996-113">Click New.</span></span>
3. <span data-ttu-id="50996-114">En el campo Cuenta de cliente, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="50996-114">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="50996-115">Por ejemplo, seleccione DE-010.</span><span class="sxs-lookup"><span data-stu-id="50996-115">For example, select DE-010.</span></span>  
4. <span data-ttu-id="50996-116">En el campo Método de pago, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="50996-116">In the Method of payment field, enter or select a value.</span></span>
    * <span data-ttu-id="50996-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="50996-117">For example.</span></span> <span data-ttu-id="50996-118">seleccione Electrónico.</span><span class="sxs-lookup"><span data-stu-id="50996-118">select Electronic.</span></span>  
5. <span data-ttu-id="50996-119">En el campo Id. de proyecto, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="50996-119">In the Direct debit mandate ID field, enter or select a value.</span></span>
6. <span data-ttu-id="50996-120">Haga clic en Agregar línea.</span><span class="sxs-lookup"><span data-stu-id="50996-120">Click Add line.</span></span>
7. <span data-ttu-id="50996-121">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="50996-121">In the Description field, type a value.</span></span>
8. <span data-ttu-id="50996-122">En el campo Cuenta principal, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="50996-122">In the Main account field, specify the desired values.</span></span>
9. <span data-ttu-id="50996-123">En el campo Precio unitario, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="50996-123">In the Unit price field, enter a number.</span></span>
10. <span data-ttu-id="50996-124">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="50996-124">Click Post.</span></span>
11. <span data-ttu-id="50996-125">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="50996-125">Click OK.</span></span>

## <a name="create-a-payment"></a><span data-ttu-id="50996-126">Crear un pago</span><span class="sxs-lookup"><span data-stu-id="50996-126">Create a payment</span></span>
1. <span data-ttu-id="50996-127">Vaya a Clientes > Pagos > Diario de pagos.</span><span class="sxs-lookup"><span data-stu-id="50996-127">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="50996-128">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="50996-128">Click New.</span></span>
3. <span data-ttu-id="50996-129">En el campo Nombre, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="50996-129">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="50996-130">Haga clic en Líneas.</span><span class="sxs-lookup"><span data-stu-id="50996-130">Click Lines.</span></span>
5. <span data-ttu-id="50996-131">Haga clic en Propuesta de pago.</span><span class="sxs-lookup"><span data-stu-id="50996-131">Click Payment proposal.</span></span>
6. <span data-ttu-id="50996-132">Haga clic en Crear propuesta de pago.</span><span class="sxs-lookup"><span data-stu-id="50996-132">Click Create payment proposal.</span></span>
7. <span data-ttu-id="50996-133">Expanda la sección Registros que incluir.</span><span class="sxs-lookup"><span data-stu-id="50996-133">Expand the Records to include section.</span></span>
8. <span data-ttu-id="50996-134">Haga clic en Filtro.</span><span class="sxs-lookup"><span data-stu-id="50996-134">Click Filter.</span></span>
9. <span data-ttu-id="50996-135">En la lista, seleccione la fila para la tabla Transacciones de cliente y el campo Forma de pago.</span><span class="sxs-lookup"><span data-stu-id="50996-135">In the list, select the row for the Customer transactions table and the Method of payment field.</span></span>
    * <span data-ttu-id="50996-136">Puede aplicar cualquier criterio para seleccionar transacciones de cliente para pagar.</span><span class="sxs-lookup"><span data-stu-id="50996-136">You can apply any criteria for selecting customer transactions to pay.</span></span> <span data-ttu-id="50996-137">Para este ejemplo, utilice Electrónico como método de pago para filtrar transacciones.</span><span class="sxs-lookup"><span data-stu-id="50996-137">For this example, use Electronic as a method of payment to filter transactions.</span></span>  
10. <span data-ttu-id="50996-138">En el campo Criterios, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="50996-138">In the Criteria field, enter or select a value.</span></span>
11. <span data-ttu-id="50996-139">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="50996-139">Click OK.</span></span>
12. <span data-ttu-id="50996-140">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="50996-140">Click OK.</span></span>
13. <span data-ttu-id="50996-141">Haga clic en Crear pagos.</span><span class="sxs-lookup"><span data-stu-id="50996-141">Click Create payments.</span></span>

## <a name="generate-a-payment-file"></a><span data-ttu-id="50996-142">Generar un archivo de pago</span><span class="sxs-lookup"><span data-stu-id="50996-142">Generate a payment file</span></span>

