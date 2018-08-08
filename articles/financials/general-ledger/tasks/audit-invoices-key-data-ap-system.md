--- 
title: Auditar facturas y datos clave en sistema de proveedores
description: Al recibir una factura de un proveedor en concepto de bienes o servicios de un pedido de compra, es posible que los procesos comerciales requieran que los bienes o servicios se reciban antes de poder aprobar la factura para su pago.
author: saraschi2
manager: AnnBe
ms.date: 02/16/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: c928edee086835479ab6d150b1dd86df1824226f
ms.contentlocale: es-es
ms.lasthandoff: 08/07/2018

---
# <a name="audit-invoices-and-key-data-in-accounts-payable"></a><span data-ttu-id="9647f-103">Auditar facturas y datos clave en sistema de proveedores</span><span class="sxs-lookup"><span data-stu-id="9647f-103">Audit invoices and key data in accounts payable</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9647f-104">Al recibir una factura de un proveedor en concepto de bienes o servicios de un pedido de compra, es posible que los procesos comerciales requieran que los bienes o servicios se reciban antes de poder aprobar la factura para su pago.</span><span class="sxs-lookup"><span data-stu-id="9647f-104">When you receive an invoice from a vendor for goods or services on a purchase order, the business processes might require that the goods or services be received before the invoice can be approved for payment.</span></span> <span data-ttu-id="9647f-105">Antes de empezar, asegúrese de que la clave de configuración Conciliación de facturas esté seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9647f-105">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span> 

<span data-ttu-id="9647f-106">En la página Parámetros de proveedores, asegúrese de que la opción Habilitar validación de conciliación de facturas esté seleccionada, el campo Registrar factura con discrepancias esté establecido en Requerir aprobación y el campo Directiva de conciliación de líneas esté establecido en Triple conciliación.</span><span class="sxs-lookup"><span data-stu-id="9647f-106">In the Accounts payable parameters page, ensure that the Enable invoice matching validation option is selected, the Post invoice with discrepancies field is set to Require approval, and the Line matching policy field is set to Three-way matching.</span></span>

<span data-ttu-id="9647f-107">Este procedimiento usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="9647f-107">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="9647f-108">El rol de administrador de proveedores o jefe de contabilidad realizaría estos pasos.</span><span class="sxs-lookup"><span data-stu-id="9647f-108">The accounts payable manager or accounting manager role would perform these steps.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="9647f-109">Crear un pedido de compra</span><span class="sxs-lookup"><span data-stu-id="9647f-109">Create a purchase order</span></span>
1. <span data-ttu-id="9647f-110">Vaya a Todos los pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="9647f-110">Go to All purchase orders.</span></span>
2. <span data-ttu-id="9647f-111">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="9647f-111">Click New.</span></span>
3. <span data-ttu-id="9647f-112">En el campo Cuenta de proveedor, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9647f-112">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="9647f-113">En el campo Cuenta de proveedor, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="9647f-113">In the Vendor account field, type a value.</span></span>
5. <span data-ttu-id="9647f-114">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="9647f-114">Click OK.</span></span>
6. <span data-ttu-id="9647f-115">Haga clic en Agregar línea.</span><span class="sxs-lookup"><span data-stu-id="9647f-115">Click Add line.</span></span>
7. <span data-ttu-id="9647f-116">En el campo Código de artículo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="9647f-116">In the Item number field, type a value.</span></span>
8. <span data-ttu-id="9647f-117">En el panel de acciones, haga clic en Compra.</span><span class="sxs-lookup"><span data-stu-id="9647f-117">On the Action Pane, click Purchase.</span></span>
9. <span data-ttu-id="9647f-118">Haga clic en Confirmar.</span><span class="sxs-lookup"><span data-stu-id="9647f-118">Click Confirm.</span></span>

## <a name="post-a-product-receipt"></a><span data-ttu-id="9647f-119">Registrar una recepción de producto</span><span class="sxs-lookup"><span data-stu-id="9647f-119">Post a product receipt</span></span>
1. <span data-ttu-id="9647f-120">En el panel de acciones, haga clic en Recibir.</span><span class="sxs-lookup"><span data-stu-id="9647f-120">On the Action Pane, click Receive.</span></span>
2. <span data-ttu-id="9647f-121">Haga clic en Recepción de producto.</span><span class="sxs-lookup"><span data-stu-id="9647f-121">Click Product receipt.</span></span>
3. <span data-ttu-id="9647f-122">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9647f-122">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="9647f-123">En el campo Recepción de producto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="9647f-123">In the Product receipt field, type a value.</span></span>
5. <span data-ttu-id="9647f-124">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="9647f-124">Click OK.</span></span>

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a><span data-ttu-id="9647f-125">Registrar y conciliar una factura de proveedor con una recepción de producto</span><span class="sxs-lookup"><span data-stu-id="9647f-125">Record and match a vendor invoice to a product receipt</span></span>
1. <span data-ttu-id="9647f-126">En el panel de acciones, haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="9647f-126">On the Action Pane, click Invoice.</span></span>
2. <span data-ttu-id="9647f-127">Haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="9647f-127">Click Invoice.</span></span>
3. <span data-ttu-id="9647f-128">En el campo Número, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="9647f-128">In the Number field, type a value.</span></span>
4. <span data-ttu-id="9647f-129">Haga clic en Valor predeterminado de origen: Cantidad pedida para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="9647f-129">Click Default from: Ordered quantity to open the drop dialog.</span></span>
5. <span data-ttu-id="9647f-130">En el campo Cantidad predeterminada para líneas, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="9647f-130">In the Default quantity for lines field, select an option.</span></span>
6. <span data-ttu-id="9647f-131">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="9647f-131">Click OK.</span></span>
7. <span data-ttu-id="9647f-132">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="9647f-132">Click Yes.</span></span>
8. <span data-ttu-id="9647f-133">Haga clic en Conciliar recepciones de producto.</span><span class="sxs-lookup"><span data-stu-id="9647f-133">Click Match product receipts.</span></span>
9. <span data-ttu-id="9647f-134">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="9647f-134">Click OK.</span></span>
10. <span data-ttu-id="9647f-135">En el panel de acciones, haga clic en Revisar.</span><span class="sxs-lookup"><span data-stu-id="9647f-135">On the Action Pane, click Review.</span></span>
11. <span data-ttu-id="9647f-136">Haga clic en Detalles coincidentes.</span><span class="sxs-lookup"><span data-stu-id="9647f-136">Click Matching details.</span></span>


