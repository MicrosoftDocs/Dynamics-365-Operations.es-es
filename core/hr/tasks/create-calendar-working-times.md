--- 
title: Crear un calendario y generar horarios de trabajo
description: Los calendarios describen la capacidad y los horarios de trabajo de los recursos de operaciones.
author: kherr75
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: d65fe0363e418f9c2e78bd78e802a4b0ea98599c
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-calendar-and-generate-working-times"></a><span data-ttu-id="077b0-103">Crear un calendario y generar horarios de trabajo</span><span class="sxs-lookup"><span data-stu-id="077b0-103">Create a calendar and generate working times</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="077b0-104">Los calendarios describen la capacidad y los horarios de trabajo de los recursos de operaciones.</span><span class="sxs-lookup"><span data-stu-id="077b0-104">Calendars describe the capacity and working times of operations resources.</span></span> <span data-ttu-id="077b0-105">Este procedimiento le ayudará a definir un calendario laboral basado en una plantilla de horario de trabajo.</span><span class="sxs-lookup"><span data-stu-id="077b0-105">This procedure will help you define a work calendar based on a working time template.</span></span> <span data-ttu-id="077b0-106">Puede revisar este procedimiento con los datos de prueba de la empresa USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="077b0-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="077b0-107">Vaya a Todos los espacios de trabajo > Administración del ciclo de vida de los recursos.</span><span class="sxs-lookup"><span data-stu-id="077b0-107">Go to All workspaces > Resource lifecycle management.</span></span>
2. <span data-ttu-id="077b0-108">Haga clic en Calendarios.</span><span class="sxs-lookup"><span data-stu-id="077b0-108">Click Calendars.</span></span>
3. <span data-ttu-id="077b0-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="077b0-109">Click New.</span></span>
4. <span data-ttu-id="077b0-110">En el campo Calendario, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="077b0-110">In the Calendar field, type a value.</span></span>
    * <span data-ttu-id="077b0-111">Este es el id. del calendario, que se usa como referencia al asignar calendarios, por ejemplo a un recurso de operaciones o un grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="077b0-111">This is the ID of the calendar, which is used as a reference when assigning calendars, such as to an operations resource or a resource group.</span></span>  
5. <span data-ttu-id="077b0-112">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="077b0-112">In the Name field, type a value.</span></span>
6. <span data-ttu-id="077b0-113">En el campo Días laborables estándar en horas, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="077b0-113">In the Standard work day in hours field, enter a number.</span></span>
7. <span data-ttu-id="077b0-114">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="077b0-114">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="077b0-115">Haga clic en Horarios de trabajo.</span><span class="sxs-lookup"><span data-stu-id="077b0-115">Click Working times.</span></span>
9. <span data-ttu-id="077b0-116">Haga clic en Crear horarios de trabajo.</span><span class="sxs-lookup"><span data-stu-id="077b0-116">Click Compose working times.</span></span>
    * <span data-ttu-id="077b0-117">Genere horas laborables para cada día del período en el que desee poder programar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="077b0-117">Generate working hours for each day in the period where you want to be able to schedule work.</span></span> <span data-ttu-id="077b0-118">A medida que pasa el tiempo, puede generar horarios de trabajo para períodos adicionales.</span><span class="sxs-lookup"><span data-stu-id="077b0-118">As time goes by, you can generate working times for additional periods.</span></span>  
10. <span data-ttu-id="077b0-119">En el campo Fecha inicial, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="077b0-119">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="077b0-120">Este es el primer día en que este calendario debe estar abierto.</span><span class="sxs-lookup"><span data-stu-id="077b0-120">This is the first day that this calendar must be open.</span></span>  
11. <span data-ttu-id="077b0-121">Especifique una fecha en el campo Fecha final.</span><span class="sxs-lookup"><span data-stu-id="077b0-121">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="077b0-122">Este es el último día en que este calendario está abierto.</span><span class="sxs-lookup"><span data-stu-id="077b0-122">This is the last day that this calendar is open.</span></span>  
12. <span data-ttu-id="077b0-123">En el campo Plantilla de horario de trabajo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="077b0-123">In the Working time template field, enter or select a value.</span></span>
    * <span data-ttu-id="077b0-124">La plantilla de horario de trabajo define las horas laborables para cada día de la semana.</span><span class="sxs-lookup"><span data-stu-id="077b0-124">The working time template defines the working hours for each day of the week.</span></span>  
13. <span data-ttu-id="077b0-125">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="077b0-125">Click OK.</span></span>
14. <span data-ttu-id="077b0-126">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="077b0-126">Close the page.</span></span>


