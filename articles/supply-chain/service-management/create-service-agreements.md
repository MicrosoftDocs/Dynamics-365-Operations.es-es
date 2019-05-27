---
title: Crear acuerdos de servicios
description: Este tema describe cómo utilizar funciones en los módulos Gestión de servicio y Gestión de proyectos y contabilidad para crear contratos de servicio.
author: ShylaThompson
manager: AnnBe
ms.date: 02/19/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a094ce9f0d9323b089055e74d41cf1f45323a7d4
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1554561"
---
# <a name="create-service-agreements"></a><span data-ttu-id="d3b98-103">Crear acuerdos de servicios</span><span class="sxs-lookup"><span data-stu-id="d3b98-103">Create service agreements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d3b98-104">Este tema describe cómo utilizar funciones en los módulos Gestión de servicio y Gestión de proyectos y contabilidad para crear contratos de servicio.</span><span class="sxs-lookup"><span data-stu-id="d3b98-104">This topic describes how to use features in the Service management and the Project management and accounting modules to create service agreements.</span></span>

## <a name="create-a-service-agreement-from-service-management"></a><span data-ttu-id="d3b98-105">Crear un acuerdo de servicio a partir de la gestión de servicio</span><span class="sxs-lookup"><span data-stu-id="d3b98-105">Create a service agreement from Service management</span></span>

1. <span data-ttu-id="d3b98-106">Vaya a **Gestión de servicio**.</span><span class="sxs-lookup"><span data-stu-id="d3b98-106">Navigate to **Service management**.</span></span>
2. <span data-ttu-id="d3b98-107">Haga clic en **Contratos de servicio** para crear una nueva línea de contrato de servicio en el encabezado de la página.</span><span class="sxs-lookup"><span data-stu-id="d3b98-107">Click **Service agreements** to create a new service agreement line in the page header.</span></span> 
3. <span data-ttu-id="d3b98-108">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="d3b98-108">Click **New**.</span></span> <span data-ttu-id="d3b98-109">Introduzca una descripción, seleccione una referencia para un proyecto en el campo **Id. de proyecto** y rellene el resto de los campos y líneas del contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="d3b98-109">Enter a description, select a reference to a project in the **Project ID** field, and fill in the rest of the fields and lines for the service agreement.</span></span> <span data-ttu-id="d3b98-110">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d3b98-110">Click **Save**.</span></span>
4. <span data-ttu-id="d3b98-111">En la pestaña **Relaciones**, seleccione **Objetos de servicio** o **Tareas de servicio** para crear relaciones de objetos de servicio o relaciones de tareas de servicio para el contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="d3b98-111">On the **Relations** tab, select **Service objects** or **Service tasks** to create service object relations or service task relations for the service agreement.</span></span> <span data-ttu-id="d3b98-112">Los objetos y las tareas de servicio para las que se crean relaciones pueden vincularse a las líneas del acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="d3b98-112">The service objects and tasks that you have created relations for can be attached on the lines of the service agreement.</span></span>
5. <span data-ttu-id="d3b98-113">En la mitad inferior de la página, puede crear las líneas del contrato de servicio copiando las líneas de una plantilla de servicio u otro acuerdo de servicio, o bien puede crear manualmente las líneas del acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="d3b98-113">In the lower half of the page, create service agreement lines by copying lines from a service template, another service agreement, or manually creating the service-agreement lines.</span></span>

> [!NOTE]
> <span data-ttu-id="d3b98-114">Si copia las líneas del contrato de servicio de otro contrato de servicio, puede indicar si desea copiar también las relaciones de objetos y tareas de servicio.</span><span class="sxs-lookup"><span data-stu-id="d3b98-114">If you copy lines into the service agreement from another service agreement, you can indicate whether you also want to copy service object and service task relations.</span></span> <span data-ttu-id="d3b98-115">Si copia estas relaciones, se añadirán a las relaciones existentes del acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="d3b98-115">If you copy these relations, they are added to any existing relations on the service agreement.</span></span> <span data-ttu-id="d3b98-116">Si copia las líneas del acuerdo de servicio de una plantilla de servicio, se copiarán automáticamente las relaciones de objetos y tareas de servicio como las relaciones de objetos y tareas de servicio de las nuevas líneas del acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="d3b98-116">If you copy service-agreement lines from a service template, the service-object and service-task relations are automatically copied as service-object relations and service-task relations on the new service-agreement lines.</span></span>

## <a name="create-service-agreement-lines-manually"></a><span data-ttu-id="d3b98-117">Crear líneas de contrato de servicio manualmente</span><span class="sxs-lookup"><span data-stu-id="d3b98-117">Create service agreement lines manually</span></span>

1. <span data-ttu-id="d3b98-118">En la página **Contratos de servicio**, agregue una línea de contrato de servicio en la cuadrícula de líneas.</span><span class="sxs-lookup"><span data-stu-id="d3b98-118">From the **Service agreements** page, add a service agreement line in the lines grid.</span></span> 
2. <span data-ttu-id="d3b98-119">Especifique la información adecuada para la línea del contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="d3b98-119">Enter the appropriate information for the service agreement line.</span></span> 
3. <span data-ttu-id="d3b98-120">Presione **CTRL+S** para guardar la línea y cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d3b98-120">Press **CTRL+S** to save the line, and then close the page.</span></span>

## <a name="create-a-service-agreement-from-project"></a><span data-ttu-id="d3b98-121">Crear un acuerdo de servicio a partir de Proyecto</span><span class="sxs-lookup"><span data-stu-id="d3b98-121">Create a service agreement from Project</span></span>

1. <span data-ttu-id="d3b98-122">Haga clic en **Gestión de proyectos y contabilidad**.</span><span class="sxs-lookup"><span data-stu-id="d3b98-122">Click **Project management and accounting**.</span></span>
2. <span data-ttu-id="d3b98-123">Haga clic en **Todos los proyectos**.</span><span class="sxs-lookup"><span data-stu-id="d3b98-123">Click **All projects**.</span></span>
3. <span data-ttu-id="d3b98-124">Seleccione el proyecto de la lista.</span><span class="sxs-lookup"><span data-stu-id="d3b98-124">Select the project from the list.</span></span>
4. <span data-ttu-id="d3b98-125">En el **Panel de acciones**, haga clic en **Gestionar**.</span><span class="sxs-lookup"><span data-stu-id="d3b98-125">On the **Action Pane**, click **Manage**.</span></span> <span data-ttu-id="d3b98-126">En el grupo de acción **Nuevo**, haga clic en **Servicio** y seleccione **Contrato de servicio**.</span><span class="sxs-lookup"><span data-stu-id="d3b98-126">In the **New** Action group, click **Service** and select **Service agreement**.</span></span>
5. <span data-ttu-id="d3b98-127">Siga los pasos en la sección titulada **Crear un contrato de servicio** según lo descrito anteriormente en este tema para introducir la referencia del proyecto.</span><span class="sxs-lookup"><span data-stu-id="d3b98-127">Follow the steps in the section titled **Create a service agreement** as described earlier in this topic to enter the project reference.</span></span>


## <a name="related-topics"></a><span data-ttu-id="d3b98-128">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d3b98-128">Related topics</span></span>

[<span data-ttu-id="d3b98-129">Acuerdos de servicio </span><span class="sxs-lookup"><span data-stu-id="d3b98-129">Service agreements</span></span>](service-agreements.md)


