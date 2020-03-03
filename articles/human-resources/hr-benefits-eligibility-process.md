---
title: Proceso de idoneidad para prestación
description: Este procedimiento muestra cómo funciona el proceso de idoneidad de la prestación.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: 57e3e1dde4b4c8038b151dabf17af0f911f2ba07
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010487"
---
# <a name="benefit-eligibility-process"></a><span data-ttu-id="27380-103">Proceso de idoneidad para prestación</span><span class="sxs-lookup"><span data-stu-id="27380-103">Benefit eligibility process</span></span>

<span data-ttu-id="27380-104">Este procedimiento muestra cómo funciona el proceso de idoneidad de la prestación.</span><span class="sxs-lookup"><span data-stu-id="27380-104">This procedure shows how the benefit eligibility process works.</span></span> <span data-ttu-id="27380-105">Cuando se complete el proceso, podrá ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="27380-105">When the process is complete you can view the results.</span></span> <span data-ttu-id="27380-106">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="27380-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="27380-107">Vaya a Recursos humanos > Prestaciones > Prestaciones.</span><span class="sxs-lookup"><span data-stu-id="27380-107">Go to Human resources > Benefits > Benefits.</span></span>
2. <span data-ttu-id="27380-108">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="27380-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="27380-109">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="27380-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="27380-110">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="27380-110">Click Edit.</span></span>
5. <span data-ttu-id="27380-111">En el campo Idoneidad, seleccione "Basada en reglas".</span><span class="sxs-lookup"><span data-stu-id="27380-111">In the Eligibility field, select 'Rule based'.</span></span>
6. <span data-ttu-id="27380-112">En el campo Tipo de regla, seleccione la regla de directiva de prestación que desea aplicar a la prestación.</span><span class="sxs-lookup"><span data-stu-id="27380-112">In the Rule type field, select the benefit policy rule you would like applied to the benefit.</span></span>
7. <span data-ttu-id="27380-113">En el panel de acciones, haga clic en Prestación.</span><span class="sxs-lookup"><span data-stu-id="27380-113">On the Action Pane, click Benefit.</span></span>
8. <span data-ttu-id="27380-114">Haga clic en Crear evento de idoneidad para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="27380-114">Click Create eligibility event to open the drop dialog.</span></span>
9. <span data-ttu-id="27380-115">En el campo Evento, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="27380-115">In the Event field, type a value.</span></span>
10. <span data-ttu-id="27380-116">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="27380-116">In the Description field, type a value.</span></span>
11. <span data-ttu-id="27380-117">Seleccione "Abrir inscripción" en el campo Tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="27380-117">In the Event type field, select 'Open enrollment'.</span></span>
12. <span data-ttu-id="27380-118">En el campo Fecha de inicio de la cobertura, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="27380-118">In the Coverage start date field, enter a date and time.</span></span>
13. <span data-ttu-id="27380-119">En el campo Fecha de inicio del período de inscripción, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="27380-119">In the Enrollment period start date field, enter a date and time.</span></span>
14. <span data-ttu-id="27380-120">En el campo Días para inscribirse, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="27380-120">In the Days to enroll field, enter a number.</span></span>
15. <span data-ttu-id="27380-121">Haga clic en Crear evento.</span><span class="sxs-lookup"><span data-stu-id="27380-121">Click Create event.</span></span>
16. <span data-ttu-id="27380-122">Haga clic en Agregar en la ficha desplegable Trabajadores.</span><span class="sxs-lookup"><span data-stu-id="27380-122">Click Add in the Workers FastTab.</span></span>
17. <span data-ttu-id="27380-123">En el campo Mostrar por tipo, seleccione "Empleados".</span><span class="sxs-lookup"><span data-stu-id="27380-123">In the Show by type field, select 'Employees'.</span></span>
18. <span data-ttu-id="27380-124">En el campo Mostrar por entidad jurídica, seleccione "Entidad jurídica actual".</span><span class="sxs-lookup"><span data-stu-id="27380-124">In the Show by legal entity field, select 'Current legal entity'.</span></span>
19. <span data-ttu-id="27380-125">En la lista, active o desactive todas las filas.</span><span class="sxs-lookup"><span data-stu-id="27380-125">In the list, mark or unmark all rows.</span></span>
20. <span data-ttu-id="27380-126">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="27380-126">Click OK.</span></span>
21. <span data-ttu-id="27380-127">Haga clic Procesar.</span><span class="sxs-lookup"><span data-stu-id="27380-127">Click Process.</span></span>
22. <span data-ttu-id="27380-128">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="27380-128">Click OK.</span></span>
23. <span data-ttu-id="27380-129">Actualice la página.</span><span class="sxs-lookup"><span data-stu-id="27380-129">Refresh the page.</span></span>
24. <span data-ttu-id="27380-130">Haga clic en Mostrar resultados.</span><span class="sxs-lookup"><span data-stu-id="27380-130">Click Show results.</span></span>
25. <span data-ttu-id="27380-131">Abrir filtro de columna Estado.</span><span class="sxs-lookup"><span data-stu-id="27380-131">Open Status column filter.</span></span>
26. <span data-ttu-id="27380-132">Ordenar de A a Z</span><span class="sxs-lookup"><span data-stu-id="27380-132">Sort A to Z</span></span>
