---
title: Crear calendarios y generar horarios de trabajo
description: Los calendarios describen la capacidad y los horarios de trabajo de los recursos de operaciones. En este artículo se explica cómo definir un calendario laboral basado en una plantilla de horario de trabajo.
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
ms.openlocfilehash: 38c0482c62e86e3e12e4bdd67f6d8f090ddfbfeb
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010445"
---
# <a name="create-calendars-and-generate-working-times"></a><span data-ttu-id="26545-104">Crear calendarios y generar horarios de trabajo</span><span class="sxs-lookup"><span data-stu-id="26545-104">Create calendars and generate working times</span></span>



<span data-ttu-id="26545-105">Los calendarios describen la capacidad y los horarios de trabajo de los recursos de operaciones.</span><span class="sxs-lookup"><span data-stu-id="26545-105">Calendars describe the capacity and working times of operations resources.</span></span> <span data-ttu-id="26545-106">En este artículo se explica cómo definir un calendario laboral basado en una plantilla de horario de trabajo.</span><span class="sxs-lookup"><span data-stu-id="26545-106">This article explains how to define a work calendar based on a working time template.</span></span> <span data-ttu-id="26545-107">Puede revisar este procedimiento con los datos de prueba de la empresa USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="26545-107">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="26545-108">En la página principal, seleccione **Administración del ciclo de vida de los recursos**.</span><span class="sxs-lookup"><span data-stu-id="26545-108">On the home page, select **Resource lifecycle management**.</span></span>
2. <span data-ttu-id="26545-109">Seleccione **Calendarios**.</span><span class="sxs-lookup"><span data-stu-id="26545-109">Select **Calendars**.</span></span>
3. <span data-ttu-id="26545-110">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="26545-110">Select **New**.</span></span>
4. <span data-ttu-id="26545-111">En el campo **Calendario**, clasifique el calendario.</span><span class="sxs-lookup"><span data-stu-id="26545-111">In the **Calendar** field, classify your calendar.</span></span> <span data-ttu-id="26545-112">Este es el id. del calendario, que se usa como referencia al asignar calendarios, por ejemplo a un recurso de operaciones o un grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="26545-112">This is the ID of the calendar, which is used as a reference when assigning calendars, such as to an operations resource or a resource group.</span></span>  
5. <span data-ttu-id="26545-113">En el campo **Nombre**, asigne un nombre al calendario.</span><span class="sxs-lookup"><span data-stu-id="26545-113">In the **Name** field, name your calendar.</span></span>
6. <span data-ttu-id="26545-114">En el campo **Días laborables estándar en horas**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="26545-114">In the **Standard work day in hours** field, enter a number.</span></span>
7. <span data-ttu-id="26545-115">Asegúrese de que la fila esté seleccionada y, a continuación, seleccione **Horarios de trabajo** en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="26545-115">Make sure the row is selected, then select **Working times** from the Action Pane.</span></span>
8. <span data-ttu-id="26545-116">Seleccione **Crear horarios de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="26545-116">Select **Compose working times**.</span></span> <span data-ttu-id="26545-117">Genere horas laborables para cada día del período en el que desee poder programar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="26545-117">Generate working hours for each day in the period where you want to be able to schedule work.</span></span> <span data-ttu-id="26545-118">A medida que pasa el tiempo, puede generar horarios de trabajo para períodos adicionales.</span><span class="sxs-lookup"><span data-stu-id="26545-118">As time goes by, you can generate working times for additional periods.</span></span>  
9. <span data-ttu-id="26545-119">En el campo **Fecha inicial**, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="26545-119">In the **From date** field, enter a date.</span></span> <span data-ttu-id="26545-120">Este es el primer día en que este calendario debe estar abierto.</span><span class="sxs-lookup"><span data-stu-id="26545-120">This is the first day that this calendar must be open.</span></span>  
10. <span data-ttu-id="26545-121">En el campo **Fecha final**, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="26545-121">In the **To date field**, enter a date.</span></span> <span data-ttu-id="26545-122">Este es el último día en que este calendario está abierto.</span><span class="sxs-lookup"><span data-stu-id="26545-122">This is the last day that this calendar is open.</span></span>  
11. <span data-ttu-id="26545-123">En el campo **Plantilla de horario de trabajo**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="26545-123">In the **Working time template** field, enter or select a value.</span></span> <span data-ttu-id="26545-124">La plantilla de horario de trabajo define las horas laborables para cada día de la semana.</span><span class="sxs-lookup"><span data-stu-id="26545-124">The working time template defines the working hours for each day of the week.</span></span>  
12. <span data-ttu-id="26545-125">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="26545-125">Select **OK**.</span></span>
13. <span data-ttu-id="26545-126">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="26545-126">Close the page.</span></span>
