---
title: Inscribir a un empleado en un plan de compensación variable
description: El director de compensaciones y de prestaciones puede inscribir a empleados en los planes de compensación variable para calcular las primas en efectivo y no efectivo para los empleados.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMCompVarEnrollEmpl
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d120f8bb52252956d75178d2ffac6ab632385e00
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "1510529"
---
# <a name="enroll-an-employee-in-a-variable-compensation-plan"></a><span data-ttu-id="df462-103">Inscribir a un empleado en un plan de compensación variable</span><span class="sxs-lookup"><span data-stu-id="df462-103">Enroll an employee in a variable compensation plan</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="df462-104">El director de compensaciones y de prestaciones puede inscribir a empleados en los planes de compensación variable para calcular las primas en efectivo y no efectivo para los empleados.</span><span class="sxs-lookup"><span data-stu-id="df462-104">The Compensation and Benefits manager can enroll employees in variable compensation plans to calculate cash and non-cash awards for employees.</span></span> <span data-ttu-id="df462-105">Este procedimiento supone que se ha creado un plan de compensación variable con el campo Habilitar inscripción definido en Sí, y que se han creado reglas de idoneidad para dicho plan de compensación variable.</span><span class="sxs-lookup"><span data-stu-id="df462-105">This procedure assumes that a variable compensation plan has been created with the Enable enrolment field set to Yes, and that eligibility rules have been created for that variable compensation plan.</span></span> <span data-ttu-id="df462-106">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="df462-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="df462-107">Para iniciar este procedimiento, vaya a Recursos humanos > Trabajadores > Empleados > Compensación > Inscripción de plan variable</span><span class="sxs-lookup"><span data-stu-id="df462-107">To begin this procedure, go to Human resources > Workers > Employees > Compensation > Variable plan enrolment</span></span>

1. <span data-ttu-id="df462-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="df462-108">Click New.</span></span>
2. <span data-ttu-id="df462-109">En el campo Plan, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="df462-109">In the Plan field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="df462-110">La búsqueda del plan se filtrará para mostrar únicamente los planes de compensación variable aptos para el empleado según las reglas de idoneidad.</span><span class="sxs-lookup"><span data-stu-id="df462-110">The plan lookup will be filtered to only show the variable compensation plans that the employee is eligible for based on the eligibility rules.</span></span>  
3. <span data-ttu-id="df462-111">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="df462-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="df462-112">Expanda la sección General.</span><span class="sxs-lookup"><span data-stu-id="df462-112">Toggle the expansion of the General section.</span></span>
5. <span data-ttu-id="df462-113">En el campo Fecha de vigencia, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="df462-113">In the Effective date field, enter a date.</span></span>
6. <span data-ttu-id="df462-114">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="df462-114">Click Save.</span></span>
7. <span data-ttu-id="df462-115">Expanda la sección Anulaciones.</span><span class="sxs-lookup"><span data-stu-id="df462-115">Toggle the expansion of the Overrides section.</span></span>
    * <span data-ttu-id="df462-116">Existe la opción de definir la fecha de regla de contratación para sobrescribir la fecha de contratación de un empleado cuando la regla de contratación especificada para el plan variable seleccionado es Porcentaje.</span><span class="sxs-lookup"><span data-stu-id="df462-116">Optionally, a hire rule date can be set to override the hire date for an employee when the hire rule specified for the selected variable plan is Percent.</span></span>  
    * <span data-ttu-id="df462-117">Si el plan variable es un porcentaje del plan base, se puede sobrescribir el porcentaje de la prima para el empleado.</span><span class="sxs-lookup"><span data-stu-id="df462-117">If the variable plan is a percent of basis plan, the award percentage can be overridden for the employee.</span></span> <span data-ttu-id="df462-118">Si el plan de compensación variable es un plan de número de unidades, se puede sobrescribir el número de unidades para el empleado.</span><span class="sxs-lookup"><span data-stu-id="df462-118">If the variable compensation plan is a number of units plan, the number of units can be overridden for the employee.</span></span>  
    * <span data-ttu-id="df462-119">Si el empleado debe recibir un importe fijo como prima, el importe se puede establecer aquí.</span><span class="sxs-lookup"><span data-stu-id="df462-119">If the employee should be given a flat amount for their award, the amount can be set here.</span></span>  
8. <span data-ttu-id="df462-120">Expanda la sección Anulación de unidades organizativas.</span><span class="sxs-lookup"><span data-stu-id="df462-120">Toggle the expansion of the Organizational overrides section.</span></span>
    * <span data-ttu-id="df462-121">Si se debe tener en cuenta el rendimiento del empleado, el rendimiento de distintos departamentos o un departamento distinto al asignado al puesto del empleado, el departamento se puede sobrescribir.</span><span class="sxs-lookup"><span data-stu-id="df462-121">If the employee's performance should take into consideration, the performance of different departments, or a department other than the one assigned on the employee's position, the department can be overridden.</span></span> <span data-ttu-id="df462-122">La columna Porcentaje debe sumar 100.</span><span class="sxs-lookup"><span data-stu-id="df462-122">The Percent column should total 100.</span></span>  

