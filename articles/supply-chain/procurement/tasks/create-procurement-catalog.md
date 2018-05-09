--- 
title: "Crear un catálogo de compras"
description: "Esta guía le muestra cómo crear un catálogo de compras."
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 2bda068c71b768eb0caadfdbf8b4fe5620bd8eea
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---
# <a name="create-a-procurement-catalog"></a><span data-ttu-id="96a8f-103">Crear un catálogo de compras</span><span class="sxs-lookup"><span data-stu-id="96a8f-103">Create a procurement catalog</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="96a8f-104">Esta guía le muestra cómo crear un catálogo de compras.</span><span class="sxs-lookup"><span data-stu-id="96a8f-104">This guide shows you how to create a procurement catalog.</span></span> <span data-ttu-id="96a8f-105">Esta tarea la llevaría a cabo normalmente un profesional de compras.</span><span class="sxs-lookup"><span data-stu-id="96a8f-105">This task would typically be carried out by a procurement professional.</span></span> <span data-ttu-id="96a8f-106">También obtendrá información acerca de cómo los empleados pueden utilizar el catálogo al crear una solicitud.</span><span class="sxs-lookup"><span data-stu-id="96a8f-106">You will also learn how employees can use the catalog when they create a requisition.</span></span> <span data-ttu-id="96a8f-107">Para que pueda crear un catálogo, debe haber una jerarquía de categoría de compras en su sistema.</span><span class="sxs-lookup"><span data-stu-id="96a8f-107">Before you can create a catalog, there must be a procurement category hierarchy in your system.</span></span> <span data-ttu-id="96a8f-108">La jerarquía es hereda por el nuevo catálogo, junto con todos los productos que se encuentran en la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="96a8f-108">The hierarchy is inherited by the new catalog, along with all the products that are in the hierarchy.</span></span> <span data-ttu-id="96a8f-109">Puede usar esta guía en la empresa de datos de demostración USMF donde la jerarquía de categoría de compras está disponible, así como los ejemplos usados en los pasos de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="96a8f-109">You can use this guide in demo data company USMF where the procurement category hierarchy is available, as well as the examples used in the procedure steps.</span></span>


## <a name="ensure-that-a-procurement-category-hierarchy-exists"></a><span data-ttu-id="96a8f-110">Asegúrese de que existe una jerarquía de categoría de compras</span><span class="sxs-lookup"><span data-stu-id="96a8f-110">Ensure that a procurement category hierarchy exists</span></span>
1. <span data-ttu-id="96a8f-111">Vaya a Adquisición y abastecimiento > Categorías de compras.</span><span class="sxs-lookup"><span data-stu-id="96a8f-111">Go to Procurement and sourcing > Procurement categories.</span></span>
    * <span data-ttu-id="96a8f-112">Una jerarquía de categoría de compras está disponible en la empresa de datos de demostración USMF y los productos se han agregado a la categoría Máquinas de oficina/Equipos informáticos.</span><span class="sxs-lookup"><span data-stu-id="96a8f-112">A procurement category hierarchy is available in the USMF demo data company and products have been added to the Office machines/Computers category.</span></span> <span data-ttu-id="96a8f-113">Si está ejecutando este procedimiento como guía de tareas, necesitará desbloquear la guía si desea desplazarse por la categoría.</span><span class="sxs-lookup"><span data-stu-id="96a8f-113">If you’re running this procedure as a task guide, you’ll need to unlock the guide if you want to browse through the category.</span></span> <span data-ttu-id="96a8f-114">Si una jerarquía no estaba disponible, la crearía haciendo clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="96a8f-114">If a hierarchy was not available, you’d create it by clicking New.</span></span> <span data-ttu-id="96a8f-115">Esto solo se puede hacer una vez.</span><span class="sxs-lookup"><span data-stu-id="96a8f-115">This can only be done once.</span></span>  
2. <span data-ttu-id="96a8f-116">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="96a8f-116">Close the page.</span></span>

## <a name="create-a-catalog"></a><span data-ttu-id="96a8f-117">Crear un catálogo</span><span class="sxs-lookup"><span data-stu-id="96a8f-117">Create a catalog</span></span>
1. <span data-ttu-id="96a8f-118">Vaya a Adquisición y abastecimiento > Catálogos > Catálogos de compras.</span><span class="sxs-lookup"><span data-stu-id="96a8f-118">Go to Procurement and sourcing > Catalogs > Procurement catalogs.</span></span>
2. <span data-ttu-id="96a8f-119">Haga clic en Nuevo catálogo de compras para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="96a8f-119">Click New procurement catalog to open the drop dialog.</span></span>
3. <span data-ttu-id="96a8f-120">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="96a8f-120">In the Name field, type a value.</span></span>
4. <span data-ttu-id="96a8f-121">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="96a8f-121">Click OK.</span></span>
5. <span data-ttu-id="96a8f-122">En el árbol, expanda “CORP PROCUREMENT CATEGORIES”.</span><span class="sxs-lookup"><span data-stu-id="96a8f-122">In the tree, expand 'CORP PROCUREMENT CATEGORIES'.</span></span>
6. <span data-ttu-id="96a8f-123">En el árbol, expanda "OFFICE MACHINES".</span><span class="sxs-lookup"><span data-stu-id="96a8f-123">In the tree, expand 'OFFICE MACHINES'.</span></span>
7. <span data-ttu-id="96a8f-124">En el árbol, seleccione "Equipos informáticos".</span><span class="sxs-lookup"><span data-stu-id="96a8f-124">In the tree, select 'Computers'.</span></span>
    * <span data-ttu-id="96a8f-125">Los productos de la categoría de compras se muestran en la lista.</span><span class="sxs-lookup"><span data-stu-id="96a8f-125">The products from the procurement category are displayed in the list.</span></span> <span data-ttu-id="96a8f-126">Si desea agregar un producto a la categoría, necesita hacer esto en la página Jerarquía de categorías de compras o en la página Detalles del artículo.</span><span class="sxs-lookup"><span data-stu-id="96a8f-126">If you want to add a product to the category you need to do this on the Procurement category hierarchy page or on the Item details page.</span></span>  
    * <span data-ttu-id="96a8f-127">El Tipo de actualización predeterminada determina si los nuevos productos que se han agregado a la jerarquía de categoría de compras son inmediatamente visibles en el catálogo.</span><span class="sxs-lookup"><span data-stu-id="96a8f-127">The Default update type determines whether new products that have been added to the procurement category hierarchy are immediately visible in the catalog.</span></span> <span data-ttu-id="96a8f-128">Si el tipo de actualización se establece en Dinámico, los cambios serán visibles de inmediato.</span><span class="sxs-lookup"><span data-stu-id="96a8f-128">If the update type is set to Dynamic, changes are visible immediately.</span></span> <span data-ttu-id="96a8f-129">Si el tipo de actualización es Estático, los nuevos productos solo son visibles para personas que usan el catálogo una vez que se ha vuelto a publicar el catálogo.</span><span class="sxs-lookup"><span data-stu-id="96a8f-129">If the update type is Static, new products are only visible to people using the catalog after the catalog has been re-published.</span></span> <span data-ttu-id="96a8f-130">La acción Publicar está disponible en el Panel de acciones de la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="96a8f-130">The Publish action is available on the Action Pane at the top of the page.</span></span> <span data-ttu-id="96a8f-131">Si los productos se eliminan de la jerarquía de categoría de compras, el cambio será visible inmediatamente, con independencia del valor en el campo Tipo de actualización predeterminada.</span><span class="sxs-lookup"><span data-stu-id="96a8f-131">If products are removed from the procurement category hierarchy, the change is immediately visible, regardless of the value in the Default update type field.</span></span>  
8. <span data-ttu-id="96a8f-132">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="96a8f-132">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="96a8f-133">Haga clic en Ocultar.</span><span class="sxs-lookup"><span data-stu-id="96a8f-133">Click Hide.</span></span>
10. <span data-ttu-id="96a8f-134">En el panel de acciones, haga clic en Navegación por categorías.</span><span class="sxs-lookup"><span data-stu-id="96a8f-134">On the Action Pane, click Category navigation.</span></span>
11. <span data-ttu-id="96a8f-135">Haga clic en Deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="96a8f-135">Click Disable.</span></span>
12. <span data-ttu-id="96a8f-136">En el panel de acciones, haga clic en Navegación por categorías.</span><span class="sxs-lookup"><span data-stu-id="96a8f-136">On the Action Pane, click Category navigation.</span></span>
13. <span data-ttu-id="96a8f-137">Haga clic en Habilitar.</span><span class="sxs-lookup"><span data-stu-id="96a8f-137">Click Enable.</span></span>
14. <span data-ttu-id="96a8f-138">Haga clic en Activar catálogo.</span><span class="sxs-lookup"><span data-stu-id="96a8f-138">Click Activate catalog.</span></span>
15. <span data-ttu-id="96a8f-139">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="96a8f-139">Close the page.</span></span>

## <a name="make-the-catalog-visible"></a><span data-ttu-id="96a8f-140">Hacer el catálogo visible</span><span class="sxs-lookup"><span data-stu-id="96a8f-140">Make the catalog visible</span></span>
1. <span data-ttu-id="96a8f-141">Vaya a Adquisición y abastecimiento > Configuración > Directivas > Directivas de compra.</span><span class="sxs-lookup"><span data-stu-id="96a8f-141">Go to Procurement and sourcing > Setup > Policies > Purchasing policies.</span></span>
2. <span data-ttu-id="96a8f-142">Seleccione USMF de directiva de compras.</span><span class="sxs-lookup"><span data-stu-id="96a8f-142">Select Procurement Policy USMF.</span></span>
    * <span data-ttu-id="96a8f-143">Necesita seleccionar la directiva de compras para la entidad jurídica en la que el trabajador conectado a su perfil de usuario puede pedir productos.</span><span class="sxs-lookup"><span data-stu-id="96a8f-143">You need to select the purchasing policy for the legal entity that the worker connected to your user profile is allowed to order products in.</span></span> <span data-ttu-id="96a8f-144">En los datos de demostración USMF, el usuario Administrador está conectado a la trabajadora Julia Funderburk y ella pide productos en USMF de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="96a8f-144">In the USMF demo data, the Admin user is connected to the worker called Julia Funderburk, and she orders products in USMF by default.</span></span>  
3. <span data-ttu-id="96a8f-145">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="96a8f-145">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="96a8f-146">Seleccione el catálogo que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="96a8f-146">Select the catalog that you’ve just created.</span></span>
5. <span data-ttu-id="96a8f-147">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="96a8f-147">Click OK.</span></span>
6. <span data-ttu-id="96a8f-148">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="96a8f-148">Close the page.</span></span>
7. <span data-ttu-id="96a8f-149">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="96a8f-149">Close the page.</span></span>

## <a name="use-the-catalog"></a><span data-ttu-id="96a8f-150">Usar el catálogo</span><span class="sxs-lookup"><span data-stu-id="96a8f-150">Use the catalog</span></span>
1. <span data-ttu-id="96a8f-151">Vaya a Adquisición y abastecimiento > Solicitudes de compra > Todas las solicitudes de compra.</span><span class="sxs-lookup"><span data-stu-id="96a8f-151">Go to Procurement and sourcing > Purchase requisitions > All purchase requisitions.</span></span>
2. <span data-ttu-id="96a8f-152">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="96a8f-152">Click New.</span></span>
3. <span data-ttu-id="96a8f-153">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="96a8f-153">In the Name field, type a value.</span></span>
4. <span data-ttu-id="96a8f-154">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="96a8f-154">Click OK.</span></span>
5. <span data-ttu-id="96a8f-155">Haga clic en Agregar productos.</span><span class="sxs-lookup"><span data-stu-id="96a8f-155">Click Add products.</span></span>
6. <span data-ttu-id="96a8f-156">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="96a8f-156">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="96a8f-157">Puede utilizar la jerarquía de categoría de la izquierda o el filtro de la parte superior de la lista para filtrar los productos.</span><span class="sxs-lookup"><span data-stu-id="96a8f-157">You can use the category hierarchy on the left or the filter at the top of the list to filter the products.</span></span>  
7. <span data-ttu-id="96a8f-158">Haga clic en Agregar a las líneas.</span><span class="sxs-lookup"><span data-stu-id="96a8f-158">Click Add to lines.</span></span>
8. <span data-ttu-id="96a8f-159">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="96a8f-159">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="96a8f-160">Haga clic en Agregar a las líneas.</span><span class="sxs-lookup"><span data-stu-id="96a8f-160">Click Add to lines.</span></span>
10. <span data-ttu-id="96a8f-161">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="96a8f-161">Click OK.</span></span>


