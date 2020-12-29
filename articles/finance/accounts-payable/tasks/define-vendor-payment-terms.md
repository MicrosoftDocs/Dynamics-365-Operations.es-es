---
title: Definir condiciones de pagos a proveedores
description: En este tema se explica cómo configurar condiciones de pago para facturas de proveedor.
author: abruer
manager: AnnBe
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PaymTerm, CashDisc
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7e6778f61a9367399e4b71d5b2bb2459c09ba508
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447443"
---
# <a name="define-vendor-payment-terms"></a><span data-ttu-id="98e7d-103">Definir condiciones de pagos a proveedores</span><span class="sxs-lookup"><span data-stu-id="98e7d-103">Define vendor payment terms</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="98e7d-104">En este tema se explica cómo configurar condiciones de pago para facturas de proveedor.</span><span class="sxs-lookup"><span data-stu-id="98e7d-104">This topic explains how to set up payment terms for vendor invoices.</span></span> <span data-ttu-id="98e7d-105">Esta tarea usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="98e7d-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="98e7d-106">Vaya a **Panel de exploración > Módulos > Proveedores > Configuración de pagos > Condiciones de pago**.</span><span class="sxs-lookup"><span data-stu-id="98e7d-106">Go to **Navigation pane > Modules > Accounts payable > Payment setup > Terms of payment**.</span></span>
2. <span data-ttu-id="98e7d-107">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="98e7d-107">Select **New**.</span></span> <span data-ttu-id="98e7d-108">La página Condiciones de pago se usa para definir cómo se calculará la fecha de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="98e7d-108">The Terms of payment page is used to define how the due date will be calculated.</span></span> <span data-ttu-id="98e7d-109">No se usa para definir cómo se calculará la fecha de descuento por pronto pago.</span><span class="sxs-lookup"><span data-stu-id="98e7d-109">It is not used to define how the cash discount date will be calculated.</span></span>  
3. <span data-ttu-id="98e7d-110">En el campo **Condiciones de pago**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="98e7d-110">In the **Terms of payment** field, type a value.</span></span>
4. <span data-ttu-id="98e7d-111">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="98e7d-111">In the **Description field**, type a value.</span></span>
5. <span data-ttu-id="98e7d-112">En el campo **Días**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="98e7d-112">In the **Days** field, enter a number.</span></span> <span data-ttu-id="98e7d-113">El número especificado aquí se usará para agregarlo a la fecha de vencimiento, o al final del período identificado en la forma de pago.</span><span class="sxs-lookup"><span data-stu-id="98e7d-113">The number entered here will be used to add to the due date, or to the end of the period identified in the Payment method.</span></span> <span data-ttu-id="98e7d-114">Por ejemplo, si selecciona **Neto**, el número se agregará a la fecha de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="98e7d-114">For example, if you select **Net**, the number will be added to the due date.</span></span> <span data-ttu-id="98e7d-115">Si selecciona **Mes actual**, para calcular la fecha de vencimiento se agregará el número al último día del mes actual.</span><span class="sxs-lookup"><span data-stu-id="98e7d-115">If you select **Current month**, it will add the number to the last day of the current month to calculate the due date.</span></span>  
6. <span data-ttu-id="98e7d-116">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="98e7d-116">Select **Save**.</span></span>
7. <span data-ttu-id="98e7d-117">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="98e7d-117">Close the page.</span></span>
8. <span data-ttu-id="98e7d-118">Vaya a **Proveedores > Configuración de pagos > Descuentos por pronto pago**.</span><span class="sxs-lookup"><span data-stu-id="98e7d-118">Go to **Accounts payable > Payment setup > Cash discounts**.</span></span>
9. <span data-ttu-id="98e7d-119">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="98e7d-119">Select **New**.</span></span>
10. <span data-ttu-id="98e7d-120">En el campo **Descuento por pronto pago**, escriba un identificador.</span><span class="sxs-lookup"><span data-stu-id="98e7d-120">In the **Cash discount** field, enter an ID.</span></span>
11. <span data-ttu-id="98e7d-121">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="98e7d-121">In the **Description** field, type a value.</span></span>
12. <span data-ttu-id="98e7d-122">Si el proveedor ofrece varios niveles de descuento, seleccione el descuento por pronto pago siguiente después de vencer el actual.</span><span class="sxs-lookup"><span data-stu-id="98e7d-122">If the vendor offers a tiered discount, select the next cash discount after the current one is expired.</span></span>
13. <span data-ttu-id="98e7d-123">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="98e7d-123">Close the page.</span></span>
14. <span data-ttu-id="98e7d-124">En el campo **Días**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="98e7d-124">In the **Days** field, enter a number.</span></span> <span data-ttu-id="98e7d-125">La cantidad especificada en el campo **Días** se usará para calcular la fecha de descuento por pronto pago, en función de la opción que se haya seleccionado en el campo **Neto/Actual**.</span><span class="sxs-lookup"><span data-stu-id="98e7d-125">The quantity entered in the **Days** field will be used to calculate the Cash discount date, based on what option was selected in the **Net/Current** field.</span></span> <span data-ttu-id="98e7d-126">Si ha seleccionado **Neto**, la cantidad se agregará a la fecha de factura para determinar la fecha de descuento por pronto pago.</span><span class="sxs-lookup"><span data-stu-id="98e7d-126">If **Net** was selected, the quantity will be added to the invoice date to determine the cash discount date.</span></span> <span data-ttu-id="98e7d-127">Si se ha seleccionado **Mes actual**, la cantidad se agregará al final del mes de la divisa para determinar la fecha de descuento por pronto pago.</span><span class="sxs-lookup"><span data-stu-id="98e7d-127">If **Current month** was selected, the quantity will be added to the end of the currency month to determine the cash discount date.</span></span>  
15. <span data-ttu-id="98e7d-128">Escriba el porcentaje de descuento por pronto pago en el campo **Descuento**.</span><span class="sxs-lookup"><span data-stu-id="98e7d-128">Enter the percentage of the cash discount in the **Discount** field.</span></span> 
16. <span data-ttu-id="98e7d-129">Especifique la cuenta principal en la que se registrará el descuento por pronto pago para las facturas de cliente. A continuación, escriba la cuenta principal en la que se registrará el descuento por pronto pago para las facturas de proveedor.</span><span class="sxs-lookup"><span data-stu-id="98e7d-129">Enter the main account to which the cash discount will be posted for customer invoices, then enter the main account to which the cash discount will be posted for vendor invoices.</span></span> <span data-ttu-id="98e7d-130">Si **Cuentas de contrapartida para descuentos** está establecida en **Usar cuenta principal para descuentos de proveedor**, se usará la cuenta principal.</span><span class="sxs-lookup"><span data-stu-id="98e7d-130">If **Discount offset accounts** is set to **Use main account for vendor discount**, then the Main account will be used.</span></span> <span data-ttu-id="98e7d-131">Si la opción se establece en **Cuentas en las líneas de factura**, el descuento por pronto pago se registrará en las cuentas de activos/gastos en las líneas de la factura.</span><span class="sxs-lookup"><span data-stu-id="98e7d-131">If the option is set to **Accounts on the invoice lines**, the cash discount will be posted to the asset/expense accounts on the invoice's lines.</span></span>  
17. <span data-ttu-id="98e7d-132">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="98e7d-132">Select **Save**.</span></span>

