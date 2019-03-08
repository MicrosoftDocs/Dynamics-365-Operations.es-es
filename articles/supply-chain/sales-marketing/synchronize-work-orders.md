---
title: Sincronizar pedidos de trabajo con proyectos desde Field Service a Finance and Operations
description: En este tema se describe las plantillas y la tarea subyacente que se usan para sincronizar pedidos de trabajo con un número de proyecto de Microsoft Dynamics 365 for Field Service a pedidos de ventas en Microsoft Dynamics 365 for Finance and Operations.
author: ChristianRytt
manager: AnnBe
ms.date: 12/20/2018
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
ms.openlocfilehash: 6b61411a5a235e2d0aad8bb25ae4a3bfcf1248d1
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "329859"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-finance-and-operations"></a><span data-ttu-id="0de13-103">Sincronizar pedidos de trabajo con proyectos desde Field Service a Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="0de13-103">Synchronize work orders with project from Field Service to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="0de13-104">En este tema se describe las plantillas y la tarea subyacente que se usan para sincronizar pedidos de trabajo con un número de proyecto de Microsoft Dynamics 365 for Field Service a pedidos de ventas en Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0de13-104">This topic discusses the templates and underlying task that are used to synchronize work orders with a project number from Microsoft Dynamics 365 for Field Service to Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="0de13-105">[![Sincronización de procesos empresariales entre Finance and Operations y Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span><span class="sxs-lookup"><span data-stu-id="0de13-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span></span>

<span data-ttu-id="0de13-106">La plantilla **Productos de Field Service (Finance and Operations a Field Service)** usada se basa en la plantilla **Productos (Finance and Operations to Sales) – Direct** del cliente potencial para cobrar.</span><span class="sxs-lookup"><span data-stu-id="0de13-106">The used **Field Service Products (Finance and Operations to Field Service)** template is based on the **Products (Finance and Operations to Sales) – Direct** template from Prospect to Cash.</span></span> <span data-ttu-id="0de13-107">Para obtener más información, consulte [Productos (Finance and Operations a Sales) – Directo](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span><span class="sxs-lookup"><span data-stu-id="0de13-107">For more information, see [Products (Finance and Operations to Sales) – Direct](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span></span>

<span data-ttu-id="0de13-108">El tema solo describe las diferencias entre las plantillas **Productos de Field Service (Finance and Operations a Field Service)** y **Productos (Finance and Operations a Sales) – Directo**.</span><span class="sxs-lookup"><span data-stu-id="0de13-108">This topic only describes the differences between the **Field Service Products (Finance and Operations to Field Service)** and **Field Service Products (Finance and Operations to Field Service)** templates.</span></span>

<span data-ttu-id="0de13-109">La principal diferencia es que esta plantilla incluye la asignación del número de proyecto asignado al pedido de trabajo en Field Service, asegurándose de que el pedido de ventas creado en Finance and Operations incluye el número de proyecto y que la facturación puede suceder en el proyecto relacionado.</span><span class="sxs-lookup"><span data-stu-id="0de13-109">The main difference is that this template includes mapping of the project number asigned to the Work order in Field Service, ensuring that the Sales order created in Finance and Operations include the project number and that invoicing can happen on the related project.</span></span> <span data-ttu-id="0de13-110">Asimismo esta plantilla usa opciones avanzadas de consulta y filtrado.</span><span class="sxs-lookup"><span data-stu-id="0de13-110">Besides this the template use Advanced Query and Filtering.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="0de13-111">Plantillas y tareas</span><span class="sxs-lookup"><span data-stu-id="0de13-111">Templates and tasks</span></span>

<span data-ttu-id="0de13-112">**Nombre de la plantilla en la integración de datos:**</span><span class="sxs-lookup"><span data-stu-id="0de13-112">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="0de13-113">Pedidos de trabajo con proyecto (de Field Service a Finance and Operations)</span><span class="sxs-lookup"><span data-stu-id="0de13-113">Work Orders with Project (Field Service to Finance and Operations)</span></span>

<span data-ttu-id="0de13-114">**Nombre de la tarea en el proyecto de integración de datos**:</span><span class="sxs-lookup"><span data-stu-id="0de13-114">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="0de13-115">WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="0de13-115">WorkOrderHeader</span></span>
- <span data-ttu-id="0de13-116">WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="0de13-116">WorkOrderHeaderProject</span></span>
- <span data-ttu-id="0de13-117">WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="0de13-117">WorkOrderProduct</span></span>
- <span data-ttu-id="0de13-118">WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="0de13-118">WorkOrderService</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="0de13-119">Solución CRM de Field Service</span><span class="sxs-lookup"><span data-stu-id="0de13-119">Field Service CRM solution</span></span>
<span data-ttu-id="0de13-120">El campo **Proyecto externo** se ha agregado a la entidad del pedido de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0de13-120">The **External Project** field has been added to the Work Order entity.</span></span> <span data-ttu-id="0de13-121">Este campo etiqueta la búsqueda y la compra de su orden de trabajo con un proyecto. Después el pedido de ventas se conectará con un proyecto en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0de13-121">This field is a lookup and buy tagging your Work Order with a project the Sales Order will then be connected to a Project within Finance and Operations.</span></span> <span data-ttu-id="0de13-122">Una vez que el **estado del sistema** cambia de Abierto - En progreso (690,970,000) a un estado más alto, el campo **Proyecto externo** se bloquea y no puede agregar, quitar o cambiar el valor.</span><span class="sxs-lookup"><span data-stu-id="0de13-122">Ones the **System Status** changes from Open – In Progress(690,970,000) to a higher status the **External Project** field will be locked and you can't add, remove or change the value.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="0de13-123">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="0de13-123">Template mapping in Data integration</span></span>

<span data-ttu-id="0de13-124">Las siguientes ilustraciones muestran la asignación de plantilla en la integración de datos.</span><span class="sxs-lookup"><span data-stu-id="0de13-124">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderheader"></a><span data-ttu-id="0de13-125">Pedidos de trabajo con proyecto (de Field Service a Finance and Operations): WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="0de13-125">Work Orders with Project (Field Service to Finance and Operations): WorkOrderHeader</span></span>

<span data-ttu-id="0de13-126">[![Asignación de la plantilla en la integración de datos](./media/FSWOP1.png)](./media/FSWOP1.png)</span><span class="sxs-lookup"><span data-stu-id="0de13-126">[![Template mapping in Data integration](./media/FSWOP1.png)](./media/FSWOP1.png)</span></span>

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderheaderproject"></a><span data-ttu-id="0de13-127">Pedidos de trabajo con proyecto (de Field Service a Finance and Operations): WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="0de13-127">Work Orders with Project (Field Service to Finance and Operations): WorkOrderHeaderProject</span></span>

<span data-ttu-id="0de13-128">[![Asignación de la plantilla en la integración de datos](./media/FSWOP2.png)](./media/FSWOP2.png)</span><span class="sxs-lookup"><span data-stu-id="0de13-128">[![Template mapping in Data integration](./media/FSWOP2.png)](./media/FSWOP2.png)</span></span>

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderproduct"></a><span data-ttu-id="0de13-129">Pedidos de trabajo con proyecto (de Field Service a Finance and Operations): WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="0de13-129">Work Orders with Project (Field Service to Finance and Operations): WorkOrderProduct</span></span>

<span data-ttu-id="0de13-130">[![Asignación de la plantilla en la integración de datos](./media/FSWOP3.png)](./media/FSWOP3.png)</span><span class="sxs-lookup"><span data-stu-id="0de13-130">[![Template mapping in Data integration](./media/FSWOP3.png)](./media/FSWOP3.png)</span></span>

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderservice"></a><span data-ttu-id="0de13-131">Pedidos de trabajo con proyecto (de Field Service a Finance and Operations): WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="0de13-131">Work Orders with Project (Field Service to Finance and Operations): WorkOrderService</span></span>

<span data-ttu-id="0de13-132">[![Asignación de la plantilla en la integración de datos](./media/FSWOP4.png)](./media/FSWOP4.png)</span><span class="sxs-lookup"><span data-stu-id="0de13-132">[![Template mapping in Data integration](./media/FSWOP4.png)](./media/FSWOP4.png)</span></span>
