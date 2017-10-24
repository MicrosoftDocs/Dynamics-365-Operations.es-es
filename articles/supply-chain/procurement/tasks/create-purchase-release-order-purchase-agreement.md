--- 
title: Crear un pedido parcial de compra de un acuerdo de compra
description: "Este procedimiento muestra cómo usar un acuerdo de compra cuando se crea un pedido de compra."
author: mkirknel
manager: AnnBe
ms.date: 12/04/2015
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: cecda03dd4d224d4319f2b0b196560389bb54195
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-purchase-release-order-from-a-purchase-agreement"></a><span data-ttu-id="ff1c9-103">Crear un pedido parcial de compra de un acuerdo de compra</span><span class="sxs-lookup"><span data-stu-id="ff1c9-103">Create a purchase release order from a purchase agreement</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ff1c9-104">Este procedimiento muestra cómo usar un acuerdo de compra cuando se crea un pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="ff1c9-104">This procedure shows how to use a purchase agreement when you create a purchase order.</span></span> <span data-ttu-id="ff1c9-105">El acuerdo de compra se tiene que aplicar en el momento de crear el pedido de compra, ya que hay condiciones generales que se deben copiar al encabezado del pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="ff1c9-105">The purchase agreement has to be applied when you create the purchase order because there are general terms that should be copied to the purchase order header.</span></span> <span data-ttu-id="ff1c9-106">Esta tarea la realizará normalmente el agente de compras.</span><span class="sxs-lookup"><span data-stu-id="ff1c9-106">Typically this task would be carried out by a purchasing agent.</span></span> <span data-ttu-id="ff1c9-107">Como requisito previo para este procedimiento, debe tener un acuerdo de compra en vigor con un compromiso de cantidad de productos para un proveedor y para artículos.</span><span class="sxs-lookup"><span data-stu-id="ff1c9-107">As a prerequisite for this guide, you must have an effective purchase agreement with a product quantity commitment for a vendor and items.</span></span> <span data-ttu-id="ff1c9-108">El mismo procedimiento puede usarse si tiene un acuerdo de compra con otros tipos de compromisos.</span><span class="sxs-lookup"><span data-stu-id="ff1c9-108">The same procedure can be used if you have a purchase agreement with other types of commitments.</span></span> <span data-ttu-id="ff1c9-109">Puede ejecutar esta guía en la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="ff1c9-109">You can run this guide in demo data company USMF.</span></span> <span data-ttu-id="ff1c9-110">Si está usando USMF, puede ejecutar el procedimiento "Creación de un acuerdo de compra" primero para establecer las condiciones previas necesarias para este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="ff1c9-110">If you’re using USMF, you can run the “Create a purchase agreement” guide first to set up the necessary preconditions for this guide.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="ff1c9-111">Crear un pedido de compra</span><span class="sxs-lookup"><span data-stu-id="ff1c9-111">Create a purchase order</span></span>
1. <span data-ttu-id="ff1c9-112">Apertura del espacio de trabajo de preparación del pedido de compra</span><span class="sxs-lookup"><span data-stu-id="ff1c9-112">Open the purchase order preparation workspace.</span></span>
2. <span data-ttu-id="ff1c9-113">Haga clic en Nuevo pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="ff1c9-113">Click New purchase order.</span></span>
3. <span data-ttu-id="ff1c9-114">En el campo Cuenta de proveedor, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ff1c9-114">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="ff1c9-115">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="ff1c9-115">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="ff1c9-116">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ff1c9-116">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="ff1c9-117">Expanda la sección General.</span><span class="sxs-lookup"><span data-stu-id="ff1c9-117">Toggle the expansion of the General section.</span></span>
7. <span data-ttu-id="ff1c9-118">En el campo Acuerdo de compra, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ff1c9-118">In the Purchase agreement field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ff1c9-119">Todos los acuerdos disponibles para el proveedor se muestran aquí.</span><span class="sxs-lookup"><span data-stu-id="ff1c9-119">All available agreements for the vendor are listed here.</span></span> <span data-ttu-id="ff1c9-120">Localice el acuerdo en vigor que desee utilizar.</span><span class="sxs-lookup"><span data-stu-id="ff1c9-120">Find the effective agreement that you want to use.</span></span>  
8. <span data-ttu-id="ff1c9-121">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ff1c9-121">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="ff1c9-122">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="ff1c9-122">Click Yes.</span></span>
10. <span data-ttu-id="ff1c9-123">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="ff1c9-123">Click OK.</span></span>

## <a name="add-a-line"></a><span data-ttu-id="ff1c9-124">Adición de una línea</span><span class="sxs-lookup"><span data-stu-id="ff1c9-124">Add a line</span></span>
1. <span data-ttu-id="ff1c9-125">En el campo Código de artículo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="ff1c9-125">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="ff1c9-126">Si hay dimensiones de inventario o de ubicación específicas en el compromiso, debe especificar los mismos valores en la línea de pedido de compra para poder usar el acuerdo.</span><span class="sxs-lookup"><span data-stu-id="ff1c9-126">If there are specific inventory or location dimensions on the commitment you must enter the same values on the purchase order line to make use of the agreement.</span></span>  
2. <span data-ttu-id="ff1c9-127">En el campo Sitio, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ff1c9-127">In the Site field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ff1c9-128">El sitio puede ya haberse cumplimentado con el valor predeterminado del pedido, o del proveedor.</span><span class="sxs-lookup"><span data-stu-id="ff1c9-128">The site may already be populated with the default value from the order, or from the vendor.</span></span> <span data-ttu-id="ff1c9-129">En tal caso, omita este paso.</span><span class="sxs-lookup"><span data-stu-id="ff1c9-129">If this is the case, skip this step.</span></span>  
3. <span data-ttu-id="ff1c9-130">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="ff1c9-130">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="ff1c9-131">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ff1c9-131">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="ff1c9-132">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="ff1c9-132">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="ff1c9-133">Verifique que el precio se haya copiado del compromiso.</span><span class="sxs-lookup"><span data-stu-id="ff1c9-133">Validate that the price is copied from the commitment.</span></span>  

## <a name="look-up-the-commitment"></a><span data-ttu-id="ff1c9-134">Búsqueda del compromiso</span><span class="sxs-lookup"><span data-stu-id="ff1c9-134">Look up the commitment</span></span>
1. <span data-ttu-id="ff1c9-135">Haga clic en Actualizar línea.</span><span class="sxs-lookup"><span data-stu-id="ff1c9-135">Click Update line.</span></span>
2. <span data-ttu-id="ff1c9-136">Haga clic en Adjunto.</span><span class="sxs-lookup"><span data-stu-id="ff1c9-136">Click Attached.</span></span>
    * <span data-ttu-id="ff1c9-137">Aquí puede obtener los detalles del acuerdo de compra.</span><span class="sxs-lookup"><span data-stu-id="ff1c9-137">Here you can get details for the purchase agreement.</span></span> <span data-ttu-id="ff1c9-138">Por ejemplo, puede ver el precio y si el precio y el descuento son fijos, lo que significa que, si cambia precios o descuentos en el pedido de compra a un valor diferente que en el compromiso, el sistema quitará el vínculo de modo que la línea de pedido de compra no satisfaga el compromiso.</span><span class="sxs-lookup"><span data-stu-id="ff1c9-138">For example, you can see the price and whether the price and discount are fixed, which means that if you change price or discount on the purchase order to a different value than on the commitment, the system will remove the link so the purchase order line does not fulfill the commitment.</span></span> <span data-ttu-id="ff1c9-139">También puede ver si está seleccionada la opción Máximo aplicado, lo que significa que la cantidad en el compromiso no puede sobrepasarse sumando todas las compras que satisfacen el compromiso.</span><span class="sxs-lookup"><span data-stu-id="ff1c9-139">You can also see if the Max is enforced option is selected, which means that the quantity on the commitment cannot be exceeded by summing all of the purchases that fulfill the commitment.</span></span>  
3. <span data-ttu-id="ff1c9-140">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ff1c9-140">Close the page.</span></span>

## <a name="look-up-the-purchase-agreement"></a><span data-ttu-id="ff1c9-141">Búsqueda del acuerdo de compra</span><span class="sxs-lookup"><span data-stu-id="ff1c9-141">Look up the purchase agreement</span></span>
1. <span data-ttu-id="ff1c9-142">En el panel de acciones, haga clic en General.</span><span class="sxs-lookup"><span data-stu-id="ff1c9-142">On the Action Pane, click General.</span></span>
2. <span data-ttu-id="ff1c9-143">Haga clic en Acuerdo de compra.</span><span class="sxs-lookup"><span data-stu-id="ff1c9-143">Click Purchase agreement.</span></span>
3. <span data-ttu-id="ff1c9-144">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ff1c9-144">Close the page.</span></span>
4. <span data-ttu-id="ff1c9-145">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ff1c9-145">Close the page.</span></span>


