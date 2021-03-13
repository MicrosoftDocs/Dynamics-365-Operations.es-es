---
title: Inscribir a un empleado en un plan de compensación fija
description: El director de compensaciones y prestaciones puede asignar a los empleados planes de compensación fija para gestionar su sueldo base.
author: andreabichsel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMCompFixedEmpl, HRMCompFixedEmplActionDialog, HcmPositionLookup, HRMCompRefPointLookup, HcmCompensationWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bc8373a4a39a1a212ab445b2b300fbddfe0e4a39
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114159"
---
# <a name="enroll-an-employee-in-a-fixed-compensation-plan"></a><span data-ttu-id="a2a9c-103">Inscribir a un empleado en un plan de compensación fija</span><span class="sxs-lookup"><span data-stu-id="a2a9c-103">Enroll an employee in a fixed compensation plan</span></span>

<span data-ttu-id="a2a9c-104">El director de compensaciones y prestaciones puede asignar a los empleados planes de compensación fija para gestionar su sueldo base.</span><span class="sxs-lookup"><span data-stu-id="a2a9c-104">The compensation and benefits manager can assign employees to fixed compensation plans to manage their base pay.</span></span> <span data-ttu-id="a2a9c-105">Este procedimiento supone que se ha creado un plan fijo y que está activo, así como que se han configurado reglas de idoneidad para el plan.</span><span class="sxs-lookup"><span data-stu-id="a2a9c-105">This procedure assumes that a fixed plan has been created and is active, and that eligibility rules have been set for the plan.</span></span> <span data-ttu-id="a2a9c-106">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="a2a9c-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="a2a9c-107">Para iniciar el procedimiento, vaya a Recursos humanos > Trabajadores > Empleados > Compensación > Plan fijo</span><span class="sxs-lookup"><span data-stu-id="a2a9c-107">To begin the procedure, go to Human resources > Workers > Employees > Compensation > Fixed plan</span></span>

1. <span data-ttu-id="a2a9c-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="a2a9c-108">Click New.</span></span>
2. <span data-ttu-id="a2a9c-109">En el campo Acción, seleccione un tipo de acción de compensación fija Contratar/Volver a contratar para describir el cambio en la compensación del empleado.</span><span class="sxs-lookup"><span data-stu-id="a2a9c-109">In the Action field, select a Fixed compensation action of type Hire/Rehire to describe the change in the employee's compensation.</span></span>
3. <span data-ttu-id="a2a9c-110">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a2a9c-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="a2a9c-111">En el campo Puesto, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a2a9c-111">In the Position field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="a2a9c-112">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a2a9c-112">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="a2a9c-113">El nivel que se muestra proviene del nivel de compensación del trabajo en el puesto.</span><span class="sxs-lookup"><span data-stu-id="a2a9c-113">The level that's displayed is from the Compensation Level of the Job on the Position.</span></span> <span data-ttu-id="a2a9c-114">El nivel se debe establecer en el trabajo para poder asignar una compensación al empleado.</span><span class="sxs-lookup"><span data-stu-id="a2a9c-114">The level must be set on the Job before compensation can be assigned to the employee.</span></span>  
6. <span data-ttu-id="a2a9c-115">En el campo Plan, seleccione el plan de compensación fija para el empleado.</span><span class="sxs-lookup"><span data-stu-id="a2a9c-115">In the Plan field, select the fixed compensation plan for the employee.</span></span> <span data-ttu-id="a2a9c-116">La búsqueda del plan se filtra para mostrar únicamente los planes aptos para el empleado según las reglas de idoneidad.</span><span class="sxs-lookup"><span data-stu-id="a2a9c-116">The Plan lookup is filtered to show only the plans that the employee is eligible for based on the Eligibility rules.</span></span>
7. <span data-ttu-id="a2a9c-117">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="a2a9c-117">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="a2a9c-118">Las fechas de vigencia y vencimiento para la compensación es establecen de forma predeterminada a partir de las fechas de inicio y fin de la asignación del puesto del trabajador.</span><span class="sxs-lookup"><span data-stu-id="a2a9c-118">The Effective and Expiration dates for the compensation default from the start and end dates for the worker's position assignment.</span></span> <span data-ttu-id="a2a9c-119">Puede ajustar estas fechas de acuerdo con sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="a2a9c-119">You can adjust these dates as needed.</span></span>  
    * <span data-ttu-id="a2a9c-120">Si el plan de compensación fija es un plan por pasos, seleccione el paso que contiene el índice salarial correcto para el empleado.</span><span class="sxs-lookup"><span data-stu-id="a2a9c-120">If the Fixed compensation plan is a step plan, select the step containing the correct pay rate for the employee.</span></span> <span data-ttu-id="a2a9c-121">Si el plan de compensación fija es un plan por categorías o grupos, indique el índice salarial correcto para el empleado.</span><span class="sxs-lookup"><span data-stu-id="a2a9c-121">If the fixed compensation plan is a grade or a band plan, enter the pay rate for the employee.</span></span> <span data-ttu-id="a2a9c-122">El índice salarial se valida en relación con los ajustes de tolerancia para el plan, y los puntos de referencia mínimos y máximos para el nivel de compensación del trabajo.</span><span class="sxs-lookup"><span data-stu-id="a2a9c-122">The pay rate will be validated against the tolerance settings for the plan, and the minimum and maximum reference points for the job's compensation level.</span></span>  
8. <span data-ttu-id="a2a9c-123">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a2a9c-123">Click OK.</span></span>

