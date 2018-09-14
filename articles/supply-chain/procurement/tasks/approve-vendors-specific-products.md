--- 
title: "Aprobar proveedores para productos específicos"
description: "Este procedimiento le muestra cómo aprobar los proveedores para los productos específicos."
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDetailsExtended, PdsApprovedVendorList, VendTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 8f2cd1badb0b924150ab51ef2efc049e6666562a
ms.contentlocale: es-es
ms.lasthandoff: 09/14/2018

---
# <a name="approve-vendors-for-specific-products"></a><span data-ttu-id="c12ca-103">Aprobar proveedores para productos específicos</span><span class="sxs-lookup"><span data-stu-id="c12ca-103">Approve vendors for specific products</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c12ca-104">Este procedimiento le muestra cómo aprobar los proveedores para los productos específicos.</span><span class="sxs-lookup"><span data-stu-id="c12ca-104">This procedure shows you how to approve vendors for specific products.</span></span> <span data-ttu-id="c12ca-105">Esto le permite controlar qué proveedores se pueden usar cuando el producto se agrega a un pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="c12ca-105">This allows you to control which vendors can be used when the product is added to a purchase order.</span></span> <span data-ttu-id="c12ca-106">Puede utilizar este procedimiento con los datos de prueba de la empresa USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="c12ca-106">You can use this procedure in demo data company USMF, or on your own data.</span></span> <span data-ttu-id="c12ca-107">Esta tarea la realizará normalmente un director de compras.</span><span class="sxs-lookup"><span data-stu-id="c12ca-107">This task would typically be carried out by a Purchasing manager.</span></span>

1. <span data-ttu-id="c12ca-108">Vaya a Gestión de información de productos > Productos > Productos emitidos.</span><span class="sxs-lookup"><span data-stu-id="c12ca-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="c12ca-109">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="c12ca-109">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="c12ca-110">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c12ca-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="c12ca-111">Expanda la sección Compra.</span><span class="sxs-lookup"><span data-stu-id="c12ca-111">Expand the Purchase section.</span></span>
    * <span data-ttu-id="c12ca-112">Si hay un proveedor principal que se muestra en el campo Proveedor, necesita agregar este proveedor como proveedor aprobado en los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="c12ca-112">If there is a primary vendor shown in the Vendor field, then you need to add this vendor as an approved vendor in the following steps.</span></span> <span data-ttu-id="c12ca-113">Anote el número del proveedor, si se muestra uno.</span><span class="sxs-lookup"><span data-stu-id="c12ca-113">Make a note of the vendor number, if one is shown.</span></span>  
5. <span data-ttu-id="c12ca-114">En el panel de acciones, haga clic en Compra.</span><span class="sxs-lookup"><span data-stu-id="c12ca-114">On the Action Pane, click Purchase.</span></span>
6. <span data-ttu-id="c12ca-115">Haga clic en Configurar.</span><span class="sxs-lookup"><span data-stu-id="c12ca-115">Click Setup.</span></span>
7. <span data-ttu-id="c12ca-116">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="c12ca-116">Click Add.</span></span>
8. <span data-ttu-id="c12ca-117">En el campo Proveedor, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c12ca-117">In the Vendor field, enter or select a value.</span></span>
    * <span data-ttu-id="c12ca-118">Seleccione el proveedor aprobado.</span><span class="sxs-lookup"><span data-stu-id="c12ca-118">Select the approved vendor.</span></span> <span data-ttu-id="c12ca-119">Al menos una de las líneas tiene que ser el proveedor principal si hubo una en el registro de producto.</span><span class="sxs-lookup"><span data-stu-id="c12ca-119">At least one of the lines has to be the primary vendor if there was one in the product record.</span></span> <span data-ttu-id="c12ca-120">Si ha anotó el número del proveedor antes, selecciónelo aquí.</span><span class="sxs-lookup"><span data-stu-id="c12ca-120">If you made a note of the vendor number earlier, select it here.</span></span>  
9. <span data-ttu-id="c12ca-121">En el campo Caducidad, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="c12ca-121">In the Expiration field, enter a date.</span></span>
    * <span data-ttu-id="c12ca-122">Elija una fecha que se encuentre unos meses en el futuro.</span><span class="sxs-lookup"><span data-stu-id="c12ca-122">Choose a date a that is a few months ahead.</span></span>  
10. <span data-ttu-id="c12ca-123">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="c12ca-123">Click Add.</span></span>
11. <span data-ttu-id="c12ca-124">En el campo Proveedor, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c12ca-124">In the Vendor field, enter or select a value.</span></span>
12. <span data-ttu-id="c12ca-125">En el campo Caducidad, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="c12ca-125">In the Expiration field, enter a date.</span></span>
    * <span data-ttu-id="c12ca-126">Elija una fecha que sea diferente de la fecha de vencimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="c12ca-126">Choose a date that is different than the previous expiration date.</span></span>  
13. <span data-ttu-id="c12ca-127">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c12ca-127">Close the page.</span></span>
14. <span data-ttu-id="c12ca-128">Haga clic en Proveedores aprobados.</span><span class="sxs-lookup"><span data-stu-id="c12ca-128">Click Approved vendors.</span></span>
15. <span data-ttu-id="c12ca-129">En el campo Caducidad, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="c12ca-129">In the Expiration field, enter a date.</span></span>
    * <span data-ttu-id="c12ca-130">Esta fecha actúa como filtro para que puede ver quiénes son los proveedores aprobados, hasta una fecha concreta.</span><span class="sxs-lookup"><span data-stu-id="c12ca-130">This date acts as a filter so you can see who the approved vendors are, up to a certain date.</span></span>  
16. <span data-ttu-id="c12ca-131">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c12ca-131">Close the page.</span></span>
17. <span data-ttu-id="c12ca-132">Haga clic en Período de vigencia.</span><span class="sxs-lookup"><span data-stu-id="c12ca-132">Click Effective period.</span></span>
18. <span data-ttu-id="c12ca-133">En el campo Mostrar proveedores expirados por, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="c12ca-133">In the Show vendors expired by field, enter a date.</span></span>
    * <span data-ttu-id="c12ca-134">Puede usar esta página para identificar proveedores donde el estado de aprobación expirará después de una fecha concreta.</span><span class="sxs-lookup"><span data-stu-id="c12ca-134">You can use this page to identify vendors where the approval status will expire after a certain date.</span></span>  
19. <span data-ttu-id="c12ca-135">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c12ca-135">Close the page.</span></span>
20. <span data-ttu-id="c12ca-136">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="c12ca-136">Click Edit.</span></span>
21. <span data-ttu-id="c12ca-137">En el campo Método de comprobación de proveedor aprobado, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="c12ca-137">In the Approved vendor check method field, select an option.</span></span>
    * <span data-ttu-id="c12ca-138">Este campo le permite seleccionar la directiva para lo que debería ocurrir si se agrega el producto a una línea de pedido de compra donde el proveedor no es un proveedor aprobado.</span><span class="sxs-lookup"><span data-stu-id="c12ca-138">This field allows you to select the policy for what should happen if the product is added to a purchase order line where the vendor is not an approved vendor.</span></span>  
22. <span data-ttu-id="c12ca-139">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="c12ca-139">Click Save.</span></span>
23. <span data-ttu-id="c12ca-140">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c12ca-140">Close the page.</span></span>
24. <span data-ttu-id="c12ca-141">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c12ca-141">Close the page.</span></span>
25. <span data-ttu-id="c12ca-142">Vaya a Adquisición y abastecimiento > Proveedores > Relaciones proveedor/artículo > Lista de proveedores aprobados por artículo.</span><span class="sxs-lookup"><span data-stu-id="c12ca-142">Go to Procurement and sourcing > Vendors > Vendor/item relations > Approved vendor list by item.</span></span>
    * <span data-ttu-id="c12ca-143">Esta página le proporciona una visión general de todos los productos y los proveedores aprobados.</span><span class="sxs-lookup"><span data-stu-id="c12ca-143">This page gives you an overview of all products and the approved vendors.</span></span>  
26. <span data-ttu-id="c12ca-144">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c12ca-144">Close the page.</span></span>
27. <span data-ttu-id="c12ca-145">Vaya a Adquisición y abastecimiento > Proveedores > Todos los proveedores.</span><span class="sxs-lookup"><span data-stu-id="c12ca-145">Go to Procurement and sourcing > Vendors > All vendors.</span></span>
    * <span data-ttu-id="c12ca-146">También puede empezar desde un proveedor y después ir a la lista de productos aprobados para dicha cuenta de proveedor.</span><span class="sxs-lookup"><span data-stu-id="c12ca-146">You can also start from a vendor and then go to the list of approved products for that vendor account.</span></span>  
28. <span data-ttu-id="c12ca-147">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="c12ca-147">In the list, find and select the desired record.</span></span>
29. <span data-ttu-id="c12ca-148">En el panel de acciones, haga clic en Adquisición.</span><span class="sxs-lookup"><span data-stu-id="c12ca-148">On the Action Pane, click Procurement.</span></span>
30. <span data-ttu-id="c12ca-149">Haga clic en Lista de proveedores aprobados por proveedor.</span><span class="sxs-lookup"><span data-stu-id="c12ca-149">Click Approved vendor list by vendor.</span></span>
31. <span data-ttu-id="c12ca-150">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c12ca-150">Close the page.</span></span>
32. <span data-ttu-id="c12ca-151">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c12ca-151">Close the page.</span></span>


