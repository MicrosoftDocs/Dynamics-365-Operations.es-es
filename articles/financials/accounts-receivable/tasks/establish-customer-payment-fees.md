---
title: Establecer cuotas de pago de cliente
description: Creación de cuotas de pago para pagos de clientes.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymFee, CustPaymModeFee, BankAccountTableLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5acb202d46ef39376a01ca592f60926786d11186
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1572983"
---
# <a name="establish-customer-payment-fees"></a><span data-ttu-id="1ea56-103">Establecer cuotas de pago de cliente</span><span class="sxs-lookup"><span data-stu-id="1ea56-103">Establish customer payment fees</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1ea56-104">Creación de cuotas de pago para pagos de clientes.</span><span class="sxs-lookup"><span data-stu-id="1ea56-104">Create payment fees for customer payments.</span></span>

<span data-ttu-id="1ea56-105">Esta tarea usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="1ea56-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="1ea56-106">Vaya a Clientes > Configuración de pagos > Cuota de pago.</span><span class="sxs-lookup"><span data-stu-id="1ea56-106">Go to Accounts receivable > Payments setup > Payment fee.</span></span>
2. <span data-ttu-id="1ea56-107">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="1ea56-107">Click New.</span></span>
3. <span data-ttu-id="1ea56-108">En el campo Id. de cuota, especifique un identificador para la cuota.</span><span class="sxs-lookup"><span data-stu-id="1ea56-108">In the Fee ID field, enter a Fee ID.</span></span>
    * <span data-ttu-id="1ea56-109">El Id. de cuota se muestra en los diarios de pagos, por lo que debe hacerlo descriptivo para comprender qué cuota se está aplicando.</span><span class="sxs-lookup"><span data-stu-id="1ea56-109">The Fee ID displays on payment journals, so make it descriptive to understand what fee is being assessed.</span></span>  
4. <span data-ttu-id="1ea56-110">Escriba un nombre para la cuota en el campo Nombre.</span><span class="sxs-lookup"><span data-stu-id="1ea56-110">In the Name field, enter a fee Name.</span></span>
5. <span data-ttu-id="1ea56-111">En el campo Descripción de cuota, especifique una descripción para la cuota.</span><span class="sxs-lookup"><span data-stu-id="1ea56-111">In the Fee description field, enter a description for the fee.</span></span>
6. <span data-ttu-id="1ea56-112">Seleccione si la cuota se cobrará al cliente o a una cuenta contable.</span><span class="sxs-lookup"><span data-stu-id="1ea56-112">Select whether the fee will be charged to the Customer or a Ledger account.</span></span>
    * <span data-ttu-id="1ea56-113">Si la cuota se aplica al cliente, seleccione Cliente.</span><span class="sxs-lookup"><span data-stu-id="1ea56-113">If the customer is assessed the fee, select Customer.</span></span> <span data-ttu-id="1ea56-114">Si la cuota se aplica a su organización como gasto, seleccione Libro mayor.</span><span class="sxs-lookup"><span data-stu-id="1ea56-114">If the fee will be assess to your organization as an expense, select Ledger.</span></span> <span data-ttu-id="1ea56-115">Para esta tarea, seleccione Cliente.</span><span class="sxs-lookup"><span data-stu-id="1ea56-115">For this task, select Customer.</span></span>  
7. <span data-ttu-id="1ea56-116">Seleccione el tipo de diario que puede usar esta cuota de pago.</span><span class="sxs-lookup"><span data-stu-id="1ea56-116">Select the type of  journal that can use this payment fee.</span></span>
    * <span data-ttu-id="1ea56-117">Si estas cuotas se usan para los pagos de cliente, el tipo de diario será probablemente Cobros.</span><span class="sxs-lookup"><span data-stu-id="1ea56-117">If these fees are used for customer payments, the journal type will likely be Customer payment.</span></span>  
8. <span data-ttu-id="1ea56-118">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="1ea56-118">Click Save.</span></span>
9. <span data-ttu-id="1ea56-119">Haga clic en Configuración de cuota de pago.</span><span class="sxs-lookup"><span data-stu-id="1ea56-119">Click Payment fee setup.</span></span>
    * <span data-ttu-id="1ea56-120">La configuración de la cuota de pago se usa para definir los criterios para cuando se aplique la cuota de pago.</span><span class="sxs-lookup"><span data-stu-id="1ea56-120">The Payment fee setup is used to define the criteria for when the payment fee will be assessed.</span></span>  <span data-ttu-id="1ea56-121">Por ejemplo, puede definir que la cuota se calculará si la cuenta bancaria es USMF OPER, y el método de pago es cheque.</span><span class="sxs-lookup"><span data-stu-id="1ea56-121">For example, you can define that the fee will be calculated if the bank account is USMF OPER, and the method of payment is check.</span></span>  
10. <span data-ttu-id="1ea56-122">Seleccione Tabla, Grupo o Todo para definir en qué cuentas bancarias se aplicará esta cuota.</span><span class="sxs-lookup"><span data-stu-id="1ea56-122">Select either Table, Group or All to define which bank accounts will be assessed this fee.</span></span>
    * <span data-ttu-id="1ea56-123">Si selecciona Todo, se podría aplicar esta cuota en todas las cuentas bancarias.</span><span class="sxs-lookup"><span data-stu-id="1ea56-123">If you select All, all bank accounts could be assessed this fee.</span></span>  <span data-ttu-id="1ea56-124">Si selecciona Tabla, solo se podría aplicar esta cuota a la cuenta bancaria que seleccione.</span><span class="sxs-lookup"><span data-stu-id="1ea56-124">If you select Table, only the bank account you select could be assessed this fee.</span></span> <span data-ttu-id="1ea56-125">Si selecciona Grupo, solo se podría aplicar esta cuota a las cuentas bancarias en el grupo de bancos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="1ea56-125">If you select Group, only the bank accounts in the selected bank group could be assessed this fee.</span></span>  
11. <span data-ttu-id="1ea56-126">Seleccione un grupo de bancos o una cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="1ea56-126">Select either a bank group or a bank account.</span></span>
    * <span data-ttu-id="1ea56-127">Si ha seleccionado Tabla, las búsquedas mostrarán cuentas bancarias.</span><span class="sxs-lookup"><span data-stu-id="1ea56-127">If you selected Table, the lookup will display bank accounts.</span></span> <span data-ttu-id="1ea56-128">Si ha seleccionado Grupo, las búsquedas mostrarán grupos de bancos.</span><span class="sxs-lookup"><span data-stu-id="1ea56-128">If you selected Group, the lookup will display bank groups.</span></span>  
12. <span data-ttu-id="1ea56-129">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="1ea56-129">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="1ea56-130">Seleccione la forma de pago para la que se aplicará esta cuota.</span><span class="sxs-lookup"><span data-stu-id="1ea56-130">Select the Method of payment for which this fee will be assessed.</span></span>
    * <span data-ttu-id="1ea56-131">Por ejemplo, puede aplicar una cuota para sus clientes si envían los pagos como cheques, en lugar de como pago electrónico.</span><span class="sxs-lookup"><span data-stu-id="1ea56-131">For example, you may assess a fee to your customers if they send payments as a check, rather than as an electronic payment.</span></span>  
14. <span data-ttu-id="1ea56-132">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="1ea56-132">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="1ea56-133">Si procede, especifique una divisa de pago.</span><span class="sxs-lookup"><span data-stu-id="1ea56-133">If relevant, enter a payment currency.</span></span>
    * <span data-ttu-id="1ea56-134">La divisa de pago se usa como criterio adicional para saber si se aplicará la cuota.</span><span class="sxs-lookup"><span data-stu-id="1ea56-134">The payment currency is used as an additional criteria for whether the fee will be assessed.</span></span>  <span data-ttu-id="1ea56-135">Por ejemplo, su banco puede cobrar una cuota adicional para los pagos recibidos en divisa USD, ya que normalmente solo tramitan la divisa EUR.</span><span class="sxs-lookup"><span data-stu-id="1ea56-135">For example, your bank may charge an extra fee for payments received in USD currency, since they normally only transact in EUR currency.</span></span>  
16. <span data-ttu-id="1ea56-136">Seleccione si la cuota será un porcentaje, un importe o un intervalo.</span><span class="sxs-lookup"><span data-stu-id="1ea56-136">Select whether the fee will be a percent, amount or interval.</span></span>
17. <span data-ttu-id="1ea56-137">Especifique el porcentaje o el importe de la cuota.</span><span class="sxs-lookup"><span data-stu-id="1ea56-137">Enter either percentage or amount of the fee.</span></span>
    * <span data-ttu-id="1ea56-138">Si el campo Porcentaje / Importe es Porcentaje, el valor especificado aquí será un porcentaje.</span><span class="sxs-lookup"><span data-stu-id="1ea56-138">If the Percentage/Amount field is Percent, then the value enter here will be a percentage.</span></span> <span data-ttu-id="1ea56-139">Si el campo Porcentaje / Importe es Importe, el valor especificado aquí será un importe.</span><span class="sxs-lookup"><span data-stu-id="1ea56-139">If the Percentage/Amount field is Amount, then the value you enter here will be an amount.</span></span> <span data-ttu-id="1ea56-140">Si el campo Porcentaje / Importe es Intervalo, use la ficha Intervalo para definir los niveles.</span><span class="sxs-lookup"><span data-stu-id="1ea56-140">If the Percentage/Amount field is Interval, use the Interval tab to define the tiers.</span></span>  
18. <span data-ttu-id="1ea56-141">En el campo Divisa de cuota, seleccione la divisa de la cuota.</span><span class="sxs-lookup"><span data-stu-id="1ea56-141">In the Fee currency field, select the currency of the fee.</span></span>
    * <span data-ttu-id="1ea56-142">Esta es la divisa en la que se creará la cuota.</span><span class="sxs-lookup"><span data-stu-id="1ea56-142">This is the currency in which the fee will be created.</span></span>  
19. <span data-ttu-id="1ea56-143">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="1ea56-143">Click Save.</span></span>

