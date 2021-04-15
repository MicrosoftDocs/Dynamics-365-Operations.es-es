---
title: Inscribir y quitar prestaciones para trabajadores
description: Este procedimiento muestra cómo se puede inscribir un único trabajador en una o más prestaciones, así como varios trabajadores se pueden inscribir en una prestación.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorker, HcmWorkerEnrollment, HcmBenefitByEligibilityLookup, HcmMassBenefitEnrollment, HcmBenefitLookup, HcmMassBenefitEnrollmentResults, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: 47e8bf46d3d38cd1b776debb835d53a22e724149
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5805859"
---
# <a name="enroll-and-remove-benefits-from-workers"></a><span data-ttu-id="c6c0a-103">Inscribir y quitar prestaciones para trabajadores</span><span class="sxs-lookup"><span data-stu-id="c6c0a-103">Enroll and remove benefits from workers</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



<span data-ttu-id="c6c0a-104">Este procedimiento muestra cómo se puede inscribir un único trabajador en una o más prestaciones, así como varios trabajadores se pueden inscribir en una prestación.</span><span class="sxs-lookup"><span data-stu-id="c6c0a-104">This procedure demonstrates how a single worker can be enrolled in one or more benefits, as well as multiple workers can be enrolled in a benefit.</span></span> <span data-ttu-id="c6c0a-105">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="c6c0a-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="enroll-a-single-worker-in-benefits"></a><span data-ttu-id="c6c0a-106">Inscripción de un trabajador en prestaciones</span><span class="sxs-lookup"><span data-stu-id="c6c0a-106">Enroll a single worker in benefits</span></span>
1. <span data-ttu-id="c6c0a-107">Vaya a Recursos humanos > Trabajadores > Empleados.</span><span class="sxs-lookup"><span data-stu-id="c6c0a-107">Go to Human resources > Workers > Employees</span></span>
2. <span data-ttu-id="c6c0a-108">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="c6c0a-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="c6c0a-109">Haga clic en Prestaciones.</span><span class="sxs-lookup"><span data-stu-id="c6c0a-109">Click Benefits.</span></span>
4. <span data-ttu-id="c6c0a-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="c6c0a-110">Click New.</span></span>
5. <span data-ttu-id="c6c0a-111">En el campo Prestación, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c6c0a-111">In the Benefit field, enter or select a value.</span></span>
6. <span data-ttu-id="c6c0a-112">En el campo Fecha de inicio de la cobertura, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="c6c0a-112">In the Coverage start date field, enter a date and time.</span></span>
7. <span data-ttu-id="c6c0a-113">En el campo Fecha final de la cobertura, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="c6c0a-113">In the Coverage end date field, enter a date and time.</span></span>
8. <span data-ttu-id="c6c0a-114">Expanda la sección Beneficiarios si los beneficiarios se deben agregar a la prestación.</span><span class="sxs-lookup"><span data-stu-id="c6c0a-114">Expand the Beneficiaries section if beneficiaries need to be added to the benefit.</span></span> <span data-ttu-id="c6c0a-115">También puede agregar dependientes de esta página en caso de ser aplicable para la prestación.</span><span class="sxs-lookup"><span data-stu-id="c6c0a-115">You can also add dependents from this page if applicable to the benefit.</span></span>
9. <span data-ttu-id="c6c0a-116">También puede editar los detalles de la inscripción de un beneficio o eliminar una inscripción en esta página.</span><span class="sxs-lookup"><span data-stu-id="c6c0a-116">You can also edit the details of a benefit enrollment or delete an enrollment on this page.</span></span> <span data-ttu-id="c6c0a-117">Cuando termine de realizar los cambios en la inscripción de la prestación, cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c6c0a-117">When you have finished making changes to the benefit enrollment, close the page.</span></span>

## <a name="enroll-multiple-workers-in-a-benefit"></a><span data-ttu-id="c6c0a-118">Inscribir varios trabajadores en una prestación</span><span class="sxs-lookup"><span data-stu-id="c6c0a-118">Enroll multiple workers in a benefit</span></span>
1. <span data-ttu-id="c6c0a-119">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c6c0a-119">Close the page.</span></span>
2. <span data-ttu-id="c6c0a-120">Vaya a Recursos humanos > Trabajadores > Empleados.</span><span class="sxs-lookup"><span data-stu-id="c6c0a-120">Go to Human resources > Workers > Employees</span></span>
3. <span data-ttu-id="c6c0a-121">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c6c0a-121">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="c6c0a-122">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="c6c0a-122">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="c6c0a-123">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="c6c0a-123">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="c6c0a-124">Haga clic en Inscribirse en prestaciones.</span><span class="sxs-lookup"><span data-stu-id="c6c0a-124">Click Enroll in benefits.</span></span>
7. <span data-ttu-id="c6c0a-125">En el campo Prestación, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c6c0a-125">In the Benefit field, enter or select a value.</span></span>
8. <span data-ttu-id="c6c0a-126">En el campo Fecha de inicio de la cobertura, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="c6c0a-126">In the Coverage start date field, enter a date and time.</span></span>
9. <span data-ttu-id="c6c0a-127">En el campo Fecha final de la cobertura, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="c6c0a-127">In the Coverage end date field, enter a date and time.</span></span>
10. <span data-ttu-id="c6c0a-128">Haga clic en Inscribir.</span><span class="sxs-lookup"><span data-stu-id="c6c0a-128">Click Enroll.</span></span>
11. <span data-ttu-id="c6c0a-129">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c6c0a-129">Close the page.</span></span>
12. <span data-ttu-id="c6c0a-130">Vaya a Recursos humanos > Prestaciones > Inscripción > Resultados de la inscripción a prestaciones.</span><span class="sxs-lookup"><span data-stu-id="c6c0a-130">Go to Human Resources > Benefits > Enrollment > Benefit enrollment results</span></span>
13. <span data-ttu-id="c6c0a-131">Busque el registro de los resultados de la prestación que busca.</span><span class="sxs-lookup"><span data-stu-id="c6c0a-131">Find the benefit results record that you are looking for.</span></span>
14. <span data-ttu-id="c6c0a-132">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c6c0a-132">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="c6c0a-133">Esta página le permite ver qué trabajadores se han inscrito en la prestación, junto con los empleados que no se han inscrito.</span><span class="sxs-lookup"><span data-stu-id="c6c0a-133">This page allows you to view which employees have been enrolled in the benefit, as well as any employees who were not enrolled.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]