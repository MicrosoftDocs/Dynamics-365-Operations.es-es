--- 
title: Registrar un cheque con pago diferido para un proveedor
description: Puede registrar detalles de un cheque posfechado antes de emitir el cheque a un proveedor utilizando un asiento del asiento de diario.
author: kweekley
manager: AnnBe
ms.date: 10/31/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 632b04848cdb6d71e7e7dbd6c6bc710d0577950a
ms.openlocfilehash: 776121532c42fde8b1c3e29b4af0bf833952c0cd
ms.contentlocale: es-es
ms.lasthandoff: 11/01/2017

---
# <a name="register-and-post-a-postdated-check-for-a-vendor"></a><span data-ttu-id="9f600-103">Registrar un cheque con pago diferido para un proveedor</span><span class="sxs-lookup"><span data-stu-id="9f600-103">Register and post a postdated check for a vendor</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9f600-104">Puede registrar detalles de un cheque posfechado antes de emitir el cheque a un proveedor utilizando un asiento del asiento de diario.</span><span class="sxs-lookup"><span data-stu-id="9f600-104">You can register the details of a postdated check before you issue the check to a vendor by using the journal voucher.</span></span> <span data-ttu-id="9f600-105">También puede registrar los cheques con fecha futura y generar transacciones financieras.</span><span class="sxs-lookup"><span data-stu-id="9f600-105">You can also post the postdated check and generate financial transactions.</span></span> <span data-ttu-id="9f600-106">Antes de registrar y enviar un cheque posfechado de un proveedor, complete las siguiente tarea:</span><span class="sxs-lookup"><span data-stu-id="9f600-106">Before you register and post a postdated check from a vendor, complete the following task:</span></span> 

<span data-ttu-id="9f600-107">Establezca cheques posfechados en la página de gestión de efectivo y bancos.</span><span class="sxs-lookup"><span data-stu-id="9f600-107">Set up postdated checks in the Cash and bank management page.</span></span> 



<span data-ttu-id="9f600-108">El rol de esta guía de tareas es Tesorero.</span><span class="sxs-lookup"><span data-stu-id="9f600-108">The role of this task guides is Treasurer.</span></span> <span data-ttu-id="9f600-109">Esta tarea usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="9f600-109">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="9f600-110">Vaya a Proveedores > Pagos > Diario de pagos.</span><span class="sxs-lookup"><span data-stu-id="9f600-110">Go to Accounts payable > Payments > Payment journal</span></span>
2. <span data-ttu-id="9f600-111">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="9f600-111">Click New.</span></span>
3. <span data-ttu-id="9f600-112">En el campo Nombre, escriba "VendPay".</span><span class="sxs-lookup"><span data-stu-id="9f600-112">In the Name field, type 'VendPay'.</span></span>
4. <span data-ttu-id="9f600-113">Haga clic en Líneas.</span><span class="sxs-lookup"><span data-stu-id="9f600-113">Click Lines.</span></span>
5. <span data-ttu-id="9f600-114">En el campo Cuenta, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="9f600-114">In the Account field, specify the desired values.</span></span>
6. <span data-ttu-id="9f600-115">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9f600-115">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="9f600-116">En el campo Débito, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="9f600-116">In the Debit field, enter a number.</span></span>
8. <span data-ttu-id="9f600-117">En el campo Forma de pago, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9f600-117">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="9f600-118">Seleccione la forma de pago del cheque con fecha futura.</span><span class="sxs-lookup"><span data-stu-id="9f600-118">Select the method of payment for the postdated check</span></span>  
9. <span data-ttu-id="9f600-119">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="9f600-119">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="9f600-120">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9f600-120">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="9f600-121">Haga clic en la ficha Cheques con fecha futura.</span><span class="sxs-lookup"><span data-stu-id="9f600-121">Click the Postdated checks tab.</span></span>
12. <span data-ttu-id="9f600-122">En el campo Número de cheque, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="9f600-122">In the Check number field, type a value.</span></span>
    * <span data-ttu-id="9f600-123">Especifique o modifique el número del cheque posfechado.</span><span class="sxs-lookup"><span data-stu-id="9f600-123">Enter or modify the number of the postdated check.</span></span>  
13. <span data-ttu-id="9f600-124">En el campo Nombre del banco emisor, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="9f600-124">In the Issuing bank name field, type a value.</span></span>
    * <span data-ttu-id="9f600-125">Escriba los detalles bancarios para el banco emisor.</span><span class="sxs-lookup"><span data-stu-id="9f600-125">enter the bank details for the issuing bank.</span></span>  
14. <span data-ttu-id="9f600-126">Haga clic en la ficha Lista.</span><span class="sxs-lookup"><span data-stu-id="9f600-126">Click the List tab.</span></span>
15. <span data-ttu-id="9f600-127">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="9f600-127">Click Post.</span></span>
16. <span data-ttu-id="9f600-128">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="9f600-128">Close the page.</span></span>
17. <span data-ttu-id="9f600-129">Haga clic en la ficha Cheques con fecha futura.</span><span class="sxs-lookup"><span data-stu-id="9f600-129">Click the Postdated checks tab.</span></span>


