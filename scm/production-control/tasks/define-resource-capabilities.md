--- 
title: Definir capacidades de recursos
description: Las capacidades del recurso describen lo que pueden realizar los recursos de operaciones.
author: sorenva
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 99c230c0e6a580f77d863b6f0be298615966c479
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="define-resource-capabilities"></a><span data-ttu-id="4d6b0-103">Definir capacidades de recursos</span><span class="sxs-lookup"><span data-stu-id="4d6b0-103">Define resource capabilities</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4d6b0-104">Las capacidades del recurso describen lo que pueden realizar los recursos de operaciones.</span><span class="sxs-lookup"><span data-stu-id="4d6b0-104">Resource capabilities describe what operations resources can do.</span></span> <span data-ttu-id="4d6b0-105">Durante la programación, los requisitos de cada trabajo y la operación se asocian con las capacidades de recursos disponibles.</span><span class="sxs-lookup"><span data-stu-id="4d6b0-105">During scheduling, the requirements of each job and operation are matched against the capabilities of the available resources.</span></span> <span data-ttu-id="4d6b0-106">Esta guía de la tarea le ayudará a crear una capacidad del recurso y asignarla a un recurso.</span><span class="sxs-lookup"><span data-stu-id="4d6b0-106">This task guide will help you create a resource capability and assign it to a resource.</span></span> <span data-ttu-id="4d6b0-107">La empresa de datos de prueba utilizada para crear esta tarea es USMF.</span><span class="sxs-lookup"><span data-stu-id="4d6b0-107">The demo data company used to create this task is USMF.</span></span>


## <a name="create-a-resource-capability"></a><span data-ttu-id="4d6b0-108">Crear una capacidad de recurso</span><span class="sxs-lookup"><span data-stu-id="4d6b0-108">Create a resource capability</span></span>
1. <span data-ttu-id="4d6b0-109">Vaya a Capacidades de recursos.</span><span class="sxs-lookup"><span data-stu-id="4d6b0-109">Go to Resource capabilities.</span></span>
2. <span data-ttu-id="4d6b0-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="4d6b0-110">Click New.</span></span>
3. <span data-ttu-id="4d6b0-111">En el campo Capacidad, escriba la identificación de la capacidad del recurso.</span><span class="sxs-lookup"><span data-stu-id="4d6b0-111">In the Capability field, type the ID of the resource capability.</span></span>
    * <span data-ttu-id="4d6b0-112">Para una operación concreta, se usa la identificación de capacidad para especificar que los recursos deben tener esta capacidad para realizar la operación.</span><span class="sxs-lookup"><span data-stu-id="4d6b0-112">For a given operation, you use the capability ID to specify that resources must have this capability to perform the operation.</span></span>  
4. <span data-ttu-id="4d6b0-113">En el campo Descripción, escriba una descripción para la capacidad.</span><span class="sxs-lookup"><span data-stu-id="4d6b0-113">In the Description field, enter a description of the capability.</span></span>

## <a name="assign-capability-to-a-resource"></a><span data-ttu-id="4d6b0-114">Asignar capacidad a un recurso</span><span class="sxs-lookup"><span data-stu-id="4d6b0-114">Assign capability to a resource</span></span>
1. <span data-ttu-id="4d6b0-115">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="4d6b0-115">Click Add.</span></span>
2. <span data-ttu-id="4d6b0-116">En el campo Recurso, escriba la identificación del recurso.</span><span class="sxs-lookup"><span data-stu-id="4d6b0-116">In the Resource field, type the ID of the resource.</span></span>
    * <span data-ttu-id="4d6b0-117">Una capacidad del recurso se puede asignar a uno o varios recursos.</span><span class="sxs-lookup"><span data-stu-id="4d6b0-117">A resource capability can be assigned to one or more resources.</span></span>  
3. <span data-ttu-id="4d6b0-118">En el campo Caducidad, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="4d6b0-118">In the Expiration field, enter a date.</span></span>
    * <span data-ttu-id="4d6b0-119">Puede usar este campo para especificar que un recurso tiene la capacidad solo durante un tiempo limitado.</span><span class="sxs-lookup"><span data-stu-id="4d6b0-119">You can use this field to specify that a resource has the capability for only a limited time.</span></span>  
4. <span data-ttu-id="4d6b0-120">En el campo Prioridad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="4d6b0-120">In the Priority field, enter a number.</span></span>
    * <span data-ttu-id="4d6b0-121">Cuando programe trabajos y operaciones, puede especificar si los recursos se seleccionan por prioridad.</span><span class="sxs-lookup"><span data-stu-id="4d6b0-121">When you schedule jobs and operations, you can specify whether to select resources by priority.</span></span> <span data-ttu-id="4d6b0-122">Si elige esto y más de un recurso puede realizar el trabajo o la operación por la fecha solicitada, se selecciona el recurso que tiene la prioridad más baja con respecto a la capacidad necesaria.</span><span class="sxs-lookup"><span data-stu-id="4d6b0-122">If you choose to do this, and more than one resource can perform the job or operation by the requested date, the resource that has the lowest priority with respect to the required capability is selected.</span></span>  
5. <span data-ttu-id="4d6b0-123">En el campo Nivel, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="4d6b0-123">In the Level field, enter a number.</span></span>
    * <span data-ttu-id="4d6b0-124">Cuando especifica que un trabajo o una operación requiere una capacidad en particular, también puede especificar el nivel mínimo requerido.</span><span class="sxs-lookup"><span data-stu-id="4d6b0-124">When you specify that a job or operation requires a particular capability, you can also specify the minimum level that is required.</span></span> <span data-ttu-id="4d6b0-125">Use el nivel de capacidad para diferenciar los recursos que pueden realizar el mismo trabajo, pero a distintas velocidades, puntos fuertes tamaños, etc.</span><span class="sxs-lookup"><span data-stu-id="4d6b0-125">Use the capability level to differentiate resources that can perform the same job, but at different speeds, strengths, sizes, and so on.</span></span>  


