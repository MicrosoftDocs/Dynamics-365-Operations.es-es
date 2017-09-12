--- 
title: Definir condiciones de pagos a proveedores
description: Configurar condiciones de pago para facturas de proveedor.
author: abruer
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: a00ca73b1bc301960132a86846749d12c39ed3f7
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="define-vendor-payment-terms"></a><span data-ttu-id="87019-103">Definir condiciones de pagos a proveedores</span><span class="sxs-lookup"><span data-stu-id="87019-103">Define vendor payment terms</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="87019-104">Configurar condiciones de pago para facturas de proveedor.</span><span class="sxs-lookup"><span data-stu-id="87019-104">Set up payment terms for vendor invoices.</span></span> <span data-ttu-id="87019-105">Esta tarea usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="87019-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="87019-106">Vaya a Proveedores > Configuración de pagos > Condiciones de pago.</span><span class="sxs-lookup"><span data-stu-id="87019-106">Go to Accounts payable > Payment setup > Terms of payment.</span></span>
2. <span data-ttu-id="87019-107">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="87019-107">Click New.</span></span>
    * <span data-ttu-id="87019-108">La página Condiciones de pago se usa para definir cómo se calculará la fecha de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="87019-108">The Terms of payment page is used to define how the due date will be calculated.</span></span> <span data-ttu-id="87019-109">No se usa para definir cómo se calculará la fecha de descuento por pronto pago.</span><span class="sxs-lookup"><span data-stu-id="87019-109">It is not used to define how the cash discount date will be calculated.</span></span>  
3. <span data-ttu-id="87019-110">En el campo Condiciones de pago, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="87019-110">In the Terms of payment field, type a value.</span></span>
4. <span data-ttu-id="87019-111">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="87019-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="87019-112">En el campo Días, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="87019-112">In the Days field, enter a number.</span></span>
    * <span data-ttu-id="87019-113">El número especificado aquí se usará para agregarlo a la fecha de vencimiento, o al final del período identificado en la forma de pago.</span><span class="sxs-lookup"><span data-stu-id="87019-113">The number entered here will be used to add to the due date, or to the end of the period identified in the Payment method.</span></span> <span data-ttu-id="87019-114">Por ejemplo, si selecciona Neto, el número se agregará a la fecha de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="87019-114">For example, if you select Net, the number will be added to the due date.</span></span> <span data-ttu-id="87019-115">Si selecciona Mes actual, para calcular la fecha de vencimiento se agregará el número al último día del mes actual.</span><span class="sxs-lookup"><span data-stu-id="87019-115">If you select Current month, it will add the number to the last day of the current month to calculate the due date.</span></span>  
6. <span data-ttu-id="87019-116">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="87019-116">Click Save.</span></span>
7. <span data-ttu-id="87019-117">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="87019-117">Close the page.</span></span>
8. <span data-ttu-id="87019-118">Vaya a Proveedores > Configuración de pagos > Descuentos por pronto pago.</span><span class="sxs-lookup"><span data-stu-id="87019-118">Go to Accounts payable > Payment setup > Cash discounts.</span></span>
9. <span data-ttu-id="87019-119">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="87019-119">Click New.</span></span>
10. <span data-ttu-id="87019-120">En el campo Descuento por pronto pago, escriba un Id.</span><span class="sxs-lookup"><span data-stu-id="87019-120">In the Cash discount field, enter an ID.</span></span>
11. <span data-ttu-id="87019-121">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="87019-121">In the Description field, type a value.</span></span>
12. <span data-ttu-id="87019-122">Si el proveedor ofrece varios niveles de descuento, seleccione el descuento por pronto pago siguiente después de vencer el actual.</span><span class="sxs-lookup"><span data-stu-id="87019-122">If the vendor offers a tiered discount, select the next cash discount after the current one is expired.</span></span>
13. <span data-ttu-id="87019-123">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="87019-123">Close the page.</span></span>
14. <span data-ttu-id="87019-124">En el campo Días, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="87019-124">In the Days field, enter a number.</span></span>
    * <span data-ttu-id="87019-125">La cantidad especificada en el campo Días se usará para calcular la fecha de descuento por pronto pago, en función de la opción que se haya seleccionado en el campo Neto/Actual.</span><span class="sxs-lookup"><span data-stu-id="87019-125">The quantity entered in the Days field will be used to calculate the Cash discount date, based on what option was selected in the Net/Current field.</span></span> <span data-ttu-id="87019-126">Si ha seleccionado Neto, la cantidad se agregará a la fecha de factura para determinar la fecha de descuento por pronto pago.</span><span class="sxs-lookup"><span data-stu-id="87019-126">If Net was selected, the quantity will be added to the invoice date to determine the cash discount date.</span></span> <span data-ttu-id="87019-127">Si se ha seleccionado Mes actual, la cantidad se agregará al final del mes de la divisa para determinar la fecha de descuento por pronto pago.</span><span class="sxs-lookup"><span data-stu-id="87019-127">If Current month was selected, the quantity will be added to the end of the currency month to determine the cash discount date.</span></span>  
15. <span data-ttu-id="87019-128">Escriba el porcentaje de descuento por pronto pago en el campo Descuento.</span><span class="sxs-lookup"><span data-stu-id="87019-128">Enter the percentage of the cash discount in the Discount field.</span></span> 
16. <span data-ttu-id="87019-129">Especifique la cuenta principal en la que se registrará el descuento por pronto pago para las facturas de cliente.</span><span class="sxs-lookup"><span data-stu-id="87019-129">Enter the main account to which the cash discount will be posted for customer invoices.</span></span>
17. <span data-ttu-id="87019-130">Especifique la cuenta principal en la que se registrará el descuento por pronto pago para las facturas de proveedor.</span><span class="sxs-lookup"><span data-stu-id="87019-130">Enter the main account to which the cash discount will be posted for vendor invoices.</span></span>
    * <span data-ttu-id="87019-131">Si Cuentas de contrapartida para descuentos está definido en Usar cuenta principal para descuentos de proveedor, se usará la cuenta principal.</span><span class="sxs-lookup"><span data-stu-id="87019-131">If 'Discount offset accounts' is set to Use main account for vendor discount, then the Main account will be used.</span></span>  <span data-ttu-id="87019-132">Si la opción se establece en las cuentas en las líneas de factura, el descuento por pronto pago se registrará en las cuentas de activos/gastos en las líneas de la factura.</span><span class="sxs-lookup"><span data-stu-id="87019-132">If the option is set to Accounts on the invoice lines, the cash discount will be posted to the asset/expense accounts on the invoice's lines.</span></span>  
18. <span data-ttu-id="87019-133">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="87019-133">Click Save.</span></span>


