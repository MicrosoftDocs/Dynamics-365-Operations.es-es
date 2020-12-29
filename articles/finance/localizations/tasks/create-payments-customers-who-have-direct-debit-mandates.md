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
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9a4714f1f1b24554684219fc1d766b4b87cff7bb
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447703"
---
# <a name="create-payments-for-a-customer-who-have-direct-debit-mandates"></a><span data-ttu-id="8d59b-103">Crear pagos para un cliente con órdenes de domiciliación bancaria</span><span class="sxs-lookup"><span data-stu-id="8d59b-103">Create payments for a customer who have direct debit mandates</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8d59b-104">Este procedimiento muestra cómo generar un archivo de pago por domiciliación bancaria ISO20022 para un cliente que tiene la domiciliación bancaria configurada y una factura que debe pagarse.</span><span class="sxs-lookup"><span data-stu-id="8d59b-104">This procedure shows how to generate an ISO20022 direct debit payment file for a customer who has direct debit configured and an invoice to be paid.</span></span> <span data-ttu-id="8d59b-105">Crear y enviar una factura es opcional.</span><span class="sxs-lookup"><span data-stu-id="8d59b-105">Creating and posting an invoice is optional.</span></span> <span data-ttu-id="8d59b-106">En lugar de tener una factura a pagar puede seleccionar una orden en un diario antes de generar un archivo de pago para admitir una situación de pago por adelantado del cliente.</span><span class="sxs-lookup"><span data-stu-id="8d59b-106">Instead of having an invoice to be paid you can select a mandate in a journal prior to generating a payment file, to support a customer prepayment scenario.</span></span>



<span data-ttu-id="8d59b-107">La empresa de datos de demostración utilizada para crear este procedimiento es DEMF.</span><span class="sxs-lookup"><span data-stu-id="8d59b-107">The demo data company used to create this procedure is DEMF.</span></span>



<span data-ttu-id="8d59b-108">Este es el quinto de cinco procedimientos que muestra el proceso de pago del cliente mediante las configuraciones de informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="8d59b-108">This is the fifth of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span> <span data-ttu-id="8d59b-109">Debe completar todas las tareas previas antes de poder completar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="8d59b-109">Before you can complete this task, you must complete the earlier tasks.</span></span> <span data-ttu-id="8d59b-110">Primero debe importar las configuraciones de informes electrónicos de pagos de cliente, configurar el método de pago y la información de su empresa y de los clientes.</span><span class="sxs-lookup"><span data-stu-id="8d59b-110">You must first import customer payment electronic reporting configurations, configure method of payments, and set up your company and customer information.</span></span> 


## <a name="post-a-free-text-invoice-with-direct-debit-information"></a><span data-ttu-id="8d59b-111">Registrar una factura de servicios con información de orden de domiciliación bancaria</span><span class="sxs-lookup"><span data-stu-id="8d59b-111">Post a free text invoice with direct debit information</span></span>
1. <span data-ttu-id="8d59b-112">Vaya a Clientes > Facturas > Todas las facturas de servicios.</span><span class="sxs-lookup"><span data-stu-id="8d59b-112">Go to Accounts receivable > Invoices > All free text invoices.</span></span>
2. <span data-ttu-id="8d59b-113">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="8d59b-113">Click New.</span></span>
3. <span data-ttu-id="8d59b-114">En el campo Cuenta de cliente, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8d59b-114">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="8d59b-115">Por ejemplo, seleccione DE-010.</span><span class="sxs-lookup"><span data-stu-id="8d59b-115">For example, select DE-010.</span></span>  
4. <span data-ttu-id="8d59b-116">En el campo Método de pago, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8d59b-116">In the Method of payment field, enter or select a value.</span></span>
    * <span data-ttu-id="8d59b-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8d59b-117">For example.</span></span> <span data-ttu-id="8d59b-118">seleccione Electrónico.</span><span class="sxs-lookup"><span data-stu-id="8d59b-118">select Electronic.</span></span>  
5. <span data-ttu-id="8d59b-119">En el campo Id. de proyecto, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8d59b-119">In the Direct debit mandate ID field, enter or select a value.</span></span>
6. <span data-ttu-id="8d59b-120">Haga clic en Agregar línea.</span><span class="sxs-lookup"><span data-stu-id="8d59b-120">Click Add line.</span></span>
7. <span data-ttu-id="8d59b-121">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="8d59b-121">In the Description field, type a value.</span></span>
8. <span data-ttu-id="8d59b-122">En el campo Cuenta principal, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="8d59b-122">In the Main account field, specify the desired values.</span></span>
9. <span data-ttu-id="8d59b-123">En el campo Precio unitario, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="8d59b-123">In the Unit price field, enter a number.</span></span>
10. <span data-ttu-id="8d59b-124">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="8d59b-124">Click Post.</span></span>
11. <span data-ttu-id="8d59b-125">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="8d59b-125">Click OK.</span></span>

## <a name="create-a-payment"></a><span data-ttu-id="8d59b-126">Crear un pago</span><span class="sxs-lookup"><span data-stu-id="8d59b-126">Create a payment</span></span>
1. <span data-ttu-id="8d59b-127">Vaya a Clientes > Pagos > Diario de pagos.</span><span class="sxs-lookup"><span data-stu-id="8d59b-127">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="8d59b-128">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="8d59b-128">Click New.</span></span>
3. <span data-ttu-id="8d59b-129">En el campo Nombre, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8d59b-129">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="8d59b-130">Haga clic en Líneas.</span><span class="sxs-lookup"><span data-stu-id="8d59b-130">Click Lines.</span></span>
5. <span data-ttu-id="8d59b-131">Haga clic en Propuesta de pago.</span><span class="sxs-lookup"><span data-stu-id="8d59b-131">Click Payment proposal.</span></span>
6. <span data-ttu-id="8d59b-132">Haga clic en Crear propuesta de pago.</span><span class="sxs-lookup"><span data-stu-id="8d59b-132">Click Create payment proposal.</span></span>
7. <span data-ttu-id="8d59b-133">Expanda la sección Registros que incluir.</span><span class="sxs-lookup"><span data-stu-id="8d59b-133">Expand the Records to include section.</span></span>
8. <span data-ttu-id="8d59b-134">Haga clic en Filtro.</span><span class="sxs-lookup"><span data-stu-id="8d59b-134">Click Filter.</span></span>
9. <span data-ttu-id="8d59b-135">En la lista, seleccione la fila para la tabla Transacciones de cliente y el campo Forma de pago.</span><span class="sxs-lookup"><span data-stu-id="8d59b-135">In the list, select the row for the Customer transactions table and the Method of payment field.</span></span>
    * <span data-ttu-id="8d59b-136">Puede aplicar cualquier criterio para seleccionar transacciones de cliente para pagar.</span><span class="sxs-lookup"><span data-stu-id="8d59b-136">You can apply any criteria for selecting customer transactions to pay.</span></span> <span data-ttu-id="8d59b-137">Para este ejemplo, utilice Electrónico como método de pago para filtrar transacciones.</span><span class="sxs-lookup"><span data-stu-id="8d59b-137">For this example, use Electronic as a method of payment to filter transactions.</span></span>  
10. <span data-ttu-id="8d59b-138">En el campo Criterios, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8d59b-138">In the Criteria field, enter or select a value.</span></span>
11. <span data-ttu-id="8d59b-139">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="8d59b-139">Click OK.</span></span>
12. <span data-ttu-id="8d59b-140">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="8d59b-140">Click OK.</span></span>
13. <span data-ttu-id="8d59b-141">Haga clic en Crear pagos.</span><span class="sxs-lookup"><span data-stu-id="8d59b-141">Click Create payments.</span></span>
