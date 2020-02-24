---
title: Conciliar el flete manualmente
description: Este procedimiento muestra cómo conciliar el flete manualmente.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, TMSFreightBillDetail, TMSInvoiceTable, TMSFreightBillInvoiceReconcile, TMSInvoiceJournal, LedgerJournalTable, LedgerJournalTransDaily
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ec17fc31df1daed943f9bc3f4cbe25a683c8ac7e
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2020
ms.locfileid: "3026323"
---
# <a name="reconcile-freight-manually"></a><span data-ttu-id="7e1ba-103">Conciliar el flete manualmente</span><span class="sxs-lookup"><span data-stu-id="7e1ba-103">Reconcile freight manually</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7e1ba-104">Este procedimiento muestra cómo conciliar el flete manualmente.</span><span class="sxs-lookup"><span data-stu-id="7e1ba-104">This procedure shows how to reconcile freight manually.</span></span> <span data-ttu-id="7e1ba-105">Esto lo hace normalmente el coordinador de transporte.</span><span class="sxs-lookup"><span data-stu-id="7e1ba-105">This is typically done by a transportation coordinator.</span></span> <span data-ttu-id="7e1ba-106">Puede utilizar este procedimiento en la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="7e1ba-106">You can use this procedure in the USMF demo data company.</span></span>


## <a name="select-a-load-to-reconcile"></a><span data-ttu-id="7e1ba-107">Seleccione una carga para conciliar</span><span class="sxs-lookup"><span data-stu-id="7e1ba-107">Select a load to reconcile</span></span>
1. <span data-ttu-id="7e1ba-108">Vaya a Administración de transporte > Planificación > Área de trabajo de planificación de la carga.</span><span class="sxs-lookup"><span data-stu-id="7e1ba-108">Go to Transportation management > Planning > Load planning workbench.</span></span>
2. <span data-ttu-id="7e1ba-109">Desactive la casilla Ocultar enviado y recibido.</span><span class="sxs-lookup"><span data-stu-id="7e1ba-109">Clear the Hide shipped and received check box.</span></span> 
3. <span data-ttu-id="7e1ba-110">En la lista, seleccione el flete que tiene el identificador de carga 00006.</span><span class="sxs-lookup"><span data-stu-id="7e1ba-110">In the list, select the load that has load ID 00006.</span></span>

## <a name="create-a-carrier-invoice"></a><span data-ttu-id="7e1ba-111">Cree una factura de transportista</span><span class="sxs-lookup"><span data-stu-id="7e1ba-111">Create a carrier invoice</span></span>
<span data-ttu-id="7e1ba-112">Si se concilia el flete manualmente y no recibe facturas de transportista automáticamente, puede crear una factura basada en el albarán de flete.</span><span class="sxs-lookup"><span data-stu-id="7e1ba-112">If you reconcile freight manually and don’t receive carrier invoices automatically, you can create an invoice based on the freight bill.</span></span>  
1. <span data-ttu-id="7e1ba-113">Haga clic en Información relacionada.</span><span class="sxs-lookup"><span data-stu-id="7e1ba-113">Click Related information.</span></span>
2. <span data-ttu-id="7e1ba-114">Haga clic en Detalles del albarán de flete.</span><span class="sxs-lookup"><span data-stu-id="7e1ba-114">Click Freight bill details.</span></span>
3. <span data-ttu-id="7e1ba-115">Haga clic en Generar factura de albarán de flete.</span><span class="sxs-lookup"><span data-stu-id="7e1ba-115">Click Generate freight bill invoice.</span></span>
4. <span data-ttu-id="7e1ba-116">En el campo Factura, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7e1ba-116">In the Invoice field, type a value.</span></span>
5. <span data-ttu-id="7e1ba-117">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="7e1ba-117">Click OK.</span></span>

## <a name="reconcile-the-invoice"></a><span data-ttu-id="7e1ba-118">Concilie la factura</span><span class="sxs-lookup"><span data-stu-id="7e1ba-118">Reconcile the invoice</span></span>
<span data-ttu-id="7e1ba-119">La conciliación de una factura de transportista y un albarán de flete se realiza línea por línea.</span><span class="sxs-lookup"><span data-stu-id="7e1ba-119">When you reconcile a carrier invoice and a freight bill, this is done line by line.</span></span>  
1. <span data-ttu-id="7e1ba-120">Haga clic en Conciliar los albaranes de flete y las facturas.</span><span class="sxs-lookup"><span data-stu-id="7e1ba-120">Click Match freight bills and invoices.</span></span>
2. <span data-ttu-id="7e1ba-121">Expanda la sección Detalles de factura.</span><span class="sxs-lookup"><span data-stu-id="7e1ba-121">Expand the Invoice details section.</span></span>
3. <span data-ttu-id="7e1ba-122">Expanda la sección Detalles del albarán de flete no conciliado.</span><span class="sxs-lookup"><span data-stu-id="7e1ba-122">Expand the Unmatched freight bill details section.</span></span>
4. <span data-ttu-id="7e1ba-123">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="7e1ba-123">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="7e1ba-124">Haga clic en Conciliar.</span><span class="sxs-lookup"><span data-stu-id="7e1ba-124">Click Match.</span></span>
6. <span data-ttu-id="7e1ba-125">Expanda la sección Detalles del albarán de flete conciliado.</span><span class="sxs-lookup"><span data-stu-id="7e1ba-125">Expand the Matched freight bill details section.</span></span>

## <a name="submit-the-invoice-for-approval"></a><span data-ttu-id="7e1ba-126">Enviar la factura para su aprobación</span><span class="sxs-lookup"><span data-stu-id="7e1ba-126">Submit the invoice for approval</span></span>
1. <span data-ttu-id="7e1ba-127">Haga clic en Enviar para aprobación.</span><span class="sxs-lookup"><span data-stu-id="7e1ba-127">Click Submit for approval.</span></span>
2. <span data-ttu-id="7e1ba-128">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="7e1ba-128">Close the page.</span></span>
3. <span data-ttu-id="7e1ba-129">Borre la casilla Ocultar elementos aprobados.</span><span class="sxs-lookup"><span data-stu-id="7e1ba-129">Clear the Hide approved check box.</span></span> 
4. <span data-ttu-id="7e1ba-130">Haga clic en Diarios de facturas de proveedor.</span><span class="sxs-lookup"><span data-stu-id="7e1ba-130">Click Vendor invoice journals.</span></span>
5. <span data-ttu-id="7e1ba-131">Haga clic para seguir el vínculo en el campo Número de diario de referencia.</span><span class="sxs-lookup"><span data-stu-id="7e1ba-131">Click to follow the link in the Reference journal number field.</span></span>
6. <span data-ttu-id="7e1ba-132">Haga clic en Líneas.</span><span class="sxs-lookup"><span data-stu-id="7e1ba-132">Click Lines.</span></span>

