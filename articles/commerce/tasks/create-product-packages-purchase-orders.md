---
title: " Crear paquetes de producto para pedidos de compra"
description: Este procedimiento le guía por la creación de un paquete de producto y su uso en un pedido de compra.
author: josaw1
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4c84c829ca1344d70dee294da35b659299d6fa37
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5802728"
---
# <a name="create-product-packages-for-purchase-orders"></a><span data-ttu-id="b9031-103"> Crear paquetes de producto para pedidos de compra</span><span class="sxs-lookup"><span data-stu-id="b9031-103">Create product packages for purchase orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b9031-104">Este procedimiento le guía por la creación de un paquete de producto y su uso en un pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="b9031-104">This procedure walks through creating a product package and using it on a purchase order.</span></span> <span data-ttu-id="b9031-105">El pedido de compra se usará para crear un pedido para un conjunto predefinido de productos.</span><span class="sxs-lookup"><span data-stu-id="b9031-105">The purchase order will be used to create an order for a pre-defined set of products.</span></span> <span data-ttu-id="b9031-106">Este procedimiento usa la empresa de datos de demostración USRT.</span><span class="sxs-lookup"><span data-stu-id="b9031-106">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-product-package"></a><span data-ttu-id="b9031-107">Crear un paquete de producto</span><span class="sxs-lookup"><span data-stu-id="b9031-107">Create a product package</span></span>
1. <span data-ttu-id="b9031-108">Vaya a Retail y Commerce > Gestión del inventario > Reabastecimiento > Paquetes de productos.</span><span class="sxs-lookup"><span data-stu-id="b9031-108">Go to Retail and Commerce > Inventory management > Replenishment > Product packages.</span></span>
2. <span data-ttu-id="b9031-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="b9031-109">Click New.</span></span>
3. <span data-ttu-id="b9031-110">En el campo Número de paquete, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="b9031-110">In the Package number field, type a value.</span></span>
4. <span data-ttu-id="b9031-111">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="b9031-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="b9031-112">En el campo Cuenta de proveedor, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b9031-112">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="b9031-113">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b9031-113">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="b9031-114">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="b9031-114">Click Add.</span></span>
8. <span data-ttu-id="b9031-115">En el campo Código de artículo, escriba "0160".</span><span class="sxs-lookup"><span data-stu-id="b9031-115">In the Item number field, type '0160'.</span></span>
9. <span data-ttu-id="b9031-116">En el campo Tamaño, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b9031-116">In the Size field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="b9031-117">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b9031-117">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="b9031-118">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="b9031-118">In the Quantity field, enter a number.</span></span>
12. <span data-ttu-id="b9031-119">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="b9031-119">Click Add.</span></span>
13. <span data-ttu-id="b9031-120">En el campo Código de artículo, escriba "0160".</span><span class="sxs-lookup"><span data-stu-id="b9031-120">In the Item number field, type '0160'.</span></span>
14. <span data-ttu-id="b9031-121">En el campo Número de variante, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b9031-121">In the Variant number field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="b9031-122">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b9031-122">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="b9031-123">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="b9031-123">In the Quantity field, enter a number.</span></span>
17. <span data-ttu-id="b9031-124">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="b9031-124">Click Add.</span></span>
18. <span data-ttu-id="b9031-125">En el campo Código de artículo, escriba "0175".</span><span class="sxs-lookup"><span data-stu-id="b9031-125">In the Item number field, type '0175'.</span></span>
19. <span data-ttu-id="b9031-126">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="b9031-126">In the Quantity field, enter a number.</span></span>
20. <span data-ttu-id="b9031-127">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="b9031-127">Click Save.</span></span>
21. <span data-ttu-id="b9031-128">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b9031-128">Close the page.</span></span>

## <a name="add-package-to-purchase-order"></a><span data-ttu-id="b9031-129">Agregar paquete a pedido de compra</span><span class="sxs-lookup"><span data-stu-id="b9031-129">Add package to purchase order</span></span>
1. <span data-ttu-id="b9031-130">Vaya a Proveedores > Pedidos de compra > Todos los pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="b9031-130">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="b9031-131">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="b9031-131">Click New.</span></span>
3. <span data-ttu-id="b9031-132">En el campo Cuenta de proveedor, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b9031-132">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="b9031-133">En la lista, seleccione el mismo proveedor que el paquete de producto para el que se creó anteriormente, si se seleccionó un proveedor.</span><span class="sxs-lookup"><span data-stu-id="b9031-133">In the list, select the same vendor that the product package was previously created for, if a vendor was selected.</span></span>
5. <span data-ttu-id="b9031-134">Expanda la sección General.</span><span class="sxs-lookup"><span data-stu-id="b9031-134">Toggle the expansion of the General section.</span></span>
6. <span data-ttu-id="b9031-135">En el campo Sitio, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b9031-135">In the Site field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="b9031-136">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b9031-136">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="b9031-137">En el campo Almacén, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b9031-137">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="b9031-138">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b9031-138">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="b9031-139">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="b9031-139">Click OK.</span></span>
11. <span data-ttu-id="b9031-140">Alterne la expansión de la sección Detalles de línea.</span><span class="sxs-lookup"><span data-stu-id="b9031-140">Toggle the expansion of the Line details section.</span></span>
12. <span data-ttu-id="b9031-141">Haga clic en la ficha Paquetes de productos.</span><span class="sxs-lookup"><span data-stu-id="b9031-141">Click the Product packages tab.</span></span>
13. <span data-ttu-id="b9031-142">Haga clic en Línea de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="b9031-142">Click Purchase order line.</span></span>
14. <span data-ttu-id="b9031-143">Haga clic en Crear líneas de paquete.</span><span class="sxs-lookup"><span data-stu-id="b9031-143">Click Create lines from package.</span></span>
15. <span data-ttu-id="b9031-144">En la lista, busque y seleccione el paquete de producto creado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="b9031-144">In the list, find and select the product package created in previous step.</span></span>
16. <span data-ttu-id="b9031-145">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="b9031-145">In the Quantity field, enter a number.</span></span>
17. <span data-ttu-id="b9031-146">Haga clic en Crear.</span><span class="sxs-lookup"><span data-stu-id="b9031-146">Click Create.</span></span>
18. <span data-ttu-id="b9031-147">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="b9031-147">Click Save.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]