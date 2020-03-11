---
title: Entidades de Common Data Service
description: Microsoft Dynamics 365 Human Resources usa Common Data Service para habilitar escenarios de extensibilidad e integración.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6879a45dd1fcc1ba718747aaaf0d7936c2eac49f
ms.sourcegitcommit: 3cad15f8ecc257d3a45c1bc1fada7c094ff4bcec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "3087355"
---
# <a name="common-data-service-entities"></a><span data-ttu-id="c100a-103">Entidades de Common Data Service</span><span class="sxs-lookup"><span data-stu-id="c100a-103">Common Data Service entities</span></span>

<span data-ttu-id="c100a-104">Microsoft Dynamics 365 Human Resources usa Common Data Service para habilitar escenarios de extensibilidad e integración.</span><span class="sxs-lookup"><span data-stu-id="c100a-104">Microsoft Dynamics 365 Human Resources uses Common Data Service to enable extensibility and integration scenarios.</span></span>

<span data-ttu-id="c100a-105">Para obtener más información acerca de Common Data Service, consulte [¿Qué es Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span><span class="sxs-lookup"><span data-stu-id="c100a-105">For more information about Common Data Service, see [What is Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span></span>

<span data-ttu-id="c100a-106">Las siguientes entidades de Recursos Humanos están disponibles en Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="c100a-106">The following Human Resources entities are available in Common Data Service.</span></span>

## <a name="benefit-entities"></a><span data-ttu-id="c100a-107">Entidades de prestación</span><span class="sxs-lookup"><span data-stu-id="c100a-107">Benefit entities</span></span>

| <span data-ttu-id="c100a-108">Nombre</span><span class="sxs-lookup"><span data-stu-id="c100a-108">Name</span></span> | <span data-ttu-id="c100a-109">Entidad</span><span class="sxs-lookup"><span data-stu-id="c100a-109">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="c100a-110">Frecuencia de cálculo de la prestación</span><span class="sxs-lookup"><span data-stu-id="c100a-110">Benefit Calculation Frequency</span></span> | <span data-ttu-id="c100a-111">cdm_benefitcalculationfrequency</span><span class="sxs-lookup"><span data-stu-id="c100a-111">cdm_benefitcalculationfrequency</span></span> |
| <span data-ttu-id="c100a-112">Período de pago de la frecuencia de cálculo de prestación</span><span class="sxs-lookup"><span data-stu-id="c100a-112">Benefit Calculation Frequency Pay Period</span></span> | <span data-ttu-id="c100a-113">cdm_benefitcalculationfrequencypayperiod</span><span class="sxs-lookup"><span data-stu-id="c100a-113">cdm_benefitcalculationfrequencypayperiod</span></span> |
| <span data-ttu-id="c100a-114">Índice de cálculo de la prestación</span><span class="sxs-lookup"><span data-stu-id="c100a-114">Benefit Calculation Rate</span></span> | <span data-ttu-id="c100a-115">cdm_benefitcalculationrate</span><span class="sxs-lookup"><span data-stu-id="c100a-115">cdm_benefitcalculationrate</span></span> |
| <span data-ttu-id="c100a-116">Detalle de índice de cálculo de la prestación</span><span class="sxs-lookup"><span data-stu-id="c100a-116">Benefit Calculation Rate Detail</span></span> | <span data-ttu-id="c100a-117">cdm_benefitcalculationratedetail</span><span class="sxs-lookup"><span data-stu-id="c100a-117">cdm_benefitcalculationratedetail</span></span> |
| <span data-ttu-id="c100a-118">Opción de prestación</span><span class="sxs-lookup"><span data-stu-id="c100a-118">Benefit Option</span></span> | <span data-ttu-id="c100a-119">cdm_benefitoption</span><span class="sxs-lookup"><span data-stu-id="c100a-119">cdm_benefitoption</span></span> |
| <span data-ttu-id="c100a-120">Plan de prestaciones</span><span class="sxs-lookup"><span data-stu-id="c100a-120">Benefit Plan</span></span> | <span data-ttu-id="c100a-121">cdm_benefitplan (No habilitada para la compatibilidad de campos personalizados)</span><span class="sxs-lookup"><span data-stu-id="c100a-121">cdm_benefitplan (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="c100a-122">Tipo de prestación</span><span class="sxs-lookup"><span data-stu-id="c100a-122">Benefit Type</span></span> | <span data-ttu-id="c100a-123">cdm_benefittype</span><span class="sxs-lookup"><span data-stu-id="c100a-123">cdm_benefittype</span></span> |

## <a name="business-process-tasks-entities"></a><span data-ttu-id="c100a-124">Entidades de tareas de procesos de negocio</span><span class="sxs-lookup"><span data-stu-id="c100a-124">Business process tasks entities</span></span>

| <span data-ttu-id="c100a-125">Nombre</span><span class="sxs-lookup"><span data-stu-id="c100a-125">Name</span></span> | <span data-ttu-id="c100a-126">Entidad</span><span class="sxs-lookup"><span data-stu-id="c100a-126">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="c100a-127">Calendario de proceso de negocio</span><span class="sxs-lookup"><span data-stu-id="c100a-127">Business Process Calendar</span></span> | <span data-ttu-id="c100a-128">cdm_businessprocesscalendar</span><span class="sxs-lookup"><span data-stu-id="c100a-128">cdm_businessprocesscalendar</span></span> |
| <span data-ttu-id="c100a-129">Asignación de grupo de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="c100a-129">Business Process Group Assignment</span></span> | <span data-ttu-id="c100a-130">cdm_businessprocessgroupassignment</span><span class="sxs-lookup"><span data-stu-id="c100a-130">cdm_businessprocessgroupassignment</span></span> |
| <span data-ttu-id="c100a-131">Grupo de tareas de biblioteca de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="c100a-131">Business Process Library Task Group</span></span> | <span data-ttu-id="c100a-132">cdm_businessprocesslibrarytaskgroup</span><span class="sxs-lookup"><span data-stu-id="c100a-132">cdm_businessprocesslibrarytaskgroup</span></span> |
| <span data-ttu-id="c100a-133">Etapa de proceso empresarial</span><span class="sxs-lookup"><span data-stu-id="c100a-133">Business Process Stage</span></span> | <span data-ttu-id="c100a-134">cdm_businessprocessstage</span><span class="sxs-lookup"><span data-stu-id="c100a-134">cdm_businessprocessstage</span></span> |
| <span data-ttu-id="c100a-135">Encabezado de plantilla de lista de comprobación</span><span class="sxs-lookup"><span data-stu-id="c100a-135">Checklist Template Header</span></span> | <span data-ttu-id="c100a-136">cdm_businessprocesstemplateheader</span><span class="sxs-lookup"><span data-stu-id="c100a-136">cdm_businessprocesstemplateheader</span></span> |
| <span data-ttu-id="c100a-137">Tarea de plantilla de lista de comprobación</span><span class="sxs-lookup"><span data-stu-id="c100a-137">Checklist Template Task</span></span> | <span data-ttu-id="c100a-138">cdm_businessprocesstemplatetask</span><span class="sxs-lookup"><span data-stu-id="c100a-138">cdm_businessprocesstemplatetask</span></span> |

## <a name="compensation-entities"></a><span data-ttu-id="c100a-139">Entidades de compensación</span><span class="sxs-lookup"><span data-stu-id="c100a-139">Compensation entities</span></span>

| <span data-ttu-id="c100a-140">Nombre</span><span class="sxs-lookup"><span data-stu-id="c100a-140">Name</span></span> | <span data-ttu-id="c100a-141">Entidad</span><span class="sxs-lookup"><span data-stu-id="c100a-141">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="c100a-142">Plan de compensación fija</span><span class="sxs-lookup"><span data-stu-id="c100a-142">Compensation Fixed Plan</span></span> | <span data-ttu-id="c100a-143">cdm_compensationfixedplan</span><span class="sxs-lookup"><span data-stu-id="c100a-143">cdm_compensationfixedplan</span></span> |
| <span data-ttu-id="c100a-144">Cuadrícula de compensación</span><span class="sxs-lookup"><span data-stu-id="c100a-144">Compensation Grid</span></span> | <span data-ttu-id="c100a-145">cdm_compensationgrid</span><span class="sxs-lookup"><span data-stu-id="c100a-145">cdm_compensationgrid</span></span> |
| <span data-ttu-id="c100a-146">Nivel de compensación</span><span class="sxs-lookup"><span data-stu-id="c100a-146">Compensation Level</span></span> | <span data-ttu-id="c100a-147">cdm_compensationlevel</span><span class="sxs-lookup"><span data-stu-id="c100a-147">cdm_compensationlevel</span></span> |
| <span data-ttu-id="c100a-148">Frecuencia de pago de compensación</span><span class="sxs-lookup"><span data-stu-id="c100a-148">Compensation Pay Frequency</span></span> | <span data-ttu-id="c100a-149">cdm_compensationpayfrequency</span><span class="sxs-lookup"><span data-stu-id="c100a-149">cdm_compensationpayfrequency</span></span> |
| <span data-ttu-id="c100a-150">Configuración de puntos de referencia de compensación</span><span class="sxs-lookup"><span data-stu-id="c100a-150">Compensation Reference Point Setup</span></span> | <span data-ttu-id="c100a-151">cdm_compensationreferencepointsetup</span><span class="sxs-lookup"><span data-stu-id="c100a-151">cdm_compensationreferencepointsetup</span></span> |
| <span data-ttu-id="c100a-152">Línea de configuración de puntos de referencia de compensación</span><span class="sxs-lookup"><span data-stu-id="c100a-152">Compensation Reference Point Setup Line</span></span> | <span data-ttu-id="c100a-153">cdm_compensationreferencepointsetupline</span><span class="sxs-lookup"><span data-stu-id="c100a-153">cdm_compensationreferencepointsetupline</span></span> |
| <span data-ttu-id="c100a-154">Región de compensación</span><span class="sxs-lookup"><span data-stu-id="c100a-154">Compensation Region</span></span> | <span data-ttu-id="c100a-155">cdm_compensationregion</span><span class="sxs-lookup"><span data-stu-id="c100a-155">cdm_compensationregion</span></span> |
| <span data-ttu-id="c100a-156">Estructura de compensación</span><span class="sxs-lookup"><span data-stu-id="c100a-156">Compensation Structure</span></span> | <span data-ttu-id="c100a-157">cdm_compensationstructure</span><span class="sxs-lookup"><span data-stu-id="c100a-157">cdm_compensationstructure</span></span> |
| <span data-ttu-id="c100a-158">Plan de compensación variable</span><span class="sxs-lookup"><span data-stu-id="c100a-158">Compensation Variable Plan</span></span> | <span data-ttu-id="c100a-159">cdm_compensationvariableplan</span><span class="sxs-lookup"><span data-stu-id="c100a-159">cdm_compensationvariableplan</span></span> |
| <span data-ttu-id="c100a-160">Nivel de plan de compensación variable</span><span class="sxs-lookup"><span data-stu-id="c100a-160">Compensation Variable Plan Level</span></span> | <span data-ttu-id="c100a-161">cdm_compensationvariableplanlevel</span><span class="sxs-lookup"><span data-stu-id="c100a-161">cdm_compensationvariableplanlevel</span></span> |
| <span data-ttu-id="c100a-162">Tipo de plan de compensación variable</span><span class="sxs-lookup"><span data-stu-id="c100a-162">Compensation Variable Plan Type</span></span> | <span data-ttu-id="c100a-163">cdm_compensationvariableplantype</span><span class="sxs-lookup"><span data-stu-id="c100a-163">cdm_compensationvariableplantype</span></span> |
| <span data-ttu-id="c100a-164">Evento de compensación fija</span><span class="sxs-lookup"><span data-stu-id="c100a-164">Fixed Compensation Event</span></span> | <span data-ttu-id="c100a-165">cdm_fixedcompensationevent</span><span class="sxs-lookup"><span data-stu-id="c100a-165">cdm_fixedcompensationevent</span></span> |
| <span data-ttu-id="c100a-166">Regla de atribución</span><span class="sxs-lookup"><span data-stu-id="c100a-166">Vesting Rule</span></span> | <span data-ttu-id="c100a-167">cdm_vestingrule</span><span class="sxs-lookup"><span data-stu-id="c100a-167">cdm_vestingrule</span></span> |
| <span data-ttu-id="c100a-168">Compensación fija del trabajador</span><span class="sxs-lookup"><span data-stu-id="c100a-168">Worker Fixed Compensation</span></span> | <span data-ttu-id="c100a-169">cdm_workerfixedcompensation</span><span class="sxs-lookup"><span data-stu-id="c100a-169">cdm_workerfixedcompensation</span></span> |

## <a name="organization-entities"></a><span data-ttu-id="c100a-170">Entidades de la organización</span><span class="sxs-lookup"><span data-stu-id="c100a-170">Organization entities</span></span>

| <span data-ttu-id="c100a-171">Nombre</span><span class="sxs-lookup"><span data-stu-id="c100a-171">Name</span></span> | <span data-ttu-id="c100a-172">Entidad</span><span class="sxs-lookup"><span data-stu-id="c100a-172">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="c100a-173">Departamento</span><span class="sxs-lookup"><span data-stu-id="c100a-173">Department</span></span> | <span data-ttu-id="c100a-174">cdm_department</span><span class="sxs-lookup"><span data-stu-id="c100a-174">cdm_department</span></span> |
| <span data-ttu-id="c100a-175">Empleo</span><span class="sxs-lookup"><span data-stu-id="c100a-175">Employment</span></span> | <span data-ttu-id="c100a-176">cdm_employment</span><span class="sxs-lookup"><span data-stu-id="c100a-176">cdm_employment</span></span> |
| <span data-ttu-id="c100a-177">Compañía</span><span class="sxs-lookup"><span data-stu-id="c100a-177">Company</span></span> | <span data-ttu-id="c100a-178">cdm_company</span><span class="sxs-lookup"><span data-stu-id="c100a-178">cdm_company</span></span> |
| <span data-ttu-id="c100a-179">Puesto</span><span class="sxs-lookup"><span data-stu-id="c100a-179">Job</span></span> | <span data-ttu-id="c100a-180">cdm_job</span><span class="sxs-lookup"><span data-stu-id="c100a-180">cdm_job</span></span> |
| <span data-ttu-id="c100a-181">Función de trabajo</span><span class="sxs-lookup"><span data-stu-id="c100a-181">Job Function</span></span> | <span data-ttu-id="c100a-182">cdm_jobfunction</span><span class="sxs-lookup"><span data-stu-id="c100a-182">cdm_jobfunction</span></span> |
| <span data-ttu-id="c100a-183">Puesto de trabajo</span><span class="sxs-lookup"><span data-stu-id="c100a-183">Job Position</span></span> | <span data-ttu-id="c100a-184">cdm_jobposition</span><span class="sxs-lookup"><span data-stu-id="c100a-184">cdm_jobposition</span></span> |
| <span data-ttu-id="c100a-185">Tipo de puesto</span><span class="sxs-lookup"><span data-stu-id="c100a-185">Position Type</span></span> | <span data-ttu-id="c100a-186">cdm_positiontype</span><span class="sxs-lookup"><span data-stu-id="c100a-186">cdm_positiontype</span></span> |
| <span data-ttu-id="c100a-187">Asignación del trabajador del puesto</span><span class="sxs-lookup"><span data-stu-id="c100a-187">Position Worker Assignment</span></span> | <span data-ttu-id="c100a-188">cdm_positionworkerassignmentmap</span><span class="sxs-lookup"><span data-stu-id="c100a-188">cdm_positionworkerassignmentmap</span></span> |
| <span data-ttu-id="c100a-189">Tipo de trabajo</span><span class="sxs-lookup"><span data-stu-id="c100a-189">Job Type</span></span> | <span data-ttu-id="c100a-190">cdm_jobtype</span><span class="sxs-lookup"><span data-stu-id="c100a-190">cdm_jobtype</span></span> |
| <span data-ttu-id="c100a-191">Idioma</span><span class="sxs-lookup"><span data-stu-id="c100a-191">Language</span></span> | <span data-ttu-id="c100a-192">cdm_language</span><span class="sxs-lookup"><span data-stu-id="c100a-192">cdm_language</span></span> |

## <a name="leave-and-absence-entities"></a><span data-ttu-id="c100a-193">Entidades de permisos y ausencias</span><span class="sxs-lookup"><span data-stu-id="c100a-193">Leave and absence entities</span></span>

| <span data-ttu-id="c100a-194">Nombre</span><span class="sxs-lookup"><span data-stu-id="c100a-194">Name</span></span> | <span data-ttu-id="c100a-195">Entidad</span><span class="sxs-lookup"><span data-stu-id="c100a-195">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="c100a-196">Transacciones bancaria de bajas</span><span class="sxs-lookup"><span data-stu-id="c100a-196">Leave Bank Transaction</span></span> | <span data-ttu-id="c100a-197">cdm_leavebanktransaction</span><span class="sxs-lookup"><span data-stu-id="c100a-197">cdm_leavebanktransaction</span></span> |
| <span data-ttu-id="c100a-198">Inscripción en baja</span><span class="sxs-lookup"><span data-stu-id="c100a-198">Leave Enrollment</span></span> | <span data-ttu-id="c100a-199">cdm_leaveenrollment</span><span class="sxs-lookup"><span data-stu-id="c100a-199">cdm_leaveenrollment</span></span> |
| <span data-ttu-id="c100a-200">Plan de bajas</span><span class="sxs-lookup"><span data-stu-id="c100a-200">Leave Plan</span></span> | <span data-ttu-id="c100a-201">cdm_leaveplan</span><span class="sxs-lookup"><span data-stu-id="c100a-201">cdm_leaveplan</span></span> |
| <span data-ttu-id="c100a-202">Solicitud de baja</span><span class="sxs-lookup"><span data-stu-id="c100a-202">Leave Request</span></span> | <span data-ttu-id="c100a-203">cdm_leaverequest</span><span class="sxs-lookup"><span data-stu-id="c100a-203">cdm_leaverequest</span></span> |
| <span data-ttu-id="c100a-204">Detalles de solicitud de baja</span><span class="sxs-lookup"><span data-stu-id="c100a-204">Leave Request Detail</span></span> | <span data-ttu-id="c100a-205">cdm_leaverequestdetail</span><span class="sxs-lookup"><span data-stu-id="c100a-205">cdm_leaverequestdetail</span></span> |
| <span data-ttu-id="c100a-206">Tipo de baja</span><span class="sxs-lookup"><span data-stu-id="c100a-206">Leave Type</span></span> | <span data-ttu-id="c100a-207">cdm_leavetype</span><span class="sxs-lookup"><span data-stu-id="c100a-207">cdm_leavetype</span></span> |
| <span data-ttu-id="c100a-208">Código de auditoría de tipo de baja</span><span class="sxs-lookup"><span data-stu-id="c100a-208">Leave Type Reason Code</span></span> | <span data-ttu-id="c100a-209">cdm_leavetypereasoncode</span><span class="sxs-lookup"><span data-stu-id="c100a-209">cdm_leavetypereasoncode</span></span> |

## <a name="payroll-entities"></a><span data-ttu-id="c100a-210">Entidades de nómina</span><span class="sxs-lookup"><span data-stu-id="c100a-210">Payroll entities</span></span>

| <span data-ttu-id="c100a-211">Nombre</span><span class="sxs-lookup"><span data-stu-id="c100a-211">Name</span></span> | <span data-ttu-id="c100a-212">Entidad</span><span class="sxs-lookup"><span data-stu-id="c100a-212">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="c100a-213">Ciclo de pago</span><span class="sxs-lookup"><span data-stu-id="c100a-213">Pay Cycle</span></span> | <span data-ttu-id="c100a-214">cdm_paycycle</span><span class="sxs-lookup"><span data-stu-id="c100a-214">cdm_paycycle</span></span> |
| <span data-ttu-id="c100a-215">Período de pago</span><span class="sxs-lookup"><span data-stu-id="c100a-215">Pay Period</span></span> | <span data-ttu-id="c100a-216">cdm_payperiod</span><span class="sxs-lookup"><span data-stu-id="c100a-216">cdm_payperiod</span></span> |
| <span data-ttu-id="c100a-217">Código de ganancia de nómina</span><span class="sxs-lookup"><span data-stu-id="c100a-217">Payroll Earning Code</span></span> | <span data-ttu-id="c100a-218">cdm_payrollearningcode</span><span class="sxs-lookup"><span data-stu-id="c100a-218">cdm_payrollearningcode</span></span> |
| <span data-ttu-id="c100a-219">Desembolso de cuenta bancaria</span><span class="sxs-lookup"><span data-stu-id="c100a-219">Bank Account Disbursement</span></span> | <span data-ttu-id="c100a-220">cdm_bankaccountdisbursement</span><span class="sxs-lookup"><span data-stu-id="c100a-220">cdm_bankaccountdisbursement</span></span> |
| <span data-ttu-id="c100a-221">Región de impuestos</span><span class="sxs-lookup"><span data-stu-id="c100a-221">Tax Region</span></span> | <span data-ttu-id="c100a-222">cdm_taxregion</span><span class="sxs-lookup"><span data-stu-id="c100a-222">cdm_taxregion</span></span> |

## <a name="worker-entities"></a><span data-ttu-id="c100a-223">Entidades del trabajador</span><span class="sxs-lookup"><span data-stu-id="c100a-223">Worker entities</span></span>

| <span data-ttu-id="c100a-224">Nombre</span><span class="sxs-lookup"><span data-stu-id="c100a-224">Name</span></span> | <span data-ttu-id="c100a-225">Entidad</span><span class="sxs-lookup"><span data-stu-id="c100a-225">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="c100a-226">Trabajador</span><span class="sxs-lookup"><span data-stu-id="c100a-226">Worker</span></span> | <span data-ttu-id="c100a-227">cdm_worker</span><span class="sxs-lookup"><span data-stu-id="c100a-227">cdm_worker</span></span> |
| <span data-ttu-id="c100a-228">Dirección de trabajador</span><span class="sxs-lookup"><span data-stu-id="c100a-228">Worker Address</span></span> | <span data-ttu-id="c100a-229">cdm_workeraddress</span><span class="sxs-lookup"><span data-stu-id="c100a-229">cdm_workeraddress</span></span> |
| <span data-ttu-id="c100a-230">Detalle personal del trabajador</span><span class="sxs-lookup"><span data-stu-id="c100a-230">Worker Personal Detail</span></span> | <span data-ttu-id="c100a-231">cdm_workerpersonaldetail</span><span class="sxs-lookup"><span data-stu-id="c100a-231">cdm_workerpersonaldetail</span></span> |
| <span data-ttu-id="c100a-232">Número de identificación de persona del trabajador</span><span class="sxs-lookup"><span data-stu-id="c100a-232">Worker Person Identification Number</span></span> | <span data-ttu-id="c100a-233">cdm_workerpersonidentificationnumber</span><span class="sxs-lookup"><span data-stu-id="c100a-233">cdm_workerpersonidentificationnumber</span></span> |
| <span data-ttu-id="c100a-234">Tipo de identificación de persona del trabajador</span><span class="sxs-lookup"><span data-stu-id="c100a-234">Worker Person Identification Type</span></span> | <span data-ttu-id="c100a-235">cdm_workerpersonidentificationtype</span><span class="sxs-lookup"><span data-stu-id="c100a-235">cdm_workerpersonidentificationtype</span></span> |
| <span data-ttu-id="c100a-236">Calendario de trabajo</span><span class="sxs-lookup"><span data-stu-id="c100a-236">Work Calendar</span></span> | <span data-ttu-id="c100a-237">cdm_workcalendar</span><span class="sxs-lookup"><span data-stu-id="c100a-237">cdm_workcalendar</span></span> |
| <span data-ttu-id="c100a-238">Día de calendario de trabajo</span><span class="sxs-lookup"><span data-stu-id="c100a-238">Work Calendar Day</span></span> | <span data-ttu-id="c100a-239">cdm_workcalendarday</span><span class="sxs-lookup"><span data-stu-id="c100a-239">cdm_workcalendarday</span></span> |
| <span data-ttu-id="c100a-240">Vacaciones calendario de trabajo</span><span class="sxs-lookup"><span data-stu-id="c100a-240">Work Calendar Holiday</span></span> |<span data-ttu-id="c100a-241">cdm_workcalendarholiday</span><span class="sxs-lookup"><span data-stu-id="c100a-241">cdm_workcalendarholiday</span></span> |
| <span data-ttu-id="c100a-242">Línea de festivo del calendario de trabajo</span><span class="sxs-lookup"><span data-stu-id="c100a-242">Work Calendar Holiday Line</span></span> | <span data-ttu-id="c100a-243">cdm_workcalendarholidayline</span><span class="sxs-lookup"><span data-stu-id="c100a-243">cdm_workcalendarholidayline</span></span> |
| <span data-ttu-id="c100a-244">Intervalo de tiempo del calendario de trabajo</span><span class="sxs-lookup"><span data-stu-id="c100a-244">Work Calendar Time Interval</span></span> | <span data-ttu-id="c100a-245">cdm_workcalendartimeinterval (No habilitada para la compatibilidad de campos personalizados)</span><span class="sxs-lookup"><span data-stu-id="c100a-245">cdm_workcalendartimeinterval (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="c100a-246">Cuenta bancaria del trabajador</span><span class="sxs-lookup"><span data-stu-id="c100a-246">Worker Bank Account</span></span> | <span data-ttu-id="c100a-247">cdm_workerbankaccount</span><span class="sxs-lookup"><span data-stu-id="c100a-247">cdm_workerbankaccount</span></span> |

## <a name="worker-setup-entities"></a><span data-ttu-id="c100a-248">Configurar entidades del trabajador</span><span class="sxs-lookup"><span data-stu-id="c100a-248">Worker setup entities</span></span>

| <span data-ttu-id="c100a-249">Nombre</span><span class="sxs-lookup"><span data-stu-id="c100a-249">Name</span></span> | <span data-ttu-id="c100a-250">Entidad</span><span class="sxs-lookup"><span data-stu-id="c100a-250">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="c100a-251">Estado de veterano</span><span class="sxs-lookup"><span data-stu-id="c100a-251">Veteran Status</span></span> | <span data-ttu-id="c100a-252">cdm_veteranstatus</span><span class="sxs-lookup"><span data-stu-id="c100a-252">cdm_veteranstatus</span></span> |
| <span data-ttu-id="c100a-253">Origen étnico</span><span class="sxs-lookup"><span data-stu-id="c100a-253">Ethnic Origin</span></span> | <span data-ttu-id="c100a-254">cdm_ethnicorigin</span><span class="sxs-lookup"><span data-stu-id="c100a-254">cdm_ethnicorigin</span></span> |
| <span data-ttu-id="c100a-255">Código de motivo</span><span class="sxs-lookup"><span data-stu-id="c100a-255">Reason Code</span></span> | <span data-ttu-id="c100a-256">cdm_reasoncode</span><span class="sxs-lookup"><span data-stu-id="c100a-256">cdm_reasoncode</span></span> |
| <span data-ttu-id="c100a-257">Agencia emisora de identificación de personas</span><span class="sxs-lookup"><span data-stu-id="c100a-257">Person Identification Issuing Agency</span></span> | <span data-ttu-id="c100a-258">cdm_personidentificationissuingagency</span><span class="sxs-lookup"><span data-stu-id="c100a-258">cdm_personidentificationissuingagency</span></span> |

## <a name="competency-entities"></a><span data-ttu-id="c100a-259">Entidades de competencia</span><span class="sxs-lookup"><span data-stu-id="c100a-259">Competency entities</span></span>

| <span data-ttu-id="c100a-260">Nombre</span><span class="sxs-lookup"><span data-stu-id="c100a-260">Name</span></span> | <span data-ttu-id="c100a-261">Entidad</span><span class="sxs-lookup"><span data-stu-id="c100a-261">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="c100a-262">Tipo de aptitud</span><span class="sxs-lookup"><span data-stu-id="c100a-262">Skill Type</span></span> | <span data-ttu-id="c100a-263">cdm_skilltype</span><span class="sxs-lookup"><span data-stu-id="c100a-263">cdm_skilltype</span></span> |

## <a name="entity-relationship-models"></a><span data-ttu-id="c100a-264">Modelos de relación de entidad</span><span class="sxs-lookup"><span data-stu-id="c100a-264">Entity relationship models</span></span>

### <a name="worker"></a><span data-ttu-id="c100a-265">Trabajador</span><span class="sxs-lookup"><span data-stu-id="c100a-265">Worker</span></span>

![Trabajador](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a><span data-ttu-id="c100a-267">Trabajo y puesto de trabajo</span><span class="sxs-lookup"><span data-stu-id="c100a-267">Job and Job Position</span></span>

![Trabajo y puesto de trabajo](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a><span data-ttu-id="c100a-269">Prestaciones</span><span class="sxs-lookup"><span data-stu-id="c100a-269">Benefits</span></span>

![Prestaciones](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a><span data-ttu-id="c100a-271">Compensación</span><span class="sxs-lookup"><span data-stu-id="c100a-271">Compensation</span></span>

![Compensación](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a><span data-ttu-id="c100a-273">Dejar</span><span class="sxs-lookup"><span data-stu-id="c100a-273">Leave</span></span>

![Dejar](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a><span data-ttu-id="c100a-275">Calendario de trabajo</span><span class="sxs-lookup"><span data-stu-id="c100a-275">Work Calendar</span></span>

![Calendario de trabajo](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a><span data-ttu-id="c100a-277">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c100a-277">See also</span></span>

[<span data-ttu-id="c100a-278">Elegir una tecnología de integración de datos</span><span class="sxs-lookup"><span data-stu-id="c100a-278">Choose a data integration technology</span></span>](hr-admin-integration-choose-technology.md)</br>
[<span data-ttu-id="c100a-279">Configurar la integración de Common Data Service</span><span class="sxs-lookup"><span data-stu-id="c100a-279">Configure Common Data Service integration</span></span>](hr-admin-integration-common-data-service.md)