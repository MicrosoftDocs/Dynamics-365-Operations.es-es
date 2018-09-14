--- 
title: Crear un acuerdo de compra
description: "Este procedimiento le guía por el proceso de creación de un acuerdo de compra."
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchAgreement, PurchAgreementCreate, InventItemIdLookupSimple, AgreementConfirmRunForm, PurchAgreementHistory
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: b317f0a0fc8f198bad9501f325557ac2a4796989
ms.contentlocale: es-es
ms.lasthandoff: 09/14/2018

---
# <a name="create-a-purchase-agreement"></a><span data-ttu-id="e16b5-103">Crear un acuerdo de compra</span><span class="sxs-lookup"><span data-stu-id="e16b5-103">Create a purchase agreement</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e16b5-104">Este procedimiento le guía por el proceso de creación de un acuerdo de compra.</span><span class="sxs-lookup"><span data-stu-id="e16b5-104">This procedure guides you through the creation of a purchase agreement.</span></span> <span data-ttu-id="e16b5-105">Esto normalmente lo haría el director de compras.</span><span class="sxs-lookup"><span data-stu-id="e16b5-105">This would typically be done by a purchasing manager.</span></span> <span data-ttu-id="e16b5-106">Puede utilizar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="e16b5-106">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="e16b5-107">Es necesario haber configurado clasificaciones de acuerdo de compra antes de comenzar.</span><span class="sxs-lookup"><span data-stu-id="e16b5-107">You need to have set up purchase agreement classifications before you start.</span></span> <span data-ttu-id="e16b5-108">Una vez que haya creado un acuerdo, podrá usarlo cuando cree un pedido de compra; esto copiará las condiciones del acuerdo de compra al encabezado y a cualquier línea del pedido a la que afecte el acuerdo.</span><span class="sxs-lookup"><span data-stu-id="e16b5-108">Once you've created an agreement you can use it when you create a PO, and this will copy the purchase agreement conditions to the header and to any lines in the order that are affected by the agreement.</span></span>


## <a name="create-a-new-purchase-agreement"></a><span data-ttu-id="e16b5-109">Creación de un acuerdo de compra nuevo</span><span class="sxs-lookup"><span data-stu-id="e16b5-109">Create a new purchase agreement</span></span>
1. <span data-ttu-id="e16b5-110">Vaya a Adquisición y abastecimiento > Acuerdos de compra > Acuerdos de compra.</span><span class="sxs-lookup"><span data-stu-id="e16b5-110">Go to Procurement and sourcing > Purchase agreements > Purchase agreements.</span></span>
2. <span data-ttu-id="e16b5-111">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="e16b5-111">Click New.</span></span>
3. <span data-ttu-id="e16b5-112">En el campo Cuenta de proveedor, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e16b5-112">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="e16b5-113">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="e16b5-113">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="e16b5-114">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e16b5-114">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="e16b5-115">En el campo Clasificación del acuerdo de compra, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e16b5-115">In the Purchase agreement classification field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="e16b5-116">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="e16b5-116">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="e16b5-117">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e16b5-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="e16b5-118">Expanda la sección General.</span><span class="sxs-lookup"><span data-stu-id="e16b5-118">Expand the General section.</span></span>
10. <span data-ttu-id="e16b5-119">En el campo Fecha de caducidad, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="e16b5-119">In the Expiration date field, enter a date.</span></span>
    * <span data-ttu-id="e16b5-120">Esta fecha de vencimiento será la predeterminada para todas las líneas de compromiso, y determinará cuánto tiempo es válido cada compromiso específico.</span><span class="sxs-lookup"><span data-stu-id="e16b5-120">This expiration date will be the default for all commitment lines and will determine how long each specific commitment is valid.</span></span>  
11. <span data-ttu-id="e16b5-121">En el campo Título del documento, escriba un nombre para el acuerdo de compra.</span><span class="sxs-lookup"><span data-stu-id="e16b5-121">In the Document title field, type a name for your purchase agreement.</span></span>
    * <span data-ttu-id="e16b5-122">Deje el campo Compromiso predeterminado en Compromiso de cantidad de producto (o cámbielo si no está así establecido).</span><span class="sxs-lookup"><span data-stu-id="e16b5-122">Leave the Default commitment field set to Product quantity commitment (or change it if it’s not set to this).</span></span>  
    * <span data-ttu-id="e16b5-123">El valor de compromiso predeterminado determina las opciones en las líneas del acuerdo.</span><span class="sxs-lookup"><span data-stu-id="e16b5-123">The default commitment value determines your options on the agreement lines.</span></span> <span data-ttu-id="e16b5-124">Si necesita un nuevo tipo de compromiso al crear las líneas del acuerdo, deberá cambiar el compromiso predeterminado en la cabecera.</span><span class="sxs-lookup"><span data-stu-id="e16b5-124">If you need a new commitment type when you’re creating the agreement lines, you need to change the default commitment on the header.</span></span>  <span data-ttu-id="e16b5-125">Hay cuatro tipos de compromiso: Compromiso de cantidad de producto: para una cantidad específica de un producto; Compromiso de valor de producto: para un importe de divisa específico de un producto; Compromiso de valor de la categoría de producto: para un importe de divisa específico en una categoría de compras en la que el importe puede ser para un artículo de catálogo o un artículo no de catálogo; Compromiso de valor para un importe de divisa específico que se puede satisfacer con cualquier producto o cualquier categoría de compra.</span><span class="sxs-lookup"><span data-stu-id="e16b5-125">There are 4 types of commitments: Product quantity commitment - for a specific quantity of a product; Product value commitment - for a specific currency amount of a product; Product category value commitment - for a specific currency amount in a procurement category where the amount can be for a catalog item or a non-catalog item; Value commitment - for a specific currency amount which can be fulfilled by any product or by any procurement category.</span></span>  
12. <span data-ttu-id="e16b5-126">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="e16b5-126">Click OK.</span></span>

## <a name="add-a-commitment"></a><span data-ttu-id="e16b5-127">Adición de un comentario</span><span class="sxs-lookup"><span data-stu-id="e16b5-127">Add a commitment</span></span>
1. <span data-ttu-id="e16b5-128">Haga clic en Agregar línea.</span><span class="sxs-lookup"><span data-stu-id="e16b5-128">Click Add line.</span></span>
2. <span data-ttu-id="e16b5-129">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e16b5-129">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="e16b5-130">En el campo Código de artículo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e16b5-130">In the Item number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="e16b5-131">Seleccione el producto para el que desee agregar un compromiso.</span><span class="sxs-lookup"><span data-stu-id="e16b5-131">Select the product you want to add a commitment for.</span></span>
5. <span data-ttu-id="e16b5-132">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e16b5-132">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="e16b5-133">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="e16b5-133">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="e16b5-134">Esta es la cantidad total que el cliente ha acordado comprar del proveedor.</span><span class="sxs-lookup"><span data-stu-id="e16b5-134">This is the total quantity that you have agreed to buy from your vendor.</span></span>  
7. <span data-ttu-id="e16b5-135">En el campo Precio unitario, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="e16b5-135">In the Unit price field, enter a number.</span></span>
8. <span data-ttu-id="e16b5-136">Expanda la sección Detalles de línea.</span><span class="sxs-lookup"><span data-stu-id="e16b5-136">Expand the Line details section.</span></span>
9. <span data-ttu-id="e16b5-137">Defina la opción Máximo aplicado en Sí.</span><span class="sxs-lookup"><span data-stu-id="e16b5-137">Set the Max is enforced option to Yes.</span></span>
    * <span data-ttu-id="e16b5-138">La opción Máximo aplicado limita el uso del compromiso.</span><span class="sxs-lookup"><span data-stu-id="e16b5-138">The Max is enforced option limits the use of the commitment.</span></span> <span data-ttu-id="e16b5-139">Solo puede comprar hasta la cantidad especificada en el campo Cantidad para la línea.</span><span class="sxs-lookup"><span data-stu-id="e16b5-139">You can only purchase up to the quantity that's specified in the Quantity field for the line.</span></span>  
10. <span data-ttu-id="e16b5-140">Contraiga la sección Detalles de línea.</span><span class="sxs-lookup"><span data-stu-id="e16b5-140">Collapse the Line details section.</span></span>

## <a name="add-header-conditions"></a><span data-ttu-id="e16b5-141">Adición de condiciones de encabezado</span><span class="sxs-lookup"><span data-stu-id="e16b5-141">Add header conditions</span></span>
1. <span data-ttu-id="e16b5-142">En el panel de acciones, haga clic en Opciones.</span><span class="sxs-lookup"><span data-stu-id="e16b5-142">On the Action Pane, click Options.</span></span>
2. <span data-ttu-id="e16b5-143">Haga clic en Cambiar vista.</span><span class="sxs-lookup"><span data-stu-id="e16b5-143">Click Change view.</span></span>
3. <span data-ttu-id="e16b5-144">Haga clic en Visualización de encabezado.</span><span class="sxs-lookup"><span data-stu-id="e16b5-144">Click Header view.</span></span>
4. <span data-ttu-id="e16b5-145">Expanda la sección Condiciones.</span><span class="sxs-lookup"><span data-stu-id="e16b5-145">Expand the Terms section.</span></span>
5. <span data-ttu-id="e16b5-146">En el campo Forma de pago, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e16b5-146">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="e16b5-147">Las condiciones de pago de la cuenta del proveedor se muestran aquí de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e16b5-147">The payment terms from the vendor account are shown here by default.</span></span>       
6. <span data-ttu-id="e16b5-148">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="e16b5-148">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="e16b5-149">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e16b5-149">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="e16b5-150">En el campo Modo de entrega, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e16b5-150">In the Mode of delivery field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="e16b5-151">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e16b5-151">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="e16b5-152">En el campo Condiciones de entrega, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e16b5-152">In the Delivery terms field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="e16b5-153">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e16b5-153">In the list, click the link in the selected row.</span></span>

## <a name="confirm-and-activate-the-agreement"></a><span data-ttu-id="e16b5-154">Confirmación y activación del acuerdo</span><span class="sxs-lookup"><span data-stu-id="e16b5-154">Confirm and activate the agreement</span></span>
1. <span data-ttu-id="e16b5-155">En el panel de acciones, haga clic en Acuerdo de compra.</span><span class="sxs-lookup"><span data-stu-id="e16b5-155">On the Action Pane, click Purchase agreement.</span></span>
2. <span data-ttu-id="e16b5-156">Haga clic en Confirmación.</span><span class="sxs-lookup"><span data-stu-id="e16b5-156">Click Confirmation.</span></span>
    * <span data-ttu-id="e16b5-157">Defina la opción Marcar acuerdo como vigente en Sí.</span><span class="sxs-lookup"><span data-stu-id="e16b5-157">Set the Mark agreement as effective option to Yes.</span></span>  
3. <span data-ttu-id="e16b5-158">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="e16b5-158">Click OK.</span></span>
4. <span data-ttu-id="e16b5-159">En el panel de acciones, haga clic en Acuerdo de compra.</span><span class="sxs-lookup"><span data-stu-id="e16b5-159">On the Action Pane, click Purchase agreement.</span></span>
5. <span data-ttu-id="e16b5-160">Haga clic en Confirmaciones del acuerdo de compra.</span><span class="sxs-lookup"><span data-stu-id="e16b5-160">Click Purchase agreement confirmations.</span></span>
    * <span data-ttu-id="e16b5-161">La opción Vista previa/Imprimir le permite generar un documento para el acuerdo de compra que después se puede imprimir o enviar al proveedor.</span><span class="sxs-lookup"><span data-stu-id="e16b5-161">The Preview/Print option allows you to generate a document for the purchase agreement which you can then print or send to the vendor.</span></span> <span data-ttu-id="e16b5-162">Si se actualiza el acuerdo más adelante y se vuelve a confirmar, aquí se mostrarán las dos versiones.</span><span class="sxs-lookup"><span data-stu-id="e16b5-162">If you update the agreement later on and re-confirm it, both versions will be shown here.</span></span>  
6. <span data-ttu-id="e16b5-163">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e16b5-163">Close the page.</span></span>


