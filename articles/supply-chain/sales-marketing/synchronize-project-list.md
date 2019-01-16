---
title: Sincronizar lista de proyectos de Finance and Operations a Field Service
description: En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar proyectos de Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.
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
ms.openlocfilehash: adcb1c1b241ce2b073cd26cf2a8a8d64931c8b0f
ms.contentlocale: es-es
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-project-list-from-finance-and-operations-to-field-service"></a><span data-ttu-id="a9491-103">Sincronizar lista de proyectos de Finance and Operations a Field Service</span><span class="sxs-lookup"><span data-stu-id="a9491-103">Synchronize project list from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="a9491-104">En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar proyectos de Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="a9491-104">This topic discusses the templates and underlying tasks that are used to synchronize projects from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="a9491-105">[![Sincronización de procesos empresariales entre Finance and Operations y Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span><span class="sxs-lookup"><span data-stu-id="a9491-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="a9491-106">Plantillas y tareas</span><span class="sxs-lookup"><span data-stu-id="a9491-106">Templates and tasks</span></span>
<span data-ttu-id="a9491-107">La plantilla y las tareas subyacentes siguientes se usan para ejecutar la sincronización de proyectos desde Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="a9491-107">The following template and underlying tasks are used to run synchronization of projects from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="a9491-108">**Nombre de la plantilla en la integración de datos:**</span><span class="sxs-lookup"><span data-stu-id="a9491-108">**Name of the template in Data integration:**</span></span>
- <span data-ttu-id="a9491-109">Proyectos (desde Finance and Operations a Field Service)</span><span class="sxs-lookup"><span data-stu-id="a9491-109">Projects (Finance and Operations to Field Service)</span></span>

<span data-ttu-id="a9491-110">**Nombres de las tareas en el proyecto de integración de datos:**</span><span class="sxs-lookup"><span data-stu-id="a9491-110">**Names of the tasks in the Data integration project:**</span></span>
- <span data-ttu-id="a9491-111">Proyectos</span><span class="sxs-lookup"><span data-stu-id="a9491-111">Projects</span></span>

<span data-ttu-id="a9491-112">Las siguientes tareas de sincronización son necesarias antes de que pueda producirse la sincronización de la lista de proyectos:</span><span class="sxs-lookup"><span data-stu-id="a9491-112">The following synchronization tasks are required before synchronization of project list can occur:</span></span>
- <span data-ttu-id="a9491-113">Cuentas (de Sales a Finance and Operations)</span><span class="sxs-lookup"><span data-stu-id="a9491-113">Accounts (Sales to Finance and Operations)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="a9491-114">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="a9491-114">Entity set</span></span>
<span data-ttu-id="a9491-115">Field Service   Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a9491-115">Field Service   Finance and Operations</span></span>

| <span data-ttu-id="a9491-116">Field Service</span><span class="sxs-lookup"><span data-stu-id="a9491-116">Field Service</span></span>           | <span data-ttu-id="a9491-117">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a9491-117">Finance and Operations</span></span>  |
|-------------------------|-------------------------|
|<span data-ttu-id="a9491-118">msdynce_externalprojects</span><span class="sxs-lookup"><span data-stu-id="a9491-118">msdynce_externalprojects</span></span> | <span data-ttu-id="a9491-119">Proyectos</span><span class="sxs-lookup"><span data-stu-id="a9491-119">Projects</span></span>                |

## <a name="entity-flow"></a><span data-ttu-id="a9491-120">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="a9491-120">Entity flow</span></span>
<span data-ttu-id="a9491-121">Los proyectos se crean en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a9491-121">Projects are created in Finance and Operations.</span></span> <span data-ttu-id="a9491-122">Los proyectos con el tiempo y el material **Tipo de proyecto** y la **Etapa de proyecto** en proceso se sincronizarán con la entidad **Proyecto externo** en Field Service, incluida la información de número de proyecto, el nombre de proyecto, la fase de proyecto y la cuenta de cliente.</span><span class="sxs-lookup"><span data-stu-id="a9491-122">Projects with **Project type** Time and material and **Project stage** In process will synchronize to the **External Project** entity in Field Service, including Project number, Project name, Project stage and Customer account information.</span></span> <span data-ttu-id="a9491-123">La lista **Proyecto externo** se utiliza para emparejar pedidos de trabajo de Field Service con proyectos de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a9491-123">The list of **External Project** is used to pair Field service Work orders with Finance and Operations projects.</span></span>
<span data-ttu-id="a9491-124">Solución de CRM de Field Service El proyecto externo es una nueva entidad que recoge todos los proyectos de Operations.</span><span class="sxs-lookup"><span data-stu-id="a9491-124">Field Service CRM solution The External Project is a new entity that gets all the Projects from Operations.</span></span>
<span data-ttu-id="a9491-125">El campo Proyecto externo se ha agregado a la entidad del pedido de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a9491-125">The External Project field has been added to the Work Order entity.</span></span> <span data-ttu-id="a9491-126">Este campo etiqueta la búsqueda y la compra de su orden de trabajo con un proyecto. Después el pedido de ventas se conectará con un proyecto en Operations.</span><span class="sxs-lookup"><span data-stu-id="a9491-126">This field is a lookup and buy tagging your Work Order with a project the Sales Order will then be connected to a Project within Operations.</span></span> <span data-ttu-id="a9491-127">Una vez que el estado del sistema cambia Abierto - En progreso (690,970,000) a un estado más alto, el campo Proyecto externo se bloquea y no puede agregar, quitar o cambiar el valor.</span><span class="sxs-lookup"><span data-stu-id="a9491-127">Ones the System Status changes Open – In Progress(690,970,000) to a higher status the External Project field will be locked and you can't add, remove or change the value.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="a9491-128">Condiciones previas y configuración de asignación</span><span class="sxs-lookup"><span data-stu-id="a9491-128">Prerequisites and mapping setup</span></span>
### <a name="in-finance-and-operations"></a><span data-ttu-id="a9491-129">En Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a9491-129">In Finance and Operations</span></span>
<span data-ttu-id="a9491-130">Habilitar el seguimiento de cambios de proyectos de entidad de datos</span><span class="sxs-lookup"><span data-stu-id="a9491-130">Enable change tracking for Data entity Projects</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="a9491-131">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="a9491-131">Template mapping in Data integration</span></span>


### <a name="projects-finance-and-operations-to-field-service-projects"></a><span data-ttu-id="a9491-132">Proyectos (desde Finance and Operations a Field Service): proyectos</span><span class="sxs-lookup"><span data-stu-id="a9491-132">Projects (Finance and Operations to Field Service): Projects</span></span>

<span data-ttu-id="a9491-133">[![Asignación de la plantilla en la integración de datos](./media/FSProject1.png)](./media/FSProject1.png)</span><span class="sxs-lookup"><span data-stu-id="a9491-133">[![Template mapping in Data integration](./media/FSProject1.png)](./media/FSProject1.png)</span></span>

