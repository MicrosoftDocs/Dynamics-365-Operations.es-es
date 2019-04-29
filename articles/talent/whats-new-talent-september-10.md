---
title: Novedades y cambios en Dynamics 365 for Talent Core HR (10 de septiembre de 2018)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 09/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-09-06
ms.dyn365.ops.version: Talent September 10, 2018 update
ms.openlocfilehash: 6682e4d013f006696b45e644b7b4861b34faa9bf
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2019
ms.locfileid: "857416"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-september-10-2018"></a><span data-ttu-id="c473a-103">Novedades y cambios en Dynamics 365 for Talent Core HR (10 de septiembre de 2018)</span><span class="sxs-lookup"><span data-stu-id="c473a-103">What's new or changed in Dynamics 365 for Talent Core HR (September 10, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c473a-104">**Compilación 8.1.138.0**</span><span class="sxs-lookup"><span data-stu-id="c473a-104">**Build 8.1.138.0**</span></span>

<span data-ttu-id="c473a-105">Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 for Talent Core HR.</span><span class="sxs-lookup"><span data-stu-id="c473a-105">This topic describes features that are either new or changed in Microsoft Dynamics 365 for Talent Core HR.</span></span>

## <a name="allow-specific-time-of-day-on-time-off-requests-half-days"></a><span data-ttu-id="c473a-106">Deje tiempo específico del día en las solicitudes de licencia (días)</span><span class="sxs-lookup"><span data-stu-id="c473a-106">Allow specific time of day on time-off requests (half days)</span></span>

<span data-ttu-id="c473a-107">Si ha configurado la licencia y la ausencia para registrar el tiempo libre en días, ahora puede activar una definición de medio día.</span><span class="sxs-lookup"><span data-stu-id="c473a-107">If leave and absence is set up so that time off is submitted in days, you can now also enable a half-day definition.</span></span> <span data-ttu-id="c473a-108">A continuación, cuando los usuarios envíen solicitudes de tiempo libre, pueden especificar si están solicitando la primera mitad o la segunda mitad del día libre.</span><span class="sxs-lookup"><span data-stu-id="c473a-108">Then, when users submit time-off requests, they can specify whether they are requesting the first half or the second half of the day off.</span></span>

<span data-ttu-id="c473a-109">Esta opción está desactivada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c473a-109">By default, this option is turned off.</span></span> <span data-ttu-id="c473a-110">Para que los empleados pidan la primera mitad o la segunda mitad del día libre, debe activar esta opción en el área **Bajas y ausencias** de los parámetros de recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="c473a-110">For employees to request the first half or second half of the day off, you must turn on this option in the **Leave and absence** area of Human resources parameters.</span></span>

<span data-ttu-id="c473a-111">El privilegio de seguridad para esta función es mantener parámetros de recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="c473a-111">The security privilege for this feature is Maintain Human Resources Parameters.</span></span>

## <a name="validation-of-leave-and-absence-entries"></a><span data-ttu-id="c473a-112">Validación de las entradas de la licencia y de la ausencia</span><span class="sxs-lookup"><span data-stu-id="c473a-112">Validation of leave and absence entries</span></span>

<span data-ttu-id="c473a-113">En función de cómo se configure la licencia, los empleados que intenten enviar una solicitud de tiempo de licencia que dure más que su día laborable reciben un mensaje de advertencia.</span><span class="sxs-lookup"><span data-stu-id="c473a-113">Depending on how leave is configured, employees who try to submit a time-off request that is longer than their work day receive a warning message.</span></span> <span data-ttu-id="c473a-114">Es decir se les advierte si intentan tomarse más de un día completo libre en una determinada fecha.</span><span class="sxs-lookup"><span data-stu-id="c473a-114">In other words, they are warned if they try to take more than a full day off on any given date.</span></span>

<span data-ttu-id="c473a-115">Esta validación está siempre activada.</span><span class="sxs-lookup"><span data-stu-id="c473a-115">This validation is always turned on.</span></span> <span data-ttu-id="c473a-116">Cada vez que los empleados superen el umbral del día que está definido, reciben una advertencia en la solicitud de tiempo de licencia.</span><span class="sxs-lookup"><span data-stu-id="c473a-116">Any time that employees exceed the day threshold that is defined, they receive a warning in their time-off request.</span></span>

## <a name="additional-fields-for-conditional-statements-in-workflows"></a><span data-ttu-id="c473a-117">Campos adicionales para las instrucciones condicionales en los flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="c473a-117">Additional fields for conditional statements in workflows</span></span>

<span data-ttu-id="c473a-118">Se han agregado campos adicionales a las instrucciones condicionales y a los marcadores de varios flujos de trabajo en Core HR.</span><span class="sxs-lookup"><span data-stu-id="c473a-118">Additional fields have been added to conditional statements and placeholders for several workflows in Core HR.</span></span>

<span data-ttu-id="c473a-119">Los siguientes campos se han agregado a los flujos de trabajo de compensación, finalización, y transferencia:</span><span class="sxs-lookup"><span data-stu-id="c473a-119">The following fields have been added to the compensation, termination, and transfer workflows:</span></span>

- <span data-ttu-id="c473a-120">EmploymentType</span><span class="sxs-lookup"><span data-stu-id="c473a-120">EmploymentType</span></span>
- <span data-ttu-id="c473a-121">LegalEntity</span><span class="sxs-lookup"><span data-stu-id="c473a-121">LegalEntity</span></span>
- <span data-ttu-id="c473a-122">AdjustedWorkerStartDate</span><span class="sxs-lookup"><span data-stu-id="c473a-122">AdjustedWorkerStartDate</span></span>
- <span data-ttu-id="c473a-123">EmployerNoticeAmount</span><span class="sxs-lookup"><span data-stu-id="c473a-123">EmployerNoticeAmount</span></span>
- <span data-ttu-id="c473a-124">EmployerUnitOfNotice</span><span class="sxs-lookup"><span data-stu-id="c473a-124">EmployerUnitOfNotice</span></span>
- <span data-ttu-id="c473a-125">TransitionDate</span><span class="sxs-lookup"><span data-stu-id="c473a-125">TransitionDate</span></span>
- <span data-ttu-id="c473a-126">WorkerNoticeAmount</span><span class="sxs-lookup"><span data-stu-id="c473a-126">WorkerNoticeAmount</span></span>
- <span data-ttu-id="c473a-127">WorkerStartDate</span><span class="sxs-lookup"><span data-stu-id="c473a-127">WorkerStartDate</span></span>
- <span data-ttu-id="c473a-128">WorkerUnitOfNotice</span><span class="sxs-lookup"><span data-stu-id="c473a-128">WorkerUnitOfNotice</span></span>
- <span data-ttu-id="c473a-129">ProbationEndDate</span><span class="sxs-lookup"><span data-stu-id="c473a-129">ProbationEndDate</span></span>
- <span data-ttu-id="c473a-130">Posición</span><span class="sxs-lookup"><span data-stu-id="c473a-130">Position</span></span>
- <span data-ttu-id="c473a-131">Unión</span><span class="sxs-lookup"><span data-stu-id="c473a-131">Union</span></span>
- <span data-ttu-id="c473a-132">Departamento</span><span class="sxs-lookup"><span data-stu-id="c473a-132">Department</span></span>
- <span data-ttu-id="c473a-133">PositionType</span><span class="sxs-lookup"><span data-stu-id="c473a-133">PositionType</span></span>
- <span data-ttu-id="c473a-134">CompLocation</span><span class="sxs-lookup"><span data-stu-id="c473a-134">CompLocation</span></span>
- <span data-ttu-id="c473a-135">Cargo</span><span class="sxs-lookup"><span data-stu-id="c473a-135">Title</span></span>
- <span data-ttu-id="c473a-136">Trabajo</span><span class="sxs-lookup"><span data-stu-id="c473a-136">Job</span></span>
- <span data-ttu-id="c473a-137">JobType</span><span class="sxs-lookup"><span data-stu-id="c473a-137">JobType</span></span>
- <span data-ttu-id="c473a-138">JobFamily</span><span class="sxs-lookup"><span data-stu-id="c473a-138">JobFamily</span></span>
- <span data-ttu-id="c473a-139">JobFunction</span><span class="sxs-lookup"><span data-stu-id="c473a-139">JobFunction</span></span>

<span data-ttu-id="c473a-140">Los campos siguientes se han agregado al flujo de trabajo de posición:</span><span class="sxs-lookup"><span data-stu-id="c473a-140">The following fields have been added to the position workflow:</span></span>

- <span data-ttu-id="c473a-141">Posición</span><span class="sxs-lookup"><span data-stu-id="c473a-141">Position</span></span>
- <span data-ttu-id="c473a-142">Unión</span><span class="sxs-lookup"><span data-stu-id="c473a-142">Union</span></span>
- <span data-ttu-id="c473a-143">Departamento</span><span class="sxs-lookup"><span data-stu-id="c473a-143">Department</span></span>
- <span data-ttu-id="c473a-144">PositionType</span><span class="sxs-lookup"><span data-stu-id="c473a-144">PositionType</span></span>
- <span data-ttu-id="c473a-145">CompLocation</span><span class="sxs-lookup"><span data-stu-id="c473a-145">CompLocation</span></span>
- <span data-ttu-id="c473a-146">Cargo</span><span class="sxs-lookup"><span data-stu-id="c473a-146">Title</span></span>
- <span data-ttu-id="c473a-147">Trabajo</span><span class="sxs-lookup"><span data-stu-id="c473a-147">Job</span></span>
- <span data-ttu-id="c473a-148">JobType</span><span class="sxs-lookup"><span data-stu-id="c473a-148">JobType</span></span>
- <span data-ttu-id="c473a-149">JobFamily</span><span class="sxs-lookup"><span data-stu-id="c473a-149">JobFamily</span></span>
- <span data-ttu-id="c473a-150">JobFunction</span><span class="sxs-lookup"><span data-stu-id="c473a-150">JobFunction</span></span>

<span data-ttu-id="c473a-151">Los campos de las instrucciones condicionales y los marcadores están disponibles para todos los usuarios que tengan acceso para configurar los flujos de trabajo anteriormente mencionados.</span><span class="sxs-lookup"><span data-stu-id="c473a-151">Fields in conditional statements and placeholders are available to all users who have access to configure the previously mentioned workflows.</span></span>

## <a name="navigation-to-attract-from-personnel-management"></a><span data-ttu-id="c473a-152">Navegación a Attract desde la dirección del personal</span><span class="sxs-lookup"><span data-stu-id="c473a-152">Navigation to Attract from personnel management</span></span>

<span data-ttu-id="c473a-153">En dirección de personal, si Attract no se ha configurado, la sección **Candidatos a contratar** solicita a los usuarios que se familiaricen con Attract en vez de mostrar el mensaje “No se encontró nada para mostrar aquí”.</span><span class="sxs-lookup"><span data-stu-id="c473a-153">In personnel management, if Attract hasn't been set up, the **Candidates to hire** section directs users to get started with Attract instead of showing the message, "We didn't find anything to show here."</span></span>

## <a name="other-changes"></a><span data-ttu-id="c473a-154">Otros cambios</span><span class="sxs-lookup"><span data-stu-id="c473a-154">Other changes</span></span>

<span data-ttu-id="c473a-155">Este lanzamiento incluye varias correcciones de errores adicionales:</span><span class="sxs-lookup"><span data-stu-id="c473a-155">This release includes several additional bug fixes:</span></span>

- <span data-ttu-id="c473a-156">Cuando se utiliza un contratista, la pestaña **Compensación** no debe estar disponible en la página de solicitud/acción.</span><span class="sxs-lookup"><span data-stu-id="c473a-156">When a contractor is hired, the **Compensation** tab should not be available on the request/action page.</span></span>
- <span data-ttu-id="c473a-157">Durante el proceso de finalización de la solicitud, no puede continuar hasta que todos los campos necesarios contengan datos.</span><span class="sxs-lookup"><span data-stu-id="c473a-157">During the request termination process, you can't continue until all required fields contain data.</span></span>
- <span data-ttu-id="c473a-158">Los problemas de visualización de fechas y de criterios de ordenación de los análisis de la dirección del personal se han abordado.</span><span class="sxs-lookup"><span data-stu-id="c473a-158">Sort order and date display issues on the Personnel management analytics have been addressed.</span></span>
