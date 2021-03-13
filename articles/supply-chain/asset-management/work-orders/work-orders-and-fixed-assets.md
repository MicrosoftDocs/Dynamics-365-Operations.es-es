---
title: Órdenes de trabajo y activos fijos
description: En este tema se explica cómo crear órdenes de trabajo y activos fijos en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4eadbdc452a5b7d28adfa0f102a9a727faad3c07
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "5016712"
---
# <a name="work-orders-and-fixed-assets"></a><span data-ttu-id="36195-103">Órdenes de trabajo y activos fijos</span><span class="sxs-lookup"><span data-stu-id="36195-103">Work orders and fixed assets</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="36195-104">En gestión de activos, los activos se pueden relacionar con los activos fijos, y puede crear órdenes de trabajo para dichos activos.</span><span class="sxs-lookup"><span data-stu-id="36195-104">In Asset Management, assets can be related to fixed assets, and you can create work orders for those assets.</span></span> <span data-ttu-id="36195-105">Si utiliza esta funcionalidad, puede obtener una visión general completa de activos fijos, de proyectos de inversión relacionados, y los costes registrados en los proyectos de inversión en los módulos **Gestión de proyectos y contabilidad** y **Activos fijos** en Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="36195-105">If you use this functionality, you can get a complete overview of fixed assets, related investment projects, and the costs that are registered on the investment projects in the **Project management and accounting** and **Fixed assets** modules in Microsoft Dynamics 365 for Finance and Operations.</span></span>

>[!NOTE]
><span data-ttu-id="36195-106">El campo **Número de activo fijo** del proyecto de trabajo de la orden de trabajo solo se establece si la opción **Inversión** está seleccionada como el tipo de proyecto en el proyecto de trabajo de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="36195-106">The **Fixed asset number** field on the work order job project is set only if **Investment** is selected as the project type on the work order job project.</span></span>

<span data-ttu-id="36195-107">En la ilustración siguiente se muestra la relación entre un proyecto de inversión en el módulo **Gestión de proyectos y contabilidad** y un proyecto de trabajo de orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="36195-107">The illustration below shows the relation between an investment project in the **Project management and accounting** module and a work order job project.</span></span>

![Figura 1](media/24-work-orders.png)

<span data-ttu-id="36195-109">El siguiente procedimiento describe la relación entre los activos, órdenes de trabajo, proyectos de trabajo de la orden de trabajo, y activos fijos.</span><span class="sxs-lookup"><span data-stu-id="36195-109">The following procedure describes the relation between assets, work orders, work order job projects, and fixed assets.</span></span>

1. <span data-ttu-id="36195-110">Cree un activo que relacione con un activo fijo.</span><span class="sxs-lookup"><span data-stu-id="36195-110">You create an asset that you relate to a fixed asset.</span></span>

![Figura 2](media/25-work-orders.png)

2. <span data-ttu-id="36195-112">Al configurar tipos de órdenes de trabajo en la página **Tipos de orden de trabajo** (**Administración de activos** > **Configuración** > **Órdenes de trabajo** > **Tipos de órdenes de trabajo**), cree un tipo de pedido de trabajo para gestionar inversiones.</span><span class="sxs-lookup"><span data-stu-id="36195-112">When you set up work order types on the **Work order types** page (**Asset management** > **Setup** > **Work orders** > **Work order types**), you create a work order type for handling investments.</span></span> <span data-ttu-id="36195-113">Consulte también [Tipos de orden de trabajo](../setup-for-work-orders/work-order-types.md).</span><span class="sxs-lookup"><span data-stu-id="36195-113">See also [Work order types](../setup-for-work-orders/work-order-types.md).</span></span>

![Figura 3](media/26-work-orders.png)

3. <span data-ttu-id="36195-115">Al configurar grupos de proyectos de órdenes de trabajo en la pestaña **Grupo de proyectos** de la página **Configuración de proyecto de orden de trabajo** (**Administración de activos** > **Configuración** > **Órdenes de trabajo** > **Configuración de proyecto**), se crea una relación entre el tipo de orden de trabajo que se usa para las inversiones y el grupo de proyectos que se creó para inversiones en la página **Grupos de proyectos** del módulo **Gestión de proyectos y contabilidad** (**Gestión de proyectos y contabilidad** > **Configuración** > **Registro** > **Grupos de proyectos**).</span><span class="sxs-lookup"><span data-stu-id="36195-115">When you set up work order project groups on the **Project group** tab of the **Work order project setup** page (**Asset management** > **Setup** > **Work orders** > **Project setup**), you create a relation between the work order type that is used for investments and the project group that was created for investments on the **Project groups** page in the **Project management and accounting** module (**Project management and accounting** > **Setup** > **Posting** > **Project groups**).</span></span>

![Figura 4](media/27-work-orders.png)

4. <span data-ttu-id="36195-117">Al crear una orden de trabajo relacionada con un activo fijo, seleccione el tipo de orden de trabajo que se usa para administrar inversiones, como **Inversión**.</span><span class="sxs-lookup"><span data-stu-id="36195-117">When you create a work order that is related to a fixed asset, you select the work order type that is used to handle investments, such as **Investment**.</span></span>

5. <span data-ttu-id="36195-118">Cuando se cree la orden de trabajo, se mostrará el tipo de pedido de trabajo relacionado en la página **Todas las órdenes de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="36195-118">When the work order is created, the related work order type is shown on the **All work orders** page.</span></span>

![Figura 5](media/28-work-orders.png)

6. <span data-ttu-id="36195-120">Cuando se crea la orden de trabajo, se crea el proyecto relacionado con la orden de trabajo en la página **Todos los proyectos** del módulo **Gestión de proyectos y contabilidad** (**Gestión de proyectos y contabilidad** > **Proyectos** > **Todos los proyectos**).</span><span class="sxs-lookup"><span data-stu-id="36195-120">When the work order is created, the project that is related to the work order is created on the **All projects** page in the **Project management and accounting** module (**Project management and accounting** > **Projects** > **All projects**).</span></span> <span data-ttu-id="36195-121">Para ver información relacionada con el proyecto, seleccione el vínculo en el campo **Id. de proyecto** de la pestaña **General** de la ficha desplegable **Detalles de línea** de la vista de detalles de la página **Todas las órdenes de trabajo** del módulo **Administración de activos** (**Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo**).</span><span class="sxs-lookup"><span data-stu-id="36195-121">To view project-related information, select the link in the **Project ID** field on the **General** tab on the **Line details** FastTab in the details view of the **All work orders** page in the **Asset management** module (**Asset management** > **Commom** > **Work orders** > **All work orders**).</span></span>

![Figura 6](media/29-work-orders.png)

7. <span data-ttu-id="36195-123">Para ver una visión general de los proyectos asociados a un activo fijo, seleccione **Activos fijos** > **Activos fijos** > **Activos fijos** y, a continuación, en el campo **Número de activo fijo** , seleccione el vínculo para que el activo fijo abra la vista de detalles.</span><span class="sxs-lookup"><span data-stu-id="36195-123">To see an overview of the projects associated with a fixed asset, select **Fixed assets** > **Fixed assets** > **Fixed assets**, and then, in the **Fixed asset number** field, select the link for the fixed asset to open the details view.</span></span> <span data-ttu-id="36195-124">Expanda el panel **Información relacionada** que se encuentra a la derecha de la página y seleccione la ficha desplegable **Proyectos asociados**.</span><span class="sxs-lookup"><span data-stu-id="36195-124">Expand the **Related information** pane on the right side of the page, and select the **Associated projects** FastTab.</span></span>

