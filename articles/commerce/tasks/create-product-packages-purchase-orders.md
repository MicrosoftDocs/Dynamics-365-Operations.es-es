---
title: " Crear paquetes de producto para pedidos de compra"
description: Este procedimiento le guía por la creación de un paquete de producto y su uso en un pedido de compra.
author: josaw1
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2b0084c6b4acbf14e3afec552575d5be26114237
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141380"
---
# <a name="create-product-packages-for-purchase-orders"></a><span data-ttu-id="ac84d-103"> Crear paquetes de producto para pedidos de compra</span><span class="sxs-lookup"><span data-stu-id="ac84d-103">Create product packages for purchase orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ac84d-104">Este procedimiento le guía por la creación de un paquete de producto y su uso en un pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="ac84d-104">This procedure walks through creating a product package and using it on a purchase order.</span></span> <span data-ttu-id="ac84d-105">El pedido de compra se usará para crear un pedido para un conjunto predefinido de productos.</span><span class="sxs-lookup"><span data-stu-id="ac84d-105">The purchase order will be used to create an order for a pre-defined set of products.</span></span> <span data-ttu-id="ac84d-106">Este procedimiento usa la empresa de datos de demostración USRT.</span><span class="sxs-lookup"><span data-stu-id="ac84d-106">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-product-package"></a><span data-ttu-id="ac84d-107">Crear un paquete de producto</span><span class="sxs-lookup"><span data-stu-id="ac84d-107">Create a product package</span></span>
1. <span data-ttu-id="ac84d-108">Vaya a Retail y Commerce > Gestión del inventario > Reabastecimiento > Paquetes de productos.</span><span class="sxs-lookup"><span data-stu-id="ac84d-108">Go to Retail and Commerce > Inventory management > Replenishment > Product packages.</span></span>
2. <span data-ttu-id="ac84d-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="ac84d-109">Click New.</span></span>
3. <span data-ttu-id="ac84d-110">En el campo Número de paquete, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="ac84d-110">In the Package number field, type a value.</span></span>
4. <span data-ttu-id="ac84d-111">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="ac84d-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="ac84d-112">En el campo Cuenta de proveedor, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ac84d-112">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="ac84d-113">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ac84d-113">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="ac84d-114">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="ac84d-114">Click Add.</span></span>
8. <span data-ttu-id="ac84d-115">En el campo Código de artículo, escriba "0160".</span><span class="sxs-lookup"><span data-stu-id="ac84d-115">In the Item number field, type '0160'.</span></span>
9. <span data-ttu-id="ac84d-116">En el campo Tamaño, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ac84d-116">In the Size field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="ac84d-117">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ac84d-117">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="ac84d-118">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="ac84d-118">In the Quantity field, enter a number.</span></span>
12. <span data-ttu-id="ac84d-119">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="ac84d-119">Click Add.</span></span>
13. <span data-ttu-id="ac84d-120">En el campo Código de artículo, escriba "0160".</span><span class="sxs-lookup"><span data-stu-id="ac84d-120">In the Item number field, type '0160'.</span></span>
14. <span data-ttu-id="ac84d-121">En el campo Número de variante, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ac84d-121">In the Variant number field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="ac84d-122">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ac84d-122">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="ac84d-123">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="ac84d-123">In the Quantity field, enter a number.</span></span>
17. <span data-ttu-id="ac84d-124">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="ac84d-124">Click Add.</span></span>
18. <span data-ttu-id="ac84d-125">En el campo Código de artículo, escriba "0175".</span><span class="sxs-lookup"><span data-stu-id="ac84d-125">In the Item number field, type '0175'.</span></span>
19. <span data-ttu-id="ac84d-126">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="ac84d-126">In the Quantity field, enter a number.</span></span>
20. <span data-ttu-id="ac84d-127">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="ac84d-127">Click Save.</span></span>
21. <span data-ttu-id="ac84d-128">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ac84d-128">Close the page.</span></span>

## <a name="add-package-to-purchase-order"></a><span data-ttu-id="ac84d-129">Agregar paquete a pedido de compra</span><span class="sxs-lookup"><span data-stu-id="ac84d-129">Add package to purchase order</span></span>
1. <span data-ttu-id="ac84d-130">Vaya a Proveedores > Pedidos de compra > Todos los pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="ac84d-130">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="ac84d-131">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="ac84d-131">Click New.</span></span>
3. <span data-ttu-id="ac84d-132">En el campo Cuenta de proveedor, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ac84d-132">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="ac84d-133">En la lista, seleccione el mismo proveedor que el paquete de producto para el que se creó anteriormente, si se seleccionó un proveedor.</span><span class="sxs-lookup"><span data-stu-id="ac84d-133">In the list, select the same vendor that the product package was previously created for, if a vendor was selected.</span></span>
5. <span data-ttu-id="ac84d-134">Expanda la sección General.</span><span class="sxs-lookup"><span data-stu-id="ac84d-134">Toggle the expansion of the General section.</span></span>
6. <span data-ttu-id="ac84d-135">En el campo Sitio, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ac84d-135">In the Site field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="ac84d-136">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ac84d-136">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="ac84d-137">En el campo Almacén, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ac84d-137">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="ac84d-138">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ac84d-138">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="ac84d-139">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="ac84d-139">Click OK.</span></span>
11. <span data-ttu-id="ac84d-140">Alterne la expansión de la sección Detalles de línea.</span><span class="sxs-lookup"><span data-stu-id="ac84d-140">Toggle the expansion of the Line details section.</span></span>
12. <span data-ttu-id="ac84d-141">Haga clic en la ficha Paquetes de productos.</span><span class="sxs-lookup"><span data-stu-id="ac84d-141">Click the Product packages tab.</span></span>
13. <span data-ttu-id="ac84d-142">Haga clic en Línea de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="ac84d-142">Click Purchase order line.</span></span>
14. <span data-ttu-id="ac84d-143">Haga clic en Crear líneas de paquete.</span><span class="sxs-lookup"><span data-stu-id="ac84d-143">Click Create lines from package.</span></span>
15. <span data-ttu-id="ac84d-144">En la lista, busque y seleccione el paquete de producto creado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="ac84d-144">In the list, find and select the product package created in previous step.</span></span>
16. <span data-ttu-id="ac84d-145">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="ac84d-145">In the Quantity field, enter a number.</span></span>
17. <span data-ttu-id="ac84d-146">Haga clic en Crear.</span><span class="sxs-lookup"><span data-stu-id="ac84d-146">Click Create.</span></span>
18. <span data-ttu-id="ac84d-147">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="ac84d-147">Click Save.</span></span>

