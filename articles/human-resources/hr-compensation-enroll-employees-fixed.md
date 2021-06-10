---
title: Inscribir a un empleado en un plan de compensación fija
description: El director de compensaciones y prestaciones puede asignar a los empleados planes de compensación fija para gestionar su sueldo base.
author: andreabichsel
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HRMCompFixedEmpl, HRMCompFixedEmplActionDialog, HcmPositionLookup, HRMCompRefPointLookup, HcmCompensationWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e5f0862c86234495c89b2a6ad947cc78e687de37
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054245"
---
# <a name="enroll-an-employee-in-a-fixed-compensation-plan"></a><span data-ttu-id="fb123-103">Inscribir a un empleado en un plan de compensación fija</span><span class="sxs-lookup"><span data-stu-id="fb123-103">Enroll an employee in a fixed compensation plan</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="fb123-104">El director de compensaciones y prestaciones puede asignar a los empleados planes de compensación fija para gestionar su sueldo base.</span><span class="sxs-lookup"><span data-stu-id="fb123-104">The compensation and benefits manager can assign employees to fixed compensation plans to manage their base pay.</span></span> <span data-ttu-id="fb123-105">Este procedimiento supone que se ha creado un plan fijo y que está activo, así como que se han configurado reglas de idoneidad para el plan.</span><span class="sxs-lookup"><span data-stu-id="fb123-105">This procedure assumes that a fixed plan has been created and is active, and that eligibility rules have been set for the plan.</span></span> <span data-ttu-id="fb123-106">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="fb123-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="fb123-107">Para iniciar el procedimiento, vaya a Recursos humanos > Trabajadores > Empleados > Compensación > Plan fijo</span><span class="sxs-lookup"><span data-stu-id="fb123-107">To begin the procedure, go to Human resources > Workers > Employees > Compensation > Fixed plan</span></span>

1. <span data-ttu-id="fb123-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="fb123-108">Click New.</span></span>
2. <span data-ttu-id="fb123-109">En el campo Acción, seleccione un tipo de acción de compensación fija Contratar/Volver a contratar para describir el cambio en la compensación del empleado.</span><span class="sxs-lookup"><span data-stu-id="fb123-109">In the Action field, select a Fixed compensation action of type Hire/Rehire to describe the change in the employee's compensation.</span></span>
3. <span data-ttu-id="fb123-110">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="fb123-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="fb123-111">En el campo Puesto, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="fb123-111">In the Position field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="fb123-112">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="fb123-112">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="fb123-113">El nivel que se muestra proviene del nivel de compensación del trabajo en el puesto.</span><span class="sxs-lookup"><span data-stu-id="fb123-113">The level that's displayed is from the Compensation Level of the Job on the Position.</span></span> <span data-ttu-id="fb123-114">El nivel se debe establecer en el trabajo para poder asignar una compensación al empleado.</span><span class="sxs-lookup"><span data-stu-id="fb123-114">The level must be set on the Job before compensation can be assigned to the employee.</span></span>  
6. <span data-ttu-id="fb123-115">En el campo Plan, seleccione el plan de compensación fija para el empleado.</span><span class="sxs-lookup"><span data-stu-id="fb123-115">In the Plan field, select the fixed compensation plan for the employee.</span></span> <span data-ttu-id="fb123-116">La búsqueda del plan se filtra para mostrar únicamente los planes aptos para el empleado según las reglas de idoneidad.</span><span class="sxs-lookup"><span data-stu-id="fb123-116">The Plan lookup is filtered to show only the plans that the employee is eligible for based on the Eligibility rules.</span></span>
7. <span data-ttu-id="fb123-117">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="fb123-117">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="fb123-118">Las fechas de vigencia y vencimiento para la compensación es establecen de forma predeterminada a partir de las fechas de inicio y fin de la asignación del puesto del trabajador.</span><span class="sxs-lookup"><span data-stu-id="fb123-118">The Effective and Expiration dates for the compensation default from the start and end dates for the worker's position assignment.</span></span> <span data-ttu-id="fb123-119">Puede ajustar estas fechas de acuerdo con sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="fb123-119">You can adjust these dates as needed.</span></span>  
    * <span data-ttu-id="fb123-120">Si el plan de compensación fija es un plan por pasos, seleccione el paso que contiene el índice salarial correcto para el empleado.</span><span class="sxs-lookup"><span data-stu-id="fb123-120">If the Fixed compensation plan is a step plan, select the step containing the correct pay rate for the employee.</span></span> <span data-ttu-id="fb123-121">Si el plan de compensación fija es un plan por categorías o grupos, indique el índice salarial correcto para el empleado.</span><span class="sxs-lookup"><span data-stu-id="fb123-121">If the fixed compensation plan is a grade or a band plan, enter the pay rate for the employee.</span></span> <span data-ttu-id="fb123-122">El índice salarial se valida en relación con los ajustes de tolerancia para el plan, y los puntos de referencia mínimos y máximos para el nivel de compensación del trabajo.</span><span class="sxs-lookup"><span data-stu-id="fb123-122">The pay rate will be validated against the tolerance settings for the plan, and the minimum and maximum reference points for the job's compensation level.</span></span>  
8. <span data-ttu-id="fb123-123">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="fb123-123">Click OK.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]