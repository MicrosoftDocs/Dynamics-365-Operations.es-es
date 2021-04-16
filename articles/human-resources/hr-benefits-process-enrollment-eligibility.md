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
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f9b1febe2690fab17586033994b10ebf260630af
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5805715"
---
# <a name="process-enrollment-eligibility"></a><span data-ttu-id="9317f-103">Proceso de idoneidad para inscripción</span><span class="sxs-lookup"><span data-stu-id="9317f-103">Process enrollment eligibility</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="9317f-104">Este artículo explica cómo ejecutar el proceso de idoneidad de inscripción.</span><span class="sxs-lookup"><span data-stu-id="9317f-104">This article explains how to run the enrollment eligibility process.</span></span>

1. <span data-ttu-id="9317f-105">En el espacio de trabajo **Administración de prestaciones**, en **Procesamiento**, seleccione **Procesamiento de idoneidad para inscripción**.</span><span class="sxs-lookup"><span data-stu-id="9317f-105">In the **Benefits management** workspace, under **Processing**, select **Enrollment eligibility processing**.</span></span>

2. <span data-ttu-id="9317f-106">En el cuadro de diálogo **Ejecutar proceso de idoneidad para la inscripción en prestaciones**, especifique valores para los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="9317f-106">In the **Run benefit enrollment eligibility process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="9317f-107">Campo</span><span class="sxs-lookup"><span data-stu-id="9317f-107">Field</span></span> | <span data-ttu-id="9317f-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="9317f-108">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="9317f-109">**Período de inscripción**</span><span class="sxs-lookup"><span data-stu-id="9317f-109">**Enrollment period**</span></span> | <span data-ttu-id="9317f-110">El periodo de inscripción para procesar la idoneidad de inscripción.</span><span class="sxs-lookup"><span data-stu-id="9317f-110">The enrollment period to process enrollment eligibility for.</span></span> |
   | <span data-ttu-id="9317f-111">**Entidad jurídica**</span><span class="sxs-lookup"><span data-stu-id="9317f-111">**Legal entity**</span></span> | <span data-ttu-id="9317f-112">La entidad jurídica para procesar la idoneidad de inscripción.</span><span class="sxs-lookup"><span data-stu-id="9317f-112">The legal entity to process enrollment eligibility for.</span></span> |
   | <span data-ttu-id="9317f-113">**Trabajador**</span><span class="sxs-lookup"><span data-stu-id="9317f-113">**Worker**</span></span> | <span data-ttu-id="9317f-114">El trabajador para procesar la idoneidad de inscripción.</span><span class="sxs-lookup"><span data-stu-id="9317f-114">The worker to process enrollment eligibility for.</span></span> <span data-ttu-id="9317f-115">Si deja este campo en blanco, la idoneidad de inscripción se procesará para todos los trabajadores.</span><span class="sxs-lookup"><span data-stu-id="9317f-115">If you leave this field blank, enrollment eligibility will be processed for all workers.</span></span> |
   | <span data-ttu-id="9317f-116">**Plan de beneficios**</span><span class="sxs-lookup"><span data-stu-id="9317f-116">**Benefit plan**</span></span> | <span data-ttu-id="9317f-117">El plan de prestaciones para procesar la idoneidad de inscripción.</span><span class="sxs-lookup"><span data-stu-id="9317f-117">The benefit plan to process enrollment eligibility for.</span></span>

3. <span data-ttu-id="9317f-118">Si desea ejecutar el proceso en segundo plano, seleccione **Ejecutar en segundo plano** y realice las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="9317f-118">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="9317f-119">Escriba información para proceso.</span><span class="sxs-lookup"><span data-stu-id="9317f-119">Enter information for the process.</span></span>

   2. <span data-ttu-id="9317f-120">Para configurar un trabajo periódico, seleccione **Periodicidad**, introduzca la información de periodicidad y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9317f-120">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="9317f-121">Para configurar una alerta de trabajo, seleccione **Alertas**, seleccione las alertas que quiera recibir y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9317f-121">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="9317f-122">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9317f-122">Select **OK**.</span></span> <span data-ttu-id="9317f-123">El proceso se ejecutará con los parámetros que establezca.</span><span class="sxs-lookup"><span data-stu-id="9317f-123">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="9317f-124">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9317f-124">Select **OK**.</span></span>

## <a name="view-process-results"></a><span data-ttu-id="9317f-125">Ver resultados de proceso</span><span class="sxs-lookup"><span data-stu-id="9317f-125">View Process Results</span></span>

<span data-ttu-id="9317f-126">Este artículo explica cómo ver los resultados del proceso de idoneidad.</span><span class="sxs-lookup"><span data-stu-id="9317f-126">This article explains how to view eligibility process results.</span></span>

1.  <span data-ttu-id="9317f-127">En el espacio de trabajo **Administración de prestaciones**, en **Procesamiento**, seleccione **Procesar resultados**.</span><span class="sxs-lookup"><span data-stu-id="9317f-127">In the **Benefits management** workspace, under **Processing**, select **Process results**.</span></span>

2.  <span data-ttu-id="9317f-128">En el formulario **Procesar resultados**, se especifican los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="9317f-128">In the **Process results** form, the following fields are specified:</span></span>

   | <span data-ttu-id="9317f-129">Campo</span><span class="sxs-lookup"><span data-stu-id="9317f-129">Field</span></span> | <span data-ttu-id="9317f-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="9317f-130">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="9317f-131">**Id. de proceso**</span><span class="sxs-lookup"><span data-stu-id="9317f-131">**Process ID**</span></span> | <span data-ttu-id="9317f-132">El Id. único para la combinación de trabajador, entidad jurídica y ejecución del proceso.</span><span class="sxs-lookup"><span data-stu-id="9317f-132">The unique ID for the combination of Worker, Legal entity, and process run.</span></span> |
   | <span data-ttu-id="9317f-133">**Tipo de proceso**</span><span class="sxs-lookup"><span data-stu-id="9317f-133">**Process type**</span></span> | <span data-ttu-id="9317f-134">Esto identifica el proceso que se ejecutó.</span><span class="sxs-lookup"><span data-stu-id="9317f-134">This identifies the process that was run.</span></span> <span data-ttu-id="9317f-135">Por ejemplo: Inscripción.</span><span class="sxs-lookup"><span data-stu-id="9317f-135">For example:  Enrollment.</span></span> |
   | <span data-ttu-id="9317f-136">**Marca de tiempo**</span><span class="sxs-lookup"><span data-stu-id="9317f-136">**Time stamp**</span></span> | <span data-ttu-id="9317f-137">La hora en que se ejecutó el proceso de elegibilidad.</span><span class="sxs-lookup"><span data-stu-id="9317f-137">The time that the eligibility process was run.</span></span> |
   | <span data-ttu-id="9317f-138">**Entidad jurídica**</span><span class="sxs-lookup"><span data-stu-id="9317f-138">**Legal entity**</span></span> | <span data-ttu-id="9317f-139">La entidad legal especificada durante el proceso de inscripción.</span><span class="sxs-lookup"><span data-stu-id="9317f-139">The legal entity specified during the enrollment process.</span></span> |
   | <span data-ttu-id="9317f-140">**Trabajador**</span><span class="sxs-lookup"><span data-stu-id="9317f-140">**Worker**</span></span> | <span data-ttu-id="9317f-141">El trabajador que se procesó.</span><span class="sxs-lookup"><span data-stu-id="9317f-141">The worker who was processed.</span></span> |
   | <span data-ttu-id="9317f-142">\*\*Plan</span><span class="sxs-lookup"><span data-stu-id="9317f-142">\*\*Plan</span></span> | <span data-ttu-id="9317f-143">El plan de prestaciones para el que se intentó la inscripción.</span><span class="sxs-lookup"><span data-stu-id="9317f-143">The Benefit plan that enrollment was attempted for.</span></span> |
   | <span data-ttu-id="9317f-144">**Regla de idoneidad**</span><span class="sxs-lookup"><span data-stu-id="9317f-144">**Eligibility rule**</span></span> | <span data-ttu-id="9317f-145">La regla de elegibilidad que se procesó.</span><span class="sxs-lookup"><span data-stu-id="9317f-145">The eligibility rule that was processed.</span></span> <span data-ttu-id="9317f-146">Si se encontró un error antes de ejecutar la elegibilidad, estará en blanco.</span><span class="sxs-lookup"><span data-stu-id="9317f-146">If an error was encountered before eligibility was run, this will be blank.</span></span> <span data-ttu-id="9317f-147">Por ejemplo: si no se ha definido la compensación para un trabajador, el proceso de elegibilidad no se ejecutará y este campo se dejará en blanco.</span><span class="sxs-lookup"><span data-stu-id="9317f-147">For example: If compensation hasn't been defined for a worker, the eligibility process won't run, and this field will be left blank.</span></span> |
   | <span data-ttu-id="9317f-148">**Estado de resultado**</span><span class="sxs-lookup"><span data-stu-id="9317f-148">**Result status**</span></span> | <span data-ttu-id="9317f-149">Esto será elegible o no elegible.</span><span class="sxs-lookup"><span data-stu-id="9317f-149">This will be Eligible or Ineligible.</span></span> <span data-ttu-id="9317f-150">El estado del resultado será No elegible si el trabajador no cumplió con los criterios de la regla de elegibilidad, si el trabajador no tiene la información requerida, como una frecuencia de pago o una compensación fija, o si falta información en el plan de prestaciones que impide que los trabajadores se inscriban.</span><span class="sxs-lookup"><span data-stu-id="9317f-150">The result status will be Ineligible if the worker didn’t meet the eligibility rule criteria, if the worker is missing required information such as a pay frequency or fixed compensation, or if there is information missing on the benefit plan that prevents workers from being enrolled.</span></span> |
   | <span data-ttu-id="9317f-151">**Mensaje de resultado**</span><span class="sxs-lookup"><span data-stu-id="9317f-151">**Result message**</span></span> | <span data-ttu-id="9317f-152">Indica por qué un trabajador no es elegible para un plan de prestaciones o si se aprobó la regla de elegibilidad.</span><span class="sxs-lookup"><span data-stu-id="9317f-152">Indicates why a worker is ineligible for a benefit plan or if the eligibility rule passed.</span></span> |



[!INCLUDE[footer-include](../includes/footer-banner.md)]