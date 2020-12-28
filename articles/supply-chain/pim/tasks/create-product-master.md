---
title: Crear un producto maestro
description: Cree un producto maestro para las variantes predefinidas.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fdb30b46a0e5a6d4fac997588dd47148f2664c03
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436851"
---
# <a name="create-a-product-master"></a><span data-ttu-id="cec98-103">Crear un producto maestro</span><span class="sxs-lookup"><span data-stu-id="cec98-103">Create a product master</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="cec98-104">Cree un producto maestro para las variantes predefinidas.</span><span class="sxs-lookup"><span data-stu-id="cec98-104">Create a product master for the predefined variants.</span></span> <span data-ttu-id="cec98-105">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="cec98-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="cec98-106">Este procedimiento se ha pensado para el diseñador de producto.</span><span class="sxs-lookup"><span data-stu-id="cec98-106">This procedure is intended for the product designer.</span></span>


## <a name="create-a-new-product-master"></a><span data-ttu-id="cec98-107">Crear un nuevo producto maestro</span><span class="sxs-lookup"><span data-stu-id="cec98-107">Create a new product master</span></span>
1. <span data-ttu-id="cec98-108">Vaya a **Panel de exploración > Módulos > Gestión de información de productos > Productos > Productos maestros**.</span><span class="sxs-lookup"><span data-stu-id="cec98-108">Go to **Navigation pane > Modules > Product information management > Products > Product masters**.</span></span>
2. <span data-ttu-id="cec98-109">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="cec98-109">Click **New**.</span></span>
3. <span data-ttu-id="cec98-110">En el campo **Número de producto**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="cec98-110">In the **Product number** field, type a value.</span></span> <span data-ttu-id="cec98-111">El número debe ser único.</span><span class="sxs-lookup"><span data-stu-id="cec98-111">The number must be unique.</span></span> <span data-ttu-id="cec98-112">Se puede especificar una secuencia numérica para el campo **Número de producto**.</span><span class="sxs-lookup"><span data-stu-id="cec98-112">A number sequence can be set for the **Product number** field.</span></span> <span data-ttu-id="cec98-113">En este caso, el usuario no tiene que especificar un valor.</span><span class="sxs-lookup"><span data-stu-id="cec98-113">In this case, the user doesn't have to enter a value.</span></span>
4. <span data-ttu-id="cec98-114">En el campo **Nombre de producto**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="cec98-114">In the **Product name** field, type a value.</span></span> <span data-ttu-id="cec98-115">Escriba un nombre del producto que sea descriptivo.</span><span class="sxs-lookup"><span data-stu-id="cec98-115">Enter a descriptive product name.</span></span> <span data-ttu-id="cec98-116">El valor predeterminado es el nombre de búsqueda, pero esto lo puede cambiar el usuario.</span><span class="sxs-lookup"><span data-stu-id="cec98-116">The value defaults to the search name, but this can be changed by the user.</span></span>
5. <span data-ttu-id="cec98-117">En el campo **Grupo de dimensiones de producto**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="cec98-117">In the **Product dimension group** field, click the drop-down button to open the lookup.</span></span> <span data-ttu-id="cec98-118">El grupo de dimensiones del producto determina cuál de las cuatro dimensiones del producto se pueden usar para crear variantes del producto.</span><span class="sxs-lookup"><span data-stu-id="cec98-118">The product dimension group determines which of the 4 product dimensions that can be used to create product variants.</span></span> <span data-ttu-id="cec98-119">Este ejemplo usa un grupo con tamaño y color.</span><span class="sxs-lookup"><span data-stu-id="cec98-119">This example uses a group with color and size.</span></span>
6. <span data-ttu-id="cec98-120">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="cec98-120">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="cec98-121">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="cec98-121">In the list, click the link in the selected row.</span></span> <span data-ttu-id="cec98-122">La **tecnología de configuración** predeterminada es Variante predefinida.</span><span class="sxs-lookup"><span data-stu-id="cec98-122">The default **Configuration technology** is 'Predefined variant'.</span></span> <span data-ttu-id="cec98-123">Es lo que se usará para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="cec98-123">This will be used for this example.</span></span>
8. <span data-ttu-id="cec98-124">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cec98-124">Click **OK**.</span></span>

## <a name="select-product-dimension-groups"></a><span data-ttu-id="cec98-125">Selección de grupos de dimensiones de producto</span><span class="sxs-lookup"><span data-stu-id="cec98-125">Select product dimension groups</span></span>
1. <span data-ttu-id="cec98-126">En el campo **Grupo de colores**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="cec98-126">In the **Color group** field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="cec98-127">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="cec98-127">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="cec98-128">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="cec98-128">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="cec98-129">En el campo **Grupo de tamaños**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="cec98-129">In the **Size group** field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="cec98-130">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="cec98-130">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="cec98-131">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="cec98-131">In the list, click the link in the selected row.</span></span>

## <a name="add-dimension-groups"></a><span data-ttu-id="cec98-132">Agregar grupos de dimensiones</span><span class="sxs-lookup"><span data-stu-id="cec98-132">Add dimension groups</span></span>
1. <span data-ttu-id="cec98-133">En el **Panel de acciones**, haga clic en **Producto**.</span><span class="sxs-lookup"><span data-stu-id="cec98-133">On the **Action Pane**, click **Product**.</span></span>
2. <span data-ttu-id="cec98-134">Haga clic en **Grupos de dimensiones** para abrir el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="cec98-134">Click **Dimension groups** to open the drop dialog.</span></span>
3. <span data-ttu-id="cec98-135">En el campo **Grupo de dimensiones de almacenamiento**, haga clic en el botón de lista desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="cec98-135">In the **Storage dimension group** field, click the drop-down button to open the lookup.</span></span> <span data-ttu-id="cec98-136">Las dimensiones de almacenamiento ayudan a controlar el modo en que los artículos se almacenan y se toman del inventario.</span><span class="sxs-lookup"><span data-stu-id="cec98-136">The storage dimensions help you control how items are stored and taken from inventory.</span></span> <span data-ttu-id="cec98-137">Por ejemplo, una dimensión de almacenamiento puede incluir el sitio y el almacén.</span><span class="sxs-lookup"><span data-stu-id="cec98-137">For example, a storage dimension can include Site and Warehouse.</span></span>
4. <span data-ttu-id="cec98-138">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="cec98-138">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="cec98-139">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="cec98-139">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="cec98-140">En el campo **Grupo de dimensiones de seguimiento**, haga clic en el botón de lista desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="cec98-140">In the **Tracking dimension group** field, click the drop-down button to open the lookup.</span></span> <span data-ttu-id="cec98-141">El grupo de dimensiones de seguimiento determina qué dimensiones de seguimiento puede agregar a un producto.</span><span class="sxs-lookup"><span data-stu-id="cec98-141">The tracking dimension group determines which tracking dimensions you can add to a product.</span></span> <span data-ttu-id="cec98-142">Por ejemplo, el número de lote y el número de serie se utilizan para hacer un seguimiento de los artículos de inventario.</span><span class="sxs-lookup"><span data-stu-id="cec98-142">For example, the batch number and serial number are used to track inventory items.</span></span>
7. <span data-ttu-id="cec98-143">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="cec98-143">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="cec98-144">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="cec98-144">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="cec98-145">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cec98-145">Click **OK**.</span></span>
10. <span data-ttu-id="cec98-146">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="cec98-146">Click **Save**.</span></span>
11. <span data-ttu-id="cec98-147">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="cec98-147">Close the page.</span></span>

