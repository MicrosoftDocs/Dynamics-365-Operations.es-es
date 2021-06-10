---
title: Procesar eventos de vida
description: Durante el ciclo de vida de los empleados en Microsoft Dynamics 365 Human Resources, cada empleado puede sufrir varios cambios en los eventos de la vida.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes, BenefitEligibilityProcessResultViewer
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: beac0d6666055a278cab0be9080e49c51885671d
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6057823"
---
# <a name="process-life-events"></a><span data-ttu-id="8b8fd-103">Procesar eventos de vida</span><span class="sxs-lookup"><span data-stu-id="8b8fd-103">Process life events</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="8b8fd-104">Durante el ciclo de vida de los empleados en Microsoft Dynamics 365 Human Resources, cada empleado puede sufrir varios cambios en los eventos de la vida.</span><span class="sxs-lookup"><span data-stu-id="8b8fd-104">During the employee lifecycle in Microsoft Dynamics 365 Human Resources, each employee may encounter various life event changes.</span></span> <span data-ttu-id="8b8fd-105">Por ejemplo, matrimonio, cambio de empleo o cambio de dependiente/beneficiario.</span><span class="sxs-lookup"><span data-stu-id="8b8fd-105">For example, marriage, change in employment, or dependent/beneficiary change.</span></span> <span data-ttu-id="8b8fd-106">Para usar eventos de vida, debe habilitar los eventos de vida en el formulario de parámetros de prestaciones, configurar los tipos de eventos de vida y configurar opciones de eventos de vida para tipos de planes.</span><span class="sxs-lookup"><span data-stu-id="8b8fd-106">To use life events, you must enable life events in the benefits parameters form, set up life event types, and set up life event options for plan types.</span></span>

<span data-ttu-id="8b8fd-107">Antes de poder procesar eventos de vida, ya debe haber ejecutado la inscripción abierta al menos una vez durante un periodo de contratación.</span><span class="sxs-lookup"><span data-stu-id="8b8fd-107">Before you can process life events, you must have already run open enrollment at least once during a hiring time frame.</span></span> <span data-ttu-id="8b8fd-108">En los Estados Unidos, la inscripción abierta suele ser una vez al año.</span><span class="sxs-lookup"><span data-stu-id="8b8fd-108">In the United States, open enrollment is typically once per year.</span></span> <span data-ttu-id="8b8fd-109">Fuera de los Estados Unidos, la inscripción abierta puede realizarse al momento de la contratación.</span><span class="sxs-lookup"><span data-stu-id="8b8fd-109">Outside the United States, open enrollment may be run at the time of hire.</span></span> <span data-ttu-id="8b8fd-110">Un trabajador no necesita seleccionar un plan de prestaciones para que se procesen los eventos de la vida, pero debe haber sido incluido en el proceso de inscripción abierta.</span><span class="sxs-lookup"><span data-stu-id="8b8fd-110">A worker does not need to select a benefit plan in order for life events to be processed, but they need to have been included in open enrollment processing.</span></span> 

<span data-ttu-id="8b8fd-111">Utilice el procesamiento de eventos de vida cuando haya trabajadores que tengan eventos de la vida que tengan lugar en una fecha futura.</span><span class="sxs-lookup"><span data-stu-id="8b8fd-111">Use life event processing when you have workers who have life events that take place on a future date.</span></span> <span data-ttu-id="8b8fd-112">Este evento procesará todos los eventos de la vida que no se hayan procesado (como eventos de vida futuros o eventos de vida que se hayan agregado que no son específicos de ningún trabajador, por ejemplo, una nueva prestación).</span><span class="sxs-lookup"><span data-stu-id="8b8fd-112">This event will process all life events that have not been processed (like future life events, or life events that have been added that are not specific to any one worker – one example is a new benefit).</span></span> <span data-ttu-id="8b8fd-113">Los eventos de vida en tiempo real están ocultos.</span><span class="sxs-lookup"><span data-stu-id="8b8fd-113">Real-time life events are hidden.</span></span>

<span data-ttu-id="8b8fd-114">Por ejemplo, si hoy es 1 de febrero y está programado que el 14 de febrero el trabajador Joe Smith cambie de entidad jurídica, si ejecuta el procesamiento de eventos de vida para el 15 de febrero, el sistema procesa todos los eventos hasta el 15 de febrero.</span><span class="sxs-lookup"><span data-stu-id="8b8fd-114">For example, if today is February 1, and on February 14 worker Joe Smith is scheduled to change legal entities, if you run life event processing for February 15, the system processes all events up until February 15.</span></span> 

1. <span data-ttu-id="8b8fd-115">En el espacio de trabajo **Administración de prestaciones**, en **Procesamiento**, seleccione **Procesamiento de eventos de vida**.</span><span class="sxs-lookup"><span data-stu-id="8b8fd-115">In the **Benefits management** workspace, under **Processing**, select **Life event processing**.</span></span>

2. <span data-ttu-id="8b8fd-116">En el cuadro de diálogo **Ejecutar proceso de evento de vida**, especifique valores para los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="8b8fd-116">In the **Run life event process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="8b8fd-117">Campo</span><span class="sxs-lookup"><span data-stu-id="8b8fd-117">Field</span></span> | <span data-ttu-id="8b8fd-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="8b8fd-118">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="8b8fd-119">**Período de inscripción**</span><span class="sxs-lookup"><span data-stu-id="8b8fd-119">**Enrollment period**</span></span> | <span data-ttu-id="8b8fd-120">El periodo de inscripción para procesar eventos de vida.</span><span class="sxs-lookup"><span data-stu-id="8b8fd-120">The enrollment period to process life events for.</span></span> |
   | <span data-ttu-id="8b8fd-121">**Entidad jurídica**</span><span class="sxs-lookup"><span data-stu-id="8b8fd-121">**Legal entity**</span></span> | <span data-ttu-id="8b8fd-122">La entidad jurídica para procesar eventos de vida.</span><span class="sxs-lookup"><span data-stu-id="8b8fd-122">The legal entity to process life events for.</span></span> |
   | <span data-ttu-id="8b8fd-123">**Fecha de evento de vida**</span><span class="sxs-lookup"><span data-stu-id="8b8fd-123">**Life event date**</span></span> | <span data-ttu-id="8b8fd-124">El sistema procesa todos los eventos durante el periodo de inscripción que ocurren hasta esta fecha.</span><span class="sxs-lookup"><span data-stu-id="8b8fd-124">The system processes all events during the enrollment period that occur up until this date.</span></span> |
   | <span data-ttu-id="8b8fd-125">**Trabajador**</span><span class="sxs-lookup"><span data-stu-id="8b8fd-125">**Worker**</span></span> | <span data-ttu-id="8b8fd-126">El trabajador para procesar eventos de vida.</span><span class="sxs-lookup"><span data-stu-id="8b8fd-126">The worker to process life events for.</span></span> <span data-ttu-id="8b8fd-127">Si deja este campo en blanco, los eventos de vida se procesarán para todos los trabajadores.</span><span class="sxs-lookup"><span data-stu-id="8b8fd-127">If you leave this field blank, life events will be processed for all workers.</span></span> |

3. <span data-ttu-id="8b8fd-128">Si desea ejecutar el proceso en segundo plano, seleccione **Ejecutar en segundo plano** y realice las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="8b8fd-128">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="8b8fd-129">Escriba información para proceso.</span><span class="sxs-lookup"><span data-stu-id="8b8fd-129">Enter information for the process.</span></span>

   2. <span data-ttu-id="8b8fd-130">Para configurar un trabajo periódico, seleccione **Periodicidad**, introduzca la información de periodicidad y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8b8fd-130">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="8b8fd-131">Para configurar una alerta de trabajo, seleccione **Alertas**, seleccione las alertas que quiera recibir y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8b8fd-131">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="8b8fd-132">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8b8fd-132">Select **OK**.</span></span> <span data-ttu-id="8b8fd-133">El proceso se ejecutará con los parámetros que establezca.</span><span class="sxs-lookup"><span data-stu-id="8b8fd-133">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="8b8fd-134">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8b8fd-134">Select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]