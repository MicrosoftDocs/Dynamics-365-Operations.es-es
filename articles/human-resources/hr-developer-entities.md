---
title: Tablas de Dataverse
description: Microsoft Dynamics 365 Human Resources usa Dataverse para habilitar escenarios de extensibilidad e integración.
author: andreabichsel
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 325bd8a9de07e3978ff6c513975a0e8db22854e0
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054365"
---
# <a name="dataverse-tables"></a><span data-ttu-id="1f534-103">Tablas de Dataverse</span><span class="sxs-lookup"><span data-stu-id="1f534-103">Dataverse tables</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="1f534-104">Microsoft Dynamics 365 Human Resources usa Dataverse para habilitar escenarios de extensibilidad e integración.</span><span class="sxs-lookup"><span data-stu-id="1f534-104">Microsoft Dynamics 365 Human Resources uses Dataverse to enable extensibility and integration scenarios.</span></span>

> [!NOTE]
> <span data-ttu-id="1f534-105">Las entidades de Human Resources se corresponden con tablas de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="1f534-105">Human Resources entities correspond to Dataverse tables.</span></span> <span data-ttu-id="1f534-106">Para obtener más información sobre Dataverse (antes denominado Common Data Service) y actualizaciones de terminología, consulte [¿Qué es Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="1f534-106">For more information about Dataverse (formerly Common Data Service) and terminology updates, see [What is Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)</span></span>

<span data-ttu-id="1f534-107">Están disponibles las siguientes entidades de Dataverse basadas en entidades de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="1f534-107">The following Dataverse tables are available based on Human Resources entities.</span></span>

## <a name="benefit-tables"></a><span data-ttu-id="1f534-108">Tablas de prestaciones</span><span class="sxs-lookup"><span data-stu-id="1f534-108">Benefit tables</span></span>

| <span data-ttu-id="1f534-109">Nombre</span><span class="sxs-lookup"><span data-stu-id="1f534-109">Name</span></span> | <span data-ttu-id="1f534-110">Tabla</span><span class="sxs-lookup"><span data-stu-id="1f534-110">Table</span></span> |
| --- | --- |
| <span data-ttu-id="1f534-111">Frecuencia de cálculo de la prestación</span><span class="sxs-lookup"><span data-stu-id="1f534-111">Benefit Calculation Frequency</span></span> | <span data-ttu-id="1f534-112">cdm_benefitcalculationfrequency</span><span class="sxs-lookup"><span data-stu-id="1f534-112">cdm_benefitcalculationfrequency</span></span> |
| <span data-ttu-id="1f534-113">Período de pago de la frecuencia de cálculo de prestación</span><span class="sxs-lookup"><span data-stu-id="1f534-113">Benefit Calculation Frequency Pay Period</span></span> | <span data-ttu-id="1f534-114">cdm_benefitcalculationfrequencypayperiod</span><span class="sxs-lookup"><span data-stu-id="1f534-114">cdm_benefitcalculationfrequencypayperiod</span></span> |
| <span data-ttu-id="1f534-115">Índice de cálculo de la prestación</span><span class="sxs-lookup"><span data-stu-id="1f534-115">Benefit Calculation Rate</span></span> | <span data-ttu-id="1f534-116">cdm_benefitcalculationrate</span><span class="sxs-lookup"><span data-stu-id="1f534-116">cdm_benefitcalculationrate</span></span> |
| <span data-ttu-id="1f534-117">Detalle de índice de cálculo de la prestación</span><span class="sxs-lookup"><span data-stu-id="1f534-117">Benefit Calculation Rate Detail</span></span> | <span data-ttu-id="1f534-118">cdm_benefitcalculationratedetail</span><span class="sxs-lookup"><span data-stu-id="1f534-118">cdm_benefitcalculationratedetail</span></span> |
| <span data-ttu-id="1f534-119">Opción de prestación</span><span class="sxs-lookup"><span data-stu-id="1f534-119">Benefit Option</span></span> | <span data-ttu-id="1f534-120">cdm_benefitoption</span><span class="sxs-lookup"><span data-stu-id="1f534-120">cdm_benefitoption</span></span> |
| <span data-ttu-id="1f534-121">Plan de prestaciones</span><span class="sxs-lookup"><span data-stu-id="1f534-121">Benefit Plan</span></span> | <span data-ttu-id="1f534-122">cdm_benefitplan (No habilitada para la compatibilidad de campos personalizados)</span><span class="sxs-lookup"><span data-stu-id="1f534-122">cdm_benefitplan (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="1f534-123">Tipo de prestación</span><span class="sxs-lookup"><span data-stu-id="1f534-123">Benefit Type</span></span> | <span data-ttu-id="1f534-124">cdm_benefittype</span><span class="sxs-lookup"><span data-stu-id="1f534-124">cdm_benefittype</span></span> |

## <a name="business-process-tasks-tables"></a><span data-ttu-id="1f534-125">Tablas de tareas de procesos de negocio</span><span class="sxs-lookup"><span data-stu-id="1f534-125">Business process tasks tables</span></span>

| <span data-ttu-id="1f534-126">Nombre</span><span class="sxs-lookup"><span data-stu-id="1f534-126">Name</span></span> | <span data-ttu-id="1f534-127">Tabla</span><span class="sxs-lookup"><span data-stu-id="1f534-127">Table</span></span> |
| --- | --- |
| <span data-ttu-id="1f534-128">Calendario de proceso de negocio</span><span class="sxs-lookup"><span data-stu-id="1f534-128">Business Process Calendar</span></span> | <span data-ttu-id="1f534-129">cdm_businessprocesscalendar</span><span class="sxs-lookup"><span data-stu-id="1f534-129">cdm_businessprocesscalendar</span></span> |
| <span data-ttu-id="1f534-130">Asignación de grupo de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="1f534-130">Business Process Group Assignment</span></span> | <span data-ttu-id="1f534-131">cdm_businessprocessgroupassignment</span><span class="sxs-lookup"><span data-stu-id="1f534-131">cdm_businessprocessgroupassignment</span></span> |
| <span data-ttu-id="1f534-132">Grupo de tareas de biblioteca de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="1f534-132">Business Process Library Task Group</span></span> | <span data-ttu-id="1f534-133">cdm_businessprocesslibrarytaskgroup</span><span class="sxs-lookup"><span data-stu-id="1f534-133">cdm_businessprocesslibrarytaskgroup</span></span> |
| <span data-ttu-id="1f534-134">Etapa de proceso empresarial</span><span class="sxs-lookup"><span data-stu-id="1f534-134">Business Process Stage</span></span> | <span data-ttu-id="1f534-135">cdm_businessprocessstage</span><span class="sxs-lookup"><span data-stu-id="1f534-135">cdm_businessprocessstage</span></span> |
| <span data-ttu-id="1f534-136">Encabezado de plantilla de lista de comprobación</span><span class="sxs-lookup"><span data-stu-id="1f534-136">Checklist Template Header</span></span> | <span data-ttu-id="1f534-137">cdm_businessprocesstemplateheader</span><span class="sxs-lookup"><span data-stu-id="1f534-137">cdm_businessprocesstemplateheader</span></span> |
| <span data-ttu-id="1f534-138">Tarea de plantilla de lista de comprobación</span><span class="sxs-lookup"><span data-stu-id="1f534-138">Checklist Template Task</span></span> | <span data-ttu-id="1f534-139">cdm_businessprocesstemplatetask</span><span class="sxs-lookup"><span data-stu-id="1f534-139">cdm_businessprocesstemplatetask</span></span> |

## <a name="compensation-tables"></a><span data-ttu-id="1f534-140">Tablas de compensación</span><span class="sxs-lookup"><span data-stu-id="1f534-140">Compensation tables</span></span>

| <span data-ttu-id="1f534-141">Nombre</span><span class="sxs-lookup"><span data-stu-id="1f534-141">Name</span></span> | <span data-ttu-id="1f534-142">Tabla</span><span class="sxs-lookup"><span data-stu-id="1f534-142">Table</span></span> |
| --- | --- |
| <span data-ttu-id="1f534-143">Plan fijo de compensación</span><span class="sxs-lookup"><span data-stu-id="1f534-143">Compensation Fixed Plan</span></span> | <span data-ttu-id="1f534-144">cdm_compensationfixedplan</span><span class="sxs-lookup"><span data-stu-id="1f534-144">cdm_compensationfixedplan</span></span> |
| <span data-ttu-id="1f534-145">Cuadrícula de compensación</span><span class="sxs-lookup"><span data-stu-id="1f534-145">Compensation Grid</span></span> | <span data-ttu-id="1f534-146">cdm_compensationgrid</span><span class="sxs-lookup"><span data-stu-id="1f534-146">cdm_compensationgrid</span></span> |
| <span data-ttu-id="1f534-147">Nivel de compensación</span><span class="sxs-lookup"><span data-stu-id="1f534-147">Compensation Level</span></span> | <span data-ttu-id="1f534-148">cdm_compensationlevel</span><span class="sxs-lookup"><span data-stu-id="1f534-148">cdm_compensationlevel</span></span> |
| <span data-ttu-id="1f534-149">Frecuencia de pago de compensación</span><span class="sxs-lookup"><span data-stu-id="1f534-149">Compensation Pay Frequency</span></span> | <span data-ttu-id="1f534-150">cdm_compensationpayfrequency</span><span class="sxs-lookup"><span data-stu-id="1f534-150">cdm_compensationpayfrequency</span></span> |
| <span data-ttu-id="1f534-151">Configuración de puntos de referencia de compensación</span><span class="sxs-lookup"><span data-stu-id="1f534-151">Compensation Reference Point Setup</span></span> | <span data-ttu-id="1f534-152">cdm_compensationreferencepointsetup</span><span class="sxs-lookup"><span data-stu-id="1f534-152">cdm_compensationreferencepointsetup</span></span> |
| <span data-ttu-id="1f534-153">Línea de configuración de puntos de referencia de compensación</span><span class="sxs-lookup"><span data-stu-id="1f534-153">Compensation Reference Point Setup Line</span></span> | <span data-ttu-id="1f534-154">cdm_compensationreferencepointsetupline</span><span class="sxs-lookup"><span data-stu-id="1f534-154">cdm_compensationreferencepointsetupline</span></span> |
| <span data-ttu-id="1f534-155">Región de compensación</span><span class="sxs-lookup"><span data-stu-id="1f534-155">Compensation Region</span></span> | <span data-ttu-id="1f534-156">cdm_compensationregion</span><span class="sxs-lookup"><span data-stu-id="1f534-156">cdm_compensationregion</span></span> |
| <span data-ttu-id="1f534-157">Estructura de compensación</span><span class="sxs-lookup"><span data-stu-id="1f534-157">Compensation Structure</span></span> | <span data-ttu-id="1f534-158">cdm_compensationstructure</span><span class="sxs-lookup"><span data-stu-id="1f534-158">cdm_compensationstructure</span></span> |
| <span data-ttu-id="1f534-159">Plan de compensación variable</span><span class="sxs-lookup"><span data-stu-id="1f534-159">Compensation Variable Plan</span></span> | <span data-ttu-id="1f534-160">cdm_compensationvariableplan</span><span class="sxs-lookup"><span data-stu-id="1f534-160">cdm_compensationvariableplan</span></span> |
| <span data-ttu-id="1f534-161">Nivel de plan de compensación variable</span><span class="sxs-lookup"><span data-stu-id="1f534-161">Compensation Variable Plan Level</span></span> | <span data-ttu-id="1f534-162">cdm_compensationvariableplanlevel</span><span class="sxs-lookup"><span data-stu-id="1f534-162">cdm_compensationvariableplanlevel</span></span> |
| <span data-ttu-id="1f534-163">Tipo de plan de compensación variable</span><span class="sxs-lookup"><span data-stu-id="1f534-163">Compensation Variable Plan Type</span></span> | <span data-ttu-id="1f534-164">cdm_compensationvariableplantype</span><span class="sxs-lookup"><span data-stu-id="1f534-164">cdm_compensationvariableplantype</span></span> |
| <span data-ttu-id="1f534-165">Evento de compensación fija</span><span class="sxs-lookup"><span data-stu-id="1f534-165">Fixed Compensation Event</span></span> | <span data-ttu-id="1f534-166">cdm_fixedcompensationevent</span><span class="sxs-lookup"><span data-stu-id="1f534-166">cdm_fixedcompensationevent</span></span> |
| <span data-ttu-id="1f534-167">Regla de atribución</span><span class="sxs-lookup"><span data-stu-id="1f534-167">Vesting Rule</span></span> | <span data-ttu-id="1f534-168">cdm_vestingrule</span><span class="sxs-lookup"><span data-stu-id="1f534-168">cdm_vestingrule</span></span> |
| <span data-ttu-id="1f534-169">Compensación fija de trabajador</span><span class="sxs-lookup"><span data-stu-id="1f534-169">Worker Fixed Compensation</span></span> | <span data-ttu-id="1f534-170">cdm_workerfixedcompensation</span><span class="sxs-lookup"><span data-stu-id="1f534-170">cdm_workerfixedcompensation</span></span> |

## <a name="organization-tables"></a><span data-ttu-id="1f534-171">Tablas de organización</span><span class="sxs-lookup"><span data-stu-id="1f534-171">Organization tables</span></span>

| <span data-ttu-id="1f534-172">Nombre</span><span class="sxs-lookup"><span data-stu-id="1f534-172">Name</span></span> | <span data-ttu-id="1f534-173">Tabla</span><span class="sxs-lookup"><span data-stu-id="1f534-173">Table</span></span> |
| --- | --- |
| <span data-ttu-id="1f534-174">Departamento</span><span class="sxs-lookup"><span data-stu-id="1f534-174">Department</span></span> | <span data-ttu-id="1f534-175">cdm_department</span><span class="sxs-lookup"><span data-stu-id="1f534-175">cdm_department</span></span> |
| <span data-ttu-id="1f534-176">Empleo</span><span class="sxs-lookup"><span data-stu-id="1f534-176">Employment</span></span> | <span data-ttu-id="1f534-177">cdm_employment</span><span class="sxs-lookup"><span data-stu-id="1f534-177">cdm_employment</span></span> |
| <span data-ttu-id="1f534-178">Empresa</span><span class="sxs-lookup"><span data-stu-id="1f534-178">Company</span></span> | <span data-ttu-id="1f534-179">cdm_company</span><span class="sxs-lookup"><span data-stu-id="1f534-179">cdm_company</span></span> |
| <span data-ttu-id="1f534-180">Puesto</span><span class="sxs-lookup"><span data-stu-id="1f534-180">Job</span></span> | <span data-ttu-id="1f534-181">cdm_job</span><span class="sxs-lookup"><span data-stu-id="1f534-181">cdm_job</span></span> |
| <span data-ttu-id="1f534-182">Función de trabajo</span><span class="sxs-lookup"><span data-stu-id="1f534-182">Job Function</span></span> | <span data-ttu-id="1f534-183">cdm_jobfunction</span><span class="sxs-lookup"><span data-stu-id="1f534-183">cdm_jobfunction</span></span> |
| <span data-ttu-id="1f534-184">Puesto de trabajo</span><span class="sxs-lookup"><span data-stu-id="1f534-184">Job Position</span></span> | <span data-ttu-id="1f534-185">cdm_jobposition</span><span class="sxs-lookup"><span data-stu-id="1f534-185">cdm_jobposition</span></span> |
| <span data-ttu-id="1f534-186">Tipo de puesto</span><span class="sxs-lookup"><span data-stu-id="1f534-186">Position Type</span></span> | <span data-ttu-id="1f534-187">cdm_positiontype</span><span class="sxs-lookup"><span data-stu-id="1f534-187">cdm_positiontype</span></span> |
| <span data-ttu-id="1f534-188">Asignación del trabajador del puesto</span><span class="sxs-lookup"><span data-stu-id="1f534-188">Position Worker Assignment</span></span> | <span data-ttu-id="1f534-189">cdm_positionworkerassignmentmap</span><span class="sxs-lookup"><span data-stu-id="1f534-189">cdm_positionworkerassignmentmap</span></span> |
| <span data-ttu-id="1f534-190">Dimensión de puesto de trabajo</span><span class="sxs-lookup"><span data-stu-id="1f534-190">Job Position Dimension</span></span> | <span data-ttu-id="1f534-191">cdm_jobpositiondimension</span><span class="sxs-lookup"><span data-stu-id="1f534-191">cdm_jobpositiondimension</span></span>|
| <span data-ttu-id="1f534-192">Tipo de trabajo</span><span class="sxs-lookup"><span data-stu-id="1f534-192">Job Type</span></span> | <span data-ttu-id="1f534-193">cdm_jobtype</span><span class="sxs-lookup"><span data-stu-id="1f534-193">cdm_jobtype</span></span> |
| <span data-ttu-id="1f534-194">Idioma</span><span class="sxs-lookup"><span data-stu-id="1f534-194">Language</span></span> | <span data-ttu-id="1f534-195">cdm_language</span><span class="sxs-lookup"><span data-stu-id="1f534-195">cdm_language</span></span> |
| <span data-ttu-id="1f534-196">Cargo</span><span class="sxs-lookup"><span data-stu-id="1f534-196">Title</span></span> | <span data-ttu-id="1f534-197">cdm_title</span><span class="sxs-lookup"><span data-stu-id="1f534-197">cdm_title</span></span> |

> [!NOTE]
> <span data-ttu-id="1f534-198">Dimensiones financieras para **Tipo de puesto**, **Asignación de puesto de trabajador** y **Empleo** proporcionan integración unidireccional a Dataverse.</span><span class="sxs-lookup"><span data-stu-id="1f534-198">Financial dimensions for **Position Type**, **Position Worker Assignment**, and **Employment** provide one-direction integration to Dataverse.</span></span> <span data-ttu-id="1f534-199">Actualmente las actualizaciones de dimensiones financieras no se pueden sincronizar desde Dataverse a Human Resources.</span><span class="sxs-lookup"><span data-stu-id="1f534-199">Financial dimensions updates currently can't synchronize from Dataverse to Human Resources.</span></span> 

## <a name="leave-and-absence-tables"></a><span data-ttu-id="1f534-200">Tablas de permisos y ausencias</span><span class="sxs-lookup"><span data-stu-id="1f534-200">Leave and absence tables</span></span>

| <span data-ttu-id="1f534-201">Nombre</span><span class="sxs-lookup"><span data-stu-id="1f534-201">Name</span></span> | <span data-ttu-id="1f534-202">Tabla</span><span class="sxs-lookup"><span data-stu-id="1f534-202">Table</span></span> |
| --- | --- |
| <span data-ttu-id="1f534-203">Transacción bancaria de bajas</span><span class="sxs-lookup"><span data-stu-id="1f534-203">Leave Bank Transaction</span></span> | <span data-ttu-id="1f534-204">cdm_leavebanktransaction</span><span class="sxs-lookup"><span data-stu-id="1f534-204">cdm_leavebanktransaction</span></span> |
| <span data-ttu-id="1f534-205">Inscripción de baja</span><span class="sxs-lookup"><span data-stu-id="1f534-205">Leave Enrollment</span></span> | <span data-ttu-id="1f534-206">cdm_leaveenrollment</span><span class="sxs-lookup"><span data-stu-id="1f534-206">cdm_leaveenrollment</span></span> |
| <span data-ttu-id="1f534-207">Plan de bajas</span><span class="sxs-lookup"><span data-stu-id="1f534-207">Leave Plan</span></span> | <span data-ttu-id="1f534-208">cdm_leaveplan</span><span class="sxs-lookup"><span data-stu-id="1f534-208">cdm_leaveplan</span></span> |
| <span data-ttu-id="1f534-209">Solicitud de baja</span><span class="sxs-lookup"><span data-stu-id="1f534-209">Leave Request</span></span> | <span data-ttu-id="1f534-210">cdm_leaverequest</span><span class="sxs-lookup"><span data-stu-id="1f534-210">cdm_leaverequest</span></span> |
| <span data-ttu-id="1f534-211">Detalles de solicitud de baja</span><span class="sxs-lookup"><span data-stu-id="1f534-211">Leave Request Detail</span></span> | <span data-ttu-id="1f534-212">cdm_leaverequestdetail</span><span class="sxs-lookup"><span data-stu-id="1f534-212">cdm_leaverequestdetail</span></span> |
| <span data-ttu-id="1f534-213">Tipo de baja</span><span class="sxs-lookup"><span data-stu-id="1f534-213">Leave Type</span></span> | <span data-ttu-id="1f534-214">cdm_leavetype</span><span class="sxs-lookup"><span data-stu-id="1f534-214">cdm_leavetype</span></span> |
| <span data-ttu-id="1f534-215">Código de auditoría de tipo de baja</span><span class="sxs-lookup"><span data-stu-id="1f534-215">Leave Type Reason Code</span></span> | <span data-ttu-id="1f534-216">cdm_leavetypereasoncode</span><span class="sxs-lookup"><span data-stu-id="1f534-216">cdm_leavetypereasoncode</span></span> |

## <a name="payroll-tables"></a><span data-ttu-id="1f534-217">Tablas de nómina</span><span class="sxs-lookup"><span data-stu-id="1f534-217">Payroll tables</span></span>

| <span data-ttu-id="1f534-218">Nombre</span><span class="sxs-lookup"><span data-stu-id="1f534-218">Name</span></span> | <span data-ttu-id="1f534-219">Tabla</span><span class="sxs-lookup"><span data-stu-id="1f534-219">Table</span></span> |
| --- | --- |
| <span data-ttu-id="1f534-220">Ciclo de pago</span><span class="sxs-lookup"><span data-stu-id="1f534-220">Pay Cycle</span></span> | <span data-ttu-id="1f534-221">cdm_paycycle</span><span class="sxs-lookup"><span data-stu-id="1f534-221">cdm_paycycle</span></span> |
| <span data-ttu-id="1f534-222">Período de pago</span><span class="sxs-lookup"><span data-stu-id="1f534-222">Pay Period</span></span> | <span data-ttu-id="1f534-223">cdm_payperiod</span><span class="sxs-lookup"><span data-stu-id="1f534-223">cdm_payperiod</span></span> |
| <span data-ttu-id="1f534-224">Código de ganancias de nómina</span><span class="sxs-lookup"><span data-stu-id="1f534-224">Payroll Earning Code</span></span> | <span data-ttu-id="1f534-225">cdm_payrollearningcode</span><span class="sxs-lookup"><span data-stu-id="1f534-225">cdm_payrollearningcode</span></span> |
| <span data-ttu-id="1f534-226">Desembolso de cuenta bancaria</span><span class="sxs-lookup"><span data-stu-id="1f534-226">Bank Account Disbursement</span></span> | <span data-ttu-id="1f534-227">cdm_bankaccountdisbursement</span><span class="sxs-lookup"><span data-stu-id="1f534-227">cdm_bankaccountdisbursement</span></span> |
| <span data-ttu-id="1f534-228">Región de impuestos</span><span class="sxs-lookup"><span data-stu-id="1f534-228">Tax Region</span></span> | <span data-ttu-id="1f534-229">cdm_taxregion</span><span class="sxs-lookup"><span data-stu-id="1f534-229">cdm_taxregion</span></span> |

## <a name="worker-tables"></a><span data-ttu-id="1f534-230">Tablas de trabajador</span><span class="sxs-lookup"><span data-stu-id="1f534-230">Worker tables</span></span>

| <span data-ttu-id="1f534-231">Nombre</span><span class="sxs-lookup"><span data-stu-id="1f534-231">Name</span></span> | <span data-ttu-id="1f534-232">Tabla</span><span class="sxs-lookup"><span data-stu-id="1f534-232">Table</span></span> |
| --- | --- |
| <span data-ttu-id="1f534-233">Trabajador</span><span class="sxs-lookup"><span data-stu-id="1f534-233">Worker</span></span> | <span data-ttu-id="1f534-234">cdm_worker</span><span class="sxs-lookup"><span data-stu-id="1f534-234">cdm_worker</span></span> |
| <span data-ttu-id="1f534-235">Dirección del trabajador</span><span class="sxs-lookup"><span data-stu-id="1f534-235">Worker Address</span></span> | <span data-ttu-id="1f534-236">cdm_workeraddress</span><span class="sxs-lookup"><span data-stu-id="1f534-236">cdm_workeraddress</span></span> |
| <span data-ttu-id="1f534-237">Detalle personal del trabajador</span><span class="sxs-lookup"><span data-stu-id="1f534-237">Worker Personal Detail</span></span> | <span data-ttu-id="1f534-238">cdm_workerpersonaldetail</span><span class="sxs-lookup"><span data-stu-id="1f534-238">cdm_workerpersonaldetail</span></span> |
| <span data-ttu-id="1f534-239">Número de identificación de persona del trabajador</span><span class="sxs-lookup"><span data-stu-id="1f534-239">Worker Person Identification Number</span></span> | <span data-ttu-id="1f534-240">cdm_workerpersonidentificationnumber</span><span class="sxs-lookup"><span data-stu-id="1f534-240">cdm_workerpersonidentificationnumber</span></span> |
| <span data-ttu-id="1f534-241">Tipo de identificación de persona del trabajador</span><span class="sxs-lookup"><span data-stu-id="1f534-241">Worker Person Identification Type</span></span> | <span data-ttu-id="1f534-242">cdm_workerpersonidentificationtype</span><span class="sxs-lookup"><span data-stu-id="1f534-242">cdm_workerpersonidentificationtype</span></span> |
| <span data-ttu-id="1f534-243">Calendario de trabajo</span><span class="sxs-lookup"><span data-stu-id="1f534-243">Work Calendar</span></span> | <span data-ttu-id="1f534-244">cdm_workcalendar</span><span class="sxs-lookup"><span data-stu-id="1f534-244">cdm_workcalendar</span></span> |
| <span data-ttu-id="1f534-245">Día de calendario de trabajo</span><span class="sxs-lookup"><span data-stu-id="1f534-245">Work Calendar Day</span></span> | <span data-ttu-id="1f534-246">cdm_workcalendarday</span><span class="sxs-lookup"><span data-stu-id="1f534-246">cdm_workcalendarday</span></span> |
| <span data-ttu-id="1f534-247">Vacaciones calendario de trabajo</span><span class="sxs-lookup"><span data-stu-id="1f534-247">Work Calendar Holiday</span></span> |<span data-ttu-id="1f534-248">cdm_workcalendarholiday</span><span class="sxs-lookup"><span data-stu-id="1f534-248">cdm_workcalendarholiday</span></span> |
| <span data-ttu-id="1f534-249">Línea de festivo del calendario de trabajo</span><span class="sxs-lookup"><span data-stu-id="1f534-249">Work Calendar Holiday Line</span></span> | <span data-ttu-id="1f534-250">cdm_workcalendarholidayline</span><span class="sxs-lookup"><span data-stu-id="1f534-250">cdm_workcalendarholidayline</span></span> |
| <span data-ttu-id="1f534-251">Intervalo de tiempo del calendario de trabajo</span><span class="sxs-lookup"><span data-stu-id="1f534-251">Work Calendar Time Interval</span></span> | <span data-ttu-id="1f534-252">cdm_workcalendartimeinterval (No habilitada para la compatibilidad de campos personalizados)</span><span class="sxs-lookup"><span data-stu-id="1f534-252">cdm_workcalendartimeinterval (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="1f534-253">Cuenta bancaria de trabajador</span><span class="sxs-lookup"><span data-stu-id="1f534-253">Worker Bank Account</span></span> | <span data-ttu-id="1f534-254">cdm_workerbankaccount</span><span class="sxs-lookup"><span data-stu-id="1f534-254">cdm_workerbankaccount</span></span> |

## <a name="worker-setup-tables"></a><span data-ttu-id="1f534-255">Tablas de configuración de trabajador</span><span class="sxs-lookup"><span data-stu-id="1f534-255">Worker setup tables</span></span>

| <span data-ttu-id="1f534-256">Nombre</span><span class="sxs-lookup"><span data-stu-id="1f534-256">Name</span></span> | <span data-ttu-id="1f534-257">Tabla</span><span class="sxs-lookup"><span data-stu-id="1f534-257">Table</span></span> |
| --- | --- |
| <span data-ttu-id="1f534-258">Estado de excombatiente</span><span class="sxs-lookup"><span data-stu-id="1f534-258">Veteran Status</span></span> | <span data-ttu-id="1f534-259">cdm_veteranstatus</span><span class="sxs-lookup"><span data-stu-id="1f534-259">cdm_veteranstatus</span></span> |
| <span data-ttu-id="1f534-260">Origen étnico</span><span class="sxs-lookup"><span data-stu-id="1f534-260">Ethnic Origin</span></span> | <span data-ttu-id="1f534-261">cdm_ethnicorigin</span><span class="sxs-lookup"><span data-stu-id="1f534-261">cdm_ethnicorigin</span></span> |
| <span data-ttu-id="1f534-262">Código de motivo</span><span class="sxs-lookup"><span data-stu-id="1f534-262">Reason Code</span></span> | <span data-ttu-id="1f534-263">cdm_reasoncode</span><span class="sxs-lookup"><span data-stu-id="1f534-263">cdm_reasoncode</span></span> |
| <span data-ttu-id="1f534-264">Agencia emisora de identificación de personas</span><span class="sxs-lookup"><span data-stu-id="1f534-264">Person Identification Issuing Agency</span></span> | <span data-ttu-id="1f534-265">cdm_personidentificationissuingagency</span><span class="sxs-lookup"><span data-stu-id="1f534-265">cdm_personidentificationissuingagency</span></span> |

## <a name="competency-tables"></a><span data-ttu-id="1f534-266">Tablas de competencia</span><span class="sxs-lookup"><span data-stu-id="1f534-266">Competency tables</span></span>

| <span data-ttu-id="1f534-267">Nombre</span><span class="sxs-lookup"><span data-stu-id="1f534-267">Name</span></span> | <span data-ttu-id="1f534-268">Tabla</span><span class="sxs-lookup"><span data-stu-id="1f534-268">Table</span></span> |
| --- | --- |
| <span data-ttu-id="1f534-269">Tipo de aptitud</span><span class="sxs-lookup"><span data-stu-id="1f534-269">Skill Type</span></span> | <span data-ttu-id="1f534-270">cdm_skilltype</span><span class="sxs-lookup"><span data-stu-id="1f534-270">cdm_skilltype</span></span> |

## <a name="table-relationship-models"></a><span data-ttu-id="1f534-271">Modelos de relación de tabla</span><span class="sxs-lookup"><span data-stu-id="1f534-271">Table relationship models</span></span>

### <a name="worker"></a><span data-ttu-id="1f534-272">Trabajador</span><span class="sxs-lookup"><span data-stu-id="1f534-272">Worker</span></span>

![Trabajador](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a><span data-ttu-id="1f534-274">Trabajo y puesto de trabajo</span><span class="sxs-lookup"><span data-stu-id="1f534-274">Job and Job Position</span></span>

![Trabajo y puesto de trabajo](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a><span data-ttu-id="1f534-276">Prestaciones</span><span class="sxs-lookup"><span data-stu-id="1f534-276">Benefits</span></span>

![Prestaciones](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a><span data-ttu-id="1f534-278">Compensación</span><span class="sxs-lookup"><span data-stu-id="1f534-278">Compensation</span></span>

![Compensación](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a><span data-ttu-id="1f534-280">Dejar</span><span class="sxs-lookup"><span data-stu-id="1f534-280">Leave</span></span>

![Dejar](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a><span data-ttu-id="1f534-282">Calendario de trabajo</span><span class="sxs-lookup"><span data-stu-id="1f534-282">Work Calendar</span></span>

![Calendario de trabajo](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a><span data-ttu-id="1f534-284">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1f534-284">See also</span></span>

[<span data-ttu-id="1f534-285">Elegir una tecnología de integración de datos</span><span class="sxs-lookup"><span data-stu-id="1f534-285">Choose a data integration technology</span></span>](hr-admin-integration-choose-technology.md)<br>
[<span data-ttu-id="1f534-286">Configurar la integración de Dataverse</span><span class="sxs-lookup"><span data-stu-id="1f534-286">Configure Dataverse integration</span></span>](hr-admin-integration-common-data-service.md)<br>
[<span data-ttu-id="1f534-287">Configurar tablas virtuales de Dataverse</span><span class="sxs-lookup"><span data-stu-id="1f534-287">Configure Dataverse virtual tables</span></span>](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[<span data-ttu-id="1f534-288">Preguntas frecuentes sobre tablas virtuales para Human Resources</span><span class="sxs-lookup"><span data-stu-id="1f534-288">Human Resources virtual tables FAQ</span></span>](hr-admin-virtual-entity-faq.md)<br>
[<span data-ttu-id="1f534-289">¿Qué es Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="1f534-289">What is Microsoft Dataverse?</span></span>](/powerapps/maker/data-platform/data-platform-intro)<br>
[<span data-ttu-id="1f534-290">Actualizaciones de terminología</span><span class="sxs-lookup"><span data-stu-id="1f534-290">Terminology updates</span></span>](/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]