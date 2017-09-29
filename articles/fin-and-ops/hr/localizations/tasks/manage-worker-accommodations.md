--- 
title: Administrar ajustes del trabajador
description: "Este procedimiento le muestra los pasos necesarios para configurar tipos de adecuación del entorno de trabajo, como sillas ergonómicas o descansos periódicos."
author: ShielaSogge
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 10d34d0b2eca95034d1f67931ff72a035be9a6b8
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="manage-worker-accommodations"></a><span data-ttu-id="ed164-103">Administrar ajustes del trabajador</span><span class="sxs-lookup"><span data-stu-id="ed164-103">Manage worker accommodations</span></span>

[!include[task guide banner](../../../includes/task-guide-banner.md)]

<span data-ttu-id="ed164-104">Este procedimiento le muestra los pasos necesarios para configurar tipos de adecuación del entorno de trabajo, como sillas ergonómicas o descansos periódicos.</span><span class="sxs-lookup"><span data-stu-id="ed164-104">This procedure walks through the steps for setting up work environment accommodation types, such as ergonomic chairs or periodic breaks.</span></span> <span data-ttu-id="ed164-105">También muestra cómo asignar estos tipos de adecuación a un trabajador y cómo aprobar o denegar el tipo de adecuación.</span><span class="sxs-lookup"><span data-stu-id="ed164-105">It also shows how to assign these accommodation types to a worker, and either approve or deny the accommodation type.</span></span> <span data-ttu-id="ed164-106">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="ed164-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="setup-accommodations"></a><span data-ttu-id="ed164-107">Configuración de adecuaciones</span><span class="sxs-lookup"><span data-stu-id="ed164-107">Setup accommodations</span></span>
1. <span data-ttu-id="ed164-108">Vaya a Recursos humanos > Configuración > Tipos de adecuaciones.</span><span class="sxs-lookup"><span data-stu-id="ed164-108">Go to Human resources > Setup > Accommodation types.</span></span>
2. <span data-ttu-id="ed164-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="ed164-109">Click New.</span></span>
3. <span data-ttu-id="ed164-110">En el campo Tipo de adecuación, especifique un nombre para la adecuación.</span><span class="sxs-lookup"><span data-stu-id="ed164-110">In the Accommodation type field, enter a name for the accommodation.</span></span> <span data-ttu-id="ed164-111">Ejemplo: Teclado.</span><span class="sxs-lookup"><span data-stu-id="ed164-111">Example: Keyboard.</span></span>
4. <span data-ttu-id="ed164-112">En el campo Descripción, especifique una descripción para la adecuación.</span><span class="sxs-lookup"><span data-stu-id="ed164-112">In the Description field, enter a description for the accommodation.</span></span> <span data-ttu-id="ed164-113">Ejemplo: Teclado ergonómico.</span><span class="sxs-lookup"><span data-stu-id="ed164-113">Example: Ergonomic Keyboard.</span></span>
5. <span data-ttu-id="ed164-114">En el campo Nota, especifique información que ayude a aclarar la adecuación.</span><span class="sxs-lookup"><span data-stu-id="ed164-114">In the Note field, enter any information that helps to clarify the accommodation.</span></span>
6. <span data-ttu-id="ed164-115">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="ed164-115">Click Save.</span></span>
7. <span data-ttu-id="ed164-116">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ed164-116">Close the page.</span></span>

## <a name="assign-accommodations"></a><span data-ttu-id="ed164-117">Asignación de adecuaciones</span><span class="sxs-lookup"><span data-stu-id="ed164-117">Assign accommodations</span></span>
1. <span data-ttu-id="ed164-118">Vaya a Recursos humanos > Trabajadores > Empleados.</span><span class="sxs-lookup"><span data-stu-id="ed164-118">Go to Human resources > Workers > Employees.</span></span>
2. <span data-ttu-id="ed164-119">Seleccione un empleado en la lista.</span><span class="sxs-lookup"><span data-stu-id="ed164-119">From the list, select an employee.</span></span>
3. <span data-ttu-id="ed164-120">Haga clic en el nombre del empleado para ver los detalles del empleado que solicita la adecuación.</span><span class="sxs-lookup"><span data-stu-id="ed164-120">Click the employee's name to view details about the employee who is requesting the accommodation.</span></span>
4. <span data-ttu-id="ed164-121">Expanda la ficha desplegable Información personal.</span><span class="sxs-lookup"><span data-stu-id="ed164-121">Expand the Personal information FastTab.</span></span>
5. <span data-ttu-id="ed164-122">Haga clic en Adecuaciones.</span><span class="sxs-lookup"><span data-stu-id="ed164-122">Click Accommodations.</span></span>
6. <span data-ttu-id="ed164-123">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="ed164-123">Click New.</span></span>
7. <span data-ttu-id="ed164-124">En el campo Tipo de adecuación, seleccione la adecuación oportuna.</span><span class="sxs-lookup"><span data-stu-id="ed164-124">In the Accommodation type field, select the appropriate accommodation.</span></span> <span data-ttu-id="ed164-125">Ejemplo: Teclado</span><span class="sxs-lookup"><span data-stu-id="ed164-125">Example: Keyboard</span></span>
8. <span data-ttu-id="ed164-126">En el campo Tarea de trabajo, indique la tarea de trabajo que requiere adecuación.</span><span class="sxs-lookup"><span data-stu-id="ed164-126">In the Job task field, enter the work task that requires the accommodation.</span></span>
9. <span data-ttu-id="ed164-127">Defina el estado apropiado en el campo Estado.</span><span class="sxs-lookup"><span data-stu-id="ed164-127">In the Status field, enter the appropriate status.</span></span> <span data-ttu-id="ed164-128">Ejemplo: Razonable</span><span class="sxs-lookup"><span data-stu-id="ed164-128">Example: Reasonable</span></span>
    * <span data-ttu-id="ed164-129">Están disponibles los siguientes estados.</span><span class="sxs-lookup"><span data-stu-id="ed164-129">The following statuses are available.</span></span> <span data-ttu-id="ed164-130">Solicitado indica que se ha creado la adecuación, pero aún no se ha revisado.</span><span class="sxs-lookup"><span data-stu-id="ed164-130">Requested indicates that the accommodation has been created but not yet reviewed.</span></span> <span data-ttu-id="ed164-131">Razonable indica que la adecuación es razonable y se concederá.</span><span class="sxs-lookup"><span data-stu-id="ed164-131">Reasonable indicates that the accommodation is reasonable and will be granted.</span></span> <span data-ttu-id="ed164-132">Carga excesiva indica que la adecuación supondrá una carga no razonable para el empleador, y por ello se ha denegado.</span><span class="sxs-lookup"><span data-stu-id="ed164-132">Undue hardship indicates that the accommodation will place an unreasonable burden on the employer, and has been denied.</span></span> <span data-ttu-id="ed164-133">En este ejemplo, la solicitud se ha aprobado inmediatamente porque la solicitud de adecuación era mínima.</span><span class="sxs-lookup"><span data-stu-id="ed164-133">In this example, the request was approved immediately because the accommodation request was minimal.</span></span>  
10. <span data-ttu-id="ed164-134">En el campo Aceptado, seleccione la persona que aceptó la solicitud de adecuación.</span><span class="sxs-lookup"><span data-stu-id="ed164-134">In the Accepted field, select the person who accepted the accommodation request.</span></span>
11. <span data-ttu-id="ed164-135">Haga clic en Seleccionar.</span><span class="sxs-lookup"><span data-stu-id="ed164-135">Click Select.</span></span>
12. <span data-ttu-id="ed164-136">En el campo de fecha de aceptación, indique la fecha y la hora en que se aceptó la solicitud de adecuación.</span><span class="sxs-lookup"><span data-stu-id="ed164-136">In the Accepted date field, enter the date and time when the accommodation request was accepted.</span></span>
13. <span data-ttu-id="ed164-137">Expanda la sección Nota.</span><span class="sxs-lookup"><span data-stu-id="ed164-137">Expand the Note section.</span></span>
14. <span data-ttu-id="ed164-138">En el campo Financiero, especifique cualquier información o costes de recursos que ayude a aclarar la repercusión de la adecuación.</span><span class="sxs-lookup"><span data-stu-id="ed164-138">In the Financial field, enter any information or resource costs that helps to clarify the impact of the accommodation.</span></span>
    * <span data-ttu-id="ed164-139">Si se ha denegado la adecuación, el campo Contestación se puede usar para indicar por qué se ha rechazado una solicitud.</span><span class="sxs-lookup"><span data-stu-id="ed164-139">If the accommodation has been denied, the Reply field can be used to indicate why a request was denied.</span></span>  
15. <span data-ttu-id="ed164-140">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="ed164-140">Click Save.</span></span>


