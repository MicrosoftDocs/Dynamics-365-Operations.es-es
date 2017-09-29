--- 
title: Registrar una factura de proveedor en el diario de facturas
description: "Esta guía de la tarea muestra cómo registrar facturas de proveedor que no están asociadas a ningún pedido de compra."
author: abruer
manager: AnnBe
ms.date: 11/15/2016
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
ms.openlocfilehash: 42f93e6d8fcf62babc3e3244bc1fe76d1efd9d13
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="record-a-vendor-invoice-in-the-invoice-journal"></a><span data-ttu-id="dc0fe-103">Registrar una factura de proveedor en el diario de facturas</span><span class="sxs-lookup"><span data-stu-id="dc0fe-103">Record a vendor invoice in the invoice journal</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="dc0fe-104">Esta guía de la tarea muestra cómo registrar facturas de proveedor que no están asociadas a ningún pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="dc0fe-104">This task guide will show how to record vendor invoices that are not associated with purchase orders.</span></span> <span data-ttu-id="dc0fe-105">Algunos ejemplos de este tipo de factura incluyen los gastos para suministros o servicios.</span><span class="sxs-lookup"><span data-stu-id="dc0fe-105">Examples of this type of invoice include expenses for supplies or services.</span></span>  <span data-ttu-id="dc0fe-106">Esta grabación usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="dc0fe-106">This recording uses the USMF demo company.</span></span>

1. <span data-ttu-id="dc0fe-107">Vaya a Proveedores > Áreas de trabajo > Entrada de factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="dc0fe-107">Go to Accounts payable > Workspaces > Vendor invoice entry.</span></span>
2. <span data-ttu-id="dc0fe-108">Haga clic en Diario de facturas nuevas.</span><span class="sxs-lookup"><span data-stu-id="dc0fe-108">Click New invoice journal.</span></span>
3. <span data-ttu-id="dc0fe-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="dc0fe-109">Click New.</span></span>
4. <span data-ttu-id="dc0fe-110">En el campo Nombre, escriba el nombre del diario o haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="dc0fe-110">In the Name field, enter the journal name or click the drop down button to open the lookup.</span></span>
5. <span data-ttu-id="dc0fe-111">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="dc0fe-111">In the Description field, type a value.</span></span>
6. <span data-ttu-id="dc0fe-112">Haga clic en Líneas.</span><span class="sxs-lookup"><span data-stu-id="dc0fe-112">Click Lines.</span></span>
    * <span data-ttu-id="dc0fe-113">En el campo Fecha, especifique la fecha de registro que va a actualizar la contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="dc0fe-113">In the Date field, enter the posting date that will update General Ledger.</span></span>  
7. <span data-ttu-id="dc0fe-114">En el campo Cuenta, especifique la cuenta del proveedor.</span><span class="sxs-lookup"><span data-stu-id="dc0fe-114">In the Account field, specify the Vendor account.</span></span>
8. <span data-ttu-id="dc0fe-115">En el campo Factura, especifique el número de factura.</span><span class="sxs-lookup"><span data-stu-id="dc0fe-115">In the Invoice field, enter the invoice number.</span></span>
9. <span data-ttu-id="dc0fe-116">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="dc0fe-116">In the Description field, type a value.</span></span>
10. <span data-ttu-id="dc0fe-117">En el campo Crédito, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="dc0fe-117">In the Credit field, enter a number.</span></span>
11. <span data-ttu-id="dc0fe-118">En el campo Cuenta de contrapartida, escriba el número de cuenta o haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="dc0fe-118">In the Offset account field, enter the account number or click the drop down button to open the lookup</span></span>
    * <span data-ttu-id="dc0fe-119">El valor predeterminado del grupo de impuestos proviene de la cuenta de proveedor</span><span class="sxs-lookup"><span data-stu-id="dc0fe-119">The Sales tax group will default from the vendor account.</span></span>  
    * <span data-ttu-id="dc0fe-120">El valor predeterminado proviene del campo Grupo de impuestos de artículos de la cuenta principal especificada en el campo Cuenta de contrapartida.</span><span class="sxs-lookup"><span data-stu-id="dc0fe-120">The Item sales tax group will default from the main account specified in the Offset account field.</span></span>  
    * <span data-ttu-id="dc0fe-121">La fecha de vencimiento se calculará según las condiciones de pago.</span><span class="sxs-lookup"><span data-stu-id="dc0fe-121">The Due date will be calculated based on the Terms of payment.</span></span>  
    * <span data-ttu-id="dc0fe-122">El descuento por pronto pago proviene de la cuenta de proveedor</span><span class="sxs-lookup"><span data-stu-id="dc0fe-122">The Cash discount will default from the Vendor account.</span></span>  
12. <span data-ttu-id="dc0fe-123">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="dc0fe-123">Click Post.</span></span>
13. <span data-ttu-id="dc0fe-124">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="dc0fe-124">Close the page.</span></span>


