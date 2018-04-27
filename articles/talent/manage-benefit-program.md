---
title: Definir y gestionar un programa de prestaciones
description: "Los Recursos humanos ofrecen una serie de herramientas que se pueden usar para configurar y mantener prestaciones, deducciones y los planes de compensación de los trabajadores que una organización ofrece o procesa para sus trabajadores. En este artículo se ofrece información acerca de cómo configurar y gestionar prestaciones."
author: kherr75
manager: AnnBe
ms.date: 11/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmBenefitEligibilityDetail, HcmBenefitSelection, SysPolicyListPage, SysPolicySourceDocumentRuleType
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent
ms.custom: 15681
ms.assetid: 6aee97ac-29f7-4b3c-8aa1-c65810de3090
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 7344fad7c4dffabd99993924604e2e497bebc5ef
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---

# <a name="define-and-manage-a-benefits-program"></a><span data-ttu-id="b95ee-104">Definir y gestionar un programa de prestaciones</span><span class="sxs-lookup"><span data-stu-id="b95ee-104">Define and manage a benefits program</span></span>

[!INCLUDE [banner](includes/banner.md)]

<span data-ttu-id="b95ee-105">Los Recursos humanos ofrecen una serie de herramientas que se pueden usar para configurar y mantener prestaciones, deducciones y los planes de compensación de los trabajadores que una organización ofrece o procesa para sus trabajadores.</span><span class="sxs-lookup"><span data-stu-id="b95ee-105">Human resources provides a set of tools that can be used to set up and maintain benefits, deductions, and workers' compensation plans that an organization offers or processes for its workers.</span></span> <span data-ttu-id="b95ee-106">En este tema se ofrece información acerca de cómo configurar y gestionar prestaciones.</span><span class="sxs-lookup"><span data-stu-id="b95ee-106">This topic provides information about how to set up and manage benefits.</span></span>

<a name="benefit-setup"></a><span data-ttu-id="b95ee-107">Configuración de prestaciones</span><span class="sxs-lookup"><span data-stu-id="b95ee-107">Benefit setup</span></span>
-------------

<span data-ttu-id="b95ee-108">Para que los trabajadores puedan inscribirse en prestaciones, debe crear los elementos de cada prestación.</span><span class="sxs-lookup"><span data-stu-id="b95ee-108">Before workers can be enrolled in benefits, you must create the elements of each benefit.</span></span> <span data-ttu-id="b95ee-109">Estos elementos combinan planes de prestaciones similares y definen la configuración predeterminada, como las tasas de deducción y los detalles de contabilidad.</span><span class="sxs-lookup"><span data-stu-id="b95ee-109">These elements combine similar benefit plans and define default settings, such as deduction rates and accounting details.</span></span> <span data-ttu-id="b95ee-110">Muchos de estos parámetros se pueden ajustar cuando los trabajadores se inscriben posteriormente en la prestación.</span><span class="sxs-lookup"><span data-stu-id="b95ee-110">Many of these settings can be adjusted when workers are later enrolled in the benefit.</span></span> <span data-ttu-id="b95ee-111">Para cada plan de prestaciones, una organización puede ofrecer varias opciones de inscripción o un trabajador puede condonar inscripción en el plan.</span><span class="sxs-lookup"><span data-stu-id="b95ee-111">For each benefit plan, an organization can offer several enrollment options, or a worker can waive enrollment in the plan.</span></span> 

<span data-ttu-id="b95ee-112">[![Flujo del proceso de prestaciones](./media/benefit-process-flow1.png)](./media/benefit-process-flow1.png)</span><span class="sxs-lookup"><span data-stu-id="b95ee-112">[![Benefit process flow](./media/benefit-process-flow1.png)](./media/benefit-process-flow1.png)</span></span>

## <a name="benefit-elements"></a><span data-ttu-id="b95ee-113">Elementos de prestación</span><span class="sxs-lookup"><span data-stu-id="b95ee-113">Benefit elements</span></span>
<span data-ttu-id="b95ee-114">Para poder comenzar a crear prestaciones e inscribir trabajadores en ellas, debe definir los elementos que componen una prestación: el tipo, el plan y las opciones.</span><span class="sxs-lookup"><span data-stu-id="b95ee-114">Before you begin to create to create benefits and enroll workers in them, you must define the elements that make up a benefit: the type, plan, and options.</span></span>

-   <span data-ttu-id="b95ee-115">**Tipo**: un conjunto de planes de una prestación determinada, como cobertura médica o estacionamiento pagado.</span><span class="sxs-lookup"><span data-stu-id="b95ee-115">**Type** – A collection of plans for a specific benefit, such as medical or parking.</span></span>
-   <span data-ttu-id="b95ee-116">**Plan**: una prestación concreta contratada a un proveedor.</span><span class="sxs-lookup"><span data-stu-id="b95ee-116">**Plan** – A specific benefit that is contracted from a provider.</span></span>
-   <span data-ttu-id="b95ee-117">**Opción**: el nivel de cobertura, como empleado sólo o como empleado y cónyuge/pareja.</span><span class="sxs-lookup"><span data-stu-id="b95ee-117">**Option** – The coverage level, such as employee only, or employee and spouse/partner.</span></span>

<span data-ttu-id="b95ee-118">Para cada tipo de prestación, como de visión o dental, una organización puede ofrecer uno o varios planes a sus trabajadores.</span><span class="sxs-lookup"><span data-stu-id="b95ee-118">For each type of benefit, such as vision or dental, an organization can offer one or more plans to its workers.</span></span> <span data-ttu-id="b95ee-119">Para cada plan, la organización puede ofrecer diferentes opciones.</span><span class="sxs-lookup"><span data-stu-id="b95ee-119">For each plan, the organization can offer different options.</span></span> <span data-ttu-id="b95ee-120">Por ejemplo, los trabajadores pueden comprar cobertura adicional de seguro de vida a término una, dos o tres veces su sueldo anual.</span><span class="sxs-lookup"><span data-stu-id="b95ee-120">For example, workers can buy additional term life insurance coverage at one, two, or three times their yearly salary.</span></span> <span data-ttu-id="b95ee-121">Cada combinación de un plan y de opciones se convierte en una prestación en la que los trabajadores pueden inscribirse.</span><span class="sxs-lookup"><span data-stu-id="b95ee-121">Each combination of a plan and options becomes a benefit that workers can enroll in.</span></span> 

<span data-ttu-id="b95ee-122">[![imagen de prestación](./media/benefit-pic.png)](./media/benefit-pic.png)</span><span class="sxs-lookup"><span data-stu-id="b95ee-122">[![benefit pic](./media/benefit-pic.png)](./media/benefit-pic.png)</span></span>

## <a name="eligibility"></a><span data-ttu-id="b95ee-123">Idoneidad</span><span class="sxs-lookup"><span data-stu-id="b95ee-123">Eligibility</span></span>
<span data-ttu-id="b95ee-124">Muchos factores determinan la idoneidad del trabajador para los distintos tipos de prestaciones que el empleador ofrece.</span><span class="sxs-lookup"><span data-stu-id="b95ee-124">Many factors determine worker eligibility for the various types of benefits that an employer offers.</span></span> <span data-ttu-id="b95ee-125">Al crear una prestación en Microsoft Dynamics Talent, puede establecer el tipo de idoneidad que se aplica a dicha prestación.</span><span class="sxs-lookup"><span data-stu-id="b95ee-125">When you create a benefit in Microsoft Talent, you can set the type of eligibility that applies to that benefit.</span></span> 

<span data-ttu-id="b95ee-126">Puede hacer que una prestación esté disponible para todos los trabajadores.</span><span class="sxs-lookup"><span data-stu-id="b95ee-126">You can make a benefit available to all workers.</span></span> <span data-ttu-id="b95ee-127">Por ejemplo, algunas empresas ofrecen pases de aparcamiento para todos los empleados como beneficio complementario.</span><span class="sxs-lookup"><span data-stu-id="b95ee-127">For example, some companies offer parking passes to all employees as a fringe benefit.</span></span> <span data-ttu-id="b95ee-128">Cuando crea esta prestación, establece la idoneidad en **Todos los trabajadores son aptos**.</span><span class="sxs-lookup"><span data-stu-id="b95ee-128">When you create this benefit, you set the eligibility to **All workers are eligible**.</span></span> 

<span data-ttu-id="b95ee-129">Para otras prestaciones, como embargos y recaudaciones de impuestos, no se aplica la idoneidad.</span><span class="sxs-lookup"><span data-stu-id="b95ee-129">For other benefits, such as garnishments and tax levies, eligibility doesn't apply.</span></span> <span data-ttu-id="b95ee-130">Al crear estos tipos de prestaciones, establece la idoneidad en **Omitir proceso de idoneidad**.</span><span class="sxs-lookup"><span data-stu-id="b95ee-130">Whey you create these types of benefits, you set the eligibility to **Bypass eligibility process**.</span></span> 

<span data-ttu-id="b95ee-131">Por último, la idoneidad de la prestación puede estar basada en reglas.</span><span class="sxs-lookup"><span data-stu-id="b95ee-131">Finally, benefit eligibility can be rule-based.</span></span> <span data-ttu-id="b95ee-132">Por ejemplo, una empresa ofrece dos tipos de prestación de seguro de vida a los empleados.</span><span class="sxs-lookup"><span data-stu-id="b95ee-132">For example, a company offers two types of life insurance benefit to employees.</span></span> <span data-ttu-id="b95ee-133">Los empleados ejecutivos son aptos para un plan de seguro de vida, mientras que los demás empleados a jornada completa son aptos para el otro plan de seguro de vida.</span><span class="sxs-lookup"><span data-stu-id="b95ee-133">Executive employees are eligible for one life insurance plan, whereas all other full-time employees are eligible for the other life insurance plan.</span></span> <span data-ttu-id="b95ee-134">En Talent, puede crear una regla de idoneidad de prestación para encontrar todos los empleados ejecutivos y otra regla para buscar todos los demás empleados a jornada completa y después aplicar esas reglas a la prestación adecuada.</span><span class="sxs-lookup"><span data-stu-id="b95ee-134">In Talent, you can create a benefit eligibility rule to find all executive employees and another rule to find all other full-time employees, and then apply those rules to the appropriate benefit.</span></span>

## <a name="enrollment"></a><span data-ttu-id="b95ee-135">Inscripción</span><span class="sxs-lookup"><span data-stu-id="b95ee-135">Enrollment</span></span>
<span data-ttu-id="b95ee-136">Una vez que haya creado las prestaciones que su organización ofrece y la idoneidad determinada, puede inscribir a sus trabajadores en prestaciones.</span><span class="sxs-lookup"><span data-stu-id="b95ee-136">After you've created the benefits that your organization offers and determined eligibility, you can enroll your workers in benefits.</span></span> <span data-ttu-id="b95ee-137">Puede inscribir a un único trabajador en prestaciones o bien, puede inscribir varios trabajadores en una o más prestaciones durante un proceso único.</span><span class="sxs-lookup"><span data-stu-id="b95ee-137">You can enroll a single worker in benefits, or you can enroll many workers in one or more benefits during a single process.</span></span> 

<span data-ttu-id="b95ee-138">A veces, una organización deja de ofrecer determinadas prestaciones.</span><span class="sxs-lookup"><span data-stu-id="b95ee-138">Sometimes, an organization stops offering certain benefits.</span></span> <span data-ttu-id="b95ee-139">En este caso, debe actualizar la prestación y los trabajadores que están inscritos en ella.</span><span class="sxs-lookup"><span data-stu-id="b95ee-139">In this case, you must update the benefit and the workers who are enrolled in.</span></span> <span data-ttu-id="b95ee-140">La expiración de prestación masiva le permite cambiar la fecha de vencimiento tanto de una prestación como las inscripciones de trabajador para esa prestación al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="b95ee-140">Mass benefit expiration lets you change the expiration date of both a benefit and the worker enrollments for that benefit at the same time.</span></span> <span data-ttu-id="b95ee-141">También puede seleccionar varios trabajadores inscritos en una prestación y cambiar la fecha final de cobertura.</span><span class="sxs-lookup"><span data-stu-id="b95ee-141">You can also select multiple workers who are enrolled in a benefit and change the ending date of their coverage.</span></span> 

<span data-ttu-id="b95ee-142">Del mismo modo, la extensión total de la prestación le permite ampliar la fecha de vencimiento tanto de una prestación como las inscripciones de trabajador para dicha prestación si decide ofrecer una prestación más tiempo de lo que planeó originalmente.</span><span class="sxs-lookup"><span data-stu-id="b95ee-142">Similarly, mass benefit extension lets you extend the expiration date of both a benefit and the worker enrollments for that benefit if you decide to offer a benefit longer than you originally planned.</span></span>

<a name="see-also"></a><span data-ttu-id="b95ee-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b95ee-143">See also</span></span>
--------

[<span data-ttu-id="b95ee-144">Directivas de idoneidad para beneficio</span><span class="sxs-lookup"><span data-stu-id="b95ee-144">Benefit eligibility policies</span></span>](benefit-eligibility-policies.md)




