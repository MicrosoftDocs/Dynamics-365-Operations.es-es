---
title: Pedidos de ventas del proyecto
description: Este tema explica cómo crear los pedidos de ventas basados en proyectos según el tiempo y materiales del proyecto.
author: KimANelson
manager: AnnBe
ms.date: 04/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2019-04-05
ms.dyn365.ops.version: AX 10.0.2
ms.openlocfilehash: 1d54c98a08dc7cccb5cafbbe401d0ce25a276c25
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2185506"
---
# <a name="project-sales-orders-for-time-and-material-projects"></a><span data-ttu-id="104b7-103">Proyecto de pedidos de ventas según el tiempo y materiales del proyecto</span><span class="sxs-lookup"><span data-stu-id="104b7-103">Project sales orders for time and material projects</span></span>

[!include[banner](../includes/banner.md)]
[!include[banner](../includes/preview-banner.md)]

<span data-ttu-id="104b7-104">En este tema se describe cómo crear un pedido de ventas para un proyecto.</span><span class="sxs-lookup"><span data-stu-id="104b7-104">This topic describes how to create a sales order for a project.</span></span> <span data-ttu-id="104b7-105">Sólo se pueden crear pedidos de ventas para proyectos del tipo **tiempo y materiales**.</span><span class="sxs-lookup"><span data-stu-id="104b7-105">Sales orders can only be created for projects of type **time and material**.</span></span>

<span data-ttu-id="104b7-106">Si un proyecto de tiempo y materiales tiene varias fuentes de financiación en el contrato del proyecto, debe habilitar el parámetro **Permitir pedidos de ventas para proyectos con varias fuentes de financiación** en la página **Parámetros de administración del proyecto y contabilidad**.</span><span class="sxs-lookup"><span data-stu-id="104b7-106">If a time and material project has multiple funding sources on the project contract, you must enable the **Allow sales orders for projects with multiple funding sources** parameter on the **Project management and accounting parameters** page.</span></span> 

> [!NOTE]
> - <span data-ttu-id="104b7-107">La compatibilidad para los pedidos de ventas de proyecto con varias fuentes de financiación estará disponible a partir de la versión 10.0.2 de la aplicación y posteriores.</span><span class="sxs-lookup"><span data-stu-id="104b7-107">Support for project sales orders with multiple funding sources is available starting with application release 10.0.2 and higher.</span></span>
> - <span data-ttu-id="104b7-108">El parámetro para habilitar el soporte para los pedidos de ventas de proyecto con varias fuentes de financiación se eliminará en la oleada de versiones de abril de 2020, tras la cual la funcionalidad siempre estará habilitada.</span><span class="sxs-lookup"><span data-stu-id="104b7-108">The parameter to enable the support for project sales orders with multiple funding sources will be removed in the April 2020 release wave, after which the functionality will always be enabled.</span></span>

<span data-ttu-id="104b7-109">Puede crear pedidos de ventas basados en proyectos de dos formas:</span><span class="sxs-lookup"><span data-stu-id="104b7-109">You can create project-based sales orders in two ways:</span></span>

- <span data-ttu-id="104b7-110">Vaya al propio proyecto.</span><span class="sxs-lookup"><span data-stu-id="104b7-110">Go to the project itself.</span></span> <span data-ttu-id="104b7-111">En el panel de acciones, seleccione **Gestionar > Tareas del artículo > Pedido de ventas**.</span><span class="sxs-lookup"><span data-stu-id="104b7-111">On the Action Pane, select **Manage > Item tasks > Sales order**.</span></span> <span data-ttu-id="104b7-112">La información de proyecto será la predeterminada para el pedido de ventas del proyecto.</span><span class="sxs-lookup"><span data-stu-id="104b7-112">The project information will default to the sales order from the project.</span></span> <span data-ttu-id="104b7-113">Si el contrato de proyecto tiene más de una fuente de financiación, deberá seleccione la fuente de financiación para establecer el cliente para el pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="104b7-113">If the project contract has more than one funding source, you will need to select the funding source to set the customer for the sales order.</span></span> <span data-ttu-id="104b7-114">Si sólo existe una fuente de financiación para el proyecto, el cliente se establecerá automáticamente.</span><span class="sxs-lookup"><span data-stu-id="104b7-114">If there is only one funding source for the project, the customer will be automatically set.</span></span>
- <span data-ttu-id="104b7-115">Vaya a la página lista **Todos los perdidos de ventas** y cree un nuevo pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="104b7-115">Go to the **All sales order** list page and create a new sales order.</span></span> <span data-ttu-id="104b7-116">Deberá seleccionar el proyecto para el pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="104b7-116">You will need to select the project for the sales order.</span></span> <span data-ttu-id="104b7-117">Tras seleccionar el proyecto, se establecerá al cliente de la fuente de financiación o deberá seleccionar la fuente de financiación si el contrato de proyecto tiene varias fuentes de financiación.</span><span class="sxs-lookup"><span data-stu-id="104b7-117">After the project is selected, the customer will be set from the funding source or you will need to select the funding source if the project contract has multiple funding sources.</span></span>

