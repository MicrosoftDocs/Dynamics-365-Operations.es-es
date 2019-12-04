---
title: EUR-00002 Especificación de una dirección de embarque para una transacción intracomunitaria
description: Este procedimiento muestra cómo especificar una dirección de embarque para una transacción de comercio intracomunitario.
author: v-oloski
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, TransportationDocument, LogisticsPostalAddress, SysLookupMultiSelectGrid,  VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog, Intrastat, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6eea2a905a59842b6f39c5b1e1c78ae6801b28e0
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2175113"
---
# <a name="eur-00002-specifying-a-lading-address-for-an-intra-community-transaction"></a><span data-ttu-id="3c032-103">EUR-00002 Especificación de una dirección de embarque para una transacción intracomunitaria</span><span class="sxs-lookup"><span data-stu-id="3c032-103">EUR-00002 Specifying a lading address for an intra-community transaction</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3c032-104">Este procedimiento muestra cómo especificar una dirección de embarque para una transacción de comercio intracomunitario.</span><span class="sxs-lookup"><span data-stu-id="3c032-104">This procedure shows how to specify a lading address for an intra-community trade transaction.</span></span> <span data-ttu-id="3c032-105">Por ejemplo, una empresa de Alemania pide artículos de un proveedor con una dirección empresarial alemana.</span><span class="sxs-lookup"><span data-stu-id="3c032-105">For example, a Germany company orders items from a vendor with a German business address.</span></span> <span data-ttu-id="3c032-106">Este proveedor tiene un almacén en Italia y envía artículos desde ahí.</span><span class="sxs-lookup"><span data-stu-id="3c032-106">This vendor has a warehouse in Italy and ships the items from there.</span></span> <span data-ttu-id="3c032-107">Esta entrega se debe notificar en Intrastat.</span><span class="sxs-lookup"><span data-stu-id="3c032-107">This delivery must be reported in the Intrastat.</span></span> <span data-ttu-id="3c032-108">El mismo comportamiento es válido para las devoluciones del cliente.</span><span class="sxs-lookup"><span data-stu-id="3c032-108">The same behavior is valid for customer returns.</span></span>
<span data-ttu-id="3c032-109">Este procedimiento se aplica a todos los países o regiones europeos.</span><span class="sxs-lookup"><span data-stu-id="3c032-109">This procedure applies to all European countries/regions.</span></span> <span data-ttu-id="3c032-110">Esta tarea se ha creado con los datos de demostración de la empresa DEMF y con una dirección principal en Alemania.</span><span class="sxs-lookup"><span data-stu-id="3c032-110">The task was created using the demo data company DEMF with a primary address in Germany.</span></span> <span data-ttu-id="3c032-111">Para poder completar este procedimiento, debe configurar los informes Intrastat.</span><span class="sxs-lookup"><span data-stu-id="3c032-111">Before you can complete this procedure, you must configure Intrastat reporting.</span></span> <span data-ttu-id="3c032-112">Este procedimiento está pensado para contables.</span><span class="sxs-lookup"><span data-stu-id="3c032-112">This procedure is intended for accountants.</span></span> <span data-ttu-id="3c032-113">Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="3c032-113">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="3c032-114">Vaya a Proveedores > Pedidos de compra > Todos los pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="3c032-114">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="3c032-115">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="3c032-115">Click New.</span></span>
3. <span data-ttu-id="3c032-116">Especifique o seleccione un valor</span><span class="sxs-lookup"><span data-stu-id="3c032-116">Enter or select a value</span></span>
    * <span data-ttu-id="3c032-117">Por ejemplo, seleccione DE-001.</span><span class="sxs-lookup"><span data-stu-id="3c032-117">For example, select DE-001.</span></span> <span data-ttu-id="3c032-118">Este proveedor tiene una dirección empresarial alemana.</span><span class="sxs-lookup"><span data-stu-id="3c032-118">This vendor has a German business address.</span></span>  
4. <span data-ttu-id="3c032-119">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="3c032-119">Click OK.</span></span>
5. <span data-ttu-id="3c032-120">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3c032-120">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="3c032-121">En el campo Número de artículo, especifique o seleccione el valor D0001.</span><span class="sxs-lookup"><span data-stu-id="3c032-121">In the Item number field, enter or select a value D0001.</span></span>
7. <span data-ttu-id="3c032-122">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="3c032-122">Click Save.</span></span>
8. <span data-ttu-id="3c032-123">En el panel de acciones, haga clic en Recibir.</span><span class="sxs-lookup"><span data-stu-id="3c032-123">On the Action Pane, click Receive.</span></span>
9. <span data-ttu-id="3c032-124">Haga clic en Detalles de transporte.</span><span class="sxs-lookup"><span data-stu-id="3c032-124">Click Transportation details.</span></span>
10. <span data-ttu-id="3c032-125">En el campo Fecha y hora de embarque, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="3c032-125">In the Loading date and time field, enter a date and time.</span></span>
11. <span data-ttu-id="3c032-126">Haga clic en Agregar dirección.</span><span class="sxs-lookup"><span data-stu-id="3c032-126">Click Add address.</span></span>
12. <span data-ttu-id="3c032-127">Haga clic en Nuevo y crear nueva dirección con propósito Embarque.</span><span class="sxs-lookup"><span data-stu-id="3c032-127">Click New and create new address with purpose Lading.</span></span>
13. <span data-ttu-id="3c032-128">En el campo Nombre o descripción, escriba "Italiano".</span><span class="sxs-lookup"><span data-stu-id="3c032-128">In the Name or description field, type 'Italian'.</span></span>
14. <span data-ttu-id="3c032-129">Seleccione Embarque como valor.</span><span class="sxs-lookup"><span data-stu-id="3c032-129">Select Lading as the value.</span></span>
    * <span data-ttu-id="3c032-130">Tenga en cuenta que el propósito de la dirección debe ser Embarque.</span><span class="sxs-lookup"><span data-stu-id="3c032-130">Note that that address purpose must be Lading.</span></span>  
15. <span data-ttu-id="3c032-131">En el campo País o región, especifique o seleccione un valor ITA.</span><span class="sxs-lookup"><span data-stu-id="3c032-131">In the Country/region field, enter or select a value ITA.</span></span>
16. <span data-ttu-id="3c032-132">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="3c032-132">Click Save.</span></span>
17. <span data-ttu-id="3c032-133">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3c032-133">Close the page.</span></span>
18. <span data-ttu-id="3c032-134">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="3c032-134">Click Save.</span></span>
    * <span data-ttu-id="3c032-135">Compruebe que la dirección de embarque es correcta.</span><span class="sxs-lookup"><span data-stu-id="3c032-135">Verify that the lading address is correct.</span></span>  
19. <span data-ttu-id="3c032-136">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3c032-136">Close the page.</span></span>
20. <span data-ttu-id="3c032-137">En el panel de acciones, haga clic en Compra.</span><span class="sxs-lookup"><span data-stu-id="3c032-137">On the Action Pane, click Purchase.</span></span>
21. <span data-ttu-id="3c032-138">Haga clic en Confirmar.</span><span class="sxs-lookup"><span data-stu-id="3c032-138">Click Confirm.</span></span>
22. <span data-ttu-id="3c032-139">En el panel de acciones, haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="3c032-139">On the Action Pane, click Invoice.</span></span>
23. <span data-ttu-id="3c032-140">Haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="3c032-140">Click Invoice.</span></span>
24. <span data-ttu-id="3c032-141">En el campo Número, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3c032-141">In the Number field, type a value.</span></span>
25. <span data-ttu-id="3c032-142">En el campo Fecha de la factura, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="3c032-142">In the Invoice date field, enter a date.</span></span>
26. <span data-ttu-id="3c032-143">Haga clic en Valor predeterminado de origen: Cantidad de recepción de producto para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="3c032-143">Click Default from: Product receipt quantity to open the drop dialog.</span></span>
27. <span data-ttu-id="3c032-144">En el campo Cantidad predeterminada para líneas, seleccione Cantidad pedida.</span><span class="sxs-lookup"><span data-stu-id="3c032-144">In the Default quantity for lines field, select 'Ordered quantity'.</span></span>
28. <span data-ttu-id="3c032-145">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="3c032-145">Click OK.</span></span>
29. <span data-ttu-id="3c032-146">Haga clic en Detalles de transporte.</span><span class="sxs-lookup"><span data-stu-id="3c032-146">Click Transportation details.</span></span>
    * <span data-ttu-id="3c032-147">Compruebe que las mercancías se envían desde Italia.</span><span class="sxs-lookup"><span data-stu-id="3c032-147">Verify that goods were shipped from Italy.</span></span> <span data-ttu-id="3c032-148">En caso necesario, puede editar los detalles de embarque.</span><span class="sxs-lookup"><span data-stu-id="3c032-148">If necessary, you can edit the lading details.</span></span>  
30. <span data-ttu-id="3c032-149">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3c032-149">Close the page.</span></span>
31. <span data-ttu-id="3c032-150">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="3c032-150">Click Post.</span></span>
32. <span data-ttu-id="3c032-151">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3c032-151">Close the page.</span></span>
33. <span data-ttu-id="3c032-152">Vaya a Impuestos > Declaraciones > Comercio exterior > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="3c032-152">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
34. <span data-ttu-id="3c032-153">Haga clic en Transferir.</span><span class="sxs-lookup"><span data-stu-id="3c032-153">Click Transfer.</span></span>
35. <span data-ttu-id="3c032-154">Seleccione Sí en el campo Factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="3c032-154">Select Yes in the Vendor invoice field.</span></span>
36. <span data-ttu-id="3c032-155">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="3c032-155">Click OK.</span></span>
37. <span data-ttu-id="3c032-156">Haga clic en la pestaña General.</span><span class="sxs-lookup"><span data-stu-id="3c032-156">Click the General tab.</span></span>
    * <span data-ttu-id="3c032-157">Busque una línea recién creada y compruebe que el remitente envió las mercancías desde Italia.</span><span class="sxs-lookup"><span data-stu-id="3c032-157">Find a newly created line and verify that the sender shipped the goods from Italy.</span></span>  
