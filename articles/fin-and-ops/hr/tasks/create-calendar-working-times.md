---
title: Crear calendario y generar horarios de trabajo
description: Los calendarios describen la capacidad y los horarios de trabajo de los recursos de operaciones.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OpResLifeCycleManagementWorkspace, WorkCalendarTable, WorkCalendarDate
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ba4bd51d2102b3036307f34ab46f94f83df4f461
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "1510137"
---
# <a name="create-calendar-and-generate-working-times"></a><span data-ttu-id="f11da-103">Crear calendario y generar horarios de trabajo</span><span class="sxs-lookup"><span data-stu-id="f11da-103">Create calendar and generate working times</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f11da-104">Los calendarios describen la capacidad y los horarios de trabajo de los recursos de operaciones.</span><span class="sxs-lookup"><span data-stu-id="f11da-104">Calendars describe the capacity and working times of operations resources.</span></span> <span data-ttu-id="f11da-105">Este procedimiento le ayudará a definir un calendario laboral basado en una plantilla de horario de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f11da-105">This procedure will help you define a work calendar based on a working time template.</span></span> <span data-ttu-id="f11da-106">Puede revisar este procedimiento con los datos de prueba de la empresa USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="f11da-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="f11da-107">Vaya a Todos los espacios de trabajo > Administración del ciclo de vida de los recursos.</span><span class="sxs-lookup"><span data-stu-id="f11da-107">Go to All workspaces > Resource lifecycle management.</span></span>
2. <span data-ttu-id="f11da-108">Haga clic en Calendarios.</span><span class="sxs-lookup"><span data-stu-id="f11da-108">Click Calendars.</span></span>
3. <span data-ttu-id="f11da-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="f11da-109">Click New.</span></span>
4. <span data-ttu-id="f11da-110">En el campo Calendario, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f11da-110">In the Calendar field, type a value.</span></span>
    * <span data-ttu-id="f11da-111">Este es el id. del calendario, que se usa como referencia al asignar calendarios, por ejemplo a un recurso de operaciones o un grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="f11da-111">This is the ID of the calendar, which is used as a reference when assigning calendars, such as to an operations resource or a resource group.</span></span>  
5. <span data-ttu-id="f11da-112">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f11da-112">In the Name field, type a value.</span></span>
6. <span data-ttu-id="f11da-113">En el campo Días laborables estándar en horas, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="f11da-113">In the Standard work day in hours field, enter a number.</span></span>
7. <span data-ttu-id="f11da-114">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f11da-114">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="f11da-115">Haga clic en Horarios de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f11da-115">Click Working times.</span></span>
9. <span data-ttu-id="f11da-116">Haga clic en Crear horarios de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f11da-116">Click Compose working times.</span></span>
    * <span data-ttu-id="f11da-117">Genere horas laborables para cada día del período en el que desee poder programar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="f11da-117">Generate working hours for each day in the period where you want to be able to schedule work.</span></span> <span data-ttu-id="f11da-118">A medida que pasa el tiempo, puede generar horarios de trabajo para períodos adicionales.</span><span class="sxs-lookup"><span data-stu-id="f11da-118">As time goes by, you can generate working times for additional periods.</span></span>  
10. <span data-ttu-id="f11da-119">En el campo Fecha inicial, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="f11da-119">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="f11da-120">Este es el primer día en que este calendario debe estar abierto.</span><span class="sxs-lookup"><span data-stu-id="f11da-120">This is the first day that this calendar must be open.</span></span>  
11. <span data-ttu-id="f11da-121">Especifique una fecha en el campo Fecha final.</span><span class="sxs-lookup"><span data-stu-id="f11da-121">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="f11da-122">Este es el último día en que este calendario está abierto.</span><span class="sxs-lookup"><span data-stu-id="f11da-122">This is the last day that this calendar is open.</span></span>  
12. <span data-ttu-id="f11da-123">En el campo Plantilla de horario de trabajo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f11da-123">In the Working time template field, enter or select a value.</span></span>
    * <span data-ttu-id="f11da-124">La plantilla de horario de trabajo define las horas laborables para cada día de la semana.</span><span class="sxs-lookup"><span data-stu-id="f11da-124">The working time template defines the working hours for each day of the week.</span></span>  
13. <span data-ttu-id="f11da-125">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="f11da-125">Click OK.</span></span>
14. <span data-ttu-id="f11da-126">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f11da-126">Close the page.</span></span>

