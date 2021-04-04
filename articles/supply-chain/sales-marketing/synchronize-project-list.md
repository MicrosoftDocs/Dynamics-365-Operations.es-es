---
title: Sincronizar lista de proyecto de Supply Chain Management a Field Service
description: En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar proyectos de Dynamics 365 Supply Chain Management a Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 03/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 3d17b226cabd0668bcdb52e9a7fdfc5973fe49b9
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5243066"
---
# <a name="synchronize-project-list-from-supply-chain-management-to-field-service"></a><span data-ttu-id="01f92-103">Sincronizar lista de proyecto de Supply Chain Management a Field Service</span><span class="sxs-lookup"><span data-stu-id="01f92-103">Synchronize project list from Supply Chain Management to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="01f92-104">En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar proyectos de Dynamics 365 Supply Chain Management a Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="01f92-104">This topic discusses the templates and underlying tasks that are used to synchronize projects from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="01f92-105">[![Sincronización de procesos empresariales entre Supply Chain Management y Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span><span class="sxs-lookup"><span data-stu-id="01f92-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="01f92-106">Plantillas y tareas</span><span class="sxs-lookup"><span data-stu-id="01f92-106">Templates and tasks</span></span>
<span data-ttu-id="01f92-107">La plantilla siguiente y las tareas subyacentes se usan para ejecutar sincronización de proyectos de Supply Chain Management a Field Service.</span><span class="sxs-lookup"><span data-stu-id="01f92-107">The following template and underlying tasks are used to run synchronization of projects from Supply Chain Management to Field Service.</span></span>

<span data-ttu-id="01f92-108">**Plantilla en la integración de datos**</span><span class="sxs-lookup"><span data-stu-id="01f92-108">**Template in Data integration**</span></span>
- <span data-ttu-id="01f92-109">Proyectos (Supply Chain Management a Field Service)</span><span class="sxs-lookup"><span data-stu-id="01f92-109">Projects (Supply Chain Management to Field Service)</span></span>

<span data-ttu-id="01f92-110">**Tarea en el proyecto de integración de datos**</span><span class="sxs-lookup"><span data-stu-id="01f92-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="01f92-111">Proyectos</span><span class="sxs-lookup"><span data-stu-id="01f92-111">Projects</span></span>

<span data-ttu-id="01f92-112">Las siguientes tareas de sincronización son necesarias antes de que pueda producirse la sincronización de la lista de proyectos:</span><span class="sxs-lookup"><span data-stu-id="01f92-112">The following synchronization tasks are required before synchronization of project list can occur:</span></span>
- <span data-ttu-id="01f92-113">Cuentas (Sales a Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="01f92-113">Accounts (Sales to Supply Chain Management)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="01f92-114">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="01f92-114">Entity set</span></span>
| <span data-ttu-id="01f92-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="01f92-115">Field Service</span></span>           | <span data-ttu-id="01f92-116">Gestión de la cadena de abastecimiento</span><span class="sxs-lookup"><span data-stu-id="01f92-116">Supply Chain Management</span></span>  |
|-------------------------|-------------------------|
|<span data-ttu-id="01f92-117">msdynce_externalprojects</span><span class="sxs-lookup"><span data-stu-id="01f92-117">msdynce_externalprojects</span></span> | <span data-ttu-id="01f92-118">Proyectos</span><span class="sxs-lookup"><span data-stu-id="01f92-118">Projects</span></span>                |

## <a name="entity-flow"></a><span data-ttu-id="01f92-119">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="01f92-119">Entity flow</span></span>
<span data-ttu-id="01f92-120">Los proyectos se crean en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="01f92-120">Projects are created in Supply Chain Management.</span></span> <span data-ttu-id="01f92-121">Los proyectos con **Tipo de proyecto** establecido en **tiempo y el material** y **Etapa de proyecto** establecido en **En proceso** se sincronizarán con la entidad **Proyecto externo** en Field Service, incluida la información de número de proyecto, el nombre de proyecto, la fase de proyecto y la cuenta de cliente.</span><span class="sxs-lookup"><span data-stu-id="01f92-121">Projects with **Project type** set to **Time and material** and **Project stage** set to **In process** will synchronize to the **External Project** entity in Field Service, including Project number, Project name, Project stage, and Customer account information.</span></span> <span data-ttu-id="01f92-122">La lista **Proyecto externo** se utiliza para emparejar pedidos de trabajo de Field Service con proyectos de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="01f92-122">The **External Project** list is used to pair Field service work orders with Supply Chain Management projects.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="01f92-123">Solución CRM de Field Service</span><span class="sxs-lookup"><span data-stu-id="01f92-123">Field Service CRM solution</span></span>
<span data-ttu-id="01f92-124">La entidad **Proyecto externo** recoge todos los proyectos de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="01f92-124">The **External Project** entity gets all the projects from Supply Chain Management.</span></span> <span data-ttu-id="01f92-125">El campo **Proyecto externo** se ha agregado a la entidad **pedido de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="01f92-125">The **External Project** field has been added to the **Work Order** entity.</span></span> <span data-ttu-id="01f92-126">Este es un campo etiqueta, así que al etiquetar su orden de trabajo con un proyecto, el pedido de ventas se conectará a un proyecto en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="01f92-126">This is a lookup field, so by tagging your work order with a project, the sales order will be connected to a project within Supply Chain Management.</span></span> <span data-ttu-id="01f92-127">Una vez que el **estado del sistema** cambie **Abierto - En progreso (690 970 000)** a un estado más alto, el campo **Proyecto externo** se bloqueará y ya no podrá agregar, quitar o cambiar el valor.</span><span class="sxs-lookup"><span data-stu-id="01f92-127">After the **System Status** changes **Open – In Progress(690,970,000)** to a higher status, the **External Project** field will be locked and you can no longer add, remove, or change the value.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="01f92-128">Condiciones previas y configuración de asignación</span><span class="sxs-lookup"><span data-stu-id="01f92-128">Prerequisites and mapping setup</span></span>
### <a name="supply-chain-management"></a><span data-ttu-id="01f92-129">Gestión de la cadena de abastecimiento</span><span class="sxs-lookup"><span data-stu-id="01f92-129">Supply Chain Management</span></span>
<span data-ttu-id="01f92-130">Habilitar el seguimiento de cambios de proyectos de entidad de datos.</span><span class="sxs-lookup"><span data-stu-id="01f92-130">Enable change tracking for Data entity projects.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="01f92-131">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="01f92-131">Template mapping in Data integration</span></span>


### <a name="projects-supply-chain-management-to-field-service-projects"></a><span data-ttu-id="01f92-132">Proyectos (Supply Chain Management a Field Service): Proyectos</span><span class="sxs-lookup"><span data-stu-id="01f92-132">Projects (Supply Chain Management to Field Service): Projects</span></span>

<span data-ttu-id="01f92-133">[![Asignación de la plantilla en la integración de datos](./media/FSProject1.png)](./media/FSProject1.png)</span><span class="sxs-lookup"><span data-stu-id="01f92-133">[![Template mapping in Data integration](./media/FSProject1.png)](./media/FSProject1.png)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]