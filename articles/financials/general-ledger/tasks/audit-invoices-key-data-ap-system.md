---
title: Auditar facturas y datos clave en sistema de proveedores
description: Al recibir una factura de un proveedor en concepto de bienes o servicios de un pedido de compra, es posible que los procesos comerciales requieran que los bienes o servicios se reciban antes de poder aprobar la factura para su pago.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, PurchEditLines, VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog,  VendJournalMatch_PackingSlip, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c6e8967fe4db67ff98fc7093792bdb82b73a33d9
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834983"
---
# <a name="audit-invoices-and-key-data-in-ap-system"></a><span data-ttu-id="84a95-103">Auditar facturas y datos clave en sistema de proveedores</span><span class="sxs-lookup"><span data-stu-id="84a95-103">Audit invoices and key data in AP system</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="84a95-104">Al recibir una factura de un proveedor en concepto de bienes o servicios de un pedido de compra, es posible que los procesos comerciales requieran que los bienes o servicios se reciban antes de poder aprobar la factura para su pago.</span><span class="sxs-lookup"><span data-stu-id="84a95-104">When you receive an invoice from a vendor for goods or services on a purchase order, the business processes might require that the goods or services be received before the invoice can be approved for payment.</span></span> <span data-ttu-id="84a95-105">Antes de empezar, asegúrese de que la clave de configuración Conciliación de facturas esté seleccionada.</span><span class="sxs-lookup"><span data-stu-id="84a95-105">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span> 

<span data-ttu-id="84a95-106">En la página Parámetros de proveedores, asegúrese de que la opción Habilitar validación de conciliación de facturas esté seleccionada, el campo Registrar factura con discrepancias esté establecido en Requerir aprobación y el campo Directiva de conciliación de líneas esté establecido en Triple conciliación.</span><span class="sxs-lookup"><span data-stu-id="84a95-106">In the Accounts payable parameters page, ensure that the Enable invoice matching validation option is selected, the Post invoice with discrepancies field is set to Require approval, and the Line matching policy field is set to Three-way matching.</span></span>

<span data-ttu-id="84a95-107">Este procedimiento usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="84a95-107">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="84a95-108">El rol de administrador de proveedores o jefe de contabilidad realizaría estos pasos.</span><span class="sxs-lookup"><span data-stu-id="84a95-108">The accounts payable manager or accounting manager role would perform these steps.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="84a95-109">Crear un pedido de compra</span><span class="sxs-lookup"><span data-stu-id="84a95-109">Create a purchase order</span></span>
1. <span data-ttu-id="84a95-110">Vaya a **Todos los pedidos de compra.**</span><span class="sxs-lookup"><span data-stu-id="84a95-110">Go to **All purchase orders**.</span></span>
2. <span data-ttu-id="84a95-111">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="84a95-111">Click **New**.</span></span>
3. <span data-ttu-id="84a95-112">En el campo **Cuenta de proveedor**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="84a95-112">In the **Vendor account** field, type a value.</span></span>
4. <span data-ttu-id="84a95-113">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="84a95-113">Click **OK**.</span></span>
5. <span data-ttu-id="84a95-114">Haga clic en **Agregar línea.**</span><span class="sxs-lookup"><span data-stu-id="84a95-114">Click **Add line**.</span></span>
6. <span data-ttu-id="84a95-115">En el campo **Código de artículo**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="84a95-115">In the **Item number** field, type a value.</span></span>
7. <span data-ttu-id="84a95-116">En el panel de acciones, haga clic en **Compra.**</span><span class="sxs-lookup"><span data-stu-id="84a95-116">On the Action Pane, click **Purchase**.</span></span>
8. <span data-ttu-id="84a95-117">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="84a95-117">Click **Confirm**.</span></span>

## <a name="post-a-product-receipt"></a><span data-ttu-id="84a95-118">Registrar una recepción de producto</span><span class="sxs-lookup"><span data-stu-id="84a95-118">Post a product receipt</span></span>
1. <span data-ttu-id="84a95-119">En el panel de acciones, haga clic en **Recibir.**</span><span class="sxs-lookup"><span data-stu-id="84a95-119">On the Action Pane, click **Receive**.</span></span>
2. <span data-ttu-id="84a95-120">Haga clic en **Recepción de producto.**</span><span class="sxs-lookup"><span data-stu-id="84a95-120">Click **Product receipt**.</span></span>
3. <span data-ttu-id="84a95-121">En el campo **Recepción de producto**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="84a95-121">In the **Product receipt** field, type a value.</span></span>
4. <span data-ttu-id="84a95-122">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="84a95-122">Click **OK**.</span></span>

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a><span data-ttu-id="84a95-123">Registrar y conciliar una factura de proveedor con una recepción de producto</span><span class="sxs-lookup"><span data-stu-id="84a95-123">Record and match a vendor invoice to a product receipt</span></span>
1. <span data-ttu-id="84a95-124">En el panel de acciones, haga clic en **Factura > Factura**.</span><span class="sxs-lookup"><span data-stu-id="84a95-124">On the Action Pane, click **Invoice > Invoice**.</span></span>
2. <span data-ttu-id="84a95-125">En el campo **Número**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="84a95-125">In the **Number** field, type a value.</span></span>
3. <span data-ttu-id="84a95-126">Haga clic en **Valor predeterminado de origen: Cantidad pedida** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="84a95-126">Click **Default from: Ordered quantity** to open the drop dialog.</span></span>
4. <span data-ttu-id="84a95-127">En el campo **Cantidad predeterminada para líneas**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="84a95-127">In the **Default quantity for lines** field, select an option.</span></span>
5. <span data-ttu-id="84a95-128">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="84a95-128">Click **OK**.</span></span>
6. <span data-ttu-id="84a95-129">Haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="84a95-129">Click **Yes**.</span></span>
7. <span data-ttu-id="84a95-130">Haga clic en **Conciliar recepciones de producto**.</span><span class="sxs-lookup"><span data-stu-id="84a95-130">Click **Match product receipts**.</span></span>
8. <span data-ttu-id="84a95-131">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="84a95-131">Click **OK**.</span></span>
9. <span data-ttu-id="84a95-132">En el panel de acciones, haga clic en **Revisar**.</span><span class="sxs-lookup"><span data-stu-id="84a95-132">On the Action Pane, click **Review**.</span></span>
10. <span data-ttu-id="84a95-133">Haga clic en **Detalles coincidentes**.</span><span class="sxs-lookup"><span data-stu-id="84a95-133">Click **Matching details**.</span></span>

