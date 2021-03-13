---
title: Pedidos de almacenes para unidades de escalado en el perímetro y en la nube
description: Este tema proporciona información sobre la capacidad de pedidos de almacén que se utiliza como parte de la carga de trabajo de la unidad de escalada de almacén.
author: perlynne
manager: tfeyr
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWarehouseOrderLine, WHSWarehouseReceiptEntry, PurchTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2021-01-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: c04127b9fe621d962be2d7fe06358b3bd1b78916
ms.sourcegitcommit: 289e9183d908825f4c8dcf85d9affd4119238d0c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2021
ms.locfileid: "5105728"
---
# <a name="warehouse-orders-for-cloud-and-edge-scale-units"></a><span data-ttu-id="43801-103">Pedidos de almacenes para unidades de escalado en el perímetro y en la nube</span><span class="sxs-lookup"><span data-stu-id="43801-103">Warehouse orders for cloud and edge scale units</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!WARNING]
> <span data-ttu-id="43801-104">No todas las funciones comerciales son totalmente compatibles con la versión preliminar pública cuando se utilizan cargas de trabajo de unidades de escalado.</span><span class="sxs-lookup"><span data-stu-id="43801-104">Not all business functionality is fully supported in the public preview when scale unit workloads are used.</span></span> <span data-ttu-id="43801-105">Si solo está usando unidades de escalado, asegúrese de utilizar solo los procesos que este tema describe explícitamente como compatibles.</span><span class="sxs-lookup"><span data-stu-id="43801-105">If you're using scale units, be sure to use only those processes that this topic explicitly describes as supported.</span></span>

## <a name="what-are-warehouse-orders"></a><span data-ttu-id="43801-106">¿Qué son los pedidos de almacén?</span><span class="sxs-lookup"><span data-stu-id="43801-106">What are warehouse orders?</span></span>

<span data-ttu-id="43801-107">Los *pedidos de almacén* son un tipo de pedido que se creó para admitir implementaciones de almacén de unidades de escalado y concentradores.</span><span class="sxs-lookup"><span data-stu-id="43801-107">*Warehouse orders* are a type of order that was created to support hub and scale unit warehouse deployments.</span></span> <span data-ttu-id="43801-108">Le permiten recibir inventario cuando está ejecutando una carga de trabajo de almacén en una unidad de escalado.</span><span class="sxs-lookup"><span data-stu-id="43801-108">They let you receive inventory when you're running a warehouse workload on a scale unit.</span></span> <span data-ttu-id="43801-109">Actualmente se utilizan solo con pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="43801-109">They are currently used only with purchase orders.</span></span>

<span data-ttu-id="43801-110">Los pedidos de almacén se utilizan como parte del procesamiento de la administración del almacén, como cuando la aplicación de almacén se utiliza para registrar el inventario físico disponible durante el procesamiento de un pedido de compra entrante.</span><span class="sxs-lookup"><span data-stu-id="43801-110">Warehouse orders are used as part of warehouse management processing, such as when the warehouse app is used to register physical on-hand inventory during processing of an inbound purchase order.</span></span> <span data-ttu-id="43801-111">Los pedidos de almacén se crean como parte del proceso *Liberar al almacén* que está disponible para pedidos de compra que especifican un almacén de unidad de escalada y artículos que están habilitados para usar procesos de administración de almacén.</span><span class="sxs-lookup"><span data-stu-id="43801-111">Warehouse orders are created as part of the *Release to warehouse* process that is available for purchase orders that specify a scale unit warehouse and items that are enabled to use warehouse management processes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="43801-112">Los pedidos de almacén están disponibles solo en implementaciones que utilizan [cargas de trabajo de administración de almacenes para unidades de escalado de perímetro y en la nube](cloud-edge-workload-warehousing.md).</span><span class="sxs-lookup"><span data-stu-id="43801-112">Warehouse orders are available only in deployments that use [warehouse management workloads for cloud and edge scale units](cloud-edge-workload-warehousing.md).</span></span>

## <a name="create-a-warehouse-order"></a><span data-ttu-id="43801-113">Crear un pedido de almacén</span><span class="sxs-lookup"><span data-stu-id="43801-113">Create a warehouse order</span></span>

<span data-ttu-id="43801-114">Para crear un pedido de almacén, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="43801-114">To create a warehouse order, follow these steps.</span></span>

1. <span data-ttu-id="43801-115">Inicie sesión en la instancia de Microsoft Dynamics 365 Supply Chain Management que se está ejecutando en el concentrador.</span><span class="sxs-lookup"><span data-stu-id="43801-115">Sign in to the instance of Microsoft Dynamics 365 Supply Chain Management that is running on the hub.</span></span> <span data-ttu-id="43801-116">(Debe iniciar el proceso *Liberar al almacén* mientras está conectado en el concentrador).</span><span class="sxs-lookup"><span data-stu-id="43801-116">(You must initiate the *Release to warehouse* process while you're signed in on the hub.)</span></span>
1. <span data-ttu-id="43801-117">Vaya a **Adquisición y abastecimiento \> Pedidos de compra \> Todos los pedidos de compra**.</span><span class="sxs-lookup"><span data-stu-id="43801-117">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="43801-118">En el panel de acciones, en la pestaña **Almacén**, en el grupo **Acciones**, seleccione **Liberar al almacén**.</span><span class="sxs-lookup"><span data-stu-id="43801-118">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="43801-119">Para ver las líneas de pedido de almacén relacionadas, abra el pedido de compra relevante, seleccione una línea en la sección **Líneas de pedido de compra** y, después, en la barra de herramientas, seleccione **Almacén \> Líneas de pedido de almacén**.</span><span class="sxs-lookup"><span data-stu-id="43801-119">To view the related warehouse order lines, open the relevant purchase order, select a line in the **Purchase order lines** section, and then, on the toolbar, select **Warehouse \> Warehouse order lines**.</span></span> <span data-ttu-id="43801-120">Para ver todas las líneas, vaya a **Gestión de almacenes \> Consultas e informes \> Líneas de pedido de almacén**.</span><span class="sxs-lookup"><span data-stu-id="43801-120">To view all the lines, go to **Warehouse management \> Inquiries and reports \> Warehouse order lines**.</span></span>

## <a name="cancel-a-warehouse-order"></a><span data-ttu-id="43801-121">Cancelar un pedido de almacén</span><span class="sxs-lookup"><span data-stu-id="43801-121">Cancel a warehouse order</span></span>

<span data-ttu-id="43801-122">Como parte del proceso *Liberar al almacén*, las transacciones de inventario de pedidos de compra están vinculadas a los pedidos de almacén y bloqueadas para que no las actualice el concentrador.</span><span class="sxs-lookup"><span data-stu-id="43801-122">As part of the *Release to warehouse* process, purchase order inventory transactions are linked to warehouse orders and locked from being updated by the hub.</span></span> <span data-ttu-id="43801-123">Si liberó al almacén por error o si tiene alguna otra razón para revertir la creación de líneas de pedido de almacén, puede solicitar cancelar las líneas de pedido de almacén.</span><span class="sxs-lookup"><span data-stu-id="43801-123">If you released to the warehouse by mistake, or if you have some other reason to reverse the creation of warehouse order lines, you can request to cancel warehouse order lines.</span></span>

<span data-ttu-id="43801-124">Para cancelar las líneas de pedido de almacén, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="43801-124">To cancel warehouse order lines, follow these steps.</span></span>

1. <span data-ttu-id="43801-125">Inicie sesión en la instancia de Supply Chain Management que se está ejecutando en el concentrador.</span><span class="sxs-lookup"><span data-stu-id="43801-125">Sign in to the Supply Chain Management instance that is running on the hub.</span></span>
1. <span data-ttu-id="43801-126">Vaya a **Gestión de almacenes \> Consultas e informes \> Líneas de pedido de almacén**.</span><span class="sxs-lookup"><span data-stu-id="43801-126">Go to **Warehouse management \> Inquiries and reports \> Warehouse order lines**.</span></span>
1. <span data-ttu-id="43801-127">Seleccione la línea relevante.</span><span class="sxs-lookup"><span data-stu-id="43801-127">Select the relevant line.</span></span>
1. <span data-ttu-id="43801-128">En el panel de acciones, seleccione **Cancelar líneas de pedido de almacén**.</span><span class="sxs-lookup"><span data-stu-id="43801-128">On the Action Pane, select **Cancel warehouse order lines**.</span></span>

> [!NOTE]
> <span data-ttu-id="43801-129">Se rechazará la solicitud de cancelación de líneas para cualquier línea que ya esté pendiente de cancelación o que se esté procesando de forma activa en un almacén que está ejecutando su carga de trabajo en una unidad de escalado.</span><span class="sxs-lookup"><span data-stu-id="43801-129">The request to cancel lines will be denied for any lines that are already pending cancellation or that are actively being processed at a warehouse that is running its workload on a scale unit.</span></span>

## <a name="monitor-a-warehouse-order"></a><span data-ttu-id="43801-130">Supervisar un pedido de almacén</span><span class="sxs-lookup"><span data-stu-id="43801-130">Monitor a warehouse order</span></span>

<span data-ttu-id="43801-131">En la visualización **Líneas de pedido de almacén**, puede supervisar el progreso de la recepción entrante revisando los valores en la columna **Cantidad restante**.</span><span class="sxs-lookup"><span data-stu-id="43801-131">In the **Warehouse order lines** view, you can monitor the progress of inbound receiving by reviewing the values in the **Quantity left to receive** column.</span></span> <span data-ttu-id="43801-132">Para ver los detalles relacionados con el trabajo que se realiza mediante la aplicación del almacén, siga uno de estos pasos.</span><span class="sxs-lookup"><span data-stu-id="43801-132">To view details that are related to work that is done by using the warehouse app, follow one of these steps.</span></span>

- <span data-ttu-id="43801-133">Vaya a **Gestión de almacenes \> Consultas e informes \> Líneas de pedido de almacén** y use el filtro para encontrar las líneas que está buscando.</span><span class="sxs-lookup"><span data-stu-id="43801-133">Go to **Warehouse management \> Inquiries and reports \> Warehouse order lines**, and use the filter to find the lines that you're looking for.</span></span>
- <span data-ttu-id="43801-134">Vaya a **Adquisición y abastecimiento \> Pedidos de compra \> Todos los pedidos de compra** y abra el pedido de compra relevante.</span><span class="sxs-lookup"><span data-stu-id="43801-134">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**, and open the relevant purchase order.</span></span> <span data-ttu-id="43801-135">En la sección **Líneas de pedido de compra**, seleccione una o más líneas y luego, en la barra de herramientas, seleccione **Almacén \> Entradas de recepción de almacén**.</span><span class="sxs-lookup"><span data-stu-id="43801-135">In the **Purchase order lines** section, select one or more lines, and then, on the toolbar, select **Warehouse \> Warehouse receipt entries**.</span></span>
