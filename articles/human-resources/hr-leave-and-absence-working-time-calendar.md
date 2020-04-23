---
title: Crear un calendario de horas de trabajo
description: Defina un calendario de horas de trabajo, días festivos y horas no laborables en Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: dc209b62836011b18362f78b63cdd3fcda884dc3
ms.sourcegitcommit: 79f8aa2c0b166a423db9b8503da53e96e3fc43dc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2020
ms.locfileid: "3198036"
---
# <a name="create-a-working-time-calendar"></a><span data-ttu-id="ff1a4-103">Crear un calendario de horas de trabajo</span><span class="sxs-lookup"><span data-stu-id="ff1a4-103">Create a working time calendar</span></span>

<span data-ttu-id="ff1a4-104">Un calendario de horas de trabajo en Dynamics 365 Human Resources muestra los días y las horas en que trabajan los empleados en su organización.</span><span class="sxs-lookup"><span data-stu-id="ff1a4-104">A working time calendar in Dynamics 365 Human Resources shows the days and hours that employees work in your organization.</span></span> <span data-ttu-id="ff1a4-105">Cuando un empleado envía una solicitud de tiempo libre, no tiene que preocuparse de días festivos y cierres.</span><span class="sxs-lookup"><span data-stu-id="ff1a4-105">When an employee submits a time-off request, they don't have to worry about holidays and closures.</span></span>

<span data-ttu-id="ff1a4-106">Para agilizar las solicitudes de tiempo libre, configure estos elementos para su organización:</span><span class="sxs-lookup"><span data-stu-id="ff1a4-106">To streamline time-off requests, configure these items for your organization:</span></span>

- <span data-ttu-id="ff1a4-107">Calendario de horario de trabajo</span><span class="sxs-lookup"><span data-stu-id="ff1a4-107">Working time calendar</span></span>
- <span data-ttu-id="ff1a4-108">Días festivos y cierres</span><span class="sxs-lookup"><span data-stu-id="ff1a4-108">Holidays and closures</span></span>
- <span data-ttu-id="ff1a4-109">Tiempo no laborable</span><span class="sxs-lookup"><span data-stu-id="ff1a4-109">Non-work time</span></span>

<span data-ttu-id="ff1a4-110">Puede agregar los dos últimos elementos mientras configura un calendario de horas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ff1a4-110">You can add the last two items while you're setting up a working time calendar.</span></span> <span data-ttu-id="ff1a4-111">También puede configurarlos o actualizarlos por separado.</span><span class="sxs-lookup"><span data-stu-id="ff1a4-111">You can also configure or update them separately.</span></span>

## <a name="set-up-a-working-time-calendar"></a><span data-ttu-id="ff1a4-112">Configurar un calendario de horas de trabajo</span><span class="sxs-lookup"><span data-stu-id="ff1a4-112">Set up a working time calendar</span></span>

<span data-ttu-id="ff1a4-113">Configure al menos un calendario de tiempo laborable que muestre sus días y horas de operación.</span><span class="sxs-lookup"><span data-stu-id="ff1a4-113">Set up at least one working time calendar that shows your days and hours of operation.</span></span> <span data-ttu-id="ff1a4-114">Si tiene ubicaciones en varios países y regiones, es posible que desee configurar un calendario de tiempo de trabajo para cada área.</span><span class="sxs-lookup"><span data-stu-id="ff1a4-114">If you have locations in multiple countries and regions, you might want to set up a working time calendar for each area.</span></span>

1. <span data-ttu-id="ff1a4-115">En la página **Administración de la organización**, seleccione **Calendarios**.</span><span class="sxs-lookup"><span data-stu-id="ff1a4-115">On the **Organization administration** page, select **Calendars**.</span></span>

2. <span data-ttu-id="ff1a4-116">Seleccione **Nuevo** y especifique un nombre y una descripción para su calendario.</span><span class="sxs-lookup"><span data-stu-id="ff1a4-116">Select **New** and enter a name and description for your calendar.</span></span>

3. <span data-ttu-id="ff1a4-117">En **Opciones de generación**, seleccione los días laborales para su organización e introduzca las horas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ff1a4-117">Under **Generation options**, select the work days for your organization and enter work times.</span></span> 
   - <span data-ttu-id="ff1a4-118">Para agregar un día festivo o un cierre, seleccione el botón **Agregar** junto a **Días festivos y cierres**.</span><span class="sxs-lookup"><span data-stu-id="ff1a4-118">To add a holiday or closure, select the **Add** button next to **Holidays and closures**.</span></span>
   - <span data-ttu-id="ff1a4-119">Para agregar tiempo no laborable, como almuerzos o descansos, seleccione **Agregar** debajo de **TIEMPO NO LABORABLE** e introduzca el nombre y el intervalo de tiempo.</span><span class="sxs-lookup"><span data-stu-id="ff1a4-119">To add non-work time, like lunches or breaks, select **Add** under **NON-WORK TIME** and enter the name and time range.</span></span>

4. <span data-ttu-id="ff1a4-120">En **Días**, seleccione **Generar** para generar los días en el calendario.</span><span class="sxs-lookup"><span data-stu-id="ff1a4-120">Under **Days**, select **Generate** to generate the days in your calendar.</span></span> <span data-ttu-id="ff1a4-121">Introduzca el intervalo de fechas para su calendario y luego seleccione **Generar días**.</span><span class="sxs-lookup"><span data-stu-id="ff1a4-121">Enter the date range for your calendar and then select **Generate days**.</span></span>

5. <span data-ttu-id="ff1a4-122">Para agregar horarios de trabajo, en **Programación de trabajos**, seleccione **Agregar** y luego introduzca las horas para cada horario de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ff1a4-122">To add work schedules, under **Work schedule**, select **Add** and then enter the times for each work schedule.</span></span>

## <a name="configure-holidays-and-closures"></a><span data-ttu-id="ff1a4-123">Configurar días festivos y cierres</span><span class="sxs-lookup"><span data-stu-id="ff1a4-123">Configure holidays and closures</span></span>

<span data-ttu-id="ff1a4-124">Puede agregar o cambiar días festivos y cierres por separado desde un calendario de horas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ff1a4-124">You can add or change holidays and closures separately from a working time calendar.</span></span>

1. <span data-ttu-id="ff1a4-125">En la página **Administración de la organización**, seleccione **Días festivos y cierres**.</span><span class="sxs-lookup"><span data-stu-id="ff1a4-125">On the **Organization administration** page, select **Holidays and closures**.</span></span>

2. <span data-ttu-id="ff1a4-126">Seleccione **Nuevo** y especifique un nombre y una fecha para el día festivo o el cierre.</span><span class="sxs-lookup"><span data-stu-id="ff1a4-126">Select **New** and enter a name and date for the holiday or closure.</span></span>

## <a name="configure-non-work-time"></a><span data-ttu-id="ff1a4-127">Configurar tiempo no laborable</span><span class="sxs-lookup"><span data-stu-id="ff1a4-127">Configure non-work time</span></span>

<span data-ttu-id="ff1a4-128">Puede agregar o cambiar horas no laborables por separado desde un calendario de horas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ff1a4-128">You can add or change non-work times separately from a working time calendar.</span></span>

1. <span data-ttu-id="ff1a4-129">En la página **Administración de la organización**, seleccione **Tiempo no laborable**.</span><span class="sxs-lookup"><span data-stu-id="ff1a4-129">On the **Organization administration** page, select **Non-work time**.</span></span>

2. <span data-ttu-id="ff1a4-130">Seleccione **Nuevo** y especifique un nombre e intervalo de tiempo para el tiempo no laborable.</span><span class="sxs-lookup"><span data-stu-id="ff1a4-130">Select **New** and enter a name and time range for the non-work time.</span></span>

<span data-ttu-id="ff1a4-131">Si ha habilitado la característica de vista previa de correcciones de días festivos de permisos y ausencias, Human Resources usa los días festivos y las fechas de cierre para determinar el número de días para ajustar para los empleados inscritos en el calendario.</span><span class="sxs-lookup"><span data-stu-id="ff1a4-131">If you've enabled the Leave and absence bank holiday corrections preview feature, Human Resources uses holidays and closure dates to determine the number of days to adjust for employees enrolled in the calendar.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff1a4-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ff1a4-132">See also</span></span>

- [<span data-ttu-id="ff1a4-133">Visión general de bajas y ausencias</span><span class="sxs-lookup"><span data-stu-id="ff1a4-133">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
- [<span data-ttu-id="ff1a4-134">Configurar tipos de permisos y ausencias</span><span class="sxs-lookup"><span data-stu-id="ff1a4-134">Configure leave and absence types</span></span>](hr-leave-and-absence-types.md)
