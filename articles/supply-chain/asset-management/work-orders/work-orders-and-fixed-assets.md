---
title: Órdenes de trabajo y activos fijos
description: En este tema se explica cómo crear órdenes de trabajo y activos fijos en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f03b7fa073c4e5338b7b5681ba7b8c9fe00a657b
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875876"
---
# <a name="work-orders-and-fixed-assets"></a><span data-ttu-id="09e09-103">Órdenes de trabajo y activos fijos</span><span class="sxs-lookup"><span data-stu-id="09e09-103">Work orders and fixed assets</span></span>


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="09e09-104">En gestión de activos, los activos se pueden relacionar con los activos fijos, y puede crear órdenes de trabajo para dichos activos.</span><span class="sxs-lookup"><span data-stu-id="09e09-104">In Asset Management, assets can be related to fixed assets, and you can create work orders for those assets.</span></span> <span data-ttu-id="09e09-105">Si utiliza esta funcionalidad, puede obtener una visión general completa de activos fijos, de proyectos de inversión relacionados, y los costes registrados en los proyectos de inversión en el módulo **Gestión de proyectos y contabilidad** y el módulo **Activos fijos** en Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="09e09-105">If you use this functionality, you can get a complete overview of fixed assets, related investment projects, and the costs registered on the investment projects in the **Project management and accounting** module and the **Fixed assets** module in Dynamics 365 for Finance and Operations.</span></span>

>[!NOTE]
><span data-ttu-id="09e09-106">El campo **Número de activo fijo** solo se completa en el proyecto de trabajo de la orden de trabajo si se selecciona el tipo “inversión” como tipo de proyecto en el proyecto de trabajo de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="09e09-106">The **Fixed asset number** field is only filled out on the work order job project if type "Investment" is selected as the project type on the work order job project.</span></span>

![Figura 1](media/24-work-orders.png)

<span data-ttu-id="09e09-108">El siguiente procedimiento describe la relación entre los activos, órdenes de trabajo, proyectos de trabajo de la orden de trabajo, y activos fijos.</span><span class="sxs-lookup"><span data-stu-id="09e09-108">The following procedure describes the relation between assets, work orders, work order job projects, and fixed assets.</span></span>

1. <span data-ttu-id="09e09-109">Se crea un activo que se relaciona con un activo fijo, tal y como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="09e09-109">You create an asset that you relate to a fixed asset, as shown in the figure below.</span></span>

![Figura 2](media/25-work-orders.png)

2. <span data-ttu-id="09e09-111">Al establecer tipos de pedido de trabajo (**Administración de activos** > **Configuración** > **Órdenes de trabajo** > **Tipos de órdenes de trabajo**), cree un tipo de pedido de trabajo para gestionar inversiones.</span><span class="sxs-lookup"><span data-stu-id="09e09-111">When you set up work order types (**Asset management** > **Setup** > **Work orders** > **Work order types**), you create a work order type for handling investments.</span></span> <span data-ttu-id="09e09-112">Consulte también [Tipos de orden de trabajo](../setup-for-work-orders/work-order-types.md).</span><span class="sxs-lookup"><span data-stu-id="09e09-112">See also [Work order types](../setup-for-work-orders/work-order-types.md).</span></span>

![Figura 3](media/26-work-orders.png)

3. <span data-ttu-id="09e09-114">Al configurar grupos de proyectos de órdenes de trabajo (vínculo **Administración de activos** > **Configuración** > **Órdenes de trabajo** > **Configuración de proyecto** > **Grupo de proyectos**), se crea una relación entre el tipo de pedido del trabajo usado para las inversiones y el grupo de proyectos creado para inversiones en el módulo **Gestión de proyectos y contabilidad** (**Gestión de proyectos y contabilidad** > **Configuración** > **Registro** > **Grupos de proyectos**).</span><span class="sxs-lookup"><span data-stu-id="09e09-114">When you set up work order project groups (**Asset management** > **Setup** > **Work orders** > **Project setup** > **Project group** link), you create a relation between the work order type used for investments and the project group created for investments in the **Project management and accounting** module (**Project management and accounting** > **Setup** > **Posting** > **Project groups**).</span></span>

![Figura 4](media/27-work-orders.png)

4. <span data-ttu-id="09e09-116">Al crear un pedido de trabajo relacionado con un objeto del activo fijo, seleccione el tipo de pedido del trabajo empleado para administrar inversiones, por ejemplo, “inversión”.</span><span class="sxs-lookup"><span data-stu-id="09e09-116">When you create a work order that relates to a fixed asset object, you select the work order type used for handling investments, for example, "Investment".</span></span>

5. <span data-ttu-id="09e09-117">Cuando se crea la orden de trabajo, se mostrará el tipo de pedido de trabajo relacionado en **Todas las órdenes de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="09e09-117">When the work order is created, the related work order type is shown in **All work orders**.</span></span>

![Figura 5](media/28-work-orders.png)

6. <span data-ttu-id="09e09-119">Cuando se crea la orden de trabajo, el proyecto relacionado con al pedido de trabajo se crea en **Gestión de proyectos y contabilidad** > **Todos los proyectos**.</span><span class="sxs-lookup"><span data-stu-id="09e09-119">When the work order is created, the project related to the work order is created in **Project management and accounting** > **All projects**.</span></span> <span data-ttu-id="09e09-120">Puede ver información relacionada con el proyecto haciendo clic en el vínculo **Id. de proyecto** en la orden de trabajo (en **Administración de activos**, abra la orden de trabajo en la vista Detalles > ficha desplegable **Detalles de línea** > pestaña **General** > campo **Identificador del proyecto**).</span><span class="sxs-lookup"><span data-stu-id="09e09-120">You can see project-related information by clicking the **Project ID** link on the work order (in **Asset management**, open the work order in Details view > **Line details** FastTab > **General** tab > **Project ID** field).</span></span>

![Figura 6](media/29-work-orders.png)

7. <span data-ttu-id="09e09-122">En **Activos fijos**, podrá obtener una visión general de los proyectos asociados a un activo fijo (**Activos fijos** > **Activos fijos** > **Activos fijos** > hacer clic en el activo fijo en el campo **Número de activo fijo** > la vista de los contenidos en el panel **Información relacionada** > la sección **Proyectos asociados**).</span><span class="sxs-lookup"><span data-stu-id="09e09-122">In **Fixed assets**, you are able to see an overview of the projects associated with a fixed asset (**Fixed assets** > **Fixed assets** > **Fixed assets** > click on the fixed asset in the **Fixed asset number** field > view the contents in the **Related information** pane > **Associated projects** section).</span></span>

