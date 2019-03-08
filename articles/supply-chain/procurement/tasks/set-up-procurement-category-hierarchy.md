---
title: Configurar una jerarquía de categorías de compras
description: Este procedimiento muestra cómo crear nuevos nodos en una jerarquía de categorías de compras y cómo configurar una categoría de compras para usarla en un proceso de compra.
author: mkirknel
manager: AnnBe
ms.date: 11/06/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 01809a8a3256342682d8a9cfb296a355310fe4ed
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "334528"
---
# <a name="set-up-a-procurement-category-hierarchy"></a><span data-ttu-id="618ab-103">Configurar una jerarquía de categorías de compras</span><span class="sxs-lookup"><span data-stu-id="618ab-103">Set up a procurement category hierarchy</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="618ab-104">Este procedimiento muestra cómo crear nuevos nodos en una jerarquía de categorías de compras y cómo configurar una categoría de compras para usarla en un proceso de compra.</span><span class="sxs-lookup"><span data-stu-id="618ab-104">This procedure shows you how to create new nodes in a procurement category hierarchy and how to configure a procurement category to be used in a procurement process.</span></span> <span data-ttu-id="618ab-105">Estas tareas las realizará normalmente el director de compras.</span><span class="sxs-lookup"><span data-stu-id="618ab-105">These tasks would typically be carried out by a Purchasing manager.</span></span> <span data-ttu-id="618ab-106">Para poder comenzar este procedimiento, debe haber una jerarquía de categorías de tipo Adquisición.</span><span class="sxs-lookup"><span data-stu-id="618ab-106">Before you can start this procedure, there must be a category hierarchy of type Procurement.</span></span> <span data-ttu-id="618ab-107">Si usa una empresa de datos de demostración, puede ejecutar este procedimiento en la empresa USMF.</span><span class="sxs-lookup"><span data-stu-id="618ab-107">If you're using a demo data company, you can run this procedure in the USMF company.</span></span>


## <a name="add-a-new-procurement-category"></a><span data-ttu-id="618ab-108">Adición de una nueva categoría de compras</span><span class="sxs-lookup"><span data-stu-id="618ab-108">Add a new procurement category</span></span>
1. <span data-ttu-id="618ab-109">Vaya a Adquisición y abastecimiento > Categorías de compras.</span><span class="sxs-lookup"><span data-stu-id="618ab-109">Go to Procurement and sourcing > Procurement categories.</span></span>
2. <span data-ttu-id="618ab-110">Haga clic en Editar jerarquía de categoría.</span><span class="sxs-lookup"><span data-stu-id="618ab-110">Click Edit category hierarchy.</span></span>
    * <span data-ttu-id="618ab-111">La jerarquía de la categoría de compras actual se muestra en el lado izquierdo de la página.</span><span class="sxs-lookup"><span data-stu-id="618ab-111">The current procurement category hierarchy is displayed in the left side of the page.</span></span> <span data-ttu-id="618ab-112">Va a modificar la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="618ab-112">You  are about to modify the hierarchy.</span></span>  
3. <span data-ttu-id="618ab-113">Haga clic en Nodo de categoría nueva.</span><span class="sxs-lookup"><span data-stu-id="618ab-113">Click New category node.</span></span>
    * <span data-ttu-id="618ab-114">El sistema selecciona el nodo superior de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="618ab-114">The system selects the top node by default.</span></span> <span data-ttu-id="618ab-115">Si está ejecutando este procedimiento como guía de tarea, puede hacer clic en el botón Desbloquear y seleccionar otro nodo principal donde insertar su nuevo nodo.</span><span class="sxs-lookup"><span data-stu-id="618ab-115">If you are running this procedure as a task guide, you can click the Unlock button and select another parent node to insert your new node into.</span></span> <span data-ttu-id="618ab-116">Una vez hecho, bloquee la guía de tarea de nuevo y haga clic en Nodo de categoría nueva.</span><span class="sxs-lookup"><span data-stu-id="618ab-116">Once that is done, lock the task guide again and then click New category node.</span></span>  
4. <span data-ttu-id="618ab-117">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="618ab-117">In the Name field, type a value.</span></span>
5. <span data-ttu-id="618ab-118">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="618ab-118">In the Description field, type a value.</span></span>
6. <span data-ttu-id="618ab-119">En el campo Nombre descriptivo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="618ab-119">In the Friendly name field, type a value.</span></span>
    * <span data-ttu-id="618ab-120">El nombre descriptivo es opcional.</span><span class="sxs-lookup"><span data-stu-id="618ab-120">The friendly name is optional.</span></span> <span data-ttu-id="618ab-121">Se mostrará en las búsquedas de categorías junto con el nombre de la categoría.</span><span class="sxs-lookup"><span data-stu-id="618ab-121">It will be displayed in category lookups together with the category name.</span></span>  
7. <span data-ttu-id="618ab-122">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="618ab-122">Click Save.</span></span>

## <a name="add-products-to-your-new-procurement-category"></a><span data-ttu-id="618ab-123">Adición de productos a su nueva categoría de compra</span><span class="sxs-lookup"><span data-stu-id="618ab-123">Add products to your new procurement category</span></span>
1. <span data-ttu-id="618ab-124">Vaya a Adquisición y abastecimiento > Categorías de compras.</span><span class="sxs-lookup"><span data-stu-id="618ab-124">Go to Procurement and sourcing > Procurement categories.</span></span>
    * <span data-ttu-id="618ab-125">Seleccione el nodo que acaba de agregar.</span><span class="sxs-lookup"><span data-stu-id="618ab-125">Select the node you just added.</span></span> <span data-ttu-id="618ab-126">Si está ejecutando este procedimiento como guía de tarea, puede que tenga que desbloquear la guía de tarea para seleccionar el nodo.</span><span class="sxs-lookup"><span data-stu-id="618ab-126">If you’re running this procedure as a task guide you might need to unlock the task guide to select the node.</span></span>  
2. <span data-ttu-id="618ab-127">Expanda la sección Productos.</span><span class="sxs-lookup"><span data-stu-id="618ab-127">Toggle the expansion of the Products section.</span></span>
3. <span data-ttu-id="618ab-128">Haga clic en Agregar para asociar productos con la categoría de adquisición.</span><span class="sxs-lookup"><span data-stu-id="618ab-128">Click Add to associate products with the procurement category.</span></span>
4. <span data-ttu-id="618ab-129">Seleccione el producto que desea agregar a la categoría de adquisición.</span><span class="sxs-lookup"><span data-stu-id="618ab-129">Select the product you want to add to the procurement category.</span></span>
5. <span data-ttu-id="618ab-130">Haga clic en la flecha para seleccionar el producto.</span><span class="sxs-lookup"><span data-stu-id="618ab-130">Click the arrow to select the product.</span></span>
6. <span data-ttu-id="618ab-131">Seleccione otro producto que agregar a la categoría de adquisición.</span><span class="sxs-lookup"><span data-stu-id="618ab-131">Select another product to add to the procurement category.</span></span>
7. <span data-ttu-id="618ab-132">Haga clic en la flecha para seleccionar el producto.</span><span class="sxs-lookup"><span data-stu-id="618ab-132">Click the arrow to select the product.</span></span>
8. <span data-ttu-id="618ab-133">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="618ab-133">Click OK.</span></span>

## <a name="add-approved-and-preferred-vendors"></a><span data-ttu-id="618ab-134">Adición de proveedores aprobados y preferidos</span><span class="sxs-lookup"><span data-stu-id="618ab-134">Add approved and preferred vendors</span></span>
1. <span data-ttu-id="618ab-135">Alterne la expansión de la sección Proveedores.</span><span class="sxs-lookup"><span data-stu-id="618ab-135">Toggle the expansion of the Vendors section.</span></span>
2. <span data-ttu-id="618ab-136">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="618ab-136">Click Add.</span></span>
    * <span data-ttu-id="618ab-137">Puede agregar un proveedor a una categoría de compra y especificar si se prefiere a un proveedor para la categoría, o simplemente es un proveedor aprobado.</span><span class="sxs-lookup"><span data-stu-id="618ab-137">You can add a vendor to a procurement category and specify whether a vendor is preferred or just approved for the category.</span></span> <span data-ttu-id="618ab-138">Al eliminar un proveedor de una categoría, el historial de transacciones con el proveedor en la categoría no se eliminarán.</span><span class="sxs-lookup"><span data-stu-id="618ab-138">When you delete a vendor from a category, the historical transactions with the vendor in the category are not deleted.</span></span>   
3. <span data-ttu-id="618ab-139">Localice el proveedor que desea agregar a la categoría.</span><span class="sxs-lookup"><span data-stu-id="618ab-139">Find the vendor you want to add to the category.</span></span>
4. <span data-ttu-id="618ab-140">Haga clic en la flecha para seleccionar al proveedor.</span><span class="sxs-lookup"><span data-stu-id="618ab-140">Click the arrow to select the vendor.</span></span>
5. <span data-ttu-id="618ab-141">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="618ab-141">Click OK.</span></span>
6. <span data-ttu-id="618ab-142">Seleccione la fila del proveedor que desee modificar.</span><span class="sxs-lookup"><span data-stu-id="618ab-142">Select the vendor row that you want to modify.</span></span>
7. <span data-ttu-id="618ab-143">En el campo Estado del proveedor, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="618ab-143">In the Vendor status field, select an option.</span></span>
    * <span data-ttu-id="618ab-144">El ajuste de la selección del proveedor en la regla de la directiva de categoría rige si aparecen disponibles en los pedidos de compra los proveedores preferidos, los aprobados o todos ellos.</span><span class="sxs-lookup"><span data-stu-id="618ab-144">The vendor selection setting in the Category policy rule governs whether preferred, approved, or all vendors are available on purchase requisitions.</span></span>   

## <a name="add-additional-information-to-the-category"></a><span data-ttu-id="618ab-145">Adición de información adicional a la categoría</span><span class="sxs-lookup"><span data-stu-id="618ab-145">Add additional information to the category</span></span>
1. <span data-ttu-id="618ab-146">Expanda la sección Grupos de criterios de evaluación de proveedor.</span><span class="sxs-lookup"><span data-stu-id="618ab-146">Toggle the expansion of the Vendor evaluation criterion groups section.</span></span>
    * <span data-ttu-id="618ab-147">Esta ficha permite definir en relación con qué criterios se deben clasificar los proveedores en la categoría de compra.</span><span class="sxs-lookup"><span data-stu-id="618ab-147">This tab allows you to define which criteria the vendors in the procurement category should be rated against.</span></span> <span data-ttu-id="618ab-148">Para ello, haría clic en Agregar y seleccione un grupo de evaluación de proveedores con los criterios en cuestión.</span><span class="sxs-lookup"><span data-stu-id="618ab-148">To do this you would click Add and then select a vendor evaluation group that contains the criteria you want.</span></span>  
2. <span data-ttu-id="618ab-149">Expanda la sección Cuestionarios.</span><span class="sxs-lookup"><span data-stu-id="618ab-149">Toggle the expansion of the Questionnaires section.</span></span>
    * <span data-ttu-id="618ab-150">Esta ficha le permite agregar cuestionarios que aparecerán en el pedido, siempre que se defina el tipo de actividad en Pedido.</span><span class="sxs-lookup"><span data-stu-id="618ab-150">This tab allows you to add questionnaires that will appear on the requisition, as long as you set the Activity type to "Requisition".</span></span> <span data-ttu-id="618ab-151">El solicitante continuación tiene que completar un cuestionario antes de que envíen un pedido de compra del producto o los productos específicos en la categoría de compras.</span><span class="sxs-lookup"><span data-stu-id="618ab-151">The requester then has to fill out a questionnaire before they submit a requisition for the specific product or products in the procurement category.</span></span>  
3. <span data-ttu-id="618ab-152">Expanda la sección Grupos de impuestos de artículos.</span><span class="sxs-lookup"><span data-stu-id="618ab-152">Toggle the expansion of the Item sales tax groups section.</span></span>
4. <span data-ttu-id="618ab-153">En el campo Grupo de impuestos de artículos, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="618ab-153">In the Item sales tax group: field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="618ab-154">Seleccione un grupo de impuestos.</span><span class="sxs-lookup"><span data-stu-id="618ab-154">Select a sales tax group.</span></span>
6. <span data-ttu-id="618ab-155">Expanda la sección Página de la categoría.</span><span class="sxs-lookup"><span data-stu-id="618ab-155">Toggle the expansion of the Category page section.</span></span>
    * <span data-ttu-id="618ab-156">Las páginas de la categoría se crean en la página Jerarquía de categoría.</span><span class="sxs-lookup"><span data-stu-id="618ab-156">Category pages are created in the Category hierarchy page.</span></span> <span data-ttu-id="618ab-157">Incluyen información acerca de la categoría de compra, como información sobre el tipo de productos en una categoría, imágenes de productos en una categoría, o anuncios, como los descuentos disponibles en una categoría.</span><span class="sxs-lookup"><span data-stu-id="618ab-157">They contain information about the procurement category such as information about the type of products in a category, images of products in a category, or announcements such as the discounts that are available in a category.</span></span> <span data-ttu-id="618ab-158">La información en una página de categoría aparece en los pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="618ab-158">The information in a category page is displayed on purchase requisitions.</span></span>  
7. <span data-ttu-id="618ab-159">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="618ab-159">Close the page.</span></span>

