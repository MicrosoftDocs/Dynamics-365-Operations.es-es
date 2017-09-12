--- 
title: Crear un nuevo acuerdo comercial
description: "Este procedimiento muestra cómo crear un acuerdo comercial por el que se registra un nuevo precio de venta acordado con un cliente específico."
author: omulvad
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 1eb7a945243387f85ec5f38cc3b969d8d030ff25
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-new-trade-agreement"></a><span data-ttu-id="e68c2-103">Crear un nuevo acuerdo comercial</span><span class="sxs-lookup"><span data-stu-id="e68c2-103">Create a new trade agreement</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e68c2-104">Este procedimiento muestra cómo crear un acuerdo comercial por el que se registra un nuevo precio de venta acordado con un cliente específico.</span><span class="sxs-lookup"><span data-stu-id="e68c2-104">This procedure shows you how to create a trade agreement where you register a new product sales price that you've agreed with a specific customer.</span></span> <span data-ttu-id="e68c2-105">Puede ejecutar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="e68c2-105">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="e68c2-106">Si utiliza sus propios datos, antes de comenzar este procedimiento deberá asegurarse de que exista un nombre de diario de acuerdo comercial en el que la relación predeterminada esté establecida en Precio (ventas).</span><span class="sxs-lookup"><span data-stu-id="e68c2-106">If you’re using your own data, before you start this guide you need to make sure that a Trade agreement journal name exists where the Default relation is set to “Price (sales)”.</span></span>


## <a name="create-and-post-a-new-trade-agreement-journal"></a><span data-ttu-id="e68c2-107">Creación y registro de un diario de acuerdos comerciales nuevos</span><span class="sxs-lookup"><span data-stu-id="e68c2-107">Create and post a new trade agreement journal</span></span>
1. <span data-ttu-id="e68c2-108">Vaya Ventas y marketing > Precios y descuentos > Diarios de acuerdos comerciales.</span><span class="sxs-lookup"><span data-stu-id="e68c2-108">Go to Sales and marketing > Prices and discounts > Trade agreement journals.</span></span>
2. <span data-ttu-id="e68c2-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="e68c2-109">Click New.</span></span>
3. <span data-ttu-id="e68c2-110">En el campo Nombre, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e68c2-110">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="e68c2-111">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="e68c2-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="e68c2-112">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e68c2-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="e68c2-113">Haga clic en Líneas.</span><span class="sxs-lookup"><span data-stu-id="e68c2-113">Click Lines.</span></span>
7. <span data-ttu-id="e68c2-114">En el campo Código de cuenta, seleccione Tabla.</span><span class="sxs-lookup"><span data-stu-id="e68c2-114">In the Account code field, select 'Table'.</span></span>
    * <span data-ttu-id="e68c2-115">En este ejemplo, va a actualizar el precio para un cliente específico, por lo que tiene que elegir Tabla.</span><span class="sxs-lookup"><span data-stu-id="e68c2-115">In this example, you're updating the price for a specific customer, which means you need to choose Table.</span></span> <span data-ttu-id="e68c2-116">Si fuera a actualizar el precio de lista del producto, seleccionaría Todo, de modo que el nuevo precio fuera válido para todos los clientes.</span><span class="sxs-lookup"><span data-stu-id="e68c2-116">If you were updating the product's list price, you would select All, so that the new price is valid for all customers.</span></span> <span data-ttu-id="e68c2-117">Si fuera a diferenciar precios entre distintos segmentos de cliente, seleccionaría Grupo.</span><span class="sxs-lookup"><span data-stu-id="e68c2-117">If you were differentiating prices among different customer segments, then you would select Group.</span></span> <span data-ttu-id="e68c2-118">Para seleccionar Grupo debe haber configurado grupos de precios de cliente.</span><span class="sxs-lookup"><span data-stu-id="e68c2-118">To select Group, you must have set up Customer price groups.</span></span>  
8. <span data-ttu-id="e68c2-119">En el campo Selección de cuentas, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e68c2-119">In the Account selection field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="e68c2-120">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="e68c2-120">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="e68c2-121">En el campo Código de artículo, seleccione Tabla.</span><span class="sxs-lookup"><span data-stu-id="e68c2-121">In the Item code field, select 'Table'.</span></span>
    * <span data-ttu-id="e68c2-122">Al introducir un acuerdo comercial del tipo Precio (ventas), solo se debe seleccionar Tabla en el campo Código de artículo.</span><span class="sxs-lookup"><span data-stu-id="e68c2-122">When you are entering a trade agreement of type 'Price (sales)', you must only select 'Table' in the Item code field.</span></span> <span data-ttu-id="e68c2-123">Esto es así porque un precio es un valor absoluto, y no puede ser el mismo para todos los productos o un grupo de productos.</span><span class="sxs-lookup"><span data-stu-id="e68c2-123">This is because a price is an absolute value and cannot be same for all products or a group of products.</span></span>  
11. <span data-ttu-id="e68c2-124">En el campo Relación de artículos, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e68c2-124">In the Item relation field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="e68c2-125">En la lista, seleccione el producto que desee incluir en el acuerdo.</span><span class="sxs-lookup"><span data-stu-id="e68c2-125">In the list, select the product you want to include in the agreement.</span></span>
    * <span data-ttu-id="e68c2-126">Anote el producto que ha seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e68c2-126">Make a note of which product you've selected.</span></span>  
13. <span data-ttu-id="e68c2-127">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e68c2-127">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="e68c2-128">Especifique una cantidad mínima en el campo Desde.</span><span class="sxs-lookup"><span data-stu-id="e68c2-128">In the From field, enter a minimum quantity.</span></span>
    * <span data-ttu-id="e68c2-129">Si el cliente tiene que pedir una cantidad mínima para poder optar al nuevo precio, deberá especificar la cantidad aquí.</span><span class="sxs-lookup"><span data-stu-id="e68c2-129">If the customer has to order a minimum quantity  before they can qualify for the new price, then you need to specify that quantity here.</span></span>  
    * <span data-ttu-id="e68c2-130">Especifique un valor en el campo A para especificar la cantidad máxima por encima de la cual no será válido el precio del acuerdo.</span><span class="sxs-lookup"><span data-stu-id="e68c2-130">Enter a value in the To field to specify the maximum quantity above which the agreement's price will not be valid.</span></span> <span data-ttu-id="e68c2-131">Si ofrece precios y descuentos según distintas cantidades por niveles, especifique cada segmento de cantidad como par de cantidades mínima y máxima en los campos Desde y Hasta, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="e68c2-131">If you offer prices and discounts based on multiple quantity breaks, then specify each quantity bracket as a pair of minimum and maximum quantity in the 'From' and 'To' fields respectively.</span></span>  
15. <span data-ttu-id="e68c2-132">En el campo Importe en divisa, escriba un precio.</span><span class="sxs-lookup"><span data-stu-id="e68c2-132">In the Amount in currency field, enter a price.</span></span>
16. <span data-ttu-id="e68c2-133">En el campo Fecha inicial, especifique una fecha desde la cual será válido este acuerdo.</span><span class="sxs-lookup"><span data-stu-id="e68c2-133">In the From date field, enter a date from which this agreement will be valid.</span></span>
17. <span data-ttu-id="e68c2-134">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="e68c2-134">Click Save.</span></span>
18. <span data-ttu-id="e68c2-135">Haga clic en Validar.</span><span class="sxs-lookup"><span data-stu-id="e68c2-135">Click Validate.</span></span>
19. <span data-ttu-id="e68c2-136">Haga clic en Validar las líneas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="e68c2-136">Click Validate selected lines.</span></span>
20. <span data-ttu-id="e68c2-137">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="e68c2-137">Click OK.</span></span>
21. <span data-ttu-id="e68c2-138">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="e68c2-138">Click Post.</span></span>
22. <span data-ttu-id="e68c2-139">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="e68c2-139">Click OK.</span></span>

## <a name="view-trade-agreements-for-a-product"></a><span data-ttu-id="e68c2-140">Visualización de acuerdos comerciales para un producto</span><span class="sxs-lookup"><span data-stu-id="e68c2-140">View trade agreements for a product</span></span>
1. <span data-ttu-id="e68c2-141">Vaya a Gestión de información de productos > Productos > Productos emitidos.</span><span class="sxs-lookup"><span data-stu-id="e68c2-141">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="e68c2-142">En la lista, busque y seleccione el producto cuyo precio acaba de actualizar.</span><span class="sxs-lookup"><span data-stu-id="e68c2-142">In the list, find and select the product whose price you have just updated.</span></span>
3. <span data-ttu-id="e68c2-143">En el panel de acciones, haga clic en Vender.</span><span class="sxs-lookup"><span data-stu-id="e68c2-143">On the Action Pane, click Sell.</span></span>
4. <span data-ttu-id="e68c2-144">Haga clic en Ver acuerdos comerciales.</span><span class="sxs-lookup"><span data-stu-id="e68c2-144">Click View trade agreements.</span></span>
    * <span data-ttu-id="e68c2-145">Revise los detalles del acuerdo comercial de precios que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="e68c2-145">Review the details of the price trade agreement you have just created.</span></span>    
5. <span data-ttu-id="e68c2-146">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e68c2-146">Close the page.</span></span>


