---
title: Configuración de cheques con pago diferido
description: En este tema se explica cómo especificar si desea registrar entradas de diario para cheques con fecha futura y qué diarios de registro desea usar para liquidar entradas y pagos de proveedor.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BankParameters, VendPaymMode, CustPaymMode
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d0d4afd74f9a0f9018629fa92ab6595bfa94f973
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026214"
---
# <a name="set-up-postdated-checks"></a><span data-ttu-id="eb75b-103">Configuración de cheques con pago diferido</span><span class="sxs-lookup"><span data-stu-id="eb75b-103">Set up postdated checks</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="eb75b-104">En este tema se explica cómo especificar si desea registrar entradas de diario para cheques con fecha futura y qué diarios de registro desea usar para liquidar entradas y pagos de proveedor.</span><span class="sxs-lookup"><span data-stu-id="eb75b-104">This topic explains how to specify whether to post journal entries for postdated checks and which posting journals to use for clearing entries and vendor payments.</span></span> <span data-ttu-id="eb75b-105">También puede especificar cuentas de compensación para cheques emitidos, cheques recibidos y retención de impuestos.</span><span class="sxs-lookup"><span data-stu-id="eb75b-105">You can also specify clearing accounts for issued checks, received checks, and withholding tax.</span></span> <span data-ttu-id="eb75b-106">Cheques con fecha futura que se emiten con el fin de realizar y recibir pagos en una fecha futura.</span><span class="sxs-lookup"><span data-stu-id="eb75b-106">Postdated checks that are issued to make and receive payments on a future date.</span></span> <span data-ttu-id="eb75b-107">Puede especificar si el cheque debe reflejarse en los libros financieros antes de la fecha de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="eb75b-107">You can specify whether the check must be reflected in the accounting books before its maturity date.</span></span>



<span data-ttu-id="eb75b-108">El rol de este procedimiento es Tesorero.</span><span class="sxs-lookup"><span data-stu-id="eb75b-108">The role of this procedure is Treasurer.</span></span> <span data-ttu-id="eb75b-109">Este procedimiento usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="eb75b-109">This procedure uses the USMF demo company.</span></span>


## <a name="set-up-postdated-checks"></a><span data-ttu-id="eb75b-110">Configuración de cheques con pago diferido</span><span class="sxs-lookup"><span data-stu-id="eb75b-110">Set up postdated checks</span></span>
1. <span data-ttu-id="eb75b-111">Vaya a Gestión de efectivo y bancos > Configurar > Parámetros de gestión de efectivo y bancos.</span><span class="sxs-lookup"><span data-stu-id="eb75b-111">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>
2. <span data-ttu-id="eb75b-112">Haga clic en la ficha Cheques con fecha futura.</span><span class="sxs-lookup"><span data-stu-id="eb75b-112">Click the Postdated checks tab.</span></span>
3. <span data-ttu-id="eb75b-113">Active o desactive la casilla Habilitar cheques con fecha futura.</span><span class="sxs-lookup"><span data-stu-id="eb75b-113">Select or clear the Enable postdated checks check box.</span></span>
4. <span data-ttu-id="eb75b-114">Active o desactive las entradas del diario de registro para la casilla de cheques con fecha futura.</span><span class="sxs-lookup"><span data-stu-id="eb75b-114">Select or clear the Post journal entries for postdated checks check box.</span></span>
5. <span data-ttu-id="eb75b-115">En el campo Cuenta de compensación para cheques emitidos, especifique los valores que le interesen.</span><span class="sxs-lookup"><span data-stu-id="eb75b-115">In the Clearing account for issued checks field, specify the desired values.</span></span>
6. <span data-ttu-id="eb75b-116">En el campo Cuenta de compensación para cheques recibidos, especifique los valores que le interesen.</span><span class="sxs-lookup"><span data-stu-id="eb75b-116">In the Clearing account for received checks field, specify the desired values.</span></span>
7. <span data-ttu-id="eb75b-117">En el campo Diario general para entidades de compensación, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="eb75b-117">In the General journal for clearing entries field, type a value.</span></span>
8. <span data-ttu-id="eb75b-118">En el campo Transferir cheques con fecha futura a este diario de pagos de proveedor, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="eb75b-118">In the Transfer postdated checks to this vendor payment journal field, type a value.</span></span>
9. <span data-ttu-id="eb75b-119">En el campo Cuenta de compensación de retención de impuestos, especifique los valores que le interesen.</span><span class="sxs-lookup"><span data-stu-id="eb75b-119">In the Withholding tax clearing account field, specify the desired values.</span></span>
10. <span data-ttu-id="eb75b-120">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="eb75b-120">Click Save.</span></span>
11. <span data-ttu-id="eb75b-121">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="eb75b-121">Close the page.</span></span>
12. <span data-ttu-id="eb75b-122">Vaya a Proveedores > Configuración de pagos > Formas de pago.</span><span class="sxs-lookup"><span data-stu-id="eb75b-122">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
13. <span data-ttu-id="eb75b-123">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="eb75b-123">Click New.</span></span>
14. <span data-ttu-id="eb75b-124">En el campo Forma de pago, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="eb75b-124">In the Method of payment field, type a value.</span></span>
15. <span data-ttu-id="eb75b-125">Seleccione la opción Registro de compensación de cheques con fecha futura para indicar que el importe del cheque se registra en una cuenta de compensación.</span><span class="sxs-lookup"><span data-stu-id="eb75b-125">Select the Postdated check clearing posting option to indicate that the check amount is posted to a clearing account.</span></span>
16. <span data-ttu-id="eb75b-126">En el campo Tipo de cuenta, seleccione Banco.</span><span class="sxs-lookup"><span data-stu-id="eb75b-126">In the Account type field, select 'Bank'.</span></span>
    * <span data-ttu-id="eb75b-127">La cuenta de contrapartida del método de pago será un banco.</span><span class="sxs-lookup"><span data-stu-id="eb75b-127">The offset account of the payment method will be a bank.</span></span>  
17. <span data-ttu-id="eb75b-128">En el campo Cuenta de pago, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="eb75b-128">In the Payment account field, specify the desired values.</span></span>
    * <span data-ttu-id="eb75b-129">Seleccione la cuenta bancaria que se utiliza para deducir el importe de la factura.</span><span class="sxs-lookup"><span data-stu-id="eb75b-129">Select the bank account that is used to deduct the invoice amount.</span></span>  
18. <span data-ttu-id="eb75b-130">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="eb75b-130">Click Save.</span></span>
19. <span data-ttu-id="eb75b-131">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="eb75b-131">Close the page.</span></span>
> [!NOTE]
> <span data-ttu-id="eb75b-132">Para poder registrar un cheque con pago diferido en una cuenta bancaria cuando la fecha de la sesión es mayor o igual que la fecha de vencimiento, debe habilitar la función **Validación de la fecha de vencimiento del registro del diario de pagos con cheques con pago diferido en la cuenta bancaria**.</span><span class="sxs-lookup"><span data-stu-id="eb75b-132">To be able to post a postdated check to a bank account when the session date is greater than or equal to the maturity date, you must enable the feature **Maturity date validation of posting payment journal with postdated checks to bank account**.</span></span> <span data-ttu-id="eb75b-133">Esta función le permite registrar diarios de pago para proveedores o clientes con cheques con pago diferido cuando la fecha de la sesión es mayor o igual que la fecha de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="eb75b-133">This feature allows you to post payment journals for vendors or customers with postdated checks, when the session date is greater than or equal to the maturity date.</span></span>
> 
> <span data-ttu-id="eb75b-134">Al configurar la **Forma de pago** (**Proveedores > Configuración de pagos > Métodos de pago**), no rellene **Cuenta puente**.</span><span class="sxs-lookup"><span data-stu-id="eb75b-134">When setting the **Method of payment** (**Accounts payable > Payment setup > Methods of payment**), do not fill in **Bridging account**.</span></span> <span data-ttu-id="eb75b-135">En este caso, la cuenta de contrapartida se completa con la cuenta bancaria, que se configura en la **Forma de pago**.</span><span class="sxs-lookup"><span data-stu-id="eb75b-135">In this case, the offset account is filled in with the bank account, which is set up in the **Method of payment**.</span></span>
>  
> <span data-ttu-id="eb75b-136">Cuando la función está habilitada y la fecha de la sesión es menor que la fecha de vencimiento, se muestra el siguiente mensaje de error al registrar un diario de pagos, "La fecha de vencimiento debe ser menor o igual a la fecha de la sesión si el tipo de cuenta de contrapartida es Banco".</span><span class="sxs-lookup"><span data-stu-id="eb75b-136">When the feature is enabled and the session date is less than the maturity date, the following error message is displayed when posting a payment journal, "Maturity date must be less or equal to the session date if offset account type is Bank".</span></span> <span data-ttu-id="eb75b-137">Si la función no está habilitada, puede registrar un diario de pagos con un cheque con pago diferido cuando la fecha de la sesión es menor que la fecha de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="eb75b-137">If the feature is not enabled, you can post a payment journal with a postdated check when the session date is less than the maturity date.</span></span>    

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
