---
title: Crear calendarios y generar horarios de trabajo
description: Los calendarios describen la capacidad y los horarios de trabajo de los recursos de operaciones. En este tema se explica cómo definir un calendario laboral basado en una plantilla de horario de trabajo.
author: andreabichsel
manager: AnnBe
ms.date: 07/09/2019
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
ms.openlocfilehash: 1645dc42e3c7145feb3081b862c6069d9032913a
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550942"
---
# <a name="create-calendars-and-generate-working-times"></a><span data-ttu-id="93d1d-104">Crear calendarios y generar horarios de trabajo</span><span class="sxs-lookup"><span data-stu-id="93d1d-104">Create calendars and generate working times</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="93d1d-105">Los calendarios describen la capacidad y los horarios de trabajo de los recursos de operaciones.</span><span class="sxs-lookup"><span data-stu-id="93d1d-105">Calendars describe the capacity and working times of operations resources.</span></span> <span data-ttu-id="93d1d-106">En este tema se explica cómo definir un calendario laboral basado en una plantilla de horario de trabajo.</span><span class="sxs-lookup"><span data-stu-id="93d1d-106">This topic explains how to define a work calendar based on a working time template.</span></span> <span data-ttu-id="93d1d-107">Puede revisar este procedimiento con los datos de prueba de la empresa USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="93d1d-107">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="93d1d-108">En la página principal, seleccione **Administración del ciclo de vida de los recursos**.</span><span class="sxs-lookup"><span data-stu-id="93d1d-108">On the home page, select **Resource lifecycle management**.</span></span>
2. <span data-ttu-id="93d1d-109">Seleccione **Calendarios**.</span><span class="sxs-lookup"><span data-stu-id="93d1d-109">Select **Calendars**.</span></span>
3. <span data-ttu-id="93d1d-110">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="93d1d-110">Select **New**.</span></span>
4. <span data-ttu-id="93d1d-111">En el campo **Calendario**, clasifique el calendario.</span><span class="sxs-lookup"><span data-stu-id="93d1d-111">In the **Calendar** field, classify your calendar.</span></span> <span data-ttu-id="93d1d-112">Este es el id. del calendario, que se usa como referencia al asignar calendarios, por ejemplo a un recurso de operaciones o un grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="93d1d-112">This is the ID of the calendar, which is used as a reference when assigning calendars, such as to an operations resource or a resource group.</span></span>  
5. <span data-ttu-id="93d1d-113">En el campo **Nombre**, asigne un nombre al calendario.</span><span class="sxs-lookup"><span data-stu-id="93d1d-113">In the **Name** field, name your calendar.</span></span>
6. <span data-ttu-id="93d1d-114">En el campo **Días laborables estándar en horas**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="93d1d-114">In the **Standard work day in hours** field, enter a number.</span></span>
7. <span data-ttu-id="93d1d-115">Asegúrese de que la fila esté seleccionada y, a continuación, seleccione **Horarios de trabajo** en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="93d1d-115">Make sure the row is selected, then select **Working times** from the Action Pane.</span></span>
8. <span data-ttu-id="93d1d-116">Seleccione **Crear horarios de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="93d1d-116">Select **Compose working times**.</span></span> <span data-ttu-id="93d1d-117">Genere horas laborables para cada día del período en el que desee poder programar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="93d1d-117">Generate working hours for each day in the period where you want to be able to schedule work.</span></span> <span data-ttu-id="93d1d-118">A medida que pasa el tiempo, puede generar horarios de trabajo para períodos adicionales.</span><span class="sxs-lookup"><span data-stu-id="93d1d-118">As time goes by, you can generate working times for additional periods.</span></span>  
9. <span data-ttu-id="93d1d-119">En el campo **Fecha inicial**, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="93d1d-119">In the **From date** field, enter a date.</span></span> <span data-ttu-id="93d1d-120">Este es el primer día en que este calendario debe estar abierto.</span><span class="sxs-lookup"><span data-stu-id="93d1d-120">This is the first day that this calendar must be open.</span></span>  
10. <span data-ttu-id="93d1d-121">En el campo **Fecha final**, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="93d1d-121">In the **To date field**, enter a date.</span></span> <span data-ttu-id="93d1d-122">Este es el último día en que este calendario está abierto.</span><span class="sxs-lookup"><span data-stu-id="93d1d-122">This is the last day that this calendar is open.</span></span>  
11. <span data-ttu-id="93d1d-123">En el campo **Plantilla de horario de trabajo**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="93d1d-123">In the **Working time template** field, enter or select a value.</span></span> <span data-ttu-id="93d1d-124">La plantilla de horario de trabajo define las horas laborables para cada día de la semana.</span><span class="sxs-lookup"><span data-stu-id="93d1d-124">The working time template defines the working hours for each day of the week.</span></span>  
12. <span data-ttu-id="93d1d-125">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="93d1d-125">Select **OK**.</span></span>
13. <span data-ttu-id="93d1d-126">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="93d1d-126">Close the page.</span></span>

