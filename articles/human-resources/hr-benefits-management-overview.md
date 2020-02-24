---
title: Visión general de la administración de prestaciones
description: Visión general de la característica de vista previa de administración de prestaciones en Dynamics 365 Human Resources. Ofrezca a sus empleados opciones de prestaciones ampliadas con una experiencia en línea fácil de usar.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 63db1b55bae9150dd87d9981136b96d72ffd0c59
ms.sourcegitcommit: 523049c363a999050c58d20695f1c7d151b3fd3e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029472"
---
# <a name="benefits-management-overview"></a><span data-ttu-id="8b090-104">Visión general de la administración de prestaciones</span><span class="sxs-lookup"><span data-stu-id="8b090-104">Benefits management overview</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="8b090-105">Para seguir siendo competitivo, debe ofrecer un amplio conjunto de prestaciones para atraer y retener a sus mejores empleados.</span><span class="sxs-lookup"><span data-stu-id="8b090-105">To remain competitive, you must offer a rich set of benefits to attract and retain your best employees.</span></span> <span data-ttu-id="8b090-106">Además de las prestaciones estándar como la cobertura médica y dental, es posible que también quiera ofrecer servicios ampliados como asistencia de adopción, programas de recreación y asignaciones de ropa.</span><span class="sxs-lookup"><span data-stu-id="8b090-106">In addition to standard benefits like medical and dental coverage, you might also want to offer expanded services like adoption assistance, recreation programs, and clothing allowances.</span></span> <span data-ttu-id="8b090-107">La característica de vista previa de administración de prestaciones en Microsoft Dynamics 365 Human Resources le brinda una solución flexible que admite una amplia variedad de opciones de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="8b090-107">The Benefits management preview feature in Microsoft Dynamics 365 Human Resources provides you with a flexible solution that supports a wide variety of benefit options.</span></span> <span data-ttu-id="8b090-108">Recursos humanos también incluye una experiencia fácil de usar para los empleados que muestra sus ofertas.</span><span class="sxs-lookup"><span data-stu-id="8b090-108">Human Resources also includes an easy-to-use employee experience that showcases your offerings.</span></span>

- <span data-ttu-id="8b090-109">Los planes de prestaciones mejoradas le permiten crear y administrar planes de prestaciones únicas y admitir tablas complejas de tasas de prestaciones y niveles anidados.</span><span class="sxs-lookup"><span data-stu-id="8b090-109">Enhanced benefits plans let you create and manage unique benefit plans and support complex benefit rate tables and nested tiers.</span></span> <span data-ttu-id="8b090-110">Puede crear fácilmente programas de beneficios, agrupaciones y reglas de inscripción automática para una experiencia más fácil para los empleados.</span><span class="sxs-lookup"><span data-stu-id="8b090-110">You can easily create benefit programs, bundles, and auto-enrollment rules for an easier employee experience.</span></span>

- <span data-ttu-id="8b090-111">Los programas de crédito flexible le permiten prorratear para asistir en la jubilación y otros eventos de la vida.</span><span class="sxs-lookup"><span data-stu-id="8b090-111">Flex credit programs let you prorate to support retirement and other life events.</span></span>

- <span data-ttu-id="8b090-112">Las extensas reglas de idoneidad garantizan que las prestaciones adecuadas estén disponibles para los empleados correctos.</span><span class="sxs-lookup"><span data-stu-id="8b090-112">Extensive eligibility rules ensure you make the right benefits available to the right employees.</span></span>

- <span data-ttu-id="8b090-113">La inscripción de prestaciones en línea ofrece una experiencia fácil para sus empleados.</span><span class="sxs-lookup"><span data-stu-id="8b090-113">Online benefits enrollment provides an easy experience for your employees.</span></span>

- <span data-ttu-id="8b090-114">El procesamiento calificado de eventos de vida se integra con el autoservicio de los empleados y también es compatible con eventos de vida futuros.</span><span class="sxs-lookup"><span data-stu-id="8b090-114">Qualified life event processing integrates with Employee self service, and also supports future life events.</span></span>

<span data-ttu-id="8b090-115">Si desea acceder a los datos de demostración, deberá volver a implementar su entorno de espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="8b090-115">If you would like to access the demo data, you'll need to redeploy your sandbox environment.</span></span>

<span data-ttu-id="8b090-116">Puede proporcionar comentarios directos o informar sobre problemas a: D365BenefitsPreview@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="8b090-116">You can provide direct feedback or report issues to:  D365BenefitsPreview@microsoft.com.</span></span>

## <a name="benefits-management-known-issues"></a><span data-ttu-id="8b090-117">Problemas conocidos de la gestión de beneficios</span><span class="sxs-lookup"><span data-stu-id="8b090-117">Benefits management known issues</span></span>

### <a name="eligibility-processing"></a><span data-ttu-id="8b090-118">Procesamiento de idoneidad</span><span class="sxs-lookup"><span data-stu-id="8b090-118">Eligibility processing</span></span>

<span data-ttu-id="8b090-119">Al ejecutar la idoneidad para las prestaciones que usan un importe de cobertura de salario a 1-5X, % de salario e importe fijo, debe establecer la fecha de **Detalles de la prestación** para la **Fecha inicial del empleado** en **Historial del empleo**.</span><span class="sxs-lookup"><span data-stu-id="8b090-119">When running eligibility for benefits that use a 1-5X Salary, % of Salary, and Flat Amount coverage amount, you must set the **Benefit details** date to the **Employee start date** in **Employment history**.</span></span> <span data-ttu-id="8b090-120">También debe incluir **Horas trabajadas**, **Frecuencia de pago** y **Importe del salario de prestaciones anual**.</span><span class="sxs-lookup"><span data-stu-id="8b090-120">You must also include **Hours worked**, **Payment frequency**, and **Annual benefits salary amount**.</span></span> <span data-ttu-id="8b090-121">Si el trabajador tiene una compensación fija, introduzca **Horas trabajadas** y **Frecuencia de pago**.</span><span class="sxs-lookup"><span data-stu-id="8b090-121">If the worker has fixed compensation, enter **Hours worked** and **Payment frequency**.</span></span> <span data-ttu-id="8b090-122">Se calculará el importe del salario anual.</span><span class="sxs-lookup"><span data-stu-id="8b090-122">The annual salary amount will calculate.</span></span> <span data-ttu-id="8b090-123">Si el empleado es asalariado, no necesita introducir **Horas trabajadas**.</span><span class="sxs-lookup"><span data-stu-id="8b090-123">If the employee is salaried, you don't need to enter **Hours worked**.</span></span> <span data-ttu-id="8b090-124">Recomendamos que al crear nuevos trabajadores, ingrese primero una compensación fija.</span><span class="sxs-lookup"><span data-stu-id="8b090-124">We recommend that when creating new workers, enter fixed compensation first.</span></span> <span data-ttu-id="8b090-125">Para actualizar el registro de detalles de prestaciones, vaya a **Trabajador > Historial del trabajador > Detalles del empleo**.</span><span class="sxs-lookup"><span data-stu-id="8b090-125">To update the benefit details record, navigate to **Worker > Worker history > Employment details**.</span></span> <span data-ttu-id="8b090-126">Ajuste la fecha a la fecha inicial del empleado.</span><span class="sxs-lookup"><span data-stu-id="8b090-126">Adjust the date to the worker's start date.</span></span>

### <a name="employee-self-service"></a><span data-ttu-id="8b090-127">Autoservicio para empleados</span><span class="sxs-lookup"><span data-stu-id="8b090-127">Employee self-service</span></span>

<span data-ttu-id="8b090-128">El importe del empleado no se calcula al actualizar el importe de la cobertura del seguro de vida.</span><span class="sxs-lookup"><span data-stu-id="8b090-128">Employee amount doesn't calculate when updating the coverage amount for life insurance.</span></span> <span data-ttu-id="8b090-129">Por ejemplo, cuando a un empleado se le ofrece un plan de seguro de vida, puede seleccionar hasta 50 000 USD en cobertura a un costo de 0,36 USD por 1000 USD de cobertura.</span><span class="sxs-lookup"><span data-stu-id="8b090-129">For example, when an employee is offered a life insurance plan, they can select up to $50,000 in coverage at a cost of $.36 per $1,000 of coverage.</span></span>  <span data-ttu-id="8b090-130">Cuando el empleado actualiza el monto de la cobertura, el costo asociado del empleado permanece en cero.</span><span class="sxs-lookup"><span data-stu-id="8b090-130">When the employee updates the coverage amount, the employee’s associated cost remains at zero.</span></span>

<span data-ttu-id="8b090-131">Para un plan de prestaciones que solo permite una única selección de ese tipo de plan, el usuario recibe un error si intenta renunciar a un plan después de seleccionarlo.</span><span class="sxs-lookup"><span data-stu-id="8b090-131">For a benefit plan that only allows a single selection of that plan type, the user receives an error if they attempt to waive a plan after selecting a plan.</span></span> <span data-ttu-id="8b090-132">Por ejemplo, un usuario selecciona un plan médico y lo coloca en su carrito.</span><span class="sxs-lookup"><span data-stu-id="8b090-132">For example, a user selects a medical plan and places it in their cart.</span></span> <span data-ttu-id="8b090-133">El usuario luego selecciona **Renunciar** para otro plan médico</span><span class="sxs-lookup"><span data-stu-id="8b090-133">The user then selects **Waive** for another medical plan.</span></span> <span data-ttu-id="8b090-134">El usuario recibirá un error.</span><span class="sxs-lookup"><span data-stu-id="8b090-134">The user will receive an error.</span></span>

## <a name="enable-benefits-management"></a><span data-ttu-id="8b090-135">Habilitar la administración de prestaciones</span><span class="sxs-lookup"><span data-stu-id="8b090-135">Enable Benefits management</span></span>

<span data-ttu-id="8b090-136">La administración de prestaciones es una característica de vista previa y solo está disponible en entornos de **Espacio abierto**.</span><span class="sxs-lookup"><span data-stu-id="8b090-136">Benefits management is a preview feature, and is only available in **Sandbox** environments.</span></span> <span data-ttu-id="8b090-137">Estos artículos describen cómo activar las características de vista previa en Recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="8b090-137">These articles describe how to turn on preview features in Human Resources.</span></span> <span data-ttu-id="8b090-138">También le indican qué características existentes en Recursos humanos reemplazan o deshabilitan la administración de prestaciones una vez que activa la administración de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="8b090-138">They also tell which existing features in Human Resources that Benefits management replaces or are disabled once you turn on Benefits management.</span></span>

- [<span data-ttu-id="8b090-139">Administrar características</span><span class="sxs-lookup"><span data-stu-id="8b090-139">Manage features</span></span>](hr-admin-manage-features.md)
- [<span data-ttu-id="8b090-140">Característica de vista previa: administración de prestaciones</span><span class="sxs-lookup"><span data-stu-id="8b090-140">Preview feature: Benefits management</span></span>](hr-admin-manage-features.md?preview-feature-benefits-management)

## <a name="configure-benefits-management"></a><span data-ttu-id="8b090-141">Configurar la administración de prestaciones</span><span class="sxs-lookup"><span data-stu-id="8b090-141">Configure Benefits management</span></span>

<span data-ttu-id="8b090-142">Antes de poder crear planes de prestaciones para sus empleados, debe configurar las opciones para los planes.</span><span class="sxs-lookup"><span data-stu-id="8b090-142">Before you can create benefit plans for your employees, you need to configure options for the plans.</span></span>

- [<span data-ttu-id="8b090-143">Establecer parámetros de administración de prestaciones</span><span class="sxs-lookup"><span data-stu-id="8b090-143">Set Benefits management parameters</span></span>](hr-benefits-setup-parameters.md)
- [<span data-ttu-id="8b090-144">Configurar reglas y opciones de idoneidad</span><span class="sxs-lookup"><span data-stu-id="8b090-144">Configure eligibility rules and options</span></span>](hr-benefits-setup-eligibility-rules.md)
- [<span data-ttu-id="8b090-145">Configurar las opciones de idoneidad de contacto personal</span><span class="sxs-lookup"><span data-stu-id="8b090-145">Configure personal contact eligibility options</span></span>](hr-benefits-setup-contact-eligibility-options.md)
- [<span data-ttu-id="8b090-146">Crear opciones de cobertura</span><span class="sxs-lookup"><span data-stu-id="8b090-146">Create coverage options</span></span>](hr-benefits-setup-coverage-options.md)
- [<span data-ttu-id="8b090-147">Configurar frecuencias de pago</span><span class="sxs-lookup"><span data-stu-id="8b090-147">Set up payment frequencies</span></span>](hr-benefits-setup-payment-frequencies.md)
- [<span data-ttu-id="8b090-148">Configurar tipos de eventos de vida</span><span class="sxs-lookup"><span data-stu-id="8b090-148">Configure life event types</span></span>](hr-benefits-setup-life-event-types.md)
- [<span data-ttu-id="8b090-149">Crear tipos de planes</span><span class="sxs-lookup"><span data-stu-id="8b090-149">Create plan types</span></span>](hr-benefits-setup-plan-types.md)
- [<span data-ttu-id="8b090-150">Configurar códigos de motivos</span><span class="sxs-lookup"><span data-stu-id="8b090-150">Set up reason codes</span></span>](hr-benefits-setup-reason-codes.md)
- [<span data-ttu-id="8b090-151">Configurar códigos de niveles</span><span class="sxs-lookup"><span data-stu-id="8b090-151">Set up tier codes</span></span>](hr-benefits-setup-tier-codes.md)
- [<span data-ttu-id="8b090-152">Configurar tasas</span><span class="sxs-lookup"><span data-stu-id="8b090-152">Configure rates</span></span>](hr-benefits-setup-rates.md)
- [<span data-ttu-id="8b090-153">Configurar deducciones</span><span class="sxs-lookup"><span data-stu-id="8b090-153">Configure deductions</span></span>](hr-benefits-setup-deductions.md)
- [<span data-ttu-id="8b090-154">Configurar días de espera</span><span class="sxs-lookup"><span data-stu-id="8b090-154">Configure waiting days</span></span>](hr-benefits-setup-waiting-days.md)
- [<span data-ttu-id="8b090-155">Configurar periodos de espera</span><span class="sxs-lookup"><span data-stu-id="8b090-155">Configure waiting periods</span></span>](hr-benefits-setup-waiting-periods.md)
- [<span data-ttu-id="8b090-156">Configurar reglas de redondeo</span><span class="sxs-lookup"><span data-stu-id="8b090-156">Set up rounding rules</span></span>](hr-benefits-setup-rounding-rules.md)
- [<span data-ttu-id="8b090-157">Crear categorías de empleo</span><span class="sxs-lookup"><span data-stu-id="8b090-157">Create employment categories</span></span>](hr-benefits-setup-employment-categories.md)
- [<span data-ttu-id="8b090-158">Configurar tipos de empleo</span><span class="sxs-lookup"><span data-stu-id="8b090-158">Set up employment types</span></span>](hr-benefits-setup-employment-types.md)
- [<span data-ttu-id="8b090-159">Configurar el autoservicio para empleados</span><span class="sxs-lookup"><span data-stu-id="8b090-159">Configure employee self service</span></span>](hr-benefits-setup-employee-self-service.md)

## <a name="create-benefit-plans"></a><span data-ttu-id="8b090-160">Crear planes de prestaciones</span><span class="sxs-lookup"><span data-stu-id="8b090-160">Create benefit plans</span></span>

<span data-ttu-id="8b090-161">Estos artículos muestran cómo crear planes de prestaciones, incluidos agrupaciones y programas de crédito flexible.</span><span class="sxs-lookup"><span data-stu-id="8b090-161">These articles show how to create benefit plans, including bundles and flex credit programs.</span></span>

- [<span data-ttu-id="8b090-162">Configurar planes de prestaciones</span><span class="sxs-lookup"><span data-stu-id="8b090-162">Set up benefit plans</span></span>](hr-benefits-plans-setup.md)
- [<span data-ttu-id="8b090-163">Crear planes de prestaciones de trabajadores</span><span class="sxs-lookup"><span data-stu-id="8b090-163">Create worker benefit plans</span></span>](hr-benefits-plans-worker.md)
- [<span data-ttu-id="8b090-164">Establecer programas de crédito flexible</span><span class="sxs-lookup"><span data-stu-id="8b090-164">Set up flex credit programs</span></span>](hr-benefits-plans-flex-credit-programs.md)
- [<span data-ttu-id="8b090-165">Configurar de eventos de vida futuros</span><span class="sxs-lookup"><span data-stu-id="8b090-165">Configure future life events</span></span>](hr-benefits-plans-future-life-events.md)

## <a name="process-benefit-plans"></a><span data-ttu-id="8b090-166">Planes del proceso de prestaciones</span><span class="sxs-lookup"><span data-stu-id="8b090-166">Process benefit plans</span></span>

<span data-ttu-id="8b090-167">Debe procesar algunos de sus cambios para activarlos.</span><span class="sxs-lookup"><span data-stu-id="8b090-167">You need to process some of your changes to make them active.</span></span>

- [<span data-ttu-id="8b090-168">Proceso de idoneidad para inscripción</span><span class="sxs-lookup"><span data-stu-id="8b090-168">Process enrollment eligibility</span></span>](hr-benefits-process-enrollment-eligibility.md)
- [<span data-ttu-id="8b090-169">Procesar eventos de vida</span><span class="sxs-lookup"><span data-stu-id="8b090-169">Process life events</span></span>](hr-benefits-process-life-events.md)
- [<span data-ttu-id="8b090-170">Procesar cambios de eventos de vida</span><span class="sxs-lookup"><span data-stu-id="8b090-170">Process life event changes</span></span>](hr-benefits-process-life-event-changes.md)
- [<span data-ttu-id="8b090-171">Procesar idoneidad de eventos de vida</span><span class="sxs-lookup"><span data-stu-id="8b090-171">Process life event eligibility</span></span>](hr-benefits-process-life-event-eligibility.md)
- [<span data-ttu-id="8b090-172">Procesar tasas de cambios</span><span class="sxs-lookup"><span data-stu-id="8b090-172">Process rate changes</span></span>](hr-benefits-process-rate-changes.md)

