---
title: Cheques con fecha futura
description: Este artículo proporciona información acerca de la compatibilidad de los cheques posfechados en Microsoft Dynamics 365 Finance. Los cheques con fecha futura son cheques que se emiten con el fin de realizar y recibir pagos en una fecha futura. Por tanto, no se puede cobrar el cheque hasta la fecha especificada.
author: ShylaThompson
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendPostDatedChecks, CustPostDatedChecks
audience: Application User
ms.reviewer: roschlom
ms.custom: 21741
ms.assetid: 4eb7c7da-1e6b-4d35-9f41-373b66103229
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9e937361802aa1443f3e2ef9f3bb95d3f4966da7
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815797"
---
# <a name="postdated-checks"></a><span data-ttu-id="e00bd-105">Cheques con fecha futura</span><span class="sxs-lookup"><span data-stu-id="e00bd-105">Postdated checks</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e00bd-106">Este artículo proporciona información acerca de la compatibilidad de los cheques posfechados.</span><span class="sxs-lookup"><span data-stu-id="e00bd-106">This article provides information about support for postdated checks.</span></span> <span data-ttu-id="e00bd-107">Los cheques con fecha futura son cheques que se emiten con el fin de realizar y recibir pagos en una fecha futura.</span><span class="sxs-lookup"><span data-stu-id="e00bd-107">Postdated checks are checks that are issued to make and receive payments on a future date.</span></span> <span data-ttu-id="e00bd-108">Por tanto, no se puede cobrar el cheque hasta la fecha especificada.</span><span class="sxs-lookup"><span data-stu-id="e00bd-108">Therefore, the check can't be cashed until the specified date.</span></span>

<span data-ttu-id="e00bd-109">Dynamics 365 Finance admite el ciclo de gestión completo para los cheques posfechados tanto en Clientes como en Proveedores, como se muestra en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="e00bd-109">Dynamics 365 Finance supports the full management cycle for postdated checks in both Accounts receivable and Accounts payable, as shown in the following table.</span></span>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e00bd-110">Situación</span><span class="sxs-lookup"><span data-stu-id="e00bd-110">Scenario</span></span></th>
<th><span data-ttu-id="e00bd-111">Detalles</span><span class="sxs-lookup"><span data-stu-id="e00bd-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="e00bd-112">Configuración de cheques con pago diferido</span><span class="sxs-lookup"><span data-stu-id="e00bd-112">Set up postdated checks</span></span></td>
<td><span data-ttu-id="e00bd-113">Debe configurar un nuevo método de pago y especifica la rutina de pago para las cuentas de compensación para los cheques emitidos, los cheques recibidos y la retención de impuestos.</span><span class="sxs-lookup"><span data-stu-id="e00bd-113">You must set up a new payment method, and specify the payment routine for clearing accounts for issued checks, received checks, and withholding tax.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e00bd-114">Registrar un cheque con pago diferido para un proveedor</span><span class="sxs-lookup"><span data-stu-id="e00bd-114">Register and post a postdated check for a vendor</span></span></td>
<td><span data-ttu-id="e00bd-115">Registrar los detalles de un cheque posfechado que emite a un proveedor.</span><span class="sxs-lookup"><span data-stu-id="e00bd-115">Register the details of a postdated check that you issue to a vendor.</span></span> <span data-ttu-id="e00bd-116">Cuando se registra el pago, se reconoce el pasivo del proveedor pero la cuenta bancaria no es crédito todavía.</span><span class="sxs-lookup"><span data-stu-id="e00bd-116">When the payment is posted, the vendor liability is recognized, but the bank account isn’t yet credit.</span></span> <span data-ttu-id="e00bd-117">En su lugar, se usa una cuenta de compensación para este propósito.</span><span class="sxs-lookup"><span data-stu-id="e00bd-117">Instead, a clearing account is used for this purpose.</span></span> </td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e00bd-118">Registro de un cheque con fecha futura para un cliente</span><span class="sxs-lookup"><span data-stu-id="e00bd-118">Register and post a postdated check for a customer</span></span></td>
<td><span data-ttu-id="e00bd-119">Registrar los detalles de un cheque con fecha futura que recibe de un cliente.</span><span class="sxs-lookup"><span data-stu-id="e00bd-119">Register the details of a postdated check that you receive from a customer.</span></span> <span data-ttu-id="e00bd-120">Cuando se registra el pago, la cuenta por cobrar del cliente es crédito pero la cuenta bancaria no es débito todavía.</span><span class="sxs-lookup"><span data-stu-id="e00bd-120">When the payment is posted, the customer receivable is credit, but the bank account isn’t yet debit.</span></span> <span data-ttu-id="e00bd-121">En su lugar, se usa una cuenta de compensación para este propósito.</span><span class="sxs-lookup"><span data-stu-id="e00bd-121">Instead, a clearing account is used for this purpose.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e00bd-122">Registrar un cheque con pago diferido de sustitución para un proveedor o cliente.</span><span class="sxs-lookup"><span data-stu-id="e00bd-122">Register and post a replacement postdated check for a customer or a vendor</span></span></td>
<td>
<span data-ttu-id="e00bd-123">Si ha perdido o dañado el cheque original a un proveedor o de un cliente, puede emitir un cheque posfechado de sustitución al proveedor.</span><span class="sxs-lookup"><span data-stu-id="e00bd-123">If your original check to a vendor or from a customer is lost or damaged, you can issue a replacement postdated check.</span></span> <span data-ttu-id="e00bd-124">Al registrar los detalles del cheque, proporcione una referencia del cheque original e indique que el nuevo cheque es una sustitución del original.</span><span class="sxs-lookup"><span data-stu-id="e00bd-124">When you register the check details, provide a reference to the original check, and indicate that the new check is a replacement for the original.</span></span> <span data-ttu-id="e00bd-125">También puede registrar el cheque de sustitución.</span><span class="sxs-lookup"><span data-stu-id="e00bd-125">You can also post the replacement check.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e00bd-126">Transferir un cheque con pago diferido de un cliente a un proveedor</span><span class="sxs-lookup"><span data-stu-id="e00bd-126">Transfer a customer postdated check to a vendor</span></span></td>
<td><span data-ttu-id="e00bd-127">Cuando reciba un cheque posfechado de un cliente, puede transferir ese cheque a un proveedor como pago.</span><span class="sxs-lookup"><span data-stu-id="e00bd-127">When you receive a postdated check from a customer, you can transfer that check to a vendor as a payment.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e00bd-128">Liquidar un cheque con pago diferido para un cliente o proveedor</span><span class="sxs-lookup"><span data-stu-id="e00bd-128">Settle a postdated check for a customer or a vendor</span></span></td>
<td><span data-ttu-id="e00bd-129">Liquidar un cheque posfechado registrado en una cuenta puente para un cliente o proveedor cuando el cheque finalmente madura.</span><span class="sxs-lookup"><span data-stu-id="e00bd-129">Settle a postdated check that is posted to a bridging account for a customer or a vendor when the check finally matures.</span></span> <span data-ttu-id="e00bd-130">Cuando se liquida el cheque, el banco es finalmente débito o crédito frente a la cuenta de compensación que se usó anterior.</span><span class="sxs-lookup"><span data-stu-id="e00bd-130">When the check is settled, the bank is finally debit or credit against the clearing account that was used earlier.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e00bd-131">Cancelar un cheque con pago diferido para un proveedor</span><span class="sxs-lookup"><span data-stu-id="e00bd-131">Cancel a postdated check for a vendor</span></span></td>
<td><span data-ttu-id="e00bd-132">Puede cancelar un cheque posfechado registrado en las situaciones siguientes: - El banco ha devuelto el cheque.</span><span class="sxs-lookup"><span data-stu-id="e00bd-132">You can cancel a posted postdated check in these situations: - The check is returned by the bank.</span></span>
<span data-ttu-id="e00bd-133">- El cheque se ha aplicado a una factura incorrecta.</span><span class="sxs-lookup"><span data-stu-id="e00bd-133">- The check is applied to an incorrect invoice.</span></span>
<span data-ttu-id="e00bd-134">- Se debe hacer un pago en efectivo en relación al cheque.</span><span class="sxs-lookup"><span data-stu-id="e00bd-134">- A cash payment is made against the check.</span></span>
  </td>
  </tr>
  <tr class="even">
  <td><span data-ttu-id="e00bd-135">Detener un pago de un cheque con pago diferido</span><span class="sxs-lookup"><span data-stu-id="e00bd-135">Stop payment for a postdated check</span></span></td>
  <td><span data-ttu-id="e00bd-136">Puede detener el pago de cheque posfechado que se emitió a un proveedor por motivos como fondos insuficientes, cambio de las condiciones del contrato con el proveedor, suministro de mercancías defectuosas por proveedor o devolución de mercancías al proveedor.</span><span class="sxs-lookup"><span data-stu-id="e00bd-136">You can stop payment on a postdated check that was issued to a vendor, for reasons such as not sufficient funds, changes in the terms of the agreement with the vendor, supply of defective goods by the vendor, or return of goods to the vendor.</span></span> <span data-ttu-id="e00bd-137">Puede detener el pago solo en los cheques que no ha compensado.</span><span class="sxs-lookup"><span data-stu-id="e00bd-137">You can stop payment only on checks that haven’t cleared.</span></span></td>
  </tr>
  </tbody>
  </table>



<span data-ttu-id="e00bd-138">Para obtener más información, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="e00bd-138">For more information, see the following topics:</span></span>

[<span data-ttu-id="e00bd-139">Configuración de cheques con pago diferido</span><span class="sxs-lookup"><span data-stu-id="e00bd-139">Set up postdated checks</span></span>](tasks/set-up-postdated-checks.md)

[<span data-ttu-id="e00bd-140">Registrar un cheque con pago diferido para un cliente</span><span class="sxs-lookup"><span data-stu-id="e00bd-140">Register and post a postdated check for a customer</span></span>](tasks/register-post-postdated-check-customer.md)

[<span data-ttu-id="e00bd-141">Liquidar un cheque con pago diferido de un cliente</span><span class="sxs-lookup"><span data-stu-id="e00bd-141">Settle a postdated check from a customer</span></span>](tasks/settle-postdated-check-customer.md)

[<span data-ttu-id="e00bd-142">Registrar un cheque con pago diferido para un proveedor</span><span class="sxs-lookup"><span data-stu-id="e00bd-142">Register and post a postdated check for a vendor</span></span>](tasks/register-post-postdated-check-vendor.md) 

[<span data-ttu-id="e00bd-143">Liquidar un cheque con pago diferido para un proveedor</span><span class="sxs-lookup"><span data-stu-id="e00bd-143">Settle a postdated check for a vendor</span></span>](tasks/settle-postdated-check-vendor.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]