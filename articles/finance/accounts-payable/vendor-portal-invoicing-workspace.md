---
title: Espacio de trabajo de facturación de colaboración de proveedor
description: Este tema explica cómo puede ver las facturas de proveedor y enviar las facturas desde el espacio de trabajo de la facturacíon de colaboración de proveedor.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendInvoiceWorkspace
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 221534
ms.assetid: c4ed62f3-d351-41d7-a2ad-790576cde4ab
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 626607814d6c747d74a13de284db097f0efd8a0c
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179838"
---
# <a name="vendor-collaboration-invoicing-workspace"></a><span data-ttu-id="6eb22-103">Espacio de trabajo de facturación de colaboración de proveedor</span><span class="sxs-lookup"><span data-stu-id="6eb22-103">Vendor collaboration invoicing workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6eb22-104">Este tema explica cómo puede ver las facturas de proveedor y enviar las facturas desde el espacio de trabajo de la facturacíon de colaboración de proveedor.</span><span class="sxs-lookup"><span data-stu-id="6eb22-104">This topic explains how you can view vendor invoices and submit invoices from the vendor collaboration invoicing workspace.</span></span>

<span data-ttu-id="6eb22-105">El espacio de trabajo de **Facturación de colaboración de proveedor** se puede usar para ver información de la factura de proveedor y para enviar facturas al sistema mediante capacidades del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6eb22-105">The **Vendor collaboration invoicing** workspace can be used to view vendor invoice information and to submit invoices to the system using workflow capabilities.</span></span>


<a name="vendor-collaboration-invoicing-workspace"></a><span data-ttu-id="6eb22-106">Espacio de trabajo de facturación de colaboración de proveedor</span><span class="sxs-lookup"><span data-stu-id="6eb22-106">Vendor collaboration invoicing workspace</span></span>
----------------------------------------

### <a name="summary-tiles"></a><span data-ttu-id="6eb22-107">Iconos de resumen</span><span class="sxs-lookup"><span data-stu-id="6eb22-107">Summary tiles</span></span>

<span data-ttu-id="6eb22-108">Las fichas de **Resumen** ofrecen una visión general de las facturas para el proveedor seleccionado.</span><span class="sxs-lookup"><span data-stu-id="6eb22-108">The **Summary** tiles give an overview of the invoices for the selected vendor.</span></span> <span data-ttu-id="6eb22-109">Puede visualizar facturas por su estado.</span><span class="sxs-lookup"><span data-stu-id="6eb22-109">You can view invoices by their state.</span></span>
-   <span data-ttu-id="6eb22-110">Las facturas de borrador no se han enviado al flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6eb22-110">Draft invoices have not been submitted to workflow.</span></span>
-   <span data-ttu-id="6eb22-111">Las facturas enviadas no aprobadas son aquellas facturas que el proveedor ha enviado pero que no se han registrado en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6eb22-111">Submitted, not approved invoices are those invoices that the vendor has submitted, but they have not been posted in the application.</span></span>
-   <span data-ttu-id="6eb22-112">Las facturas aprobadas no pagadas son aquellas facturas que el proveedor ha registrado pero que todavía no se han pagado por completo.</span><span class="sxs-lookup"><span data-stu-id="6eb22-112">Approved, not paid invoices are those that have been posted, but they have not yet been fully paid.</span></span>
-   <span data-ttu-id="6eb22-113">Las facturas pagadas son aquellas que se han pagado por completo en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6eb22-113">Paid invoices are those that have been fully paid in the application.</span></span>

<span data-ttu-id="6eb22-114">Si hace clic en una ficha, abrirá una vista filtrada de la página **Lista de facturas**.</span><span class="sxs-lookup"><span data-stu-id="6eb22-114">Clicking on a tile will open a filtered view of the **Invoices list** page.</span></span>

### <a name="tabular-lists"></a><span data-ttu-id="6eb22-115">Listas tabulares</span><span class="sxs-lookup"><span data-stu-id="6eb22-115">Tabular lists</span></span>

<span data-ttu-id="6eb22-116">En la sección **Listas tabulares**, el estado de la facturación se desglosa de forma similar a las fichas del resumen: Borrador y Enviado, listas no aprobadas.</span><span class="sxs-lookup"><span data-stu-id="6eb22-116">In the **Tabular lists** section, the status of the invoicing is broken down in similar ways as the summary tiles: Draft and Submitted, not approved lists.</span></span> <span data-ttu-id="6eb22-117">Cuando se encuentre en estado de Borrador, una factura se puede enviar al flujo de trabajo o eliminarse.</span><span class="sxs-lookup"><span data-stu-id="6eb22-117">While in the Draft state, an invoice can be submitted to workflow or deleted.</span></span> <span data-ttu-id="6eb22-118">La última lista tabular es una opción para buscar facturas.</span><span class="sxs-lookup"><span data-stu-id="6eb22-118">The last tabular list is an option to find invoices.</span></span> <span data-ttu-id="6eb22-119">Puede filtrar según busca para permitir búsquedas más rápidas.</span><span class="sxs-lookup"><span data-stu-id="6eb22-119">You can filter as you search, to allow for faster searches.</span></span>

### <a name="all-vendor-invoices-list-page"></a><span data-ttu-id="6eb22-120">Página de la lista de todas las facturas de proveedor</span><span class="sxs-lookup"><span data-stu-id="6eb22-120">All vendor invoices list page</span></span>

<span data-ttu-id="6eb22-121">Puede ver todas las facturas de proveedor registradas y sin registrar en la página de la lista de **Facturas de colaboración de proveedore**.</span><span class="sxs-lookup"><span data-stu-id="6eb22-121">You can view all posted and unposted vendor invoices on the **Vendor collaboration invoices** list page.</span></span> <span data-ttu-id="6eb22-122">Puede usar dicha página para ver el estado del pago de las facturas.</span><span class="sxs-lookup"><span data-stu-id="6eb22-122">You can use this list page to view the payment status of the invoices.</span></span> <span data-ttu-id="6eb22-123">Los estados del pago incluyen No registradas, Sin pagar, Pagadas parcialemente y Pagadas completamente.</span><span class="sxs-lookup"><span data-stu-id="6eb22-123">The payment statuses include Unposted, Unpaid, Partially paid, and Fully paid.</span></span>
<span data-ttu-id="6eb22-124">Crear una nueva factura a partir de un pedido de compra</span><span class="sxs-lookup"><span data-stu-id="6eb22-124">Creating a new invoice from a purchase order</span></span>

<span data-ttu-id="6eb22-125">Puede crear una nueva factura de proveedor seleccionando la acción **Nueva** en el espacio de trabajo de **Facturación de colaboración de proveedor**.</span><span class="sxs-lookup"><span data-stu-id="6eb22-125">You can create a new vendor invoice by selecting the **New** action on the **Vendor collaboration invoicing** workspace.</span></span> <span data-ttu-id="6eb22-126">El proveedor debe proporcionar el número de pedido de compra y de factura.</span><span class="sxs-lookup"><span data-stu-id="6eb22-126">The purchase order number and invoice number must be provided by the vendor.</span></span> <span data-ttu-id="6eb22-127">De forma predeterminada, todas las líneas de pedido de compra del proveedor aparecerán en la nueva factura.</span><span class="sxs-lookup"><span data-stu-id="6eb22-127">By default, all of the lines from the vendor's purchase order will appear on the new invoice.</span></span> <span data-ttu-id="6eb22-128">La información sobre cantidad y coste se puede editar antes de enviar la factura de proveedor al flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6eb22-128">The quantity and cost information can be edited prior to submitting the vendor invoice to workflow.</span></span> <span data-ttu-id="6eb22-129">Puede adjuntar archivos, notas, imágenes y direcciones URL a una factura antes de enviarla.</span><span class="sxs-lookup"><span data-stu-id="6eb22-129">You can attach files, notes, images, and URLs to an invoice before submitting it.</span></span>

<span data-ttu-id="6eb22-130">Para obtener más información, consulte [Colaboración de proveedor con proveedores externos](../../supply-chain/procurement/vendor-collaboration-work-external-vendors.md)</span><span class="sxs-lookup"><span data-stu-id="6eb22-130">For more information, see [Vendor collaboration with external vendors](../../supply-chain/procurement/vendor-collaboration-work-external-vendors.md)</span></span>


