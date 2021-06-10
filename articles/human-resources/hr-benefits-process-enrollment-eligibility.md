---
title: Proceso de idoneidad para inscripción
description: Este artículo explica cómo ejecutar el proceso de idoneidad de inscripción.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4dd63e755f0afdbce411b3001410d2e56036e432
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054269"
---
# <a name="process-enrollment-eligibility"></a><span data-ttu-id="d5a61-103">Proceso de idoneidad para inscripción</span><span class="sxs-lookup"><span data-stu-id="d5a61-103">Process enrollment eligibility</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="d5a61-104">Este artículo explica cómo ejecutar el proceso de idoneidad de inscripción.</span><span class="sxs-lookup"><span data-stu-id="d5a61-104">This article explains how to run the enrollment eligibility process.</span></span>

1. <span data-ttu-id="d5a61-105">En el espacio de trabajo **Administración de prestaciones**, en **Procesamiento**, seleccione **Procesamiento de idoneidad para inscripción**.</span><span class="sxs-lookup"><span data-stu-id="d5a61-105">In the **Benefits management** workspace, under **Processing**, select **Enrollment eligibility processing**.</span></span>

2. <span data-ttu-id="d5a61-106">En el cuadro de diálogo **Ejecutar proceso de idoneidad para la inscripción en prestaciones**, especifique valores para los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="d5a61-106">In the **Run benefit enrollment eligibility process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="d5a61-107">Campo</span><span class="sxs-lookup"><span data-stu-id="d5a61-107">Field</span></span> | <span data-ttu-id="d5a61-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="d5a61-108">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="d5a61-109">**Período de inscripción**</span><span class="sxs-lookup"><span data-stu-id="d5a61-109">**Enrollment period**</span></span> | <span data-ttu-id="d5a61-110">El periodo de inscripción para procesar la idoneidad de inscripción.</span><span class="sxs-lookup"><span data-stu-id="d5a61-110">The enrollment period to process enrollment eligibility for.</span></span> |
   | <span data-ttu-id="d5a61-111">**Entidad jurídica**</span><span class="sxs-lookup"><span data-stu-id="d5a61-111">**Legal entity**</span></span> | <span data-ttu-id="d5a61-112">La entidad jurídica para procesar la idoneidad de inscripción.</span><span class="sxs-lookup"><span data-stu-id="d5a61-112">The legal entity to process enrollment eligibility for.</span></span> |
   | <span data-ttu-id="d5a61-113">**Trabajador**</span><span class="sxs-lookup"><span data-stu-id="d5a61-113">**Worker**</span></span> | <span data-ttu-id="d5a61-114">El trabajador para procesar la idoneidad de inscripción.</span><span class="sxs-lookup"><span data-stu-id="d5a61-114">The worker to process enrollment eligibility for.</span></span> <span data-ttu-id="d5a61-115">Si deja este campo en blanco, la idoneidad de inscripción se procesará para todos los trabajadores.</span><span class="sxs-lookup"><span data-stu-id="d5a61-115">If you leave this field blank, enrollment eligibility will be processed for all workers.</span></span> |
   | <span data-ttu-id="d5a61-116">**Plan de beneficios**</span><span class="sxs-lookup"><span data-stu-id="d5a61-116">**Benefit plan**</span></span> | <span data-ttu-id="d5a61-117">El plan de prestaciones para procesar la idoneidad de inscripción.</span><span class="sxs-lookup"><span data-stu-id="d5a61-117">The benefit plan to process enrollment eligibility for.</span></span>

3. <span data-ttu-id="d5a61-118">Si desea ejecutar el proceso en segundo plano, seleccione **Ejecutar en segundo plano** y realice las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="d5a61-118">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="d5a61-119">Escriba información para proceso.</span><span class="sxs-lookup"><span data-stu-id="d5a61-119">Enter information for the process.</span></span>

   2. <span data-ttu-id="d5a61-120">Para configurar un trabajo periódico, seleccione **Periodicidad**, introduzca la información de periodicidad y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d5a61-120">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="d5a61-121">Para configurar una alerta de trabajo, seleccione **Alertas**, seleccione las alertas que quiera recibir y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d5a61-121">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="d5a61-122">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d5a61-122">Select **OK**.</span></span> <span data-ttu-id="d5a61-123">El proceso se ejecutará con los parámetros que establezca.</span><span class="sxs-lookup"><span data-stu-id="d5a61-123">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="d5a61-124">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d5a61-124">Select **OK**.</span></span>

## <a name="view-process-results"></a><span data-ttu-id="d5a61-125">Ver resultados de proceso</span><span class="sxs-lookup"><span data-stu-id="d5a61-125">View Process Results</span></span>

<span data-ttu-id="d5a61-126">Este artículo explica cómo ver los resultados del proceso de idoneidad.</span><span class="sxs-lookup"><span data-stu-id="d5a61-126">This article explains how to view eligibility process results.</span></span>

1.  <span data-ttu-id="d5a61-127">En el espacio de trabajo **Administración de prestaciones**, en **Procesamiento**, seleccione **Procesar resultados**.</span><span class="sxs-lookup"><span data-stu-id="d5a61-127">In the **Benefits management** workspace, under **Processing**, select **Process results**.</span></span>

2.  <span data-ttu-id="d5a61-128">En el formulario **Procesar resultados**, se especifican los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="d5a61-128">In the **Process results** form, the following fields are specified:</span></span>

   | <span data-ttu-id="d5a61-129">Campo</span><span class="sxs-lookup"><span data-stu-id="d5a61-129">Field</span></span> | <span data-ttu-id="d5a61-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="d5a61-130">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="d5a61-131">**Id. de proceso**</span><span class="sxs-lookup"><span data-stu-id="d5a61-131">**Process ID**</span></span> | <span data-ttu-id="d5a61-132">El Id. único para la combinación de trabajador, entidad jurídica y ejecución del proceso.</span><span class="sxs-lookup"><span data-stu-id="d5a61-132">The unique ID for the combination of Worker, Legal entity, and process run.</span></span> |
   | <span data-ttu-id="d5a61-133">**Tipo de proceso**</span><span class="sxs-lookup"><span data-stu-id="d5a61-133">**Process type**</span></span> | <span data-ttu-id="d5a61-134">Esto identifica el proceso que se ejecutó.</span><span class="sxs-lookup"><span data-stu-id="d5a61-134">This identifies the process that was run.</span></span> <span data-ttu-id="d5a61-135">Por ejemplo: Inscripción.</span><span class="sxs-lookup"><span data-stu-id="d5a61-135">For example:  Enrollment.</span></span> |
   | <span data-ttu-id="d5a61-136">**Marca de tiempo**</span><span class="sxs-lookup"><span data-stu-id="d5a61-136">**Time stamp**</span></span> | <span data-ttu-id="d5a61-137">La hora en que se ejecutó el proceso de elegibilidad.</span><span class="sxs-lookup"><span data-stu-id="d5a61-137">The time that the eligibility process was run.</span></span> |
   | <span data-ttu-id="d5a61-138">**Entidad jurídica**</span><span class="sxs-lookup"><span data-stu-id="d5a61-138">**Legal entity**</span></span> | <span data-ttu-id="d5a61-139">La entidad legal especificada durante el proceso de inscripción.</span><span class="sxs-lookup"><span data-stu-id="d5a61-139">The legal entity specified during the enrollment process.</span></span> |
   | <span data-ttu-id="d5a61-140">**Trabajador**</span><span class="sxs-lookup"><span data-stu-id="d5a61-140">**Worker**</span></span> | <span data-ttu-id="d5a61-141">El trabajador que se procesó.</span><span class="sxs-lookup"><span data-stu-id="d5a61-141">The worker who was processed.</span></span> |
   | <span data-ttu-id="d5a61-142">\*\*Plan</span><span class="sxs-lookup"><span data-stu-id="d5a61-142">\*\*Plan</span></span> | <span data-ttu-id="d5a61-143">El plan de prestaciones para el que se intentó la inscripción.</span><span class="sxs-lookup"><span data-stu-id="d5a61-143">The Benefit plan that enrollment was attempted for.</span></span> |
   | <span data-ttu-id="d5a61-144">**Regla de idoneidad**</span><span class="sxs-lookup"><span data-stu-id="d5a61-144">**Eligibility rule**</span></span> | <span data-ttu-id="d5a61-145">La regla de elegibilidad que se procesó.</span><span class="sxs-lookup"><span data-stu-id="d5a61-145">The eligibility rule that was processed.</span></span> <span data-ttu-id="d5a61-146">Si se encontró un error antes de ejecutar la elegibilidad, estará en blanco.</span><span class="sxs-lookup"><span data-stu-id="d5a61-146">If an error was encountered before eligibility was run, this will be blank.</span></span> <span data-ttu-id="d5a61-147">Por ejemplo: si no se ha definido la compensación para un trabajador, el proceso de elegibilidad no se ejecutará y este campo se dejará en blanco.</span><span class="sxs-lookup"><span data-stu-id="d5a61-147">For example: If compensation hasn't been defined for a worker, the eligibility process won't run, and this field will be left blank.</span></span> |
   | <span data-ttu-id="d5a61-148">**Estado de resultado**</span><span class="sxs-lookup"><span data-stu-id="d5a61-148">**Result status**</span></span> | <span data-ttu-id="d5a61-149">Esto será elegible o no elegible.</span><span class="sxs-lookup"><span data-stu-id="d5a61-149">This will be Eligible or Ineligible.</span></span> <span data-ttu-id="d5a61-150">El estado del resultado será No elegible si el trabajador no cumplió con los criterios de la regla de elegibilidad, si el trabajador no tiene la información requerida, como una frecuencia de pago o una compensación fija, o si falta información en el plan de prestaciones que impide que los trabajadores se inscriban.</span><span class="sxs-lookup"><span data-stu-id="d5a61-150">The result status will be Ineligible if the worker didn’t meet the eligibility rule criteria, if the worker is missing required information such as a pay frequency or fixed compensation, or if there is information missing on the benefit plan that prevents workers from being enrolled.</span></span> |
   | <span data-ttu-id="d5a61-151">**Mensaje de resultado**</span><span class="sxs-lookup"><span data-stu-id="d5a61-151">**Result message**</span></span> | <span data-ttu-id="d5a61-152">Indica por qué un trabajador no es elegible para un plan de prestaciones o si se aprobó la regla de elegibilidad.</span><span class="sxs-lookup"><span data-stu-id="d5a61-152">Indicates why a worker is ineligible for a benefit plan or if the eligibility rule passed.</span></span> |



[!INCLUDE[footer-include](../includes/footer-banner.md)]