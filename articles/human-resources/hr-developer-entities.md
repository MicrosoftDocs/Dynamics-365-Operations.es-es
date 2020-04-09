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
ms.openlocfilehash: c8e0288da16829c04a9b97c0a52caa8bd27cddf8
ms.sourcegitcommit: fde8045ea49d0cf26d5e7ac5a0da5c0d3d69d5bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3166507"
---
# <a name="common-data-service-entities"></a><span data-ttu-id="594d5-103">Entidades de Common Data Service</span><span class="sxs-lookup"><span data-stu-id="594d5-103">Common Data Service entities</span></span>

<span data-ttu-id="594d5-104">Microsoft Dynamics 365 Human Resources usa Common Data Service para habilitar escenarios de extensibilidad e integración.</span><span class="sxs-lookup"><span data-stu-id="594d5-104">Microsoft Dynamics 365 Human Resources uses Common Data Service to enable extensibility and integration scenarios.</span></span>

<span data-ttu-id="594d5-105">Para obtener más información acerca de Common Data Service, consulte [¿Qué es Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span><span class="sxs-lookup"><span data-stu-id="594d5-105">For more information about Common Data Service, see [What is Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span></span>

<span data-ttu-id="594d5-106">Las siguientes entidades de Recursos Humanos están disponibles en Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="594d5-106">The following Human Resources entities are available in Common Data Service.</span></span>

## <a name="benefit-entities"></a><span data-ttu-id="594d5-107">Entidades de prestación</span><span class="sxs-lookup"><span data-stu-id="594d5-107">Benefit entities</span></span>

| <span data-ttu-id="594d5-108">Nombre</span><span class="sxs-lookup"><span data-stu-id="594d5-108">Name</span></span> | <span data-ttu-id="594d5-109">Entidad</span><span class="sxs-lookup"><span data-stu-id="594d5-109">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="594d5-110">Frecuencia de cálculo de la prestación</span><span class="sxs-lookup"><span data-stu-id="594d5-110">Benefit Calculation Frequency</span></span> | <span data-ttu-id="594d5-111">cdm_benefitcalculationfrequency</span><span class="sxs-lookup"><span data-stu-id="594d5-111">cdm_benefitcalculationfrequency</span></span> |
| <span data-ttu-id="594d5-112">Período de pago de la frecuencia de cálculo de prestación</span><span class="sxs-lookup"><span data-stu-id="594d5-112">Benefit Calculation Frequency Pay Period</span></span> | <span data-ttu-id="594d5-113">cdm_benefitcalculationfrequencypayperiod</span><span class="sxs-lookup"><span data-stu-id="594d5-113">cdm_benefitcalculationfrequencypayperiod</span></span> |
| <span data-ttu-id="594d5-114">Índice de cálculo de la prestación</span><span class="sxs-lookup"><span data-stu-id="594d5-114">Benefit Calculation Rate</span></span> | <span data-ttu-id="594d5-115">cdm_benefitcalculationrate</span><span class="sxs-lookup"><span data-stu-id="594d5-115">cdm_benefitcalculationrate</span></span> |
| <span data-ttu-id="594d5-116">Detalle de índice de cálculo de la prestación</span><span class="sxs-lookup"><span data-stu-id="594d5-116">Benefit Calculation Rate Detail</span></span> | <span data-ttu-id="594d5-117">cdm_benefitcalculationratedetail</span><span class="sxs-lookup"><span data-stu-id="594d5-117">cdm_benefitcalculationratedetail</span></span> |
| <span data-ttu-id="594d5-118">Opción de prestación</span><span class="sxs-lookup"><span data-stu-id="594d5-118">Benefit Option</span></span> | <span data-ttu-id="594d5-119">cdm_benefitoption</span><span class="sxs-lookup"><span data-stu-id="594d5-119">cdm_benefitoption</span></span> |
| <span data-ttu-id="594d5-120">Plan de prestaciones</span><span class="sxs-lookup"><span data-stu-id="594d5-120">Benefit Plan</span></span> | <span data-ttu-id="594d5-121">cdm_benefitplan (No habilitada para la compatibilidad de campos personalizados)</span><span class="sxs-lookup"><span data-stu-id="594d5-121">cdm_benefitplan (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="594d5-122">Tipo de prestación</span><span class="sxs-lookup"><span data-stu-id="594d5-122">Benefit Type</span></span> | <span data-ttu-id="594d5-123">cdm_benefittype</span><span class="sxs-lookup"><span data-stu-id="594d5-123">cdm_benefittype</span></span> |

## <a name="business-process-tasks-entities"></a><span data-ttu-id="594d5-124">Entidades de tareas de procesos de negocio</span><span class="sxs-lookup"><span data-stu-id="594d5-124">Business process tasks entities</span></span>

| <span data-ttu-id="594d5-125">Nombre</span><span class="sxs-lookup"><span data-stu-id="594d5-125">Name</span></span> | <span data-ttu-id="594d5-126">Entidad</span><span class="sxs-lookup"><span data-stu-id="594d5-126">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="594d5-127">Calendario de proceso de negocio</span><span class="sxs-lookup"><span data-stu-id="594d5-127">Business Process Calendar</span></span> | <span data-ttu-id="594d5-128">cdm_businessprocesscalendar</span><span class="sxs-lookup"><span data-stu-id="594d5-128">cdm_businessprocesscalendar</span></span> |
| <span data-ttu-id="594d5-129">Asignación de grupo de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="594d5-129">Business Process Group Assignment</span></span> | <span data-ttu-id="594d5-130">cdm_businessprocessgroupassignment</span><span class="sxs-lookup"><span data-stu-id="594d5-130">cdm_businessprocessgroupassignment</span></span> |
| <span data-ttu-id="594d5-131">Grupo de tareas de biblioteca de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="594d5-131">Business Process Library Task Group</span></span> | <span data-ttu-id="594d5-132">cdm_businessprocesslibrarytaskgroup</span><span class="sxs-lookup"><span data-stu-id="594d5-132">cdm_businessprocesslibrarytaskgroup</span></span> |
| <span data-ttu-id="594d5-133">Etapa de proceso empresarial</span><span class="sxs-lookup"><span data-stu-id="594d5-133">Business Process Stage</span></span> | <span data-ttu-id="594d5-134">cdm_businessprocessstage</span><span class="sxs-lookup"><span data-stu-id="594d5-134">cdm_businessprocessstage</span></span> |
| <span data-ttu-id="594d5-135">Encabezado de plantilla de lista de comprobación</span><span class="sxs-lookup"><span data-stu-id="594d5-135">Checklist Template Header</span></span> | <span data-ttu-id="594d5-136">cdm_businessprocesstemplateheader</span><span class="sxs-lookup"><span data-stu-id="594d5-136">cdm_businessprocesstemplateheader</span></span> |
| <span data-ttu-id="594d5-137">Tarea de plantilla de lista de comprobación</span><span class="sxs-lookup"><span data-stu-id="594d5-137">Checklist Template Task</span></span> | <span data-ttu-id="594d5-138">cdm_businessprocesstemplatetask</span><span class="sxs-lookup"><span data-stu-id="594d5-138">cdm_businessprocesstemplatetask</span></span> |

## <a name="compensation-entities"></a><span data-ttu-id="594d5-139">Entidades de compensación</span><span class="sxs-lookup"><span data-stu-id="594d5-139">Compensation entities</span></span>

| <span data-ttu-id="594d5-140">Nombre</span><span class="sxs-lookup"><span data-stu-id="594d5-140">Name</span></span> | <span data-ttu-id="594d5-141">Entidad</span><span class="sxs-lookup"><span data-stu-id="594d5-141">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="594d5-142">Plan de compensación fija</span><span class="sxs-lookup"><span data-stu-id="594d5-142">Compensation Fixed Plan</span></span> | <span data-ttu-id="594d5-143">cdm_compensationfixedplan</span><span class="sxs-lookup"><span data-stu-id="594d5-143">cdm_compensationfixedplan</span></span> |
| <span data-ttu-id="594d5-144">Cuadrícula de compensación</span><span class="sxs-lookup"><span data-stu-id="594d5-144">Compensation Grid</span></span> | <span data-ttu-id="594d5-145">cdm_compensationgrid</span><span class="sxs-lookup"><span data-stu-id="594d5-145">cdm_compensationgrid</span></span> |
| <span data-ttu-id="594d5-146">Nivel de compensación</span><span class="sxs-lookup"><span data-stu-id="594d5-146">Compensation Level</span></span> | <span data-ttu-id="594d5-147">cdm_compensationlevel</span><span class="sxs-lookup"><span data-stu-id="594d5-147">cdm_compensationlevel</span></span> |
| <span data-ttu-id="594d5-148">Frecuencia de pago de compensación</span><span class="sxs-lookup"><span data-stu-id="594d5-148">Compensation Pay Frequency</span></span> | <span data-ttu-id="594d5-149">cdm_compensationpayfrequency</span><span class="sxs-lookup"><span data-stu-id="594d5-149">cdm_compensationpayfrequency</span></span> |
| <span data-ttu-id="594d5-150">Configuración de puntos de referencia de compensación</span><span class="sxs-lookup"><span data-stu-id="594d5-150">Compensation Reference Point Setup</span></span> | <span data-ttu-id="594d5-151">cdm_compensationreferencepointsetup</span><span class="sxs-lookup"><span data-stu-id="594d5-151">cdm_compensationreferencepointsetup</span></span> |
| <span data-ttu-id="594d5-152">Línea de configuración de puntos de referencia de compensación</span><span class="sxs-lookup"><span data-stu-id="594d5-152">Compensation Reference Point Setup Line</span></span> | <span data-ttu-id="594d5-153">cdm_compensationreferencepointsetupline</span><span class="sxs-lookup"><span data-stu-id="594d5-153">cdm_compensationreferencepointsetupline</span></span> |
| <span data-ttu-id="594d5-154">Región de compensación</span><span class="sxs-lookup"><span data-stu-id="594d5-154">Compensation Region</span></span> | <span data-ttu-id="594d5-155">cdm_compensationregion</span><span class="sxs-lookup"><span data-stu-id="594d5-155">cdm_compensationregion</span></span> |
| <span data-ttu-id="594d5-156">Estructura de compensación</span><span class="sxs-lookup"><span data-stu-id="594d5-156">Compensation Structure</span></span> | <span data-ttu-id="594d5-157">cdm_compensationstructure</span><span class="sxs-lookup"><span data-stu-id="594d5-157">cdm_compensationstructure</span></span> |
| <span data-ttu-id="594d5-158">Plan de compensación variable</span><span class="sxs-lookup"><span data-stu-id="594d5-158">Compensation Variable Plan</span></span> | <span data-ttu-id="594d5-159">cdm_compensationvariableplan</span><span class="sxs-lookup"><span data-stu-id="594d5-159">cdm_compensationvariableplan</span></span> |
| <span data-ttu-id="594d5-160">Nivel de plan de compensación variable</span><span class="sxs-lookup"><span data-stu-id="594d5-160">Compensation Variable Plan Level</span></span> | <span data-ttu-id="594d5-161">cdm_compensationvariableplanlevel</span><span class="sxs-lookup"><span data-stu-id="594d5-161">cdm_compensationvariableplanlevel</span></span> |
| <span data-ttu-id="594d5-162">Tipo de plan de compensación variable</span><span class="sxs-lookup"><span data-stu-id="594d5-162">Compensation Variable Plan Type</span></span> | <span data-ttu-id="594d5-163">cdm_compensationvariableplantype</span><span class="sxs-lookup"><span data-stu-id="594d5-163">cdm_compensationvariableplantype</span></span> |
| <span data-ttu-id="594d5-164">Evento de compensación fija</span><span class="sxs-lookup"><span data-stu-id="594d5-164">Fixed Compensation Event</span></span> | <span data-ttu-id="594d5-165">cdm_fixedcompensationevent</span><span class="sxs-lookup"><span data-stu-id="594d5-165">cdm_fixedcompensationevent</span></span> |
| <span data-ttu-id="594d5-166">Regla de atribución</span><span class="sxs-lookup"><span data-stu-id="594d5-166">Vesting Rule</span></span> | <span data-ttu-id="594d5-167">cdm_vestingrule</span><span class="sxs-lookup"><span data-stu-id="594d5-167">cdm_vestingrule</span></span> |
| <span data-ttu-id="594d5-168">Compensación fija del trabajador</span><span class="sxs-lookup"><span data-stu-id="594d5-168">Worker Fixed Compensation</span></span> | <span data-ttu-id="594d5-169">cdm_workerfixedcompensation</span><span class="sxs-lookup"><span data-stu-id="594d5-169">cdm_workerfixedcompensation</span></span> |

## <a name="organization-entities"></a><span data-ttu-id="594d5-170">Entidades de la organización</span><span class="sxs-lookup"><span data-stu-id="594d5-170">Organization entities</span></span>

| <span data-ttu-id="594d5-171">Nombre</span><span class="sxs-lookup"><span data-stu-id="594d5-171">Name</span></span> | <span data-ttu-id="594d5-172">Entidad</span><span class="sxs-lookup"><span data-stu-id="594d5-172">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="594d5-173">Departamento</span><span class="sxs-lookup"><span data-stu-id="594d5-173">Department</span></span> | <span data-ttu-id="594d5-174">cdm_department</span><span class="sxs-lookup"><span data-stu-id="594d5-174">cdm_department</span></span> |
| <span data-ttu-id="594d5-175">Empleo</span><span class="sxs-lookup"><span data-stu-id="594d5-175">Employment</span></span> | <span data-ttu-id="594d5-176">cdm_employment</span><span class="sxs-lookup"><span data-stu-id="594d5-176">cdm_employment</span></span> |
| <span data-ttu-id="594d5-177">Compañía</span><span class="sxs-lookup"><span data-stu-id="594d5-177">Company</span></span> | <span data-ttu-id="594d5-178">cdm_company</span><span class="sxs-lookup"><span data-stu-id="594d5-178">cdm_company</span></span> |
| <span data-ttu-id="594d5-179">Puesto</span><span class="sxs-lookup"><span data-stu-id="594d5-179">Job</span></span> | <span data-ttu-id="594d5-180">cdm_job</span><span class="sxs-lookup"><span data-stu-id="594d5-180">cdm_job</span></span> |
| <span data-ttu-id="594d5-181">Función de trabajo</span><span class="sxs-lookup"><span data-stu-id="594d5-181">Job Function</span></span> | <span data-ttu-id="594d5-182">cdm_jobfunction</span><span class="sxs-lookup"><span data-stu-id="594d5-182">cdm_jobfunction</span></span> |
| <span data-ttu-id="594d5-183">Puesto de trabajo</span><span class="sxs-lookup"><span data-stu-id="594d5-183">Job Position</span></span> | <span data-ttu-id="594d5-184">cdm_jobposition</span><span class="sxs-lookup"><span data-stu-id="594d5-184">cdm_jobposition</span></span> |
| <span data-ttu-id="594d5-185">Tipo de puesto</span><span class="sxs-lookup"><span data-stu-id="594d5-185">Position Type</span></span> | <span data-ttu-id="594d5-186">cdm_positiontype</span><span class="sxs-lookup"><span data-stu-id="594d5-186">cdm_positiontype</span></span> |
| <span data-ttu-id="594d5-187">Asignación del trabajador del puesto</span><span class="sxs-lookup"><span data-stu-id="594d5-187">Position Worker Assignment</span></span> | <span data-ttu-id="594d5-188">cdm_positionworkerassignmentmap</span><span class="sxs-lookup"><span data-stu-id="594d5-188">cdm_positionworkerassignmentmap</span></span> |
| <span data-ttu-id="594d5-189">Dimensión de puesto de trabajo</span><span class="sxs-lookup"><span data-stu-id="594d5-189">Job Position Dimension</span></span> | <span data-ttu-id="594d5-190">cdm_jobpositiondimension</span><span class="sxs-lookup"><span data-stu-id="594d5-190">cdm_jobpositiondimension</span></span>|
| <span data-ttu-id="594d5-191">Tipo de trabajo</span><span class="sxs-lookup"><span data-stu-id="594d5-191">Job Type</span></span> | <span data-ttu-id="594d5-192">cdm_jobtype</span><span class="sxs-lookup"><span data-stu-id="594d5-192">cdm_jobtype</span></span> |
| <span data-ttu-id="594d5-193">Idioma</span><span class="sxs-lookup"><span data-stu-id="594d5-193">Language</span></span> | <span data-ttu-id="594d5-194">cdm_language</span><span class="sxs-lookup"><span data-stu-id="594d5-194">cdm_language</span></span> |
| <span data-ttu-id="594d5-195">Cargo</span><span class="sxs-lookup"><span data-stu-id="594d5-195">Title</span></span> | <span data-ttu-id="594d5-196">cdm_title</span><span class="sxs-lookup"><span data-stu-id="594d5-196">cdm_title</span></span> |

> [!NOTE]
> <span data-ttu-id="594d5-197">Dimensiones financieras para **Tipo de puesto**, **Asignación de puesto de trabajador** y **Empleo** proporcionan integración unidireccional a Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="594d5-197">Financial dimensions for **Position Type**, **Position Worker Assignment**, and **Employment** provide one-direction integration to Common Data Service.</span></span> <span data-ttu-id="594d5-198">Actualmente las actualizaciones de dimensiones financieras no se pueden sincronizar desde Common Data Service a Human Resources.</span><span class="sxs-lookup"><span data-stu-id="594d5-198">Financial dimensions updates currently can't synchronize from Common Data Service to Human Resources.</span></span> 

## <a name="leave-and-absence-entities"></a><span data-ttu-id="594d5-199">Entidades de permisos y ausencias</span><span class="sxs-lookup"><span data-stu-id="594d5-199">Leave and absence entities</span></span>

| <span data-ttu-id="594d5-200">Nombre</span><span class="sxs-lookup"><span data-stu-id="594d5-200">Name</span></span> | <span data-ttu-id="594d5-201">Entidad</span><span class="sxs-lookup"><span data-stu-id="594d5-201">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="594d5-202">Transacción bancaria de bajas</span><span class="sxs-lookup"><span data-stu-id="594d5-202">Leave Bank Transaction</span></span> | <span data-ttu-id="594d5-203">cdm_leavebanktransaction</span><span class="sxs-lookup"><span data-stu-id="594d5-203">cdm_leavebanktransaction</span></span> |
| <span data-ttu-id="594d5-204">Inscripción en baja</span><span class="sxs-lookup"><span data-stu-id="594d5-204">Leave Enrollment</span></span> | <span data-ttu-id="594d5-205">cdm_leaveenrollment</span><span class="sxs-lookup"><span data-stu-id="594d5-205">cdm_leaveenrollment</span></span> |
| <span data-ttu-id="594d5-206">Plan de bajas</span><span class="sxs-lookup"><span data-stu-id="594d5-206">Leave Plan</span></span> | <span data-ttu-id="594d5-207">cdm_leaveplan</span><span class="sxs-lookup"><span data-stu-id="594d5-207">cdm_leaveplan</span></span> |
| <span data-ttu-id="594d5-208">Solicitud de baja</span><span class="sxs-lookup"><span data-stu-id="594d5-208">Leave Request</span></span> | <span data-ttu-id="594d5-209">cdm_leaverequest</span><span class="sxs-lookup"><span data-stu-id="594d5-209">cdm_leaverequest</span></span> |
| <span data-ttu-id="594d5-210">Detalles de solicitud de baja</span><span class="sxs-lookup"><span data-stu-id="594d5-210">Leave Request Detail</span></span> | <span data-ttu-id="594d5-211">cdm_leaverequestdetail</span><span class="sxs-lookup"><span data-stu-id="594d5-211">cdm_leaverequestdetail</span></span> |
| <span data-ttu-id="594d5-212">Tipo de baja</span><span class="sxs-lookup"><span data-stu-id="594d5-212">Leave Type</span></span> | <span data-ttu-id="594d5-213">cdm_leavetype</span><span class="sxs-lookup"><span data-stu-id="594d5-213">cdm_leavetype</span></span> |
| <span data-ttu-id="594d5-214">Código de auditoría de tipo de baja</span><span class="sxs-lookup"><span data-stu-id="594d5-214">Leave Type Reason Code</span></span> | <span data-ttu-id="594d5-215">cdm_leavetypereasoncode</span><span class="sxs-lookup"><span data-stu-id="594d5-215">cdm_leavetypereasoncode</span></span> |

## <a name="payroll-entities"></a><span data-ttu-id="594d5-216">Entidades de nómina</span><span class="sxs-lookup"><span data-stu-id="594d5-216">Payroll entities</span></span>

| <span data-ttu-id="594d5-217">Nombre</span><span class="sxs-lookup"><span data-stu-id="594d5-217">Name</span></span> | <span data-ttu-id="594d5-218">Entidad</span><span class="sxs-lookup"><span data-stu-id="594d5-218">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="594d5-219">Ciclo de pago</span><span class="sxs-lookup"><span data-stu-id="594d5-219">Pay Cycle</span></span> | <span data-ttu-id="594d5-220">cdm_paycycle</span><span class="sxs-lookup"><span data-stu-id="594d5-220">cdm_paycycle</span></span> |
| <span data-ttu-id="594d5-221">Período de pago</span><span class="sxs-lookup"><span data-stu-id="594d5-221">Pay Period</span></span> | <span data-ttu-id="594d5-222">cdm_payperiod</span><span class="sxs-lookup"><span data-stu-id="594d5-222">cdm_payperiod</span></span> |
| <span data-ttu-id="594d5-223">Código de ganancia de nómina</span><span class="sxs-lookup"><span data-stu-id="594d5-223">Payroll Earning Code</span></span> | <span data-ttu-id="594d5-224">cdm_payrollearningcode</span><span class="sxs-lookup"><span data-stu-id="594d5-224">cdm_payrollearningcode</span></span> |
| <span data-ttu-id="594d5-225">Desembolso de cuenta bancaria</span><span class="sxs-lookup"><span data-stu-id="594d5-225">Bank Account Disbursement</span></span> | <span data-ttu-id="594d5-226">cdm_bankaccountdisbursement</span><span class="sxs-lookup"><span data-stu-id="594d5-226">cdm_bankaccountdisbursement</span></span> |
| <span data-ttu-id="594d5-227">Región de impuestos</span><span class="sxs-lookup"><span data-stu-id="594d5-227">Tax Region</span></span> | <span data-ttu-id="594d5-228">cdm_taxregion</span><span class="sxs-lookup"><span data-stu-id="594d5-228">cdm_taxregion</span></span> |

## <a name="worker-entities"></a><span data-ttu-id="594d5-229">Entidades del trabajador</span><span class="sxs-lookup"><span data-stu-id="594d5-229">Worker entities</span></span>

| <span data-ttu-id="594d5-230">Nombre</span><span class="sxs-lookup"><span data-stu-id="594d5-230">Name</span></span> | <span data-ttu-id="594d5-231">Entidad</span><span class="sxs-lookup"><span data-stu-id="594d5-231">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="594d5-232">Trabajador</span><span class="sxs-lookup"><span data-stu-id="594d5-232">Worker</span></span> | <span data-ttu-id="594d5-233">cdm_worker</span><span class="sxs-lookup"><span data-stu-id="594d5-233">cdm_worker</span></span> |
| <span data-ttu-id="594d5-234">Dirección de trabajador</span><span class="sxs-lookup"><span data-stu-id="594d5-234">Worker Address</span></span> | <span data-ttu-id="594d5-235">cdm_workeraddress</span><span class="sxs-lookup"><span data-stu-id="594d5-235">cdm_workeraddress</span></span> |
| <span data-ttu-id="594d5-236">Detalle personal del trabajador</span><span class="sxs-lookup"><span data-stu-id="594d5-236">Worker Personal Detail</span></span> | <span data-ttu-id="594d5-237">cdm_workerpersonaldetail</span><span class="sxs-lookup"><span data-stu-id="594d5-237">cdm_workerpersonaldetail</span></span> |
| <span data-ttu-id="594d5-238">Número de identificación de persona del trabajador</span><span class="sxs-lookup"><span data-stu-id="594d5-238">Worker Person Identification Number</span></span> | <span data-ttu-id="594d5-239">cdm_workerpersonidentificationnumber</span><span class="sxs-lookup"><span data-stu-id="594d5-239">cdm_workerpersonidentificationnumber</span></span> |
| <span data-ttu-id="594d5-240">Tipo de identificación de persona del trabajador</span><span class="sxs-lookup"><span data-stu-id="594d5-240">Worker Person Identification Type</span></span> | <span data-ttu-id="594d5-241">cdm_workerpersonidentificationtype</span><span class="sxs-lookup"><span data-stu-id="594d5-241">cdm_workerpersonidentificationtype</span></span> |
| <span data-ttu-id="594d5-242">Calendario de trabajo</span><span class="sxs-lookup"><span data-stu-id="594d5-242">Work Calendar</span></span> | <span data-ttu-id="594d5-243">cdm_workcalendar</span><span class="sxs-lookup"><span data-stu-id="594d5-243">cdm_workcalendar</span></span> |
| <span data-ttu-id="594d5-244">Día de calendario de trabajo</span><span class="sxs-lookup"><span data-stu-id="594d5-244">Work Calendar Day</span></span> | <span data-ttu-id="594d5-245">cdm_workcalendarday</span><span class="sxs-lookup"><span data-stu-id="594d5-245">cdm_workcalendarday</span></span> |
| <span data-ttu-id="594d5-246">Vacaciones calendario de trabajo</span><span class="sxs-lookup"><span data-stu-id="594d5-246">Work Calendar Holiday</span></span> |<span data-ttu-id="594d5-247">cdm_workcalendarholiday</span><span class="sxs-lookup"><span data-stu-id="594d5-247">cdm_workcalendarholiday</span></span> |
| <span data-ttu-id="594d5-248">Línea de festivo del calendario de trabajo</span><span class="sxs-lookup"><span data-stu-id="594d5-248">Work Calendar Holiday Line</span></span> | <span data-ttu-id="594d5-249">cdm_workcalendarholidayline</span><span class="sxs-lookup"><span data-stu-id="594d5-249">cdm_workcalendarholidayline</span></span> |
| <span data-ttu-id="594d5-250">Intervalo de tiempo del calendario de trabajo</span><span class="sxs-lookup"><span data-stu-id="594d5-250">Work Calendar Time Interval</span></span> | <span data-ttu-id="594d5-251">cdm_workcalendartimeinterval (No habilitada para la compatibilidad de campos personalizados)</span><span class="sxs-lookup"><span data-stu-id="594d5-251">cdm_workcalendartimeinterval (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="594d5-252">Cuenta bancaria del trabajador</span><span class="sxs-lookup"><span data-stu-id="594d5-252">Worker Bank Account</span></span> | <span data-ttu-id="594d5-253">cdm_workerbankaccount</span><span class="sxs-lookup"><span data-stu-id="594d5-253">cdm_workerbankaccount</span></span> |

## <a name="worker-setup-entities"></a><span data-ttu-id="594d5-254">Configurar entidades del trabajador</span><span class="sxs-lookup"><span data-stu-id="594d5-254">Worker setup entities</span></span>

| <span data-ttu-id="594d5-255">Nombre</span><span class="sxs-lookup"><span data-stu-id="594d5-255">Name</span></span> | <span data-ttu-id="594d5-256">Entidad</span><span class="sxs-lookup"><span data-stu-id="594d5-256">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="594d5-257">Estado de veterano</span><span class="sxs-lookup"><span data-stu-id="594d5-257">Veteran Status</span></span> | <span data-ttu-id="594d5-258">cdm_veteranstatus</span><span class="sxs-lookup"><span data-stu-id="594d5-258">cdm_veteranstatus</span></span> |
| <span data-ttu-id="594d5-259">Origen étnico</span><span class="sxs-lookup"><span data-stu-id="594d5-259">Ethnic Origin</span></span> | <span data-ttu-id="594d5-260">cdm_ethnicorigin</span><span class="sxs-lookup"><span data-stu-id="594d5-260">cdm_ethnicorigin</span></span> |
| <span data-ttu-id="594d5-261">Código de motivo</span><span class="sxs-lookup"><span data-stu-id="594d5-261">Reason Code</span></span> | <span data-ttu-id="594d5-262">cdm_reasoncode</span><span class="sxs-lookup"><span data-stu-id="594d5-262">cdm_reasoncode</span></span> |
| <span data-ttu-id="594d5-263">Agencia emisora de identificación de personas</span><span class="sxs-lookup"><span data-stu-id="594d5-263">Person Identification Issuing Agency</span></span> | <span data-ttu-id="594d5-264">cdm_personidentificationissuingagency</span><span class="sxs-lookup"><span data-stu-id="594d5-264">cdm_personidentificationissuingagency</span></span> |

## <a name="competency-entities"></a><span data-ttu-id="594d5-265">Entidades de competencia</span><span class="sxs-lookup"><span data-stu-id="594d5-265">Competency entities</span></span>

| <span data-ttu-id="594d5-266">Nombre</span><span class="sxs-lookup"><span data-stu-id="594d5-266">Name</span></span> | <span data-ttu-id="594d5-267">Entidad</span><span class="sxs-lookup"><span data-stu-id="594d5-267">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="594d5-268">Tipo de aptitud</span><span class="sxs-lookup"><span data-stu-id="594d5-268">Skill Type</span></span> | <span data-ttu-id="594d5-269">cdm_skilltype</span><span class="sxs-lookup"><span data-stu-id="594d5-269">cdm_skilltype</span></span> |

## <a name="entity-relationship-models"></a><span data-ttu-id="594d5-270">Modelos de relación de entidad</span><span class="sxs-lookup"><span data-stu-id="594d5-270">Entity relationship models</span></span>

### <a name="worker"></a><span data-ttu-id="594d5-271">Trabajador</span><span class="sxs-lookup"><span data-stu-id="594d5-271">Worker</span></span>

![Trabajador](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a><span data-ttu-id="594d5-273">Trabajo y puesto de trabajo</span><span class="sxs-lookup"><span data-stu-id="594d5-273">Job and Job Position</span></span>

![Trabajo y puesto de trabajo](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a><span data-ttu-id="594d5-275">Prestaciones</span><span class="sxs-lookup"><span data-stu-id="594d5-275">Benefits</span></span>

![Prestaciones](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a><span data-ttu-id="594d5-277">Compensación</span><span class="sxs-lookup"><span data-stu-id="594d5-277">Compensation</span></span>

![Compensación](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a><span data-ttu-id="594d5-279">Dejar</span><span class="sxs-lookup"><span data-stu-id="594d5-279">Leave</span></span>

![Dejar](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a><span data-ttu-id="594d5-281">Calendario de trabajo</span><span class="sxs-lookup"><span data-stu-id="594d5-281">Work Calendar</span></span>

![Calendario de trabajo](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a><span data-ttu-id="594d5-283">Consulte también</span><span class="sxs-lookup"><span data-stu-id="594d5-283">See also</span></span>

[<span data-ttu-id="594d5-284">Elegir una tecnología de integración de datos</span><span class="sxs-lookup"><span data-stu-id="594d5-284">Choose a data integration technology</span></span>](hr-admin-integration-choose-technology.md)</br>
[<span data-ttu-id="594d5-285">Configurar la integración de Common Data Service</span><span class="sxs-lookup"><span data-stu-id="594d5-285">Configure Common Data Service integration</span></span>](hr-admin-integration-common-data-service.md)
