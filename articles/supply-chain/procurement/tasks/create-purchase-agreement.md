---
title: Crear un acuerdo de compra
description: Este tema le guía por el proceso de creación de un acuerdo de compra.
author: mkirknel
manager: tfehr
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchAgreement, PurchAgreementCreate, InventItemIdLookupSimple, AgreementConfirmRunForm, PurchAgreementHistory
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1edfd4e56910376d0596eec5eff2af888f7dc98d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436796"
---
# <a name="create-a-purchase-agreement"></a><span data-ttu-id="5596f-103">Crear un acuerdo de compra</span><span class="sxs-lookup"><span data-stu-id="5596f-103">Create a purchase agreement</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5596f-104">Este tema le guía por el proceso de creación de un acuerdo de compra.</span><span class="sxs-lookup"><span data-stu-id="5596f-104">This topic guides you through the creation of a purchase agreement.</span></span> <span data-ttu-id="5596f-105">Esto normalmente lo haría el director de compras.</span><span class="sxs-lookup"><span data-stu-id="5596f-105">This would typically be done by a purchasing manager.</span></span> <span data-ttu-id="5596f-106">Puede utilizar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="5596f-106">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="5596f-107">Es necesario haber configurado clasificaciones de acuerdo de compra antes de comenzar.</span><span class="sxs-lookup"><span data-stu-id="5596f-107">You need to have set up purchase agreement classifications before you start.</span></span> <span data-ttu-id="5596f-108">Una vez que haya creado un acuerdo, podrá usarlo cuando cree un pedido de compra; esto copiará las condiciones del acuerdo de compra al encabezado y a cualquier línea del pedido a la que afecte el acuerdo.</span><span class="sxs-lookup"><span data-stu-id="5596f-108">Once you've created an agreement you can use it when you create a PO, and this will copy the purchase agreement conditions to the header and to any lines in the order that are affected by the agreement.</span></span>


## <a name="create-a-new-purchase-agreement"></a><span data-ttu-id="5596f-109">Creación de un acuerdo de compra nuevo</span><span class="sxs-lookup"><span data-stu-id="5596f-109">Create a new purchase agreement</span></span>
1. <span data-ttu-id="5596f-110">Vaya a **Panel de exploración > Módulos > Adquisición y abastecimiento > Acuerdos de compra > Acuerdos de compra**.</span><span class="sxs-lookup"><span data-stu-id="5596f-110">Go to **Navigation pane > Modules > Procurement and sourcing > Purchase agreements > Purchase agreements**.</span></span>
2. <span data-ttu-id="5596f-111">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="5596f-111">Click **New**.</span></span>
3. <span data-ttu-id="5596f-112">En el campo **Cuenta del proveedor**, seleccione el menú desplegable y la fila del registro deseado.</span><span class="sxs-lookup"><span data-stu-id="5596f-112">In the **Vendor account** field, select the drop-down menu and select the row of the desired record.</span></span>
4. <span data-ttu-id="5596f-113">En el campo **Clasificación de acuerdos de compra**, seleccione el menú desplegable y la fila del registro deseado.</span><span class="sxs-lookup"><span data-stu-id="5596f-113">In the **Purchase agreement classification** field, select the drop-down menu and select the row of the desired record.</span></span>
5. <span data-ttu-id="5596f-114">Expanda la ficha desplegable **General**.</span><span class="sxs-lookup"><span data-stu-id="5596f-114">Expand the **General** FastTab.</span></span>
6. <span data-ttu-id="5596f-115">En el campo **Fecha de caducidad**, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="5596f-115">In the **Expiration date** field, enter a date.</span></span>

    - <span data-ttu-id="5596f-116">Esta fecha de vencimiento será la predeterminada para todas las líneas de compromiso, y determinará cuánto tiempo es válido cada compromiso específico.</span><span class="sxs-lookup"><span data-stu-id="5596f-116">This expiration date will be the default for all commitment lines and will determine how long each specific commitment is valid.</span></span>  

7. <span data-ttu-id="5596f-117">En el campo **Título del documento**, escriba un nombre para el acuerdo de compra.</span><span class="sxs-lookup"><span data-stu-id="5596f-117">In the **Document title** field, type a name for your purchase agreement.</span></span>

    - <span data-ttu-id="5596f-118">Deje el campo **Compromiso predeterminado** en **Compromiso de cantidad de producto** (o cámbielo si no está así establecido).</span><span class="sxs-lookup"><span data-stu-id="5596f-118">Leave the **Default commitment** field set to **Product quantity commitment** (or change it if it's not set to this).</span></span>  
    - <span data-ttu-id="5596f-119">El valor de compromiso predeterminado determina las opciones en las líneas del acuerdo.</span><span class="sxs-lookup"><span data-stu-id="5596f-119">The default commitment value determines your options on the agreement lines.</span></span> <span data-ttu-id="5596f-120">Si necesita un nuevo tipo de compromiso al crear las líneas del acuerdo, deberá cambiar el compromiso predeterminado en la cabecera.</span><span class="sxs-lookup"><span data-stu-id="5596f-120">If you need a new commitment type when you're creating the agreement lines, you need to change the default commitment on the header.</span></span> <span data-ttu-id="5596f-121">Hay cuatro tipos de compromiso: **Compromiso de cantidad de producto**: para una cantidad específica de un producto; **Compromiso de valor de producto**: para un importe de divisa específico de un producto; **Compromiso de valor de la categoría de producto**: para un importe de divisa específico en una categoría de compras en la que el importe puede ser para un artículo de catálogo o un artículo no de catálogo; **Compromiso de valor** para un importe de divisa específico que se puede satisfacer con cualquier producto o cualquier categoría de compra.</span><span class="sxs-lookup"><span data-stu-id="5596f-121">There are 4 types of commitments: **Product quantity commitment** - for a specific quantity of a product; **Product value commitment** - for a specific currency amount of a product; **Product category value commitment** - for a specific currency amount in a procurement category where the amount can be for a catalog item or a non-catalog item; **Value commitment** - for a specific currency amount which can be fulfilled by any product or by any procurement category.</span></span>  

8. <span data-ttu-id="5596f-122">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5596f-122">Select **OK**.</span></span>

## <a name="add-a-commitment"></a><span data-ttu-id="5596f-123">Adición de un comentario</span><span class="sxs-lookup"><span data-stu-id="5596f-123">Add a commitment</span></span>
1. <span data-ttu-id="5596f-124">Seleccione **Agregar línea**.</span><span class="sxs-lookup"><span data-stu-id="5596f-124">Select **Add line**.</span></span>
2. <span data-ttu-id="5596f-125">En el campo **Código de artículo**, seleccione en el menú desplegable el registro que desea.</span><span class="sxs-lookup"><span data-stu-id="5596f-125">In the **Item number** field, select the desired record from the drop-down menu.</span></span>
3. <span data-ttu-id="5596f-126">En el campo **Cantidad**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="5596f-126">In the **Quantity** field, enter a number.</span></span> <span data-ttu-id="5596f-127">Esta es la cantidad total que el cliente ha acordado comprar del proveedor.</span><span class="sxs-lookup"><span data-stu-id="5596f-127">This is the total quantity that you have agreed to buy from your vendor.</span></span>  
4. <span data-ttu-id="5596f-128">En el campo **Precio unitario**, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="5596f-128">In the **Unit price** field, enter a number.</span></span>
5. <span data-ttu-id="5596f-129">Expanda la sección **Detalles de línea.**</span><span class="sxs-lookup"><span data-stu-id="5596f-129">Expand the **Line details** section.</span></span>
6. <span data-ttu-id="5596f-130">Defina la opción **Máximo aplicado** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="5596f-130">Set the **Max is enforced** option to **Yes**.</span></span> <span data-ttu-id="5596f-131">La opción **Máximo aplicado** limita el uso del compromiso.</span><span class="sxs-lookup"><span data-stu-id="5596f-131">The **Max is enforced** option limits the use of the commitment.</span></span> <span data-ttu-id="5596f-132">Solo puede comprar hasta la cantidad especificada en el campo **Cantidad** para la línea.</span><span class="sxs-lookup"><span data-stu-id="5596f-132">You can only purchase up to the quantity that's specified in the **Quantity** field for the line.</span></span>  

## <a name="add-header-conditions"></a><span data-ttu-id="5596f-133">Adición de condiciones de encabezado</span><span class="sxs-lookup"><span data-stu-id="5596f-133">Add header conditions</span></span>
1. <span data-ttu-id="5596f-134">En el panel de acciones, seleccione **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="5596f-134">On the Action Pane, select **Options**.</span></span>
2. <span data-ttu-id="5596f-135">Seleccione **Cambiar vista**.</span><span class="sxs-lookup"><span data-stu-id="5596f-135">Select **Change view**.</span></span>
3. <span data-ttu-id="5596f-136">Seleccione **Visualización de encabezado**.</span><span class="sxs-lookup"><span data-stu-id="5596f-136">Select **Header view**.</span></span>
4. <span data-ttu-id="5596f-137">Expanda la sección **Condiciones**.</span><span class="sxs-lookup"><span data-stu-id="5596f-137">Expand the **Terms** section.</span></span>
5. <span data-ttu-id="5596f-138">En el campo **Método de pago**, seleccione en el menú desplegable el registro que desee.</span><span class="sxs-lookup"><span data-stu-id="5596f-138">In the **Method of payment** field, select the desired record in the drop-down menu.</span></span> <span data-ttu-id="5596f-139">Las condiciones de pago de la cuenta del proveedor se muestran aquí de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5596f-139">The payment terms from the vendor account are shown here by default.</span></span>  
6. <span data-ttu-id="5596f-140">En el campo **Modo de entrega**, seleccione en el menú desplegable el registro que desee.</span><span class="sxs-lookup"><span data-stu-id="5596f-140">In the **Mode of delivery** field, select the desired record in the drop-down menu.</span></span>
7. <span data-ttu-id="5596f-141">En el campo **Condiciones de entrega**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="5596f-141">In the **Delivery terms** field, select the drop-down button to open the lookup.</span></span>

## <a name="confirm-and-activate-the-agreement"></a><span data-ttu-id="5596f-142">Confirmación y activación del acuerdo</span><span class="sxs-lookup"><span data-stu-id="5596f-142">Confirm and activate the agreement</span></span>
1. <span data-ttu-id="5596f-143">En el panel de acciones, haga clic en **Acuerdo de compra**.</span><span class="sxs-lookup"><span data-stu-id="5596f-143">On the Action Pane, select **Purchase agreement**.</span></span>
2. <span data-ttu-id="5596f-144">Seleccione **Confirmación**.</span><span class="sxs-lookup"><span data-stu-id="5596f-144">Select **Confirmation**.</span></span> <span data-ttu-id="5596f-145">Defina la opción **Marcar acuerdo como vigente** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="5596f-145">Set the **Mark agreement as effective** option to **Yes**.</span></span>  
3. <span data-ttu-id="5596f-146">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5596f-146">Select **OK**.</span></span>
4. <span data-ttu-id="5596f-147">En el panel de acciones, haga clic en **Acuerdo de compra**.</span><span class="sxs-lookup"><span data-stu-id="5596f-147">On the Action Pane, select **Purchase agreement**.</span></span>
5. <span data-ttu-id="5596f-148">Seleccione **Confirmaciones del acuerdo de compra**.</span><span class="sxs-lookup"><span data-stu-id="5596f-148">Select **Purchase agreement confirmations**.</span></span> <span data-ttu-id="5596f-149">La opción **Vista previa/Imprimir** le permite generar un documento para el acuerdo de compra que después se puede imprimir o enviar al proveedor.</span><span class="sxs-lookup"><span data-stu-id="5596f-149">The **Preview/Print** option allows you to generate a document for the purchase agreement which you can then print or send to the vendor.</span></span> <span data-ttu-id="5596f-150">Si se actualiza el acuerdo más adelante y se vuelve a confirmar, aquí se mostrarán las dos versiones.</span><span class="sxs-lookup"><span data-stu-id="5596f-150">If you update the agreement later on and re-confirm it, both versions will be shown here.</span></span>  
6. <span data-ttu-id="5596f-151">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="5596f-151">Close the page.</span></span>

