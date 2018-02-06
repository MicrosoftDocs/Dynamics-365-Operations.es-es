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
ms.search.scope: Operations, Talent
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a05fec7b79003d5b98470d85644d70bd1dbac285
ms.openlocfilehash: 83c2495eb7602282d7bb97515e655f3dbd33cb4a
ms.contentlocale: es-es
ms.lasthandoff: 02/06/2018

---
# <a name="manage-worker-accommodations"></a><span data-ttu-id="b5d40-103">Administrar ajustes del trabajador</span><span class="sxs-lookup"><span data-stu-id="b5d40-103">Manage worker accommodations</span></span>

[!include[task guide banner](../../../includes/task-guide-banner.md)]

<span data-ttu-id="b5d40-104">Este procedimiento le muestra los pasos necesarios para configurar tipos de adecuación del entorno de trabajo, como sillas ergonómicas o descansos periódicos.</span><span class="sxs-lookup"><span data-stu-id="b5d40-104">This procedure walks through the steps for setting up work environment accommodation types, such as ergonomic chairs or periodic breaks.</span></span> <span data-ttu-id="b5d40-105">También muestra cómo asignar estos tipos de adecuación a un trabajador y cómo aprobar o denegar el tipo de adecuación.</span><span class="sxs-lookup"><span data-stu-id="b5d40-105">It also shows how to assign these accommodation types to a worker, and either approve or deny the accommodation type.</span></span> <span data-ttu-id="b5d40-106">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="b5d40-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="setup-accommodations"></a><span data-ttu-id="b5d40-107">Configuración de adecuaciones</span><span class="sxs-lookup"><span data-stu-id="b5d40-107">Setup accommodations</span></span>
1. <span data-ttu-id="b5d40-108">Vaya a Recursos humanos > Configuración > Tipos de adecuaciones.</span><span class="sxs-lookup"><span data-stu-id="b5d40-108">Go to Human resources > Setup > Accommodation types.</span></span>
2. <span data-ttu-id="b5d40-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="b5d40-109">Click New.</span></span>
3. <span data-ttu-id="b5d40-110">En el campo Tipo de adecuación, especifique un nombre para la adecuación.</span><span class="sxs-lookup"><span data-stu-id="b5d40-110">In the Accommodation type field, enter a name for the accommodation.</span></span> <span data-ttu-id="b5d40-111">Ejemplo: Teclado.</span><span class="sxs-lookup"><span data-stu-id="b5d40-111">Example: Keyboard.</span></span>
4. <span data-ttu-id="b5d40-112">En el campo Descripción, especifique una descripción para la adecuación.</span><span class="sxs-lookup"><span data-stu-id="b5d40-112">In the Description field, enter a description for the accommodation.</span></span> <span data-ttu-id="b5d40-113">Ejemplo: Teclado ergonómico.</span><span class="sxs-lookup"><span data-stu-id="b5d40-113">Example: Ergonomic Keyboard.</span></span>
5. <span data-ttu-id="b5d40-114">En el campo Nota, especifique información que ayude a aclarar la adecuación.</span><span class="sxs-lookup"><span data-stu-id="b5d40-114">In the Note field, enter any information that helps to clarify the accommodation.</span></span>
6. <span data-ttu-id="b5d40-115">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="b5d40-115">Click Save.</span></span>
7. <span data-ttu-id="b5d40-116">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b5d40-116">Close the page.</span></span>

## <a name="assign-accommodations"></a><span data-ttu-id="b5d40-117">Asignación de adecuaciones</span><span class="sxs-lookup"><span data-stu-id="b5d40-117">Assign accommodations</span></span>
1. <span data-ttu-id="b5d40-118">Vaya a Recursos humanos > Trabajadores > Empleados.</span><span class="sxs-lookup"><span data-stu-id="b5d40-118">Go to Human resources > Workers > Employees.</span></span>
2. <span data-ttu-id="b5d40-119">Seleccione un empleado en la lista.</span><span class="sxs-lookup"><span data-stu-id="b5d40-119">From the list, select an employee.</span></span>
3. <span data-ttu-id="b5d40-120">Haga clic en el nombre del empleado para ver los detalles del empleado que solicita la adecuación.</span><span class="sxs-lookup"><span data-stu-id="b5d40-120">Click the employee's name to view details about the employee who is requesting the accommodation.</span></span>
4. <span data-ttu-id="b5d40-121">Expanda la ficha desplegable Información personal.</span><span class="sxs-lookup"><span data-stu-id="b5d40-121">Expand the Personal information FastTab.</span></span>
5. <span data-ttu-id="b5d40-122">Haga clic en Adecuaciones.</span><span class="sxs-lookup"><span data-stu-id="b5d40-122">Click Accommodations.</span></span>
6. <span data-ttu-id="b5d40-123">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="b5d40-123">Click New.</span></span>
7. <span data-ttu-id="b5d40-124">En el campo Tipo de adecuación, seleccione la adecuación oportuna.</span><span class="sxs-lookup"><span data-stu-id="b5d40-124">In the Accommodation type field, select the appropriate accommodation.</span></span> <span data-ttu-id="b5d40-125">Ejemplo: Teclado</span><span class="sxs-lookup"><span data-stu-id="b5d40-125">Example: Keyboard</span></span>
8. <span data-ttu-id="b5d40-126">En el campo Tarea de trabajo, indique la tarea de trabajo que requiere adecuación.</span><span class="sxs-lookup"><span data-stu-id="b5d40-126">In the Job task field, enter the work task that requires the accommodation.</span></span>
9. <span data-ttu-id="b5d40-127">Defina el estado apropiado en el campo Estado.</span><span class="sxs-lookup"><span data-stu-id="b5d40-127">In the Status field, enter the appropriate status.</span></span> <span data-ttu-id="b5d40-128">Ejemplo: Razonable</span><span class="sxs-lookup"><span data-stu-id="b5d40-128">Example: Reasonable</span></span>
    * <span data-ttu-id="b5d40-129">Están disponibles los siguientes estados.</span><span class="sxs-lookup"><span data-stu-id="b5d40-129">The following statuses are available.</span></span> <span data-ttu-id="b5d40-130">Solicitado indica que se ha creado la adecuación, pero aún no se ha revisado.</span><span class="sxs-lookup"><span data-stu-id="b5d40-130">Requested indicates that the accommodation has been created but not yet reviewed.</span></span> <span data-ttu-id="b5d40-131">Razonable indica que la adecuación es razonable y se concederá.</span><span class="sxs-lookup"><span data-stu-id="b5d40-131">Reasonable indicates that the accommodation is reasonable and will be granted.</span></span> <span data-ttu-id="b5d40-132">Carga excesiva indica que la adecuación supondrá una carga no razonable para el empleador, y por ello se ha denegado.</span><span class="sxs-lookup"><span data-stu-id="b5d40-132">Undue hardship indicates that the accommodation will place an unreasonable burden on the employer, and has been denied.</span></span> <span data-ttu-id="b5d40-133">En este ejemplo, la solicitud se ha aprobado inmediatamente porque la solicitud de adecuación era mínima.</span><span class="sxs-lookup"><span data-stu-id="b5d40-133">In this example, the request was approved immediately because the accommodation request was minimal.</span></span>  
10. <span data-ttu-id="b5d40-134">En el campo Aceptado, seleccione la persona que aceptó la solicitud de adecuación.</span><span class="sxs-lookup"><span data-stu-id="b5d40-134">In the Accepted field, select the person who accepted the accommodation request.</span></span>
11. <span data-ttu-id="b5d40-135">Haga clic en Seleccionar.</span><span class="sxs-lookup"><span data-stu-id="b5d40-135">Click Select.</span></span>
12. <span data-ttu-id="b5d40-136">En el campo de fecha de aceptación, indique la fecha y la hora en que se aceptó la solicitud de adecuación.</span><span class="sxs-lookup"><span data-stu-id="b5d40-136">In the Accepted date field, enter the date and time when the accommodation request was accepted.</span></span>
13. <span data-ttu-id="b5d40-137">Expanda la sección Nota.</span><span class="sxs-lookup"><span data-stu-id="b5d40-137">Expand the Note section.</span></span>
14. <span data-ttu-id="b5d40-138">En el campo Financiero, especifique cualquier información o costes de recursos que ayude a aclarar la repercusión de la adecuación.</span><span class="sxs-lookup"><span data-stu-id="b5d40-138">In the Financial field, enter any information or resource costs that helps to clarify the impact of the accommodation.</span></span>
    * <span data-ttu-id="b5d40-139">Si se ha denegado la adecuación, el campo Contestación se puede usar para indicar por qué se ha rechazado una solicitud.</span><span class="sxs-lookup"><span data-stu-id="b5d40-139">If the accommodation has been denied, the Reply field can be used to indicate why a request was denied.</span></span>  
15. <span data-ttu-id="b5d40-140">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="b5d40-140">Click Save.</span></span>


