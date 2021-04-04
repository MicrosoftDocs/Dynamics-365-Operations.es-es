---
title: Crear activos en función de los pedidos de compra
description: En este tema se explica cómo puede crear una lista de artículos de activo que se puede usar como la base para crear activos para trabajos de mantenimiento en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectItem, EntAssetPendingAssets
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 97b40528db4acc2627b087e8ee90bfd1fd79efa7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5253287"
---
# <a name="create-assets-based-on-purchase-orders"></a><span data-ttu-id="23b49-103">Crear activos en función de los pedidos de compra</span><span class="sxs-lookup"><span data-stu-id="23b49-103">Create assets based on purchase orders</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="23b49-104">En este tema se explica cómo puede crear una lista de artículos de activo que se puede usar como la base para crear activos para trabajos de mantenimiento en Administración de activos.</span><span class="sxs-lookup"><span data-stu-id="23b49-104">This topic explains how you can create a list of asset items that can be used as a basis for creating assets for maintenance jobs in Asset Management.</span></span> <span data-ttu-id="23b49-105">Según los artículos del activo, podrá ver una lista de las líneas de pedido de compra que se han creado en esos artículos.</span><span class="sxs-lookup"><span data-stu-id="23b49-105">Based on the asset items, you are able to view a list of the purchase order lines that have been created on those items.</span></span> <span data-ttu-id="23b49-106">El propósito de esta funcionalidad es crear fácilmente un activo en Administración de activos a partir de un pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="23b49-106">The purpose of this functionality is to easily create an asset in Asset Management based on a purchase order.</span></span>

<span data-ttu-id="23b49-107">Primero, se configuran los artículos que se van a usar para crear activos a partir de un pedido de compra en **Artículos de activo**.</span><span class="sxs-lookup"><span data-stu-id="23b49-107">First, you set up the items to be used for creating assets from a purchase order in **Asset items**.</span></span> <span data-ttu-id="23b49-108">Después de crear una línea de pedido de compra, debe crear los activos en **Activos pendientes**.</span><span class="sxs-lookup"><span data-stu-id="23b49-108">After creating a purchase order line, you create the assets in **Pending assets**.</span></span> <span data-ttu-id="23b49-109">Se puede decidir en qué etapa del pedido de compra se debe crear el activo.</span><span class="sxs-lookup"><span data-stu-id="23b49-109">It is possible to decide at which stage of the purchase order the asset should be created.</span></span>


## <a name="select-asset-items"></a><span data-ttu-id="23b49-110">Seleccionar artículos de activo</span><span class="sxs-lookup"><span data-stu-id="23b49-110">Select asset items</span></span>

1. <span data-ttu-id="23b49-111">Haga clic en **Administración de activos** > **Configuración** > **Activos** > **Artículos**.</span><span class="sxs-lookup"><span data-stu-id="23b49-111">Click **Asset management** > **Setup** > **Assets** > **Items**.</span></span>
2. <span data-ttu-id="23b49-112">Haga clic en **Nuevo** para crear un nuevo artículo de activo.</span><span class="sxs-lookup"><span data-stu-id="23b49-112">Click **New** to create a new asset item.</span></span>
3. <span data-ttu-id="23b49-113">Seleccione el elemento el campo **Número de artículo**.</span><span class="sxs-lookup"><span data-stu-id="23b49-113">Select the item in the **Item number** field.</span></span> <span data-ttu-id="23b49-114">Al salir de ese campo, el nombre del artículo se inserta automáticamente en el campo **Nombre del producto**.</span><span class="sxs-lookup"><span data-stu-id="23b49-114">When you leave that field, the item name is automatically inserted in the **Product name** field.</span></span>
4. <span data-ttu-id="23b49-115">En la ficha desplegable **General**, seleccione un tipo de activo para el artículo.</span><span class="sxs-lookup"><span data-stu-id="23b49-115">On the **General** FastTab, select an asset type for the item.</span></span>
5. <span data-ttu-id="23b49-116">Seleccione el fabricante y el modelo del activo para el artículo.</span><span class="sxs-lookup"><span data-stu-id="23b49-116">Select asset manufacturer and model for the item.</span></span>
6. <span data-ttu-id="23b49-117">Guarde el artículo.</span><span class="sxs-lookup"><span data-stu-id="23b49-117">Save the item.</span></span>


## <a name="create-assets-from-pending-assets"></a><span data-ttu-id="23b49-118">Crear activos a partir de activos pendientes</span><span class="sxs-lookup"><span data-stu-id="23b49-118">Create assets from pending assets</span></span>

1. <span data-ttu-id="23b49-119">Haga clic en **Administración de activos** > **Común** > **Activos** > **Activos pendiente**.</span><span class="sxs-lookup"><span data-stu-id="23b49-119">Click **Asset management** > **Common** > **Assets** > **Pending Assets**.</span></span>
2. <span data-ttu-id="23b49-120">Verá una lista actualizada de los pedidos de compra en función de los artículos seleccionados en **Artículos de activo**.</span><span class="sxs-lookup"><span data-stu-id="23b49-120">You will see an updated list of the purchase orders based on the items selected in **Asset items**.</span></span>
3. <span data-ttu-id="23b49-121">Puede filtrar el estado de los pedidos de compra para seleccionar en qué estado de ciclo de vida debe crearse el activo.</span><span class="sxs-lookup"><span data-stu-id="23b49-121">You can filter the status of purchase orders to select at which lifecycle state the asset should be created.</span></span> <span data-ttu-id="23b49-122">Por ejemplo, puede que solo quiera crear activos cuando se registre una recepción de productos en un pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="23b49-122">For example, you may only want to create assets when a product receipt has been posted on a purchase order.</span></span>
4. <span data-ttu-id="23b49-123">Seleccione el vínculo **Número de referencia** en una línea de pedido de compra para ver información detallada sobre el artículo.</span><span class="sxs-lookup"><span data-stu-id="23b49-123">Select the **Reference number** link on a purchase order line to view detailed information about the item.</span></span>
5. <span data-ttu-id="23b49-124">Si desea editar las dimensiones que se van a mostrar en la ficha desplegable **Dimensiones de inventario**, haga clic en el botón **Mostrar dimensiones** y realice las selecciones necesarias.</span><span class="sxs-lookup"><span data-stu-id="23b49-124">If you want to edit which dimensions are displayed on the **Inventory dimensions** FastTab, click the **Display Dimensions** button, and make your selections.</span></span>
6. <span data-ttu-id="23b49-125">Si desea crear un activo a partir de una línea de pedido de compra, active la casilla de la columna **Marcar** para dicha línea en la página de lista, y haga clic en **Crear activos**.</span><span class="sxs-lookup"><span data-stu-id="23b49-125">If you want to create an asset based on a purchase order line, select the check box in the **Mark** column for that line on the list page, and click **Create assets**.</span></span> <span data-ttu-id="23b49-126">Se mostrará un mensaje para notificarle el identificador del activo.</span><span class="sxs-lookup"><span data-stu-id="23b49-126">A message will be displayed informing you of the asset ID.</span></span>
7. <span data-ttu-id="23b49-127">Seleccione el activo en la lista **Todos los activos** y haga clic en el botón **Editar** para agregar más información al activo.</span><span class="sxs-lookup"><span data-stu-id="23b49-127">Select the asset in the **All assets** list and click **Edit** to add more information to the asset.</span></span>
8. <span data-ttu-id="23b49-128">En **Activos pendientes**, si desea eliminar una línea porque no desea crear un activo, active la casilla en la columna **Marcar** para dicha línea y haga clic en **Descartar activos pendientes**.</span><span class="sxs-lookup"><span data-stu-id="23b49-128">In **Pending assets**, if you want to delete a line because you don't want to create an asset, select the check box in the **Mark** column for that line, and click **Discard pending assets**.</span></span> <span data-ttu-id="23b49-129">Se mostrará un mensaje para notificarle el identificador del activo.</span><span class="sxs-lookup"><span data-stu-id="23b49-129">A message will be displayed informing you of the asset ID.</span></span> <span data-ttu-id="23b49-130">No se eliminan ni el pedido de compra ni el pedido de ventas, solo se elimina el registro a partir del cual podría haber creado un activo en **Administración de activos**.</span><span class="sxs-lookup"><span data-stu-id="23b49-130">You are not deleting the purchase order or sales order, just the record from which you could have created an asset in **Asset Management**.</span></span>

>[!NOTE]
><span data-ttu-id="23b49-131">Todas las dimensiones del producto (tamaño, color, configuración, etc.). se transfieren automáticamente a los atributos del activo.</span><span class="sxs-lookup"><span data-stu-id="23b49-131">All product dimensions (size, color, configuration etc.) are automatically transferred to the asset attributes.</span></span> <span data-ttu-id="23b49-132">Las dimensiones de seguimiento (número de serie) se almacenan directamente en el activo en el momento de su creación.</span><span class="sxs-lookup"><span data-stu-id="23b49-132">Tracking dimensions (serial number) are stored directly on the asset when the asset is created.</span></span>


## <a name="find-pending-assets"></a><span data-ttu-id="23b49-133">Buscar activos pendientes</span><span class="sxs-lookup"><span data-stu-id="23b49-133">Find pending assets</span></span>

<span data-ttu-id="23b49-134">Puede ejecutar un **Recuento de activos pendientes** para ver si hay activos pendientes.</span><span class="sxs-lookup"><span data-stu-id="23b49-134">You can run a **Pending asset count** to check for pending assets.</span></span> <span data-ttu-id="23b49-135">Por ejemplo, esta función puede utilizarse para recibir una notificación cada vez que un activo pendiente esté listo para la creación de un activo.</span><span class="sxs-lookup"><span data-stu-id="23b49-135">For example, this function can be used for receiving a notification each time a pending asset is ready to be created as an asset.</span></span>

1. <span data-ttu-id="23b49-136">Haga clic en **Administración de activos** > **Periódico** > **Activos** > **Recuento de activos pendientes**.</span><span class="sxs-lookup"><span data-stu-id="23b49-136">Click **Asset management** > **Periodic** > **Assets** > **Pending asset count**.</span></span>
2. <span data-ttu-id="23b49-137">Haga clic en **Aceptar** para ejecutar el trabajo y actualizar la lista en **Activos pendientes**.</span><span class="sxs-lookup"><span data-stu-id="23b49-137">Click **OK** to run the job and update the list in **Pending assets**.</span></span>
3. <span data-ttu-id="23b49-138">Puede configurar este trabajo para que se ejecute como un trabajo por lotes (por ejemplo, una vez al día).</span><span class="sxs-lookup"><span data-stu-id="23b49-138">You can set up this job to run as a batch job, for example, once each day.</span></span>

<span data-ttu-id="23b49-139">**Precaución:** si se cambian los datos en un pedido de compra *después* de crear un activo partir del artículo correspondiente, esos cambios no se reflejarán en el activo.</span><span class="sxs-lookup"><span data-stu-id="23b49-139">**Caution:** If data is changed on a purchase order *after* you have created an asset based on the appertaining item, those changes will not be reflected on the asset.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]