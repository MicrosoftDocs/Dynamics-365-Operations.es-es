---
title: Sincronizar pedidos de trabajo con proyecto de Field Service a Supply Chain Management
description: En este tema se describe las plantillas y la tarea subyacente que se usan para sincronizar pedidos de trabajo con un número de proyecto de Dynamics 365 Field Service a pedidos de ventas en Dynamics 365 Supply Chain Management.
author: ChristianRytt
manager: AnnBe
ms.date: 03/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 3678fbca8244ae6dcd050f6a91ff3b35d90e1064
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2019
ms.locfileid: "2251716"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-supply-chain-management"></a><span data-ttu-id="bb65b-103">Sincronizar pedidos de trabajo con proyecto de Field Service a Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="bb65b-103">Synchronize work orders with project from Field Service to Supply Chain Management</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="bb65b-104">En este tema se describe las plantillas y la tarea subyacente que se usan para sincronizar pedidos de trabajo con un número de proyecto de Dynamics 365 Field Service a pedidos de ventas en Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bb65b-104">This topic discusses the templates and underlying task that are used to synchronize work orders with a project number from Dynamics 365 Field Service to Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="bb65b-105">[![Sincronización de procesos empresariales entre Supply Chain Management y Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span><span class="sxs-lookup"><span data-stu-id="bb65b-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span></span>

<span data-ttu-id="bb65b-106">La plantilla **Pedidos de trabajo con proyecto (de Field Service a Supply Chain Management)** se basa en la plantilla **Pedidos de trabajo (de Field Service a Supply Chain Management)**.</span><span class="sxs-lookup"><span data-stu-id="bb65b-106">The used **Work Orders with Project (Field Service to Supply Chain Management)** template is based on the **Work Orders (Field Service to Supply Chain Management)** template.</span></span> <span data-ttu-id="bb65b-107">Para obtener más información, consulte [Sincronizar pedidos de trabajo en Field Service con pedidos de ventas en Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order)</span><span class="sxs-lookup"><span data-stu-id="bb65b-107">For more information, see [Synchronize work orders in Field Service to sales orders in Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

<span data-ttu-id="bb65b-108">Este tema describe sólo las diferencias entre las dos plantillas:</span><span class="sxs-lookup"><span data-stu-id="bb65b-108">This topic only describes the differences between the two templates:</span></span>
- <span data-ttu-id="bb65b-109">**Órdenes de trabajo con proyecto (Field Service a Supply Chain Management)**</span><span class="sxs-lookup"><span data-stu-id="bb65b-109">**Work Orders with Project (Field Service to Supply Chain Management)**</span></span>
- <span data-ttu-id="bb65b-110">**Órdenes de trabajo (Field Service a Supply Chain Management)**</span><span class="sxs-lookup"><span data-stu-id="bb65b-110">**Work Orders (Field Service to Supply Chain Management)**</span></span>

<span data-ttu-id="bb65b-111">La principal diferencia es que esta plantilla incluye la asignación del número de proyecto asignado al pedido de trabajo en Field Service, asegurándose de que el pedido de ventas creado en Supply Chain Management incluye el número de proyecto y que la facturación puede suceder en el proyecto relacionado.</span><span class="sxs-lookup"><span data-stu-id="bb65b-111">The main difference is that this template includes mapping of the project number asigned to the Work order in Field Service, ensuring that the Sales order created in Supply Chain Management include the project number and that invoicing can happen on the related project.</span></span> <span data-ttu-id="bb65b-112">Asimismo esta plantilla usa opciones avanzadas de consulta y filtrado.</span><span class="sxs-lookup"><span data-stu-id="bb65b-112">Besides this the template use Advanced Query and Filtering.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="bb65b-113">Plantillas y tareas</span><span class="sxs-lookup"><span data-stu-id="bb65b-113">Templates and tasks</span></span>

<span data-ttu-id="bb65b-114">**Nombre de la plantilla en la integración de datos:**</span><span class="sxs-lookup"><span data-stu-id="bb65b-114">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="bb65b-115">Órdenes de trabajo con proyecto (Field Service a Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="bb65b-115">Work Orders with Project (Field Service to Supply Chain Management)</span></span>

<span data-ttu-id="bb65b-116">**Nombre de la tarea en el proyecto de integración de datos**:</span><span class="sxs-lookup"><span data-stu-id="bb65b-116">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="bb65b-117">WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="bb65b-117">WorkOrderHeader</span></span>
- <span data-ttu-id="bb65b-118">WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="bb65b-118">WorkOrderHeaderProject</span></span>
- <span data-ttu-id="bb65b-119">WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="bb65b-119">WorkOrderProduct</span></span>
- <span data-ttu-id="bb65b-120">WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="bb65b-120">WorkOrderService</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="bb65b-121">Solución CRM de Field Service</span><span class="sxs-lookup"><span data-stu-id="bb65b-121">Field Service CRM solution</span></span>
<span data-ttu-id="bb65b-122">El campo **Proyecto externo** se ha agregado a la entidad del pedido de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bb65b-122">The **External Project** field has been added to the Work Order entity.</span></span> <span data-ttu-id="bb65b-123">Este campo etiqueta la búsqueda y la compra de su orden de trabajo con un proyecto. Después el pedido de ventas se conectará con un proyecto en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bb65b-123">This field is a lookup and buy tagging your Work Order with a project the Sales Order will then be connected to a Project within Supply Chain Management.</span></span> <span data-ttu-id="bb65b-124">Cuando el **Estado del sistema** cambia de Abierto - En progreso (690,970,000) a un estado más alto, el campo **Proyecto externo** se bloquea y no puede agregar, quitar o cambiar el valor.</span><span class="sxs-lookup"><span data-stu-id="bb65b-124">When the **System Status** changes from Open – In Progress(690,970,000) to a higher status, the **External Project** field will be locked and you can't add, remove, or change the value.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="bb65b-125">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="bb65b-125">Template mapping in Data integration</span></span>

<span data-ttu-id="bb65b-126">Las siguientes ilustraciones muestran la asignación de plantilla en la integración de datos.</span><span class="sxs-lookup"><span data-stu-id="bb65b-126">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderheader"></a><span data-ttu-id="bb65b-127">Órdenes de trabajo con proyecto (Field Service a Supply Chain Management): WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="bb65b-127">Work Orders with Project (Field Service to Supply Chain Management): WorkOrderHeader</span></span>

<span data-ttu-id="bb65b-128">[![Asignación de la plantilla en la integración de datos](./media/FSWOP1.png)](./media/FSWOP1.png)</span><span class="sxs-lookup"><span data-stu-id="bb65b-128">[![Template mapping in Data integration](./media/FSWOP1.png)](./media/FSWOP1.png)</span></span>

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderheaderproject"></a><span data-ttu-id="bb65b-129">Órdenes de trabajo con proyecto (Field Service a Supply Chain Management): WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="bb65b-129">Work Orders with Project (Field Service to Supply Chain Management): WorkOrderHeaderProject</span></span>

<span data-ttu-id="bb65b-130">[![Asignación de la plantilla en la integración de datos](./media/FSWOP2.png)](./media/FSWOP2.png)</span><span class="sxs-lookup"><span data-stu-id="bb65b-130">[![Template mapping in Data integration](./media/FSWOP2.png)](./media/FSWOP2.png)</span></span>

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderproduct"></a><span data-ttu-id="bb65b-131">Órdenes de trabajo con proyecto (Field Service a Supply Chain Management): WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="bb65b-131">Work Orders with Project (Field Service to Supply Chain Management): WorkOrderProduct</span></span>

<span data-ttu-id="bb65b-132">[![Asignación de la plantilla en la integración de datos](./media/FSWOP3.png)](./media/FSWOP3.png)</span><span class="sxs-lookup"><span data-stu-id="bb65b-132">[![Template mapping in Data integration](./media/FSWOP3.png)](./media/FSWOP3.png)</span></span>

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderservice"></a><span data-ttu-id="bb65b-133">Órdenes de trabajo con proyecto (Field Service a Supply Chain Management): WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="bb65b-133">Work Orders with Project (Field Service to Supply Chain Management): WorkOrderService</span></span>

<span data-ttu-id="bb65b-134">[![Asignación de la plantilla en la integración de datos](./media/FSWOP4.png)](./media/FSWOP4.png)</span><span class="sxs-lookup"><span data-stu-id="bb65b-134">[![Template mapping in Data integration](./media/FSWOP4.png)](./media/FSWOP4.png)</span></span>
