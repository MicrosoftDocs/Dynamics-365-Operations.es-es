---
title: Administrar inventario en tienda
description: "En este artículo se describen los tipos de documentos que puede usar para gestionar el inventario."
author: rubencdelgado
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 21391
ms.assetid: bfef3717-d0e0-491d-8466-d8a9c995177d
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 6245d37ace9f46ecce83a0cf80a014d5de898bbc
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="manage-store-inventory"></a><span data-ttu-id="86046-103">Administrar inventario en tienda</span><span class="sxs-lookup"><span data-stu-id="86046-103">Manage store inventory</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="86046-104">En este artículo se describen los tipos de documentos que puede usar para gestionar el inventario.</span><span class="sxs-lookup"><span data-stu-id="86046-104">This article describes the types of documents that you can use to manage inventory.</span></span>

<span data-ttu-id="86046-105">Puede utilizar los siguientes tipos de documentos para gestionar el inventario de la organización.</span><span class="sxs-lookup"><span data-stu-id="86046-105">You can use the following types of documents to manage your organization's inventory.</span></span>

## <a name="purchase-orders"></a><span data-ttu-id="86046-106">Pedidos de compra</span><span class="sxs-lookup"><span data-stu-id="86046-106">Purchase orders</span></span>
<span data-ttu-id="86046-107">Los pedidos de compra se crean en la oficina central.</span><span class="sxs-lookup"><span data-stu-id="86046-107">Purchase orders are created at the head office.</span></span> <span data-ttu-id="86046-108">Si se incluye un almacén comercial en el encabezado del pedido de compra, el pedido se puede recibir en la tienda mediante Modern POS (MPOS) o Cloud POS en Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="86046-108">If a retail warehouse is included in the purchase order header, the order can be received at the store by using Modern POS (MPOS) or Cloud POS in Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="86046-109">Después de especificar las cantidades que se reciben en la tienda, se pueden guardar de manera local para realizar otras modificaciones.</span><span class="sxs-lookup"><span data-stu-id="86046-109">After the quantities that are received at the store are entered, they can be saved locally for additional modification.</span></span> <span data-ttu-id="86046-110">Otra opción es que las cantidades se comprometan y se envíen a la oficina central.</span><span class="sxs-lookup"><span data-stu-id="86046-110">Alternatively, the quantities can be committed and sent to the head office.</span></span> <span data-ttu-id="86046-111">En la oficina central, las cantidades que se han recibido en la tienda se muestran en Dynamics 365 for Retail, en el campo **Recibir ahora** del pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="86046-111">At the head office, the quantities that were received at the store are displayed in Dynamics 365 for Retail, in the **Receive now** field on the purchase order.</span></span>

## <a name="transfer-orders"></a><span data-ttu-id="86046-112">Transferir pedidos</span><span class="sxs-lookup"><span data-stu-id="86046-112">Transfer orders</span></span>
<span data-ttu-id="86046-113">Un pedido de transferencia puede especificar que una tienda concreta es una ubicación desde la que se pueden enviar artículos.</span><span class="sxs-lookup"><span data-stu-id="86046-113">A transfer order can specify that a particular store is a location that items can be shipped from.</span></span> <span data-ttu-id="86046-114">En este caso, el pedido de transferencia aparece en la tienda como una solicitud de selección en MPOS o PDV en la nube.</span><span class="sxs-lookup"><span data-stu-id="86046-114">In this case, the transfer order appears at the store as a picking request in MPOS or Cloud POS.</span></span> <span data-ttu-id="86046-115">Después de seleccionar las cantidades solicitadas, se comprometen y se envían a la oficina central.</span><span class="sxs-lookup"><span data-stu-id="86046-115">After the quantities that are requested are picked, they are committed and sent to the head office.</span></span> <span data-ttu-id="86046-116">En la oficina central, las cantidades que se han seleccionado en la tienda se muestran en Dynamics 365 for Retail, en el campo **Enviar ahora** del pedido de transferencia.</span><span class="sxs-lookup"><span data-stu-id="86046-116">At the head office, the quantities that were picked at the store are displayed in Dynamics 365 for Retail, in the **Ship now** field on the transfer order.</span></span> <span data-ttu-id="86046-117">Un pedido de transferencia puede especificar que una tienda concreta es una ubicación a la que se pueden enviar artículos.</span><span class="sxs-lookup"><span data-stu-id="86046-117">A transfer order may specify that a particular store is a location that items can be shipped to.</span></span> <span data-ttu-id="86046-118">En este caso, el pedido de transferencia aparece en la tienda como una solicitud de recepción en MPOS o PDV en la nube.</span><span class="sxs-lookup"><span data-stu-id="86046-118">In this case, the transfer order appears at the store as a receiving request in MPOS or Cloud POS.</span></span> <span data-ttu-id="86046-119">Después de especificar las cantidades que se reciben en la tienda, se pueden guardar de manera local para realizar otras modificaciones.</span><span class="sxs-lookup"><span data-stu-id="86046-119">After the quantities that are received at the store are entered, they can be saved locally for additional modification.</span></span> <span data-ttu-id="86046-120">Otra opción es que las cantidades se comprometan y se envíen a la oficina central.</span><span class="sxs-lookup"><span data-stu-id="86046-120">Alternatively, the quantities can be committed and sent to the head office.</span></span> <span data-ttu-id="86046-121">En la oficina central, las cantidades que se han recibido en la tienda se muestran en Dynamics 365 for Retail, en el campo **Recibir ahora** del pedido de transferencia.</span><span class="sxs-lookup"><span data-stu-id="86046-121">At the head office, the quantities that were received at the store are displayed in Dynamics 365 for Retail, in the **Receive now** field on the transfer order.</span></span>

## <a name="stock-counts"></a><span data-ttu-id="86046-122">Recuentos de existencias</span><span class="sxs-lookup"><span data-stu-id="86046-122">Stock counts</span></span>
<span data-ttu-id="86046-123">Los recuentos de existencias se pueden programar o no.</span><span class="sxs-lookup"><span data-stu-id="86046-123">Stock counts can be either scheduled or unscheduled.</span></span> <span data-ttu-id="86046-124">Los recuentos de existencias programados se inician en la oficina central, que especifica los artículos que se deben contar.</span><span class="sxs-lookup"><span data-stu-id="86046-124">Scheduled stock counts are initiated at the head office, which specifies the items that must be counted.</span></span> <span data-ttu-id="86046-125">La oficina central crea un documento que se puede recibir en la tienda, donde se especifican las cantidades de existencias disponibles reales en MPOS o PDV en la nube.</span><span class="sxs-lookup"><span data-stu-id="86046-125">The head office creates a counting document that can be received at the store, where the quantities of actual on-hand stock are entered in MPOS or Cloud POS.</span></span> <span data-ttu-id="86046-126">Los recuentos de existencias no programados se inician en una tienda y las cantidades de existencias disponibles se actualizan en MPOS o PDV en la nube.</span><span class="sxs-lookup"><span data-stu-id="86046-126">Unscheduled stock counts are initiated at a store, and the quantities of actual on-hand stock are updated in either MPOS or Cloud POS.</span></span> <span data-ttu-id="86046-127">A diferencia de los recuentos programados de existencias, los recuentos no programados de existencias no tienen una lista predefinida de artículos.</span><span class="sxs-lookup"><span data-stu-id="86046-127">Unlike scheduled stock counts, unscheduled stock counts do not have a predefined list of items.</span></span> <span data-ttu-id="86046-128">Cuando finaliza un recuento de existencias de cualquier tipo, se compromete y se envía a la oficina central.</span><span class="sxs-lookup"><span data-stu-id="86046-128">When a stock count of either type is completed, it is committed and sent to the head office.</span></span> <span data-ttu-id="86046-129">En la oficina central, se valida y se registra el recuento.</span><span class="sxs-lookup"><span data-stu-id="86046-129">At the head office, the count is validated and posted.</span></span>

## <a name="inventory-lookup"></a><span data-ttu-id="86046-130">Búsqueda de inventario</span><span class="sxs-lookup"><span data-stu-id="86046-130">Inventory lookup</span></span>
<span data-ttu-id="86046-131">La cantidad de producto disponible actualmente para múltiples tiendas y almacenes se puede ver en la página de consulta de inventario.</span><span class="sxs-lookup"><span data-stu-id="86046-131">The current product quantity on hand for multiple stores and warehouses can be viewed on the Inventory lookup page.</span></span> <span data-ttu-id="86046-132">Además de la cantidad disponible actual, las cantidades futuras de neto no comprometido (NNC) se pueden visualizar para cada tienda.</span><span class="sxs-lookup"><span data-stu-id="86046-132">In addition to the current quantity on hand, the future available to promise (ATP) quantities can be viewed for each individual store.</span></span> <span data-ttu-id="86046-133">Para ello, seleccione la tienda para la que desea ver el NNC y después para haga clic en **Mostrar disponibilidad en tienda**.</span><span class="sxs-lookup"><span data-stu-id="86046-133">To do so, select the store that you want to view the ATP for and then click **Show store availability**.</span></span>





