---
title: Registrar la factura de proveedor y cuadrarla con la cantidad recibida
description: Al recibir una factura de un proveedor en concepto de bienes o servicios de un pedido de compra, es posible que los procesos comerciales requieran que los bienes o servicios se reciban antes de poder aprobar la factura para su pago.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, PurchEditLines, VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog,  VendJournalMatch_PackingSlip, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: be1e818e8a97684248c9c0b9d43c39e631f855f5
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979272"
---
# <a name="record-vendor-invoice-and-match-against-received-quantity"></a><span data-ttu-id="44f75-103">Registrar la factura de proveedor y cuadrarla con la cantidad recibida</span><span class="sxs-lookup"><span data-stu-id="44f75-103">Record vendor invoice and match against received quantity</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="44f75-104">Al recibir una factura de un proveedor en concepto de bienes o servicios de un pedido de compra, es posible que los procesos comerciales requieran que los bienes o servicios se reciban antes de poder aprobar la factura para su pago.</span><span class="sxs-lookup"><span data-stu-id="44f75-104">When you receive an invoice from a vendor for goods or services on a purchase order, the business processes might require that the goods or services be received before the invoice can be approved for payment.</span></span> <span data-ttu-id="44f75-105">Antes de empezar, asegúrese de que la clave de configuración Conciliación de facturas esté seleccionada.</span><span class="sxs-lookup"><span data-stu-id="44f75-105">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span> 

<span data-ttu-id="44f75-106">En la página Parámetros de proveedores, asegúrese de que la opción Habilitar validación de conciliación de facturas esté seleccionada, el campo Registrar factura con discrepancias esté establecido en Requerir aprobación y el campo Directiva de conciliación de líneas esté establecido en Triple conciliación.</span><span class="sxs-lookup"><span data-stu-id="44f75-106">In the Accounts payable parameters page, ensure that the Enable invoice matching validation option is selected, the Post invoice with discrepancies field is set to Require approval, and the Line matching policy field is set to Three-way matching.</span></span>

<span data-ttu-id="44f75-107">Este procedimiento usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="44f75-107">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="44f75-108">El rol de administrador de proveedores o jefe de contabilidad realizaría estos pasos.</span><span class="sxs-lookup"><span data-stu-id="44f75-108">The accounts payable manager or accounting manager role would perform these steps.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="44f75-109">Crear un pedido de compra</span><span class="sxs-lookup"><span data-stu-id="44f75-109">Create a purchase order</span></span>
1. <span data-ttu-id="44f75-110">Vaya a Todos los pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="44f75-110">Go to All purchase orders.</span></span>
2. <span data-ttu-id="44f75-111">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="44f75-111">Click New.</span></span>
3. <span data-ttu-id="44f75-112">En el campo Cuenta de proveedor, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="44f75-112">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="44f75-113">En el campo Cuenta de proveedor, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="44f75-113">In the Vendor account field, type a value.</span></span>
5. <span data-ttu-id="44f75-114">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="44f75-114">Click OK.</span></span>
6. <span data-ttu-id="44f75-115">Haga clic en Agregar línea.</span><span class="sxs-lookup"><span data-stu-id="44f75-115">Click Add line.</span></span>
7. <span data-ttu-id="44f75-116">En el campo Código de artículo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="44f75-116">In the Item number field, type a value.</span></span>
8. <span data-ttu-id="44f75-117">En el panel de acciones, haga clic en Compra.</span><span class="sxs-lookup"><span data-stu-id="44f75-117">On the Action Pane, click Purchase.</span></span>
9. <span data-ttu-id="44f75-118">Haga clic en Confirmar.</span><span class="sxs-lookup"><span data-stu-id="44f75-118">Click Confirm.</span></span>

## <a name="post-a-product-receipt"></a><span data-ttu-id="44f75-119">Registrar una recepción de producto</span><span class="sxs-lookup"><span data-stu-id="44f75-119">Post a product receipt</span></span>
1. <span data-ttu-id="44f75-120">En el panel de acciones, haga clic en Recibir.</span><span class="sxs-lookup"><span data-stu-id="44f75-120">On the Action Pane, click Receive.</span></span>
2. <span data-ttu-id="44f75-121">Haga clic en Recepción de producto.</span><span class="sxs-lookup"><span data-stu-id="44f75-121">Click Product receipt.</span></span>
3. <span data-ttu-id="44f75-122">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="44f75-122">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="44f75-123">En el campo Recepción de producto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="44f75-123">In the Product receipt field, type a value.</span></span>
5. <span data-ttu-id="44f75-124">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="44f75-124">Click OK.</span></span>

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a><span data-ttu-id="44f75-125">Registrar y conciliar una factura de proveedor con una recepción de producto</span><span class="sxs-lookup"><span data-stu-id="44f75-125">Record and match a vendor invoice to a product receipt</span></span>
1. <span data-ttu-id="44f75-126">En el panel de acciones, haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="44f75-126">On the Action Pane, click Invoice.</span></span>
2. <span data-ttu-id="44f75-127">Haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="44f75-127">Click Invoice.</span></span>
3. <span data-ttu-id="44f75-128">En el campo Número, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="44f75-128">In the Number field, type a value.</span></span>
4. <span data-ttu-id="44f75-129">Haga clic en Valor predeterminado de origen: Cantidad pedida para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="44f75-129">Click Default from: Ordered quantity to open the drop dialog.</span></span>
5. <span data-ttu-id="44f75-130">En el campo Cantidad predeterminada para líneas, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="44f75-130">In the Default quantity for lines field, select an option.</span></span>
6. <span data-ttu-id="44f75-131">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="44f75-131">Click OK.</span></span>
7. <span data-ttu-id="44f75-132">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="44f75-132">Click Yes.</span></span>
8. <span data-ttu-id="44f75-133">Haga clic en Conciliar recepciones de producto.</span><span class="sxs-lookup"><span data-stu-id="44f75-133">Click Match product receipts.</span></span>
9. <span data-ttu-id="44f75-134">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="44f75-134">Click OK.</span></span>
10. <span data-ttu-id="44f75-135">En el panel de acciones, haga clic en Revisar.</span><span class="sxs-lookup"><span data-stu-id="44f75-135">On the Action Pane, click Review.</span></span>
11. <span data-ttu-id="44f75-136">Haga clic en Detalles coincidentes.</span><span class="sxs-lookup"><span data-stu-id="44f75-136">Click Matching details.</span></span>

