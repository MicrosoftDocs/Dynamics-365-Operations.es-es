---
title: Sincronizar lista de proyectos de Finance and Operations a Field Service
description: En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar proyectos de Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 01/14/2019
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
ms.openlocfilehash: b5aeb4c3925994d7488e8e113e88b9d06ee6b350
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "312517"
---
# <a name="synchronize-project-list-from-finance-and-operations-to-field-service"></a><span data-ttu-id="8833e-103">Sincronizar lista de proyectos de Finance and Operations a Field Service</span><span class="sxs-lookup"><span data-stu-id="8833e-103">Synchronize project list from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="8833e-104">En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar proyectos de Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="8833e-104">This topic discusses the templates and underlying tasks that are used to synchronize projects from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="8833e-105">[![Sincronización de procesos empresariales entre Finance and Operations y Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span><span class="sxs-lookup"><span data-stu-id="8833e-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="8833e-106">Plantillas y tareas</span><span class="sxs-lookup"><span data-stu-id="8833e-106">Templates and tasks</span></span>
<span data-ttu-id="8833e-107">Se utilizan la plantilla y las tareas subyacentes siguientes para ejecutar la sincronización de proyectos de Microsoft Dynamics 365 for Finance and Operations en Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="8833e-107">The following template and underlying tasks are used to run synchronization of projects from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="8833e-108">**Plantilla en la integración de datos**</span><span class="sxs-lookup"><span data-stu-id="8833e-108">**Template in Data integration**</span></span>
- <span data-ttu-id="8833e-109">Proyectos (desde Finance and Operations a Field Service)</span><span class="sxs-lookup"><span data-stu-id="8833e-109">Projects (Finance and Operations to Field Service)</span></span>

<span data-ttu-id="8833e-110">**Tarea en el proyecto de integración de datos**</span><span class="sxs-lookup"><span data-stu-id="8833e-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="8833e-111">Proyectos</span><span class="sxs-lookup"><span data-stu-id="8833e-111">Projects</span></span>

<span data-ttu-id="8833e-112">Las siguientes tareas de sincronización son necesarias antes de que pueda producirse la sincronización de la lista de proyectos:</span><span class="sxs-lookup"><span data-stu-id="8833e-112">The following synchronization tasks are required before synchronization of project list can occur:</span></span>
- <span data-ttu-id="8833e-113">Cuentas (de Sales a Finance and Operations)</span><span class="sxs-lookup"><span data-stu-id="8833e-113">Accounts (Sales to Finance and Operations)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="8833e-114">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="8833e-114">Entity set</span></span>
| <span data-ttu-id="8833e-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="8833e-115">Field Service</span></span>           | <span data-ttu-id="8833e-116">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8833e-116">Finance and Operations</span></span>  |
|-------------------------|-------------------------|
|<span data-ttu-id="8833e-117">msdynce_externalprojects</span><span class="sxs-lookup"><span data-stu-id="8833e-117">msdynce_externalprojects</span></span> | <span data-ttu-id="8833e-118">Proyectos</span><span class="sxs-lookup"><span data-stu-id="8833e-118">Projects</span></span>                |

## <a name="entity-flow"></a><span data-ttu-id="8833e-119">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="8833e-119">Entity flow</span></span>
<span data-ttu-id="8833e-120">Los proyectos se crean en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8833e-120">Projects are created in Finance and Operations.</span></span> <span data-ttu-id="8833e-121">Los proyectos con **Tipo de proyecto** establecido en **tiempo y el material** y **Etapa de proyecto** establecido en **En proceso** se sincronizarán con la entidad **Proyecto externo** en Field Service, incluida la información de número de proyecto, el nombre de proyecto, la fase de proyecto y la cuenta de cliente.</span><span class="sxs-lookup"><span data-stu-id="8833e-121">Projects with **Project type** set to **Time and material** and **Project stage** set to **In process** will synchronize to the **External Project** entity in Field Service, including Project number, Project name, Project stage, and Customer account information.</span></span> <span data-ttu-id="8833e-122">La lista **Proyecto externo** se utiliza para emparejar pedidos de trabajo de Field Service con proyectos de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8833e-122">The **External Project** list is used to pair Field service work orders with Finance and Operations projects.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="8833e-123">Solución CRM de Field Service</span><span class="sxs-lookup"><span data-stu-id="8833e-123">Field Service CRM solution</span></span>
<span data-ttu-id="8833e-124">La entidad **Proyecto externo** recoge todos los proyectos de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8833e-124">The **External Project** entity gets all the projects from Finance and Operations.</span></span> <span data-ttu-id="8833e-125">El campo **Proyecto externo** se ha agregado a la entidad **pedido de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="8833e-125">The **External Project** field has been added to the **Work Order** entity.</span></span> <span data-ttu-id="8833e-126">Este es un campo de búsqueda, por lo que etiquetado su orden de trabajo con un proyecto, el pedido de ventas se conectará con un proyecto en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8833e-126">This is a lookup field, so by tagging your work order with a project, the sales order will be connected to a project within Finance and Operations.</span></span> <span data-ttu-id="8833e-127">Una vez que el **estado del sistema** cambie **Abierto - En progreso (690 970 000)** a un estado más alto, el campo **Proyecto externo** se bloqueará y ya no podrá agregar, quitar o cambiar el valor.</span><span class="sxs-lookup"><span data-stu-id="8833e-127">After the **System Status** changes **Open – In Progress(690,970,000)** to a higher status, the **External Project** field will be locked and you can no longer add, remove, or change the value.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="8833e-128">Condiciones previas y configuración de asignación</span><span class="sxs-lookup"><span data-stu-id="8833e-128">Prerequisites and mapping setup</span></span>
### <a name="finance-and-operations"></a><span data-ttu-id="8833e-129">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8833e-129">Finance and Operations</span></span>
<span data-ttu-id="8833e-130">Habilitar el seguimiento de cambios de proyectos de entidad de datos.</span><span class="sxs-lookup"><span data-stu-id="8833e-130">Enable change tracking for Data entity projects.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="8833e-131">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="8833e-131">Template mapping in Data integration</span></span>


### <a name="projects-finance-and-operations-to-field-service-projects"></a><span data-ttu-id="8833e-132">Proyectos (desde Finance and Operations a Field Service): proyectos</span><span class="sxs-lookup"><span data-stu-id="8833e-132">Projects (Finance and Operations to Field Service): Projects</span></span>

<span data-ttu-id="8833e-133">[![Asignación de la plantilla en la integración de datos](./media/FSProject1.png)](./media/FSProject1.png)</span><span class="sxs-lookup"><span data-stu-id="8833e-133">[![Template mapping in Data integration](./media/FSProject1.png)](./media/FSProject1.png)</span></span>
