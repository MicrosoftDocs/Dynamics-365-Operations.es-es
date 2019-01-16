---
title: Sincronizar pedidos de trabajo de Finance and Operations a Field Service
description: "En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar pedidos de trabajo con un número de proyecto de Microsoft Dynamics 365 for Field Service a Microsoft Dynamics 365 for Finance and Operations."
author: ChristianRytt
manager: AnnBe
ms.date: 12/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.translationtype: HT
ms.sourcegitcommit: 8c6cb481f1a3fe48d329c5936118d8df88a4175b
ms.openlocfilehash: f5bd6b8c554688d0d1b2bfd93a34a60a95412bf3
ms.contentlocale: es-es
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-work-orders-with-project-from-field-service-to-finance-and-operations"></a><span data-ttu-id="ac67a-103">Sincronizar pedidos de trabajo con proyectos desde Field Service a Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ac67a-103">Synchronize work orders with project from Field Service to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="ac67a-104">En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar pedidos de trabajo con un número de proyecto de Microsoft Dynamics 365 for Field Service a Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ac67a-104">This topic discusses the templates and underlying task that are used to synchronize work orders with a project number from Microsoft Dynamics 365 for Field Service to Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="ac67a-105">[![Sincronización de procesos empresariales entre Finance and Operations y Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span><span class="sxs-lookup"><span data-stu-id="ac67a-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span></span>

<span data-ttu-id="ac67a-106">La plantilla **Productos de Field Service (Finance and Operations a Field Service)** usada se basa en la plantilla **Productos (Finance and Operations to Sales) – Direct** del cliente potencial para cobrar.</span><span class="sxs-lookup"><span data-stu-id="ac67a-106">The used **Field Service Products (Finance and Operations to Field Service)** template is based on the **Products (Finance and Operations to Sales) – Direct** template from Prospect to Cash.</span></span> <span data-ttu-id="ac67a-107">Para obtener más información, consulte [Productos (Finance and Operations a Sales) – Directo](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span><span class="sxs-lookup"><span data-stu-id="ac67a-107">For more information, see [Products (Finance and Operations to Sales) – Direct](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span></span>

<span data-ttu-id="ac67a-108">El tema solo describe las diferencias entre las plantillas **Productos de Field Service (Finance and Operations a Field Service)** y **Productos (Finance and Operations a Sales) – Directo**.</span><span class="sxs-lookup"><span data-stu-id="ac67a-108">This topic only describes the differences between the **Field Service Products (Finance and Operations to Field Service)** and **Field Service Products (Finance and Operations to Field Service)** templates.</span></span>

<span data-ttu-id="ac67a-109">La principal diferencia es que esta plantilla incluye la asignación del número de proyecto asignado al pedido de trabajo en Field Service, asegurándose de que el pedido de ventas creado en Finance and Operations incluye el número de proyecto y que la facturación puede suceder en el proyecto relacionado.</span><span class="sxs-lookup"><span data-stu-id="ac67a-109">The main difference is that this template include mapping of the project number asigned to the Work order in Field Service, ensuring that the Sales order created in Finance and Operations include the project number and that invoicing can happen on the related project.</span></span> <span data-ttu-id="ac67a-110">Asimismo esta plantilla usa opciones avanzadas de consulta y filtrado.</span><span class="sxs-lookup"><span data-stu-id="ac67a-110">Besides this the template use Advanced Query and Filtering.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="ac67a-111">Plantillas y tareas</span><span class="sxs-lookup"><span data-stu-id="ac67a-111">Templates and tasks</span></span>

<span data-ttu-id="ac67a-112">**Nombre de la plantilla en la integración de datos:**</span><span class="sxs-lookup"><span data-stu-id="ac67a-112">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="ac67a-113">Pedidos de trabajo con proyecto (de Field Service a Finance and Operations)</span><span class="sxs-lookup"><span data-stu-id="ac67a-113">Work Orders with Project (Field Service to Finance and Operations)</span></span>

<span data-ttu-id="ac67a-114">**Nombre de la tarea en el proyecto de integración de datos**:</span><span class="sxs-lookup"><span data-stu-id="ac67a-114">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="ac67a-115">WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="ac67a-115">WorkOrderHeader</span></span>
- <span data-ttu-id="ac67a-116">WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="ac67a-116">WorkOrderHeaderProject</span></span>
- <span data-ttu-id="ac67a-117">WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="ac67a-117">WorkOrderProduct</span></span>
- <span data-ttu-id="ac67a-118">WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="ac67a-118">WorkOrderService</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="ac67a-119">Solución CRM de Field Service</span><span class="sxs-lookup"><span data-stu-id="ac67a-119">Field Service CRM solution</span></span>
<span data-ttu-id="ac67a-120">El campo **Proyecto externo** se ha agregado a la entidad del pedido de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ac67a-120">The **External Project** field has been added to the Work Order entity.</span></span> <span data-ttu-id="ac67a-121">Este campo etiqueta la búsqueda y la compra de su orden de trabajo con un proyecto. Después el pedido de ventas se conectará con un proyecto en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ac67a-121">This field is a lookup and buy tagging your Work Order with a project the Sales Order will then be connected to a Project within Finance and Operations.</span></span> <span data-ttu-id="ac67a-122">Una vez que el **estado del sistema** cambia de Abierto - En progreso (690,970,000) a un estado más alto, el campo **Proyecto externo** se bloquea y no puede agregar, quitar o cambiar el valor.</span><span class="sxs-lookup"><span data-stu-id="ac67a-122">Ones the **System Status** changes from Open – In Progress(690,970,000) to a higher status the **External Project** field will be locked and you can't add, remove or change the value.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="ac67a-123">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="ac67a-123">Template mapping in Data integration</span></span>

<span data-ttu-id="ac67a-124">Las siguientes ilustraciones muestran la asignación de plantilla en la integración de datos.</span><span class="sxs-lookup"><span data-stu-id="ac67a-124">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderheader"></a><span data-ttu-id="ac67a-125">Pedidos de trabajo con proyecto (de Field Service a Finance and Operations): WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="ac67a-125">Work Orders with Project (Field Service to Finance and Operations): WorkOrderHeader</span></span>

<span data-ttu-id="ac67a-126">[![Asignación de la plantilla en la integración de datos](./media/FSWOP1.png)](./media/FSWOP1.png)</span><span class="sxs-lookup"><span data-stu-id="ac67a-126">[![Template mapping in Data integration](./media/FSWOP1.png)](./media/FSWOP1.png)</span></span>

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderheaderproject"></a><span data-ttu-id="ac67a-127">Pedidos de trabajo con proyecto (de Field Service a Finance and Operations): WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="ac67a-127">Work Orders with Project (Field Service to Finance and Operations): WorkOrderHeaderProject</span></span>

<span data-ttu-id="ac67a-128">[![Asignación de la plantilla en la integración de datos](./media/FSWOP2.png)](./media/FSWOP2.png)</span><span class="sxs-lookup"><span data-stu-id="ac67a-128">[![Template mapping in Data integration](./media/FSWOP2.png)](./media/FSWOP2.png)</span></span>

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderproduct"></a><span data-ttu-id="ac67a-129">Pedidos de trabajo con proyecto (de Field Service a Finance and Operations): WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="ac67a-129">Work Orders with Project (Field Service to Finance and Operations): WorkOrderProduct</span></span>

<span data-ttu-id="ac67a-130">[![Asignación de la plantilla en la integración de datos](./media/FSWOP3.png)](./media/FSWOP3.png)</span><span class="sxs-lookup"><span data-stu-id="ac67a-130">[![Template mapping in Data integration](./media/FSWOP3.png)](./media/FSWOP3.png)</span></span>

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderservice"></a><span data-ttu-id="ac67a-131">Pedidos de trabajo con proyecto (de Field Service a Finance and Operations): WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="ac67a-131">Work Orders with Project (Field Service to Finance and Operations): WorkOrderService</span></span>

<span data-ttu-id="ac67a-132">[![Asignación de la plantilla en la integración de datos](./media/FSWOP4.png)](./media/FSWOP4.png)</span><span class="sxs-lookup"><span data-stu-id="ac67a-132">[![Template mapping in Data integration](./media/FSWOP4.png)](./media/FSWOP4.png)</span></span>

