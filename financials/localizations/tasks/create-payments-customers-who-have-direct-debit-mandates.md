--- 
title: "Crear pagos para un cliente con órdenes de domiciliación bancaria"
description: "Este procedimiento muestra cómo generar un archivo de pago por domiciliación bancaria ISO20022 para un cliente que tiene la domiciliación bancaria configurada y una factura que debe pagarse."
author: mrolecki
manager: AnnBe
ms.date: 10/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: efbe1a14e96497d7cd0fd2273499c66cbed58dbe
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="create-payments-for-a-customer-who-have-direct-debit-mandates"></a><span data-ttu-id="0170d-103">Crear pagos para un cliente con órdenes de domiciliación bancaria</span><span class="sxs-lookup"><span data-stu-id="0170d-103">Create payments for a customer who have direct debit mandates</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0170d-104">Este procedimiento muestra cómo generar un archivo de pago por domiciliación bancaria ISO20022 para un cliente que tiene la domiciliación bancaria configurada y una factura que debe pagarse.</span><span class="sxs-lookup"><span data-stu-id="0170d-104">This procedure shows how to generate an ISO20022 direct debit payment file for a customer who has direct debit configured and an invoice to be paid.</span></span> <span data-ttu-id="0170d-105">Crear y enviar una factura es opcional.</span><span class="sxs-lookup"><span data-stu-id="0170d-105">Creating and posting an invoice is optional.</span></span> <span data-ttu-id="0170d-106">En lugar de tener una factura a pagar puede seleccionar una orden en un diario antes de generar un archivo de pago para admitir una situación de pago por adelantado del cliente.</span><span class="sxs-lookup"><span data-stu-id="0170d-106">Instead of having an invoice to be paid you can select a mandate in a journal prior to generating a payment file, to support a customer prepayment scenario.</span></span>



<span data-ttu-id="0170d-107">La empresa de datos de demostración utilizada para crear este procedimiento es DEMF.</span><span class="sxs-lookup"><span data-stu-id="0170d-107">The demo data company used to create this procedure is DEMF.</span></span>



<span data-ttu-id="0170d-108">Este es el quinto de cinco procedimientos que muestra el proceso de pago del cliente mediante las configuraciones de informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="0170d-108">This is the fifth of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span> <span data-ttu-id="0170d-109">Debe completar todas las tareas previas antes de poder completar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="0170d-109">Before you can complete this task, you must complete the earlier tasks.</span></span> <span data-ttu-id="0170d-110">Primero debe importar las configuraciones de informes electrónicos de pagos de cliente, configurar el método de pago y la información de su empresa y de los clientes.</span><span class="sxs-lookup"><span data-stu-id="0170d-110">You must first import customer payment electronic reporting configurations, configure method of payments, and set up your company and customer information.</span></span> 


## <a name="post-a-free-text-invoice-with-direct-debit-information"></a><span data-ttu-id="0170d-111">Registrar una factura de servicios con información de orden de domiciliación bancaria</span><span class="sxs-lookup"><span data-stu-id="0170d-111">Post a free text invoice with direct debit information</span></span>
1. <span data-ttu-id="0170d-112">Vaya a Clientes > Facturas > Todas las facturas de servicios.</span><span class="sxs-lookup"><span data-stu-id="0170d-112">Go to Accounts receivable > Invoices > All free text invoices.</span></span>
2. <span data-ttu-id="0170d-113">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="0170d-113">Click New.</span></span>
3. <span data-ttu-id="0170d-114">En el campo Cuenta de cliente, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0170d-114">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="0170d-115">Por ejemplo, seleccione DE-010.</span><span class="sxs-lookup"><span data-stu-id="0170d-115">For example, select DE-010.</span></span>  
4. <span data-ttu-id="0170d-116">En el campo Método de pago, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0170d-116">In the Method of payment field, enter or select a value.</span></span>
    * <span data-ttu-id="0170d-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0170d-117">For example.</span></span> <span data-ttu-id="0170d-118">seleccione Electrónico.</span><span class="sxs-lookup"><span data-stu-id="0170d-118">select Electronic.</span></span>  
5. <span data-ttu-id="0170d-119">En el campo Id. de proyecto, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0170d-119">In the Direct debit mandate ID field, enter or select a value.</span></span>
6. <span data-ttu-id="0170d-120">Haga clic en Agregar línea.</span><span class="sxs-lookup"><span data-stu-id="0170d-120">Click Add line.</span></span>
7. <span data-ttu-id="0170d-121">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="0170d-121">In the Description field, type a value.</span></span>
8. <span data-ttu-id="0170d-122">En el campo Cuenta principal, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="0170d-122">In the Main account field, specify the desired values.</span></span>
9. <span data-ttu-id="0170d-123">En el campo Precio unitario, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="0170d-123">In the Unit price field, enter a number.</span></span>
10. <span data-ttu-id="0170d-124">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="0170d-124">Click Post.</span></span>
11. <span data-ttu-id="0170d-125">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="0170d-125">Click OK.</span></span>

## <a name="create-a-payment"></a><span data-ttu-id="0170d-126">Crear un pago</span><span class="sxs-lookup"><span data-stu-id="0170d-126">Create a payment</span></span>
1. <span data-ttu-id="0170d-127">Vaya a Clientes > Pagos > Diario de pagos.</span><span class="sxs-lookup"><span data-stu-id="0170d-127">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="0170d-128">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="0170d-128">Click New.</span></span>
3. <span data-ttu-id="0170d-129">En el campo Nombre, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0170d-129">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="0170d-130">Haga clic en Líneas.</span><span class="sxs-lookup"><span data-stu-id="0170d-130">Click Lines.</span></span>
5. <span data-ttu-id="0170d-131">Haga clic en Propuesta de pago.</span><span class="sxs-lookup"><span data-stu-id="0170d-131">Click Payment proposal.</span></span>
6. <span data-ttu-id="0170d-132">Haga clic en Crear propuesta de pago.</span><span class="sxs-lookup"><span data-stu-id="0170d-132">Click Create payment proposal.</span></span>
7. <span data-ttu-id="0170d-133">Expanda la sección Registros que incluir.</span><span class="sxs-lookup"><span data-stu-id="0170d-133">Expand the Records to include section.</span></span>
8. <span data-ttu-id="0170d-134">Haga clic en Filtro.</span><span class="sxs-lookup"><span data-stu-id="0170d-134">Click Filter.</span></span>
9. <span data-ttu-id="0170d-135">En la lista, seleccione la fila para la tabla Transacciones de cliente y el campo Forma de pago.</span><span class="sxs-lookup"><span data-stu-id="0170d-135">In the list, select the row for the Customer transactions table and the Method of payment field.</span></span>
    * <span data-ttu-id="0170d-136">Puede aplicar cualquier criterio para seleccionar transacciones de cliente para pagar.</span><span class="sxs-lookup"><span data-stu-id="0170d-136">You can apply any criteria for selecting customer transactions to pay.</span></span> <span data-ttu-id="0170d-137">Para este ejemplo, utilice Electrónico como método de pago para filtrar transacciones.</span><span class="sxs-lookup"><span data-stu-id="0170d-137">For this example, use Electronic as a method of payment to filter transactions.</span></span>  
10. <span data-ttu-id="0170d-138">En el campo Criterios, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0170d-138">In the Criteria field, enter or select a value.</span></span>
11. <span data-ttu-id="0170d-139">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="0170d-139">Click OK.</span></span>
12. <span data-ttu-id="0170d-140">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="0170d-140">Click OK.</span></span>
13. <span data-ttu-id="0170d-141">Haga clic en Crear pagos.</span><span class="sxs-lookup"><span data-stu-id="0170d-141">Click Create payments.</span></span>

## <a name="generate-a-payment-file"></a><span data-ttu-id="0170d-142">Generar un archivo de pago</span><span class="sxs-lookup"><span data-stu-id="0170d-142">Generate a payment file</span></span>


