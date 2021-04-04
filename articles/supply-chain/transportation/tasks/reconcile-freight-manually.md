---
title: Conciliar el flete manualmente
description: Este procedimiento muestra cómo conciliar el flete manualmente.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, TMSFreightBillDetail, TMSInvoiceTable, TMSFreightBillInvoiceReconcile, TMSInvoiceJournal, LedgerJournalTable, LedgerJournalTransDaily, TMSFBDetailReconcile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: becda50b5d176ceb350c471b154aed1842c31a3b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5247199"
---
# <a name="reconcile-freight-manually"></a><span data-ttu-id="a0952-103">Conciliar el flete manualmente</span><span class="sxs-lookup"><span data-stu-id="a0952-103">Reconcile freight manually</span></span>

<span data-ttu-id="a0952-104">[!include [banner](../../includes/banner.md)]]</span><span class="sxs-lookup"><span data-stu-id="a0952-104">[!include [banner](../../includes/banner.md)]]</span></span>

<span data-ttu-id="a0952-105">Este procedimiento muestra cómo conciliar el flete manualmente.</span><span class="sxs-lookup"><span data-stu-id="a0952-105">This procedure shows how to reconcile freight manually.</span></span> <span data-ttu-id="a0952-106">Esto lo hace normalmente el coordinador de transporte.</span><span class="sxs-lookup"><span data-stu-id="a0952-106">This is typically done by a transportation coordinator.</span></span> <span data-ttu-id="a0952-107">Puede utilizar este procedimiento en la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="a0952-107">You can use this procedure in the USMF demo data company.</span></span>


## <a name="select-a-load-to-reconcile"></a><span data-ttu-id="a0952-108">Seleccione una carga para conciliar</span><span class="sxs-lookup"><span data-stu-id="a0952-108">Select a load to reconcile</span></span>
1. <span data-ttu-id="a0952-109">Vaya a Administración de transporte > Planificación > Área de trabajo de planificación de la carga.</span><span class="sxs-lookup"><span data-stu-id="a0952-109">Go to Transportation management > Planning > Load planning workbench.</span></span>
2. <span data-ttu-id="a0952-110">Desactive la casilla Ocultar enviado y recibido.</span><span class="sxs-lookup"><span data-stu-id="a0952-110">Clear the Hide shipped and received check box.</span></span> 
3. <span data-ttu-id="a0952-111">En la lista, seleccione el flete que tiene el identificador de carga 00006.</span><span class="sxs-lookup"><span data-stu-id="a0952-111">In the list, select the load that has load ID 00006.</span></span>

## <a name="create-a-carrier-invoice"></a><span data-ttu-id="a0952-112">Cree una factura de transportista</span><span class="sxs-lookup"><span data-stu-id="a0952-112">Create a carrier invoice</span></span>
<span data-ttu-id="a0952-113">Si se concilia el flete manualmente y no recibe facturas de transportista automáticamente, puede crear una factura basada en el albarán de flete.</span><span class="sxs-lookup"><span data-stu-id="a0952-113">If you reconcile freight manually and don't receive carrier invoices automatically, you can create an invoice based on the freight bill.</span></span>  
1. <span data-ttu-id="a0952-114">Haga clic en Información relacionada.</span><span class="sxs-lookup"><span data-stu-id="a0952-114">Click Related information.</span></span>
2. <span data-ttu-id="a0952-115">Haga clic en Detalles del albarán de flete.</span><span class="sxs-lookup"><span data-stu-id="a0952-115">Click Freight bill details.</span></span>
3. <span data-ttu-id="a0952-116">Haga clic en Generar factura de albarán de flete.</span><span class="sxs-lookup"><span data-stu-id="a0952-116">Click Generate freight bill invoice.</span></span>
4. <span data-ttu-id="a0952-117">En el campo Factura, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="a0952-117">In the Invoice field, type a value.</span></span>
5. <span data-ttu-id="a0952-118">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a0952-118">Click OK.</span></span>

## <a name="reconcile-the-invoice"></a><span data-ttu-id="a0952-119">Concilie la factura</span><span class="sxs-lookup"><span data-stu-id="a0952-119">Reconcile the invoice</span></span>
<span data-ttu-id="a0952-120">La conciliación de una factura de transportista y un albarán de flete se realiza línea por línea.</span><span class="sxs-lookup"><span data-stu-id="a0952-120">When you reconcile a carrier invoice and a freight bill, this is done line by line.</span></span>  
1. <span data-ttu-id="a0952-121">Haga clic en Conciliar los albaranes de flete y las facturas.</span><span class="sxs-lookup"><span data-stu-id="a0952-121">Click Match freight bills and invoices.</span></span>
2. <span data-ttu-id="a0952-122">Expanda la sección Detalles de factura.</span><span class="sxs-lookup"><span data-stu-id="a0952-122">Expand the Invoice details section.</span></span>
3. <span data-ttu-id="a0952-123">Expanda la sección Detalles del albarán de flete no conciliado.</span><span class="sxs-lookup"><span data-stu-id="a0952-123">Expand the Unmatched freight bill details section.</span></span>
4. <span data-ttu-id="a0952-124">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a0952-124">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="a0952-125">Haga clic en Conciliar.</span><span class="sxs-lookup"><span data-stu-id="a0952-125">Click Match.</span></span>
6. <span data-ttu-id="a0952-126">Expanda la sección Detalles del albarán de flete conciliado.</span><span class="sxs-lookup"><span data-stu-id="a0952-126">Expand the Matched freight bill details section.</span></span>

## <a name="submit-the-invoice-for-approval"></a><span data-ttu-id="a0952-127">Enviar la factura para su aprobación</span><span class="sxs-lookup"><span data-stu-id="a0952-127">Submit the invoice for approval</span></span>
1. <span data-ttu-id="a0952-128">Haga clic en Enviar para aprobación.</span><span class="sxs-lookup"><span data-stu-id="a0952-128">Click Submit for approval.</span></span>
2. <span data-ttu-id="a0952-129">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="a0952-129">Close the page.</span></span>
3. <span data-ttu-id="a0952-130">Borre la casilla Ocultar elementos aprobados.</span><span class="sxs-lookup"><span data-stu-id="a0952-130">Clear the Hide approved check box.</span></span> 
4. <span data-ttu-id="a0952-131">Haga clic en Diarios de facturas de proveedor.</span><span class="sxs-lookup"><span data-stu-id="a0952-131">Click Vendor invoice journals.</span></span>
5. <span data-ttu-id="a0952-132">Haga clic para seguir el vínculo en el campo Número de diario de referencia.</span><span class="sxs-lookup"><span data-stu-id="a0952-132">Click to follow the link in the Reference journal number field.</span></span>
6. <span data-ttu-id="a0952-133">Haga clic en Líneas.</span><span class="sxs-lookup"><span data-stu-id="a0952-133">Click Lines.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]