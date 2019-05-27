---
title: Sincronizar pedidos de trabajo con proyectos desde Field Service a Finance and Operations
description: En este tema se describe las plantillas y la tarea subyacente que se usan para sincronizar pedidos de trabajo con un número de proyecto de Microsoft Dynamics 365 for Field Service a pedidos de ventas en Microsoft Dynamics 365 for Finance and Operations.
author: ChristianRytt
manager: AnnBe
ms.date: 03/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 5ca01b085315d916a18c512af28fc7534ce76ee8
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "1536742"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-finance-and-operations"></a><span data-ttu-id="1dc61-103">Sincronizar pedidos de trabajo con proyectos desde Field Service a Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="1dc61-103">Synchronize work orders with project from Field Service to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="1dc61-104">En este tema se describe las plantillas y la tarea subyacente que se usan para sincronizar pedidos de trabajo con un número de proyecto de Microsoft Dynamics 365 for Field Service a pedidos de ventas en Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1dc61-104">This topic discusses the templates and underlying task that are used to synchronize work orders with a project number from Microsoft Dynamics 365 for Field Service to Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="1dc61-105">[![Sincronización de procesos empresariales entre Finance and Operations y Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span><span class="sxs-lookup"><span data-stu-id="1dc61-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span></span>

<span data-ttu-id="1dc61-106">La plantilla **Pedidos de trabajo con proyecto (de Field Service a Fin and Ops)** se basa en la plantilla **Pedidos de trabajo (de Field Service a Fin and Ops)**.</span><span class="sxs-lookup"><span data-stu-id="1dc61-106">The used **Work Orders with Project (Field Service to Fin and Ops)** template is based on the **Work Orders (Field Service to Fin and Ops)** template.</span></span> <span data-ttu-id="1dc61-107">Para obtener más información, consulte [Sincronizar pedidos de trabajo en Field Service con pedidos de ventas en Finance and Operations](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order)</span><span class="sxs-lookup"><span data-stu-id="1dc61-107">For more information, see [Synchronize work orders in Field Service to sales orders in Finance and Operations](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

<span data-ttu-id="1dc61-108">Este tema describe sólo las diferencias entre las dos plantillas:</span><span class="sxs-lookup"><span data-stu-id="1dc61-108">This topic only describes the differences between the two templates:</span></span>
- <span data-ttu-id="1dc61-109">**Pedidos de trabajo con proyecto (de Field Service a Fin and Ops)**</span><span class="sxs-lookup"><span data-stu-id="1dc61-109">**Work Orders with Project (Field Service to Fin and Ops)**</span></span>
- <span data-ttu-id="1dc61-110">**Pedidos de trabajo (de Field Service a Fin and Ops)**</span><span class="sxs-lookup"><span data-stu-id="1dc61-110">**Work Orders (Field Service to Fin and Ops)**</span></span>

<span data-ttu-id="1dc61-111">La principal diferencia es que esta plantilla incluye la asignación del número de proyecto asignado al pedido de trabajo en Field Service, asegurándose de que el pedido de ventas creado en Finance and Operations incluye el número de proyecto y que la facturación puede suceder en el proyecto relacionado.</span><span class="sxs-lookup"><span data-stu-id="1dc61-111">The main difference is that this template includes mapping of the project number asigned to the Work order in Field Service, ensuring that the Sales order created in Finance and Operations include the project number and that invoicing can happen on the related project.</span></span> <span data-ttu-id="1dc61-112">Asimismo esta plantilla usa opciones avanzadas de consulta y filtrado.</span><span class="sxs-lookup"><span data-stu-id="1dc61-112">Besides this the template use Advanced Query and Filtering.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="1dc61-113">Plantillas y tareas</span><span class="sxs-lookup"><span data-stu-id="1dc61-113">Templates and tasks</span></span>

<span data-ttu-id="1dc61-114">**Nombre de la plantilla en la integración de datos:**</span><span class="sxs-lookup"><span data-stu-id="1dc61-114">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="1dc61-115">Pedidos de trabajo con proyecto (de Field Service a Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="1dc61-115">Work Orders with Project (Field Service to Fin and Ops)</span></span>

<span data-ttu-id="1dc61-116">**Nombre de la tarea en el proyecto de integración de datos**:</span><span class="sxs-lookup"><span data-stu-id="1dc61-116">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="1dc61-117">WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="1dc61-117">WorkOrderHeader</span></span>
- <span data-ttu-id="1dc61-118">WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="1dc61-118">WorkOrderHeaderProject</span></span>
- <span data-ttu-id="1dc61-119">WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="1dc61-119">WorkOrderProduct</span></span>
- <span data-ttu-id="1dc61-120">WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="1dc61-120">WorkOrderService</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="1dc61-121">Solución CRM de Field Service</span><span class="sxs-lookup"><span data-stu-id="1dc61-121">Field Service CRM solution</span></span>
<span data-ttu-id="1dc61-122">El campo **Proyecto externo** se ha agregado a la entidad del pedido de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1dc61-122">The **External Project** field has been added to the Work Order entity.</span></span> <span data-ttu-id="1dc61-123">Este campo etiqueta la búsqueda y la compra de su orden de trabajo con un proyecto. Después el pedido de ventas se conectará con un proyecto en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1dc61-123">This field is a lookup and buy tagging your Work Order with a project the Sales Order will then be connected to a Project within Finance and Operations.</span></span> <span data-ttu-id="1dc61-124">Una vez que el **estado del sistema** cambia de Abierto - En progreso (690,970,000) a un estado más alto, el campo **Proyecto externo** se bloquea y no puede agregar, quitar o cambiar el valor.</span><span class="sxs-lookup"><span data-stu-id="1dc61-124">Ones the **System Status** changes from Open – In Progress(690,970,000) to a higher status the **External Project** field will be locked and you can't add, remove or change the value.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="1dc61-125">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="1dc61-125">Template mapping in Data integration</span></span>

<span data-ttu-id="1dc61-126">Las siguientes ilustraciones muestran la asignación de plantilla en la integración de datos.</span><span class="sxs-lookup"><span data-stu-id="1dc61-126">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderheader"></a><span data-ttu-id="1dc61-127">Pedidos de trabajo con proyecto (de Field Service a Fin and Ops): WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="1dc61-127">Work Orders with Project (Field Service to Fin and Ops): WorkOrderHeader</span></span>

<span data-ttu-id="1dc61-128">[![Asignación de la plantilla en la integración de datos](./media/FSWOP1.png)](./media/FSWOP1.png)</span><span class="sxs-lookup"><span data-stu-id="1dc61-128">[![Template mapping in Data integration](./media/FSWOP1.png)](./media/FSWOP1.png)</span></span>

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderheaderproject"></a><span data-ttu-id="1dc61-129">Pedidos de trabajo con proyecto (de Field Service a Fin and Ops): WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="1dc61-129">Work Orders with Project (Field Service to Fin and Ops): WorkOrderHeaderProject</span></span>

<span data-ttu-id="1dc61-130">[![Asignación de la plantilla en la integración de datos](./media/FSWOP2.png)](./media/FSWOP2.png)</span><span class="sxs-lookup"><span data-stu-id="1dc61-130">[![Template mapping in Data integration](./media/FSWOP2.png)](./media/FSWOP2.png)</span></span>

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderproduct"></a><span data-ttu-id="1dc61-131">Pedidos de trabajo con proyecto (de Field Service a Fin and Ops): WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="1dc61-131">Work Orders with Project (Field Service to Fin and Ops): WorkOrderProduct</span></span>

<span data-ttu-id="1dc61-132">[![Asignación de la plantilla en la integración de datos](./media/FSWOP3.png)](./media/FSWOP3.png)</span><span class="sxs-lookup"><span data-stu-id="1dc61-132">[![Template mapping in Data integration](./media/FSWOP3.png)](./media/FSWOP3.png)</span></span>

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderservice"></a><span data-ttu-id="1dc61-133">Pedidos de trabajo con proyecto (de Field Service a Fin and Ops): WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="1dc61-133">Work Orders with Project (Field Service to Fin and Ops): WorkOrderService</span></span>

<span data-ttu-id="1dc61-134">[![Asignación de la plantilla en la integración de datos](./media/FSWOP4.png)](./media/FSWOP4.png)</span><span class="sxs-lookup"><span data-stu-id="1dc61-134">[![Template mapping in Data integration](./media/FSWOP4.png)](./media/FSWOP4.png)</span></span>
