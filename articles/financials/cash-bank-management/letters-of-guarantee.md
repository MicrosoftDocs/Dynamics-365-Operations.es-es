---
title: "Cartas de garantía"
description: "Este artículo proporciona información acerca de las cartas de garantía. En una carta de garantía, un banco acepta pagar una cierta cantidad de dinero a una persona si uno de los clientes del banco se retrasa en un pago o en la obligación a dicha persona."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankLGGuarantee
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 18291
ms.assetid: 5c0b5e37-d51d-4a01-bb37-1882173abb9f
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: c2072c571d584185e867f221c24dc44cdbad1dd6
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---

# <a name="letters-of-guarantee"></a><span data-ttu-id="6f112-104">Cartas de garantía</span><span class="sxs-lookup"><span data-stu-id="6f112-104">Letters of guarantee</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6f112-105">Este artículo proporciona información acerca de las cartas de garantía.</span><span class="sxs-lookup"><span data-stu-id="6f112-105">This article provides information about letters of guarantee.</span></span> <span data-ttu-id="6f112-106">En una carta de garantía, un banco acepta pagar una cierta cantidad de dinero a una persona si uno de los clientes del banco se retrasa en un pago o en la obligación a dicha persona.</span><span class="sxs-lookup"><span data-stu-id="6f112-106">In a letter of guarantee, a bank agrees to pay a specific amount of money to a person if one of the bank's customers defaults on a payment or obligation to that person.</span></span> 

<span data-ttu-id="6f112-107">Una carta de garantía es un contrato mediante el cual un banco (el garante) paga una cierta cantidad de dinero a alguna persona (el beneficiario) si un cliente del banco (la entidad de seguridad) lo establece en un pago o una obligación al beneficiario.</span><span class="sxs-lookup"><span data-stu-id="6f112-107">A letter of guarantee is an agreement by a bank (the guarantor) to pay a set amount of money to some person (the beneficiary) if a bank customer (the principal) defaults on a payment or an obligation to the beneficiary.</span></span> <span data-ttu-id="6f112-108">Las cartas de garantía no son transferibles.</span><span class="sxs-lookup"><span data-stu-id="6f112-108">Letters of guarantee aren't transferable.</span></span> <span data-ttu-id="6f112-109">Solo se aplican al beneficiario nombrado en el acuerdo.</span><span class="sxs-lookup"><span data-stu-id="6f112-109">They apply only to the beneficiary who is named in the agreement.</span></span> <span data-ttu-id="6f112-110">La entidad de seguridad puede aplicar un aumento o una reducción del valor de una colección de la garantía, sujeto a las condiciones del contrato.</span><span class="sxs-lookup"><span data-stu-id="6f112-110">The principal can request an increase or decrease in the value of a letter of guarantee, subject to the terms of the agreement.</span></span> 

<span data-ttu-id="6f112-111">Para liquidar una carta de garantía, el beneficiario debe enviar la carta de garantía original e informar al banco del valor predeterminado de la entidad de seguridad antes de la fecha de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="6f112-111">To liquidate a letter of guarantee, the beneficiary must submit the original letter of guarantee and inform the bank of the principal’s default before the expiration date.</span></span> <span data-ttu-id="6f112-112">El banco paga al importe debido a la cuenta del beneficiario, según las condiciones de la carta de garantía.</span><span class="sxs-lookup"><span data-stu-id="6f112-112">The bank then pays the amount that is due to the beneficiary's account, according to the terms in the letter of guarantee.</span></span> <span data-ttu-id="6f112-113">El banco reserva un porcentaje de pago como margen.</span><span class="sxs-lookup"><span data-stu-id="6f112-113">The bank reserves a percentage of the payment as a margin.</span></span> <span data-ttu-id="6f112-114">El porcentaje se conviene y se especifica en las condiciones del contrato.</span><span class="sxs-lookup"><span data-stu-id="6f112-114">The percentage is agreed upon and specified in the terms of the agreement.</span></span> 

<span data-ttu-id="6f112-115">Puede crear un código para realizar un seguimiento del propósito de una carta de garantía.</span><span class="sxs-lookup"><span data-stu-id="6f112-115">You can create a code to track the purpose of a letter of guarantee.</span></span> <span data-ttu-id="6f112-116">También puede especificar los motivos que se pueden asociar a una carta de garantía cuando se cancela la carta.</span><span class="sxs-lookup"><span data-stu-id="6f112-116">You can also specify the reasons that can be associated with a letter of guarantee when the letter is canceled.</span></span> <span data-ttu-id="6f112-117">Puede ver los códigos de propósito y los motivos del banco en las páginas **Códigos de propósito de pago** y **Motivos de banco**.</span><span class="sxs-lookup"><span data-stu-id="6f112-117">You can view the purpose codes and bank reasons on the **Payment purpose codes** and **Bank reasons** pages.</span></span> 

<span data-ttu-id="6f112-118">Puede usar la página **Carta de garantía** para completar estas tareas:</span><span class="sxs-lookup"><span data-stu-id="6f112-118">You can use the **Letter of guarantee** page to complete these tasks:</span></span>

-   <span data-ttu-id="6f112-119">Crear las entradas del libro mayor correctas y eliminar la entrada manual.</span><span class="sxs-lookup"><span data-stu-id="6f112-119">Create correct ledger entries, and eliminate manual entry.</span></span>
-   <span data-ttu-id="6f112-120">Registrar todas las transacciones monetarias y no monetarias y realizar un seguimiento de los saldos de la carta de garantía.</span><span class="sxs-lookup"><span data-stu-id="6f112-120">Record all monetary and nonmonetary transactions, and track balances of letters of guarantee.</span></span>
-   <span data-ttu-id="6f112-121">Registrar y realizar un seguimiento del vencimiento y el estado de las cartas de garantía.</span><span class="sxs-lookup"><span data-stu-id="6f112-121">Record and track the status and expiration of letters of guarantee.</span></span>
-   <span data-ttu-id="6f112-122">Generar un informe que enumere los bancos que usan cartas de garantía.</span><span class="sxs-lookup"><span data-stu-id="6f112-122">Generate a report that lists the banks that are holding letters of guarantee.</span></span>

<span data-ttu-id="6f112-123">En la tabla siguiente se describen las acciones que se pueden realizar en una carta de garantía.</span><span class="sxs-lookup"><span data-stu-id="6f112-123">The following table describes the actions that you can perform on a letter of guarantee.</span></span>

| <span data-ttu-id="6f112-124">Acción</span><span class="sxs-lookup"><span data-stu-id="6f112-124">Action</span></span>              | <span data-ttu-id="6f112-125">Propósito</span><span class="sxs-lookup"><span data-stu-id="6f112-125">Purpose</span></span>                                                                                                                   |
|---------------------|---------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="6f112-126">Enviar al banco</span><span class="sxs-lookup"><span data-stu-id="6f112-126">Submit to bank</span></span>      | <span data-ttu-id="6f112-127">Mostrar la solicitud de carta de garantía al banco.</span><span class="sxs-lookup"><span data-stu-id="6f112-127">Submit the letter of guarantee request to the bank.</span></span>                                                                       |
| <span data-ttu-id="6f112-128">Recibir del banco</span><span class="sxs-lookup"><span data-stu-id="6f112-128">Receive from bank</span></span>   | <span data-ttu-id="6f112-129">Una vez que el banco acepta la solicitud enviada, recoger la carta de garantía del banco.</span><span class="sxs-lookup"><span data-stu-id="6f112-129">After the bank agrees to the submitted request, collect the letter of guarantee from the bank.</span></span>                            |
| <span data-ttu-id="6f112-130">Darla al beneficiario</span><span class="sxs-lookup"><span data-stu-id="6f112-130">Give to beneficiary</span></span> | <span data-ttu-id="6f112-131">Una vez que reciba la carta de garantía del banco, proporcionar la carta de garantía al beneficiario.</span><span class="sxs-lookup"><span data-stu-id="6f112-131">After you receive the letter of guarantee from the bank, provide the letter of guarantee to the beneficiary.</span></span>              |
| <span data-ttu-id="6f112-132">Aumentar el valor</span><span class="sxs-lookup"><span data-stu-id="6f112-132">Increase value</span></span>      | <span data-ttu-id="6f112-133">Si el beneficiario y la entidad de seguridad están de acuerdo, aumentar el valor monetario.</span><span class="sxs-lookup"><span data-stu-id="6f112-133">If the beneficiary and the principal agree, increase the monetary value.</span></span>                                                  |
| <span data-ttu-id="6f112-134">Reducir el valor</span><span class="sxs-lookup"><span data-stu-id="6f112-134">Decrease value</span></span>      | <span data-ttu-id="6f112-135">Si el beneficiario y la entidad de seguridad están de acuerdo, reducir el valor monetario.</span><span class="sxs-lookup"><span data-stu-id="6f112-135">If the beneficiary and the principal agree, decrease the monetary value.</span></span>                                                  |
| <span data-ttu-id="6f112-136">Ampliar</span><span class="sxs-lookup"><span data-stu-id="6f112-136">Extend</span></span>              | <span data-ttu-id="6f112-137">Una vez que proporcione la carta de garantía al beneficiario, ampliar el período de validez si es necesaria una ampliación.</span><span class="sxs-lookup"><span data-stu-id="6f112-137">After you provide the letter of guarantee to the beneficiary, extend the period of validity, if an extension is required.</span></span> |
| <span data-ttu-id="6f112-138">Cancelar</span><span class="sxs-lookup"><span data-stu-id="6f112-138">Cancel</span></span>              | <span data-ttu-id="6f112-139">Cuando ya no se aplica el propósito para el que la carta de garantía se ha solicitado, cancelar el contrato.</span><span class="sxs-lookup"><span data-stu-id="6f112-139">When the purpose that the letter of guarantee was requested for no longer applies, cancel the agreement.</span></span>                  |
| <span data-ttu-id="6f112-140">Liquidar</span><span class="sxs-lookup"><span data-stu-id="6f112-140">Liquidate</span></span>           | <span data-ttu-id="6f112-141">Cuando el beneficiario muestra la carta de garantía al banco, cobrar la carta de garantía.</span><span class="sxs-lookup"><span data-stu-id="6f112-141">When the beneficiary presents the letter of guarantee to the bank, cash out the letter of guarantee.</span></span>                      |


<span data-ttu-id="6f112-142">Para obtener más información, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="6f112-142">For more information, see the following topics:</span></span>

[<span data-ttu-id="6f112-143">Transacción de carta de garantía</span><span class="sxs-lookup"><span data-stu-id="6f112-143">Letter of guarantee transaction</span></span>](tasks/letter-guarantee-transaction.md)

[<span data-ttu-id="6f112-144">Configuración de créditos bancarios y perfiles de contabilización para cartas de garantía</span><span class="sxs-lookup"><span data-stu-id="6f112-144">Set up bank facilities and posting profiles for letters of guarantee</span></span>](tasks/set-up-bank-facilities-posting-profiles.md)



