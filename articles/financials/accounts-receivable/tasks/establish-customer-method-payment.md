--- 
title: "Establecer método de pago de cliente"
description: "Creación de una forma de pago para pagos de clientes."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 10/26/2017
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
ms.sourcegitcommit: ef3cad6538d9efbd1c1881f4b7d771382d9b1ba8
ms.openlocfilehash: 0ba359567126efaa8274644444a8a261e24c6621
ms.contentlocale: es-es
ms.lasthandoff: 10/26/2017

---
# <a name="establish-customer-method-of-payment"></a><span data-ttu-id="77d63-103">Establecer método de pago de cliente</span><span class="sxs-lookup"><span data-stu-id="77d63-103">Establish customer method of payment</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="77d63-104">Creación de una forma de pago para pagos de clientes.</span><span class="sxs-lookup"><span data-stu-id="77d63-104">Create a method of payment for customer payments.</span></span> <span data-ttu-id="77d63-105">Esta tarea usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="77d63-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="77d63-106">Vaya a Clientes > Configuración de pagos > Formas de pago.</span><span class="sxs-lookup"><span data-stu-id="77d63-106">Go to Accounts receivable > Payments setup > Methods of payment.</span></span>
2. <span data-ttu-id="77d63-107">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="77d63-107">Click New.</span></span>
3. <span data-ttu-id="77d63-108">En el campo Forma de pago, especifique un Id. para la forma de pago.</span><span class="sxs-lookup"><span data-stu-id="77d63-108">In the Method of payment field, enter an ID for the method of payment.</span></span>
    * <span data-ttu-id="77d63-109">El id. de método de pago se muestra en las facturas y los pagos, por lo que debe escribir uno bastante descriptivo para comprender qué tipo de pago se registra y para qué cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="77d63-109">The Method of payment ID is shown on invoices and payments, so make it descriptive enough to understand what type of payment is being recorded, and for what bank account.</span></span>  
4. <span data-ttu-id="77d63-110">En el campo Descripción, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="77d63-110">In the Description field, enter a description.</span></span>
5. <span data-ttu-id="77d63-111">Seleccione qué estado de pago es necesario para que los pagos se registren.</span><span class="sxs-lookup"><span data-stu-id="77d63-111">Select what payment status is required in order for payments to be posted.</span></span>
    * <span data-ttu-id="77d63-112">Al crear un pago de cliente, solo se puede registrar cuando el estado de pago coincide con el estado de pago que se define aquí.</span><span class="sxs-lookup"><span data-stu-id="77d63-112">When creating a customer payment, it can only be posted when the payment status matches the payment status you define here.</span></span>  
6. <span data-ttu-id="77d63-113">Seleccione cómo se deben crear los pagos de los clientes para las facturas.</span><span class="sxs-lookup"><span data-stu-id="77d63-113">Select how customers payments should be created for invoices.</span></span>
    * <span data-ttu-id="77d63-114">Esta opción solo se usa al ejecutar una propuesta de pago.</span><span class="sxs-lookup"><span data-stu-id="77d63-114">This option is only used when running a payment proposal.</span></span> <span data-ttu-id="77d63-115">Se podría usar una propuesta de pago para los pagos del cliente al realizar débitos directos y si se retiran los fondos de las cuentas bancarias de los clientes.</span><span class="sxs-lookup"><span data-stu-id="77d63-115">A payment proposal could be used for customer payments when doing direct debits, and pulling the funds from the customers' bank accounts.</span></span>  
7. <span data-ttu-id="77d63-116">Seleccione el tipo de pago.</span><span class="sxs-lookup"><span data-stu-id="77d63-116">Select the type of payment.</span></span>
    * <span data-ttu-id="77d63-117">El tipo de pago ayudará a determinar si se producirá o no alguna validación en el pago.</span><span class="sxs-lookup"><span data-stu-id="77d63-117">The payment type will help determine whether some validation will occur or not on the payment.</span></span>  
8. <span data-ttu-id="77d63-118">Seleccione en qué tipo de cuenta se registrarán los pagos.</span><span class="sxs-lookup"><span data-stu-id="77d63-118">Select what account type payments will post to.</span></span>
    * <span data-ttu-id="77d63-119">Normalmente, el banco se seleccionará para esta opción.</span><span class="sxs-lookup"><span data-stu-id="77d63-119">Typically, Bank would be selected for this option.</span></span>  
9. <span data-ttu-id="77d63-120">Seleccione la cuenta bancaria en la que se registrará este pago.</span><span class="sxs-lookup"><span data-stu-id="77d63-120">Select the bank account into which this payment will be recorded.</span></span>
10. <span data-ttu-id="77d63-121">Especifique el tipo de transacción bancaria para identificar el tipo de pago usado por su banco.</span><span class="sxs-lookup"><span data-stu-id="77d63-121">Enter the Bank transaction type to identify the type of payment used by your bank.</span></span>
    * <span data-ttu-id="77d63-122">El tipo de transacción bancaria se usa durante el proceso de conciliación bancaria y puede hacer más fácil la conciliación.</span><span class="sxs-lookup"><span data-stu-id="77d63-122">The bank transaction type is used during the bank reconciliation process, and can make reconciliation easier.</span></span>  
11. <span data-ttu-id="77d63-123">Seleccione si este pago se registrará temporalmente en una cuenta puente.</span><span class="sxs-lookup"><span data-stu-id="77d63-123">Select whether this payment will temporarily post to a bridging account.</span></span>
    * <span data-ttu-id="77d63-124">Si desea intentar la hora flotante para que un pago desactive el banco, use la funcionalidad de puente.</span><span class="sxs-lookup"><span data-stu-id="77d63-124">If you want to try the float time for a payment to clear the bank, use the Bridging functionality.</span></span> <span data-ttu-id="77d63-125">El pago se registrará temporalmente en una cuenta contable hasta se compense en el banco, en cuyo momento el pago se moverá a la cuenta bancaria que ha definido aquí.</span><span class="sxs-lookup"><span data-stu-id="77d63-125">The payment will temporarily post to a Ledger account until it clears the bank, at which time the payment will move to the bank account you defined here.</span></span>  
12. <span data-ttu-id="77d63-126">Escriba la cuenta principal utilizada para la contabilización puente.</span><span class="sxs-lookup"><span data-stu-id="77d63-126">Enter the main account used for the bridging posting.</span></span>
    * <span data-ttu-id="77d63-127">Esta es la cuenta principal en la que el pago se registrará temporalmente si usa el puente.</span><span class="sxs-lookup"><span data-stu-id="77d63-127">This is the main account to which the payment will temporarily post if using bridging.</span></span>  
13. <span data-ttu-id="77d63-128">Use la ficha Formato de archivo para definir la configuración de los pagos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="77d63-128">Use the File format tab to define setting for electronic payments.</span></span>
14. <span data-ttu-id="77d63-129">Use la ficha Control de pagos para definir los campos que son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="77d63-129">Use the Payment control tab to define fields that are mandatory.</span></span>
    * <span data-ttu-id="77d63-130">Por ejemplo, si necesita que se depositen todos los pagos con este método de pago, puede elegir esta opción en esta ficha.</span><span class="sxs-lookup"><span data-stu-id="77d63-130">For example, if you require all payments with this method of payment to be deposited, you can choose that option on this tab.</span></span>  
15. <span data-ttu-id="77d63-131">Use la ficha Atributos de pago para definir qué atributos de pago usar para esta forma de pago.</span><span class="sxs-lookup"><span data-stu-id="77d63-131">Use the Payment attributes tab to define which payment attributes you want to use for this method of payment.</span></span>
16. <span data-ttu-id="77d63-132">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="77d63-132">Click Save.</span></span>


