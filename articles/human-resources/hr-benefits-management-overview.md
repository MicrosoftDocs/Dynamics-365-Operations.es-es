---
title: Visión general de administración de prestaciones
description: Visión general de la característica de administración de prestaciones en Dynamics 365 Human Resources. Ofrezca a sus empleados opciones de prestaciones ampliadas con una experiencia en línea fácil de usar.
author: andreabichsel
manager: AnnBe
ms.date: 09/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
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
ms.openlocfilehash: e2e8fcdd0b6124b459c4dc073e2929418d18bcc5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420380"
---
# <a name="benefits-management-overview"></a><span data-ttu-id="2a669-104">Visión general de la administración de prestaciones</span><span class="sxs-lookup"><span data-stu-id="2a669-104">Benefits management overview</span></span>

<span data-ttu-id="2a669-105">Para seguir siendo competitivo, debe ofrecer un amplio conjunto de prestaciones para atraer y retener a sus mejores empleados.</span><span class="sxs-lookup"><span data-stu-id="2a669-105">To remain competitive, you must offer a rich set of benefits to attract and retain your best employees.</span></span> <span data-ttu-id="2a669-106">Además de las prestaciones estándar como la cobertura médica y dental, es posible que también quiera ofrecer servicios ampliados como asistencia de adopción, programas de recreación y asignaciones de ropa.</span><span class="sxs-lookup"><span data-stu-id="2a669-106">In addition to standard benefits like medical and dental coverage, you might also want to offer expanded services like adoption assistance, recreation programs, and clothing allowances.</span></span> <span data-ttu-id="2a669-107">La administración de prestaciones en Microsoft Dynamics 365 Human Resources le brinda una solución flexible que admite una amplia variedad de opciones de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="2a669-107">Benefits management in Microsoft Dynamics 365 Human Resources provides you with a flexible solution that supports a wide variety of benefit options.</span></span> <span data-ttu-id="2a669-108">Recursos humanos también incluye una experiencia fácil de usar para los empleados que muestra sus ofertas.</span><span class="sxs-lookup"><span data-stu-id="2a669-108">Human Resources also includes an easy-to-use employee experience that showcases your offerings.</span></span>

- <span data-ttu-id="2a669-109">Los planes de prestaciones mejoradas le permiten crear y administrar planes de prestaciones únicas y admitir tablas complejas de tasas de prestaciones y niveles anidados.</span><span class="sxs-lookup"><span data-stu-id="2a669-109">Enhanced benefits plans let you create and manage unique benefit plans and support complex benefit rate tables and nested tiers.</span></span> <span data-ttu-id="2a669-110">Puede crear fácilmente programas de beneficios, agrupaciones y reglas de inscripción automática para una experiencia más fácil para los empleados.</span><span class="sxs-lookup"><span data-stu-id="2a669-110">You can easily create benefit programs, bundles, and auto-enrollment rules for an easier employee experience.</span></span>

- <span data-ttu-id="2a669-111">Los programas de crédito flexible le permiten prorratear para asistir en la jubilación y otros eventos de la vida.</span><span class="sxs-lookup"><span data-stu-id="2a669-111">Flex credit programs let you prorate to support retirement and other life events.</span></span>

- <span data-ttu-id="2a669-112">Las extensas reglas de idoneidad garantizan que las prestaciones adecuadas estén disponibles para los empleados correctos.</span><span class="sxs-lookup"><span data-stu-id="2a669-112">Extensive eligibility rules ensure you make the right benefits available to the right employees.</span></span>

- <span data-ttu-id="2a669-113">La inscripción de prestaciones en línea ofrece una experiencia fácil para sus empleados.</span><span class="sxs-lookup"><span data-stu-id="2a669-113">Online benefits enrollment provides an easy experience for your employees.</span></span>

- <span data-ttu-id="2a669-114">El procesamiento calificado de eventos de vida admite eventos de vida futuros.</span><span class="sxs-lookup"><span data-stu-id="2a669-114">Qualified life event processing supports future life events.</span></span>

<span data-ttu-id="2a669-115">Si desea acceder a los datos de demostración, deberá volver a implementar su entorno de espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="2a669-115">If you would like to access the demo data, you'll need to redeploy your sandbox environment.</span></span>

## <a name="enable-benefits-management"></a><span data-ttu-id="2a669-116">Habilitar la administración de prestaciones</span><span class="sxs-lookup"><span data-stu-id="2a669-116">Enable Benefits management</span></span>

<span data-ttu-id="2a669-117">Este tema describe cómo activar las características en Recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="2a669-117">This topic describes how to turn on features in Human Resources.</span></span> <span data-ttu-id="2a669-118">También le indica qué características existentes en Human Resources reemplazan o deshabilitan la administración de prestaciones una vez que activa la administración de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="2a669-118">It also tells which existing features in Human Resources that Benefits management replaces or are disabled once you turn on Benefits management.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2a669-119">Después de habilitar la gestión de prestaciones en un entorno de **Producción**, no puede deshabilitarlo.</span><span class="sxs-lookup"><span data-stu-id="2a669-119">After you enable Benefits management in a **Production** environment, you can't disable it.</span></span> <span data-ttu-id="2a669-120">Recomendamos habilitar y probar la gestión de prestaciones en un entorno **Espacio aislado** antes de habilitarlo en un entorno de **Producción**.</span><span class="sxs-lookup"><span data-stu-id="2a669-120">We recommend enabling and testing Benefits management in a **Sandbox** environment before enabling it in a **Production** environment.</span></span> <span data-ttu-id="2a669-121">Existen diferencias significativas entre la funcionalidad de prestación heredada y la nueva funcionalidad de administración de prestaciones que requieren una configuración adicional y deben probarse antes de su puesta en producción.</span><span class="sxs-lookup"><span data-stu-id="2a669-121">There are significant differences between the legacy Benefit functionality and new Benefits management functionality that require additional setup and should be tested prior to being placed into production.</span></span>

- [<span data-ttu-id="2a669-122">Administrar características</span><span class="sxs-lookup"><span data-stu-id="2a669-122">Manage features</span></span>](hr-admin-manage-features.md)

## <a name="configure-employee-information"></a><span data-ttu-id="2a669-123">Configurar información de empleados</span><span class="sxs-lookup"><span data-stu-id="2a669-123">Configure employee information</span></span>

<span data-ttu-id="2a669-124">Antes de poder inscribir a los empleados en las prestaciones, debe proporcionar la información requerida.</span><span class="sxs-lookup"><span data-stu-id="2a669-124">Before you can enroll employees in benefits, you must provide required information.</span></span> <span data-ttu-id="2a669-125">Debe inscribir a un empleado en un **Plan de compensación fija** en su fecha de inicio, y debe seleccionar una **Frecuencia de pago de prestaciones** en **Detalles de empleo** en el formulario el **Trabajador**.</span><span class="sxs-lookup"><span data-stu-id="2a669-125">You must enroll an employee in a **Fixed compensation plan** on their start date, and you must select a **Benefit pay frequency** in **Employment details** on the **Worker** form.</span></span>

<span data-ttu-id="2a669-126">Si tiene un empleado que recibe una compensación adicional como comisiones, puede agregar una cantidad **Salario anual de prestaciones** desde el registro del empleado.</span><span class="sxs-lookup"><span data-stu-id="2a669-126">If you have an employee who receives supplemental compensation like commissions, you can add a **Benefits annual salary** amount from the employee record.</span></span> <span data-ttu-id="2a669-127">Recursos Humanos utilizará la cantidad **Salario anual de prestaciones** al determinar los importes de cobertura, en lugar del importe anual de compensación fija.</span><span class="sxs-lookup"><span data-stu-id="2a669-127">Human Resources will use the **Benefits annual salary** amount when determining coverage amounts, instead of the fixed compensation annual amount.</span></span> <span data-ttu-id="2a669-128">El **Salario anual de prestaciones** debe ser válido a partir de la fecha de inicio del empleado o del comienzo del período de prestaciones, lo que sea más reciente.</span><span class="sxs-lookup"><span data-stu-id="2a669-128">The **Benefits annual salary** must be valid as of the employee’s start date or the beginning of the benefit period, whichever is latest.</span></span> <span data-ttu-id="2a669-129">Si se registra una compensación fija y un importe de salario anual de prestaciones para un empleado, el salario anual de prestaciones se utilizará para determinar los importes de cobertura.</span><span class="sxs-lookup"><span data-stu-id="2a669-129">If both a fixed compensation and benefits annual salary amount is recorded for an employee, the benefits annual salary will be used in determining coverage amounts.</span></span>

<span data-ttu-id="2a669-130">Cuando crea un plan de prestaciones que utiliza tarifas que se basan en el sexo o la edad, debe ingresar una fecha de nacimiento y género del empleado para calcular el costo de la prestaciones.</span><span class="sxs-lookup"><span data-stu-id="2a669-130">When you create a benefit plan that uses rates that are based on gender or age, you must enter a birth date and gender for the employee to calculate the benefit cost.</span></span>

## <a name="configure-benefits-management"></a><span data-ttu-id="2a669-131">Configurar la administración de prestaciones</span><span class="sxs-lookup"><span data-stu-id="2a669-131">Configure Benefits management</span></span>

<span data-ttu-id="2a669-132">Antes de poder crear planes de prestaciones para sus empleados, debe configurar las opciones para los planes.</span><span class="sxs-lookup"><span data-stu-id="2a669-132">Before you can create benefit plans for your employees, you need to configure options for the plans.</span></span>

- [<span data-ttu-id="2a669-133">Establecer parámetros de administración de prestaciones</span><span class="sxs-lookup"><span data-stu-id="2a669-133">Set Benefits management parameters</span></span>](hr-benefits-setup-parameters.md)
- [<span data-ttu-id="2a669-134">Configurar reglas y opciones de idoneidad</span><span class="sxs-lookup"><span data-stu-id="2a669-134">Configure eligibility rules and options</span></span>](hr-benefits-setup-eligibility-rules.md)
- [<span data-ttu-id="2a669-135">Configurar las opciones de elegibilidad de contacto personal</span><span class="sxs-lookup"><span data-stu-id="2a669-135">Configure personal contact eligibility options</span></span>](hr-benefits-setup-contact-eligibility-options.md)
- [<span data-ttu-id="2a669-136">Crear opciones de cobertura</span><span class="sxs-lookup"><span data-stu-id="2a669-136">Create coverage options</span></span>](hr-benefits-setup-coverage-options.md)
- [<span data-ttu-id="2a669-137">Configurar frecuencias de pago</span><span class="sxs-lookup"><span data-stu-id="2a669-137">Set up payment frequencies</span></span>](hr-benefits-setup-payment-frequencies.md)
- [<span data-ttu-id="2a669-138">Configurar tipos de eventos de vida</span><span class="sxs-lookup"><span data-stu-id="2a669-138">Configure life event types</span></span>](hr-benefits-setup-life-event-types.md)
- [<span data-ttu-id="2a669-139">Crear tipos de planes</span><span class="sxs-lookup"><span data-stu-id="2a669-139">Create plan types</span></span>](hr-benefits-setup-plan-types.md)
- [<span data-ttu-id="2a669-140">Configurar códigos de motivos</span><span class="sxs-lookup"><span data-stu-id="2a669-140">Set up reason codes</span></span>](hr-benefits-setup-reason-codes.md)
- [<span data-ttu-id="2a669-141">Configurar códigos de nivel</span><span class="sxs-lookup"><span data-stu-id="2a669-141">Set up tier codes</span></span>](hr-benefits-setup-tier-codes.md)
- [<span data-ttu-id="2a669-142">Configurar tarifas</span><span class="sxs-lookup"><span data-stu-id="2a669-142">Configure rates</span></span>](hr-benefits-setup-rates.md)
- [<span data-ttu-id="2a669-143">Configurar deducciones</span><span class="sxs-lookup"><span data-stu-id="2a669-143">Configure deductions</span></span>](hr-benefits-setup-deductions.md)
- [<span data-ttu-id="2a669-144">Configurar días de espera</span><span class="sxs-lookup"><span data-stu-id="2a669-144">Configure waiting days</span></span>](hr-benefits-setup-waiting-days.md)
- [<span data-ttu-id="2a669-145">Configurar períodos de espera</span><span class="sxs-lookup"><span data-stu-id="2a669-145">Configure waiting periods</span></span>](hr-benefits-setup-waiting-periods.md)
- [<span data-ttu-id="2a669-146">Configurar reglas de redondeo</span><span class="sxs-lookup"><span data-stu-id="2a669-146">Set up rounding rules</span></span>](hr-benefits-setup-rounding-rules.md)
- [<span data-ttu-id="2a669-147">Crear categorías de empleo</span><span class="sxs-lookup"><span data-stu-id="2a669-147">Create employment categories</span></span>](hr-benefits-setup-employment-categories.md)
- [<span data-ttu-id="2a669-148">Configurar tipos de empleo</span><span class="sxs-lookup"><span data-stu-id="2a669-148">Set up employment types</span></span>](hr-benefits-setup-employment-types.md)
- [<span data-ttu-id="2a669-149">Configurar el autoservicio para empleados</span><span class="sxs-lookup"><span data-stu-id="2a669-149">Configure employee self service</span></span>](hr-benefits-setup-employee-self-service.md)

## <a name="create-benefit-plans"></a><span data-ttu-id="2a669-150">Crear planes de prestaciones</span><span class="sxs-lookup"><span data-stu-id="2a669-150">Create benefit plans</span></span>

<span data-ttu-id="2a669-151">Estos artículos muestran cómo crear planes de prestaciones, incluidos agrupaciones y programas de crédito flexible.</span><span class="sxs-lookup"><span data-stu-id="2a669-151">These articles show how to create benefit plans, including bundles and flex credit programs.</span></span>

- [<span data-ttu-id="2a669-152">Configurar planes de prestaciones</span><span class="sxs-lookup"><span data-stu-id="2a669-152">Set up benefit plans</span></span>](hr-benefits-plans-setup.md)
- [<span data-ttu-id="2a669-153">Configurar programas de crédito flexible</span><span class="sxs-lookup"><span data-stu-id="2a669-153">Set up flex credit programs</span></span>](hr-benefits-plans-flex-credit-programs.md)

## <a name="process-benefit-plans"></a><span data-ttu-id="2a669-154">Procesar planes de beneficios</span><span class="sxs-lookup"><span data-stu-id="2a669-154">Process benefit plans</span></span>

<span data-ttu-id="2a669-155">Debe procesar algunos de sus cambios para activarlos.</span><span class="sxs-lookup"><span data-stu-id="2a669-155">You need to process some of your changes to make them active.</span></span>

- [<span data-ttu-id="2a669-156">Proceso de idoneidad para inscripción</span><span class="sxs-lookup"><span data-stu-id="2a669-156">Process enrollment eligibility</span></span>](hr-benefits-process-enrollment-eligibility.md)
- [<span data-ttu-id="2a669-157">Procesar eventos de vida</span><span class="sxs-lookup"><span data-stu-id="2a669-157">Process life events</span></span>](hr-benefits-process-life-events.md)
- [<span data-ttu-id="2a669-158">Procesar cambios de eventos de vida</span><span class="sxs-lookup"><span data-stu-id="2a669-158">Process life event changes</span></span>](hr-benefits-process-life-event-changes.md)
- [<span data-ttu-id="2a669-159">Procesar idoneidad de eventos de vida</span><span class="sxs-lookup"><span data-stu-id="2a669-159">Process life event eligibility</span></span>](hr-benefits-process-life-event-eligibility.md)
- [<span data-ttu-id="2a669-160">Procesar tasas de cambios</span><span class="sxs-lookup"><span data-stu-id="2a669-160">Process rate changes</span></span>](hr-benefits-process-rate-changes.md)

