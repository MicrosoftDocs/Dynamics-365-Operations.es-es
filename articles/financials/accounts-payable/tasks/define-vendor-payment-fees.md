---
title: Definir cuotas de pagos a proveedores
description: Configuración de cuotas de pago para proveedores.
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPaymFee, VendPaymModeFee, BankAccountTableLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4e9e723ec54b6f34082c422ce4c8e48bf52d2e3e
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835480"
---
# <a name="define-vendor-payment-fees"></a><span data-ttu-id="aae48-103">Definir cuotas de pagos a proveedores</span><span class="sxs-lookup"><span data-stu-id="aae48-103">Define vendor payment fees</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="aae48-104">Configuración de cuotas de pago para proveedores.</span><span class="sxs-lookup"><span data-stu-id="aae48-104">Set up vendor payment fees.</span></span> <span data-ttu-id="aae48-105">Esta tarea usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="aae48-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="aae48-106">Vaya a Proveedores > Configuración de pagos > Cuota de pago.</span><span class="sxs-lookup"><span data-stu-id="aae48-106">Go to Accounts payable > Payment setup > Payment fee.</span></span>
2. <span data-ttu-id="aae48-107">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="aae48-107">Click New.</span></span>
3. <span data-ttu-id="aae48-108">En el campo Id. de cuota, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="aae48-108">In the Fee ID field, type a value.</span></span>
    * <span data-ttu-id="aae48-109">El identificador de cuota debe describir cuando se usará esta cuota, como "Cuota_EFT".</span><span class="sxs-lookup"><span data-stu-id="aae48-109">The Fee ID should describe when this fee will be used, such as "EFT_Fee".</span></span>  
4. <span data-ttu-id="aae48-110">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="aae48-110">In the Name field, type a value.</span></span>
5. <span data-ttu-id="aae48-111">En el campo Descripción de cuota, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="aae48-111">In the Fee description field, type a value.</span></span>
    * <span data-ttu-id="aae48-112">Agregue una descripción para proporcionar más detalles sobre cuándo se aplica la cuota.</span><span class="sxs-lookup"><span data-stu-id="aae48-112">Add a description to provide more detail on when the fee is assessed.</span></span>  
6. <span data-ttu-id="aae48-113">En el campo Cargo, seleccione Proveedor o Libro mayor.</span><span class="sxs-lookup"><span data-stu-id="aae48-113">In the Charge field, select either Vendor or Ledger.</span></span>
    * <span data-ttu-id="aae48-114">Libro mayor se usa cuando la cuota se cobrará a su organización.</span><span class="sxs-lookup"><span data-stu-id="aae48-114">Ledger is used when the fee will be expensed to your organization.</span></span>  <span data-ttu-id="aae48-115">Proveedor se usa cuando la cuota se aplicará al proveedor.</span><span class="sxs-lookup"><span data-stu-id="aae48-115">Vendor is used when the fee will be assessed to the vendor.</span></span>  
7. <span data-ttu-id="aae48-116">Especifique una cuenta principal donde contabilizar como gasto la cuota.</span><span class="sxs-lookup"><span data-stu-id="aae48-116">Enter a main account for where the fee will be expensed.</span></span>
    * <span data-ttu-id="aae48-117">Esta opción solo está disponible si se ha seleccionado Libro mayor como opción Cargo.</span><span class="sxs-lookup"><span data-stu-id="aae48-117">This option is only available when selecting Ledger as the Charge option.</span></span>  
8. <span data-ttu-id="aae48-118">Seleccione el diario en el que se puede usar esta cuota.</span><span class="sxs-lookup"><span data-stu-id="aae48-118">Select the journal on which this fee can be used.</span></span> 
    * <span data-ttu-id="aae48-119">Para una cuota de pago de proveedor, seleccionaría el diario Pagos del proveedor.</span><span class="sxs-lookup"><span data-stu-id="aae48-119">For a vendor payment fee, you would select the journal 'Vendor disbursement.'</span></span>  
9. <span data-ttu-id="aae48-120">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="aae48-120">Click Save.</span></span>
10. <span data-ttu-id="aae48-121">Haga clic en Configuración de cuota de pago.</span><span class="sxs-lookup"><span data-stu-id="aae48-121">Click Payment fee setup.</span></span>
    * <span data-ttu-id="aae48-122">Continúe con la configuración de la cuota de pago para definir cuándo debe incluirse la cuota de manera predeterminada en el diario seleccionado.</span><span class="sxs-lookup"><span data-stu-id="aae48-122">Continue to the Payment fee setup to define when the fee should default onto the journal you selected.</span></span>  
11. <span data-ttu-id="aae48-123">Seleccione Tabla, Grupo o Todo.</span><span class="sxs-lookup"><span data-stu-id="aae48-123">Select either Table, Group or All.</span></span>
    * <span data-ttu-id="aae48-124">Tabla se usa para seleccionar una única cuenta bancaria; Grupo se usa para seleccionar un grupo de bancos; y Todo se usa para emplear esta configuración de cuota en todas las cuentas bancarias.</span><span class="sxs-lookup"><span data-stu-id="aae48-124">Table is used to select a single bank account, Group is used to select a bank group, and All is to use this fee setup for all bank accounts</span></span>  
12. <span data-ttu-id="aae48-125">Seleccione un grupo de bancos o una cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="aae48-125">Select either a bank group or a bank account.</span></span>
    * <span data-ttu-id="aae48-126">La búsqueda mostrará el grupo de bancos si seleccionó Grupo, y cuentas bancarias si seleccionó Tabla.</span><span class="sxs-lookup"><span data-stu-id="aae48-126">The lookup will show bank group if you selected Group, and will show bank accounts if you selected Table.</span></span>  
13. <span data-ttu-id="aae48-127">Seleccione la forma de pago para cuando se aplique esta cuota.</span><span class="sxs-lookup"><span data-stu-id="aae48-127">Select the method of payment for when this fee will be assessed.</span></span>
14. <span data-ttu-id="aae48-128">Seleccione la especificación de pago para la forma de pago seleccionada.</span><span class="sxs-lookup"><span data-stu-id="aae48-128">Select the Payment specification for the selected method of payment.</span></span>
    * <span data-ttu-id="aae48-129">Especificación del pago se utiliza con formas de pago de transferencia electrónica de fondos.</span><span class="sxs-lookup"><span data-stu-id="aae48-129">The Payment specification is used with electronic fund transfer methods of payment.</span></span>  
15. <span data-ttu-id="aae48-130">Seleccione si la cuota es un porcentaje, un importe o un intervalo.</span><span class="sxs-lookup"><span data-stu-id="aae48-130">Select whether the fee is a percentage, amount or interval.</span></span>
16. <span data-ttu-id="aae48-131">Escriba el porcentaje o el importe de la cuota.</span><span class="sxs-lookup"><span data-stu-id="aae48-131">Enter the percentage or amount of the fee.</span></span>
    * <span data-ttu-id="aae48-132">Si la cuota es un porcentaje, especifique el porcentaje.</span><span class="sxs-lookup"><span data-stu-id="aae48-132">If the Fee is a percentage, enter the percentage.</span></span> <span data-ttu-id="aae48-133">Si la cuota es un importe, especifique el importe de la cuota.</span><span class="sxs-lookup"><span data-stu-id="aae48-133">If the Fee is an amount, enter the amount of the fee.</span></span> <span data-ttu-id="aae48-134">Si la cuota es un intervalo, use la ficha Intervalo para definir las tasas por niveles.</span><span class="sxs-lookup"><span data-stu-id="aae48-134">If the Fee is an interval, use the Interval tab to defined the tiered fees.</span></span>  
17. <span data-ttu-id="aae48-135">En el campo Divisa de cuota, seleccione la divisa para la que se aplicará la cuota.</span><span class="sxs-lookup"><span data-stu-id="aae48-135">In the Fee currency field, select the currency in which the fee will be assessed.</span></span>
    * <span data-ttu-id="aae48-136">Esta divisa es para la cuota.</span><span class="sxs-lookup"><span data-stu-id="aae48-136">This currency is for the fee.</span></span> <span data-ttu-id="aae48-137">La divisa de pago se usa para definir si la regla de cuota se debe aplicar basándose en la divisa de pago.</span><span class="sxs-lookup"><span data-stu-id="aae48-137">The payment currency is used to define when the fee rule should be assessed based on the payment's currency.</span></span> <span data-ttu-id="aae48-138">Por ejemplo, su banco puede cobrar una cuota cuando se realiza un pago en euros, pero en el resto de los pagos no se aplica una cuota.</span><span class="sxs-lookup"><span data-stu-id="aae48-138">For example, your bank may charge a fee when a payment is made in EUR, but all other payments aren't assessed a fee.</span></span>  
18. <span data-ttu-id="aae48-139">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="aae48-139">Click Save.</span></span>

