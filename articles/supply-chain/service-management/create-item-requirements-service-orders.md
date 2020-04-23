---
title: Crear requisito del artículo desde el pedido de servicio
description: Si necesita reservar artículos específicos para un pedido de servicio, puede crear requisitos de artículo de inventario para él.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1c5ca3c1e74c642de117c708c039614da9e0ec15
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3202868"
---
# <a name="create-item-requirements-for-service-orders"></a><span data-ttu-id="c188a-103">Crear requisito del artículo desde el pedido de servicio</span><span class="sxs-lookup"><span data-stu-id="c188a-103">Create item requirements for service orders</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="c188a-104">Puede crear un pedido de servicio para administrar y realizar un seguimiento de los servicios que proporciona a sus clientes.</span><span class="sxs-lookup"><span data-stu-id="c188a-104">You can create a service order to track and manage services that you provide to your customers.</span></span> <span data-ttu-id="c188a-105">Si necesita reservar artículos específicos para un pedido de servicio, puede crear requisitos de artículo de inventario para él.</span><span class="sxs-lookup"><span data-stu-id="c188a-105">If you need to reserve specific items for a service order, you can create inventory item requirements for it.</span></span> <span data-ttu-id="c188a-106">Un requisito de artículo se puede usar inmediatamente del inventario o bien, puede iniciar un pedido de producción para el artículo.</span><span class="sxs-lookup"><span data-stu-id="c188a-106">An item requirement can be immediately consumed from inventory, or it can initiate a production order for the item.</span></span>

<span data-ttu-id="c188a-107">Si usa un requisito de artículo en lugar de una transacción de artículos, podrá planificar la entrega justo antes del uso real del artículo, crear un pedido de compras, incluir el artículo en el marco del acuerdo comercial e incluir el requisito de artículo en la planificación de producción.</span><span class="sxs-lookup"><span data-stu-id="c188a-107">By using an item requirement instead of an item transaction, you can plan for delivery just before the item is actually used, create a purchase order, include the item in the trade-agreement framework, and include the item requirement in production planning.</span></span>

<span data-ttu-id="c188a-108">Los requisitos de artículo para los pedidos de servicio se procesan a través de un proyecto.</span><span class="sxs-lookup"><span data-stu-id="c188a-108">Item requirements for service orders are processed through a project.</span></span> <span data-ttu-id="c188a-109">Para crear un requisito de artículo en un pedido de servicio, este último debe estar asignado a un proyecto.</span><span class="sxs-lookup"><span data-stu-id="c188a-109">To create an item requirement on a service order, the service order must be assigned to a project.</span></span> <span data-ttu-id="c188a-110">Tras crear un requisito de artículo para un pedido de servicio, puede ver los requeridos de artículos en el formulario **Proyectos** para el proyecto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="c188a-110">After you create an item requirement for a service order, you can view the item requirement in the **Projects** form for the selected project.</span></span>

## <a name="create-an-item-requirement-for-a-service-order"></a><span data-ttu-id="c188a-111">Crear un requisito de artículo para un pedido de servicio</span><span class="sxs-lookup"><span data-stu-id="c188a-111">Create an item requirement for a service order</span></span>

1.  <span data-ttu-id="c188a-112">Haga clic en **Gestión de servicio** \> **Común** \> **Pedidos de servicio** \> **Pedidos de servicio**.</span><span class="sxs-lookup"><span data-stu-id="c188a-112">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="c188a-113">Seleccione el pedido de servicio para el que desea crear un requisito de artículo.</span><span class="sxs-lookup"><span data-stu-id="c188a-113">Select the service order that you want to create an item requirement for.</span></span>

3.  <span data-ttu-id="c188a-114">A continuación, en el **panel de acciones**, en la ficha **Distribución**, haga clic en **Requisito de artículo**.</span><span class="sxs-lookup"><span data-stu-id="c188a-114">On the **Action Pane**, on the **Dispatch** tab, click **Item requirement**.</span></span>

4.  <span data-ttu-id="c188a-115">En el formulario **Requisitos de artículos**, especifique la información para el artículo requerido.</span><span class="sxs-lookup"><span data-stu-id="c188a-115">In the **Item requirements** form, enter information for the required item.</span></span> <span data-ttu-id="c188a-116">Para obtener más información acerca de campos específicos, vea [Requisitos de artículos (formulario)](https://technet.microsoft.com/library/aa552021\(v=ax.60\)).</span><span class="sxs-lookup"><span data-stu-id="c188a-116">For more information about the specific fields, see [Item requirements (form)](https://technet.microsoft.com/library/aa552021\(v=ax.60\)).</span></span>

## <a name="create-an-item-requirement-for-a-service-agreement"></a><span data-ttu-id="c188a-117">Crear un requisito de artículo para un acuerdo de servicio</span><span class="sxs-lookup"><span data-stu-id="c188a-117">Create an item requirement for a service agreement</span></span>

1.  <span data-ttu-id="c188a-118">Haga clic en **Gestión de servicio** \> **Común** \> **Contratos de servicio** \> **Contratos de servicio**.</span><span class="sxs-lookup"><span data-stu-id="c188a-118">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="c188a-119">Abra el acuerdo de servicio para el que desea crear un requisito de artículo.</span><span class="sxs-lookup"><span data-stu-id="c188a-119">Open the service agreement for which you want to create an item requirement.</span></span>

3.  <span data-ttu-id="c188a-120">En la ficha desplegable **Líneas**, haga clic en **Agregar** para crear una línea nueva.</span><span class="sxs-lookup"><span data-stu-id="c188a-120">On the **Lines** FastTab, click **Add** to create a new line.</span></span>

4.  <span data-ttu-id="c188a-121">En el campo **Tipo de transacción**, seleccione **Artículo**.</span><span class="sxs-lookup"><span data-stu-id="c188a-121">In the **Transaction type** field, select **Item**.</span></span>

5.  <span data-ttu-id="c188a-122">En el campo **Configuración del artículo**, seleccione **Requisito de artículo**.</span><span class="sxs-lookup"><span data-stu-id="c188a-122">In the **Item setup** field, select **Item requirement**.</span></span>

6.  <span data-ttu-id="c188a-123">En el campo **Código de artículo**, seleccione el artículo que se requiere para el acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="c188a-123">In the **Item number** field, select the item that is required for the service agreement.</span></span>

7.  <span data-ttu-id="c188a-124">En la ficha desplegable **Detalles de línea** , en la pestaña **Dimensiones del producto** , en el campo **sitio** , seleccione el sitio del inventario del artículo.</span><span class="sxs-lookup"><span data-stu-id="c188a-124">On the **Line details** FastTab, on the **Product dimensions** tab, in the **Site** field, select the inventory site for the item.</span></span>

8.  <span data-ttu-id="c188a-125">Para crear un pedido de servicio a partir de la línea del acuerdo de servicio, en la ficha desplegable **Líneas**, haga clic en **Crear pedidos de servicio** y especifique la información pertinente en el formulario **Crear pedidos de servicio**.</span><span class="sxs-lookup"><span data-stu-id="c188a-125">To create a service order from the agreement line, on the **Lines** FastTab, click **Create service orders**, and then enter the relevant information in the **Create service orders** form.</span></span> 


## <a name="see-also"></a><span data-ttu-id="c188a-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c188a-126">See also</span></span>

<span data-ttu-id="c188a-127">[Crear pedidos de servicio automáticamente](create-service-orders-automatically.md).</span><span class="sxs-lookup"><span data-stu-id="c188a-127">[Create service orders automatically](create-service-orders-automatically.md).</span></span>

  


