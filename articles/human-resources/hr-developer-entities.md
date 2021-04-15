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
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e316cda9b9c5361c0a2837e7ed6c050e76cc39b9
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5793618"
---
# <a name="dataverse-tables"></a><span data-ttu-id="2d3bc-103">Tablas de Dataverse</span><span class="sxs-lookup"><span data-stu-id="2d3bc-103">Dataverse tables</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="2d3bc-104">Microsoft Dynamics 365 Human Resources usa Dataverse para habilitar escenarios de extensibilidad e integración.</span><span class="sxs-lookup"><span data-stu-id="2d3bc-104">Microsoft Dynamics 365 Human Resources uses Dataverse to enable extensibility and integration scenarios.</span></span>

> [!NOTE]
> <span data-ttu-id="2d3bc-105">Las entidades de Human Resources se corresponden con tablas de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="2d3bc-105">Human Resources entities correspond to Dataverse tables.</span></span> <span data-ttu-id="2d3bc-106">Para obtener más información sobre Dataverse (antes denominado Common Data Service) y actualizaciones de terminología, consulte [¿Qué es Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="2d3bc-106">For more information about Dataverse (formerly Common Data Service) and terminology updates, see [What is Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)</span></span>

<span data-ttu-id="2d3bc-107">Están disponibles las siguientes entidades de Dataverse basadas en entidades de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2d3bc-107">The following Dataverse tables are available based on Human Resources entities.</span></span>

## <a name="benefit-tables"></a><span data-ttu-id="2d3bc-108">Tablas de prestaciones</span><span class="sxs-lookup"><span data-stu-id="2d3bc-108">Benefit tables</span></span>

| <span data-ttu-id="2d3bc-109">Nombre</span><span class="sxs-lookup"><span data-stu-id="2d3bc-109">Name</span></span> | <span data-ttu-id="2d3bc-110">Tabla</span><span class="sxs-lookup"><span data-stu-id="2d3bc-110">Table</span></span> |
| --- | --- |
| <span data-ttu-id="2d3bc-111">Frecuencia de cálculo de la prestación</span><span class="sxs-lookup"><span data-stu-id="2d3bc-111">Benefit Calculation Frequency</span></span> | <span data-ttu-id="2d3bc-112">cdm_benefitcalculationfrequency</span><span class="sxs-lookup"><span data-stu-id="2d3bc-112">cdm_benefitcalculationfrequency</span></span> |
| <span data-ttu-id="2d3bc-113">Período de pago de la frecuencia de cálculo de prestación</span><span class="sxs-lookup"><span data-stu-id="2d3bc-113">Benefit Calculation Frequency Pay Period</span></span> | <span data-ttu-id="2d3bc-114">cdm_benefitcalculationfrequencypayperiod</span><span class="sxs-lookup"><span data-stu-id="2d3bc-114">cdm_benefitcalculationfrequencypayperiod</span></span> |
| <span data-ttu-id="2d3bc-115">Índice de cálculo de la prestación</span><span class="sxs-lookup"><span data-stu-id="2d3bc-115">Benefit Calculation Rate</span></span> | <span data-ttu-id="2d3bc-116">cdm_benefitcalculationrate</span><span class="sxs-lookup"><span data-stu-id="2d3bc-116">cdm_benefitcalculationrate</span></span> |
| <span data-ttu-id="2d3bc-117">Detalle de índice de cálculo de la prestación</span><span class="sxs-lookup"><span data-stu-id="2d3bc-117">Benefit Calculation Rate Detail</span></span> | <span data-ttu-id="2d3bc-118">cdm_benefitcalculationratedetail</span><span class="sxs-lookup"><span data-stu-id="2d3bc-118">cdm_benefitcalculationratedetail</span></span> |
| <span data-ttu-id="2d3bc-119">Opción de prestación</span><span class="sxs-lookup"><span data-stu-id="2d3bc-119">Benefit Option</span></span> | <span data-ttu-id="2d3bc-120">cdm_benefitoption</span><span class="sxs-lookup"><span data-stu-id="2d3bc-120">cdm_benefitoption</span></span> |
| <span data-ttu-id="2d3bc-121">Plan de prestaciones</span><span class="sxs-lookup"><span data-stu-id="2d3bc-121">Benefit Plan</span></span> | <span data-ttu-id="2d3bc-122">cdm_benefitplan (No habilitada para la compatibilidad de campos personalizados)</span><span class="sxs-lookup"><span data-stu-id="2d3bc-122">cdm_benefitplan (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="2d3bc-123">Tipo de prestación</span><span class="sxs-lookup"><span data-stu-id="2d3bc-123">Benefit Type</span></span> | <span data-ttu-id="2d3bc-124">cdm_benefittype</span><span class="sxs-lookup"><span data-stu-id="2d3bc-124">cdm_benefittype</span></span> |

## <a name="business-process-tasks-tables"></a><span data-ttu-id="2d3bc-125">Tablas de tareas de procesos de negocio</span><span class="sxs-lookup"><span data-stu-id="2d3bc-125">Business process tasks tables</span></span>

| <span data-ttu-id="2d3bc-126">Nombre</span><span class="sxs-lookup"><span data-stu-id="2d3bc-126">Name</span></span> | <span data-ttu-id="2d3bc-127">Tabla</span><span class="sxs-lookup"><span data-stu-id="2d3bc-127">Table</span></span> |
| --- | --- |
| <span data-ttu-id="2d3bc-128">Calendario de proceso de negocio</span><span class="sxs-lookup"><span data-stu-id="2d3bc-128">Business Process Calendar</span></span> | <span data-ttu-id="2d3bc-129">cdm_businessprocesscalendar</span><span class="sxs-lookup"><span data-stu-id="2d3bc-129">cdm_businessprocesscalendar</span></span> |
| <span data-ttu-id="2d3bc-130">Asignación de grupo de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="2d3bc-130">Business Process Group Assignment</span></span> | <span data-ttu-id="2d3bc-131">cdm_businessprocessgroupassignment</span><span class="sxs-lookup"><span data-stu-id="2d3bc-131">cdm_businessprocessgroupassignment</span></span> |
| <span data-ttu-id="2d3bc-132">Grupo de tareas de biblioteca de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="2d3bc-132">Business Process Library Task Group</span></span> | <span data-ttu-id="2d3bc-133">cdm_businessprocesslibrarytaskgroup</span><span class="sxs-lookup"><span data-stu-id="2d3bc-133">cdm_businessprocesslibrarytaskgroup</span></span> |
| <span data-ttu-id="2d3bc-134">Etapa de proceso empresarial</span><span class="sxs-lookup"><span data-stu-id="2d3bc-134">Business Process Stage</span></span> | <span data-ttu-id="2d3bc-135">cdm_businessprocessstage</span><span class="sxs-lookup"><span data-stu-id="2d3bc-135">cdm_businessprocessstage</span></span> |
| <span data-ttu-id="2d3bc-136">Encabezado de plantilla de lista de comprobación</span><span class="sxs-lookup"><span data-stu-id="2d3bc-136">Checklist Template Header</span></span> | <span data-ttu-id="2d3bc-137">cdm_businessprocesstemplateheader</span><span class="sxs-lookup"><span data-stu-id="2d3bc-137">cdm_businessprocesstemplateheader</span></span> |
| <span data-ttu-id="2d3bc-138">Tarea de plantilla de lista de comprobación</span><span class="sxs-lookup"><span data-stu-id="2d3bc-138">Checklist Template Task</span></span> | <span data-ttu-id="2d3bc-139">cdm_businessprocesstemplatetask</span><span class="sxs-lookup"><span data-stu-id="2d3bc-139">cdm_businessprocesstemplatetask</span></span> |

## <a name="compensation-tables"></a><span data-ttu-id="2d3bc-140">Tablas de compensación</span><span class="sxs-lookup"><span data-stu-id="2d3bc-140">Compensation tables</span></span>

| <span data-ttu-id="2d3bc-141">Nombre</span><span class="sxs-lookup"><span data-stu-id="2d3bc-141">Name</span></span> | <span data-ttu-id="2d3bc-142">Tabla</span><span class="sxs-lookup"><span data-stu-id="2d3bc-142">Table</span></span> |
| --- | --- |
| <span data-ttu-id="2d3bc-143">Plan fijo de compensación</span><span class="sxs-lookup"><span data-stu-id="2d3bc-143">Compensation Fixed Plan</span></span> | <span data-ttu-id="2d3bc-144">cdm_compensationfixedplan</span><span class="sxs-lookup"><span data-stu-id="2d3bc-144">cdm_compensationfixedplan</span></span> |
| <span data-ttu-id="2d3bc-145">Cuadrícula de compensación</span><span class="sxs-lookup"><span data-stu-id="2d3bc-145">Compensation Grid</span></span> | <span data-ttu-id="2d3bc-146">cdm_compensationgrid</span><span class="sxs-lookup"><span data-stu-id="2d3bc-146">cdm_compensationgrid</span></span> |
| <span data-ttu-id="2d3bc-147">Nivel de compensación</span><span class="sxs-lookup"><span data-stu-id="2d3bc-147">Compensation Level</span></span> | <span data-ttu-id="2d3bc-148">cdm_compensationlevel</span><span class="sxs-lookup"><span data-stu-id="2d3bc-148">cdm_compensationlevel</span></span> |
| <span data-ttu-id="2d3bc-149">Frecuencia de pago de compensación</span><span class="sxs-lookup"><span data-stu-id="2d3bc-149">Compensation Pay Frequency</span></span> | <span data-ttu-id="2d3bc-150">cdm_compensationpayfrequency</span><span class="sxs-lookup"><span data-stu-id="2d3bc-150">cdm_compensationpayfrequency</span></span> |
| <span data-ttu-id="2d3bc-151">Configuración de puntos de referencia de compensación</span><span class="sxs-lookup"><span data-stu-id="2d3bc-151">Compensation Reference Point Setup</span></span> | <span data-ttu-id="2d3bc-152">cdm_compensationreferencepointsetup</span><span class="sxs-lookup"><span data-stu-id="2d3bc-152">cdm_compensationreferencepointsetup</span></span> |
| <span data-ttu-id="2d3bc-153">Línea de configuración de puntos de referencia de compensación</span><span class="sxs-lookup"><span data-stu-id="2d3bc-153">Compensation Reference Point Setup Line</span></span> | <span data-ttu-id="2d3bc-154">cdm_compensationreferencepointsetupline</span><span class="sxs-lookup"><span data-stu-id="2d3bc-154">cdm_compensationreferencepointsetupline</span></span> |
| <span data-ttu-id="2d3bc-155">Región de compensación</span><span class="sxs-lookup"><span data-stu-id="2d3bc-155">Compensation Region</span></span> | <span data-ttu-id="2d3bc-156">cdm_compensationregion</span><span class="sxs-lookup"><span data-stu-id="2d3bc-156">cdm_compensationregion</span></span> |
| <span data-ttu-id="2d3bc-157">Estructura de compensación</span><span class="sxs-lookup"><span data-stu-id="2d3bc-157">Compensation Structure</span></span> | <span data-ttu-id="2d3bc-158">cdm_compensationstructure</span><span class="sxs-lookup"><span data-stu-id="2d3bc-158">cdm_compensationstructure</span></span> |
| <span data-ttu-id="2d3bc-159">Plan de compensación variable</span><span class="sxs-lookup"><span data-stu-id="2d3bc-159">Compensation Variable Plan</span></span> | <span data-ttu-id="2d3bc-160">cdm_compensationvariableplan</span><span class="sxs-lookup"><span data-stu-id="2d3bc-160">cdm_compensationvariableplan</span></span> |
| <span data-ttu-id="2d3bc-161">Nivel de plan de compensación variable</span><span class="sxs-lookup"><span data-stu-id="2d3bc-161">Compensation Variable Plan Level</span></span> | <span data-ttu-id="2d3bc-162">cdm_compensationvariableplanlevel</span><span class="sxs-lookup"><span data-stu-id="2d3bc-162">cdm_compensationvariableplanlevel</span></span> |
| <span data-ttu-id="2d3bc-163">Tipo de plan de compensación variable</span><span class="sxs-lookup"><span data-stu-id="2d3bc-163">Compensation Variable Plan Type</span></span> | <span data-ttu-id="2d3bc-164">cdm_compensationvariableplantype</span><span class="sxs-lookup"><span data-stu-id="2d3bc-164">cdm_compensationvariableplantype</span></span> |
| <span data-ttu-id="2d3bc-165">Evento de compensación fija</span><span class="sxs-lookup"><span data-stu-id="2d3bc-165">Fixed Compensation Event</span></span> | <span data-ttu-id="2d3bc-166">cdm_fixedcompensationevent</span><span class="sxs-lookup"><span data-stu-id="2d3bc-166">cdm_fixedcompensationevent</span></span> |
| <span data-ttu-id="2d3bc-167">Regla de atribución</span><span class="sxs-lookup"><span data-stu-id="2d3bc-167">Vesting Rule</span></span> | <span data-ttu-id="2d3bc-168">cdm_vestingrule</span><span class="sxs-lookup"><span data-stu-id="2d3bc-168">cdm_vestingrule</span></span> |
| <span data-ttu-id="2d3bc-169">Compensación fija de trabajador</span><span class="sxs-lookup"><span data-stu-id="2d3bc-169">Worker Fixed Compensation</span></span> | <span data-ttu-id="2d3bc-170">cdm_workerfixedcompensation</span><span class="sxs-lookup"><span data-stu-id="2d3bc-170">cdm_workerfixedcompensation</span></span> |

## <a name="organization-tables"></a><span data-ttu-id="2d3bc-171">Tablas de organización</span><span class="sxs-lookup"><span data-stu-id="2d3bc-171">Organization tables</span></span>

| <span data-ttu-id="2d3bc-172">Nombre</span><span class="sxs-lookup"><span data-stu-id="2d3bc-172">Name</span></span> | <span data-ttu-id="2d3bc-173">Tabla</span><span class="sxs-lookup"><span data-stu-id="2d3bc-173">Table</span></span> |
| --- | --- |
| <span data-ttu-id="2d3bc-174">Departamento</span><span class="sxs-lookup"><span data-stu-id="2d3bc-174">Department</span></span> | <span data-ttu-id="2d3bc-175">cdm_department</span><span class="sxs-lookup"><span data-stu-id="2d3bc-175">cdm_department</span></span> |
| <span data-ttu-id="2d3bc-176">Empleo</span><span class="sxs-lookup"><span data-stu-id="2d3bc-176">Employment</span></span> | <span data-ttu-id="2d3bc-177">cdm_employment</span><span class="sxs-lookup"><span data-stu-id="2d3bc-177">cdm_employment</span></span> |
| <span data-ttu-id="2d3bc-178">Empresa</span><span class="sxs-lookup"><span data-stu-id="2d3bc-178">Company</span></span> | <span data-ttu-id="2d3bc-179">cdm_company</span><span class="sxs-lookup"><span data-stu-id="2d3bc-179">cdm_company</span></span> |
| <span data-ttu-id="2d3bc-180">Puesto</span><span class="sxs-lookup"><span data-stu-id="2d3bc-180">Job</span></span> | <span data-ttu-id="2d3bc-181">cdm_job</span><span class="sxs-lookup"><span data-stu-id="2d3bc-181">cdm_job</span></span> |
| <span data-ttu-id="2d3bc-182">Función de trabajo</span><span class="sxs-lookup"><span data-stu-id="2d3bc-182">Job Function</span></span> | <span data-ttu-id="2d3bc-183">cdm_jobfunction</span><span class="sxs-lookup"><span data-stu-id="2d3bc-183">cdm_jobfunction</span></span> |
| <span data-ttu-id="2d3bc-184">Puesto de trabajo</span><span class="sxs-lookup"><span data-stu-id="2d3bc-184">Job Position</span></span> | <span data-ttu-id="2d3bc-185">cdm_jobposition</span><span class="sxs-lookup"><span data-stu-id="2d3bc-185">cdm_jobposition</span></span> |
| <span data-ttu-id="2d3bc-186">Tipo de puesto</span><span class="sxs-lookup"><span data-stu-id="2d3bc-186">Position Type</span></span> | <span data-ttu-id="2d3bc-187">cdm_positiontype</span><span class="sxs-lookup"><span data-stu-id="2d3bc-187">cdm_positiontype</span></span> |
| <span data-ttu-id="2d3bc-188">Asignación del trabajador del puesto</span><span class="sxs-lookup"><span data-stu-id="2d3bc-188">Position Worker Assignment</span></span> | <span data-ttu-id="2d3bc-189">cdm_positionworkerassignmentmap</span><span class="sxs-lookup"><span data-stu-id="2d3bc-189">cdm_positionworkerassignmentmap</span></span> |
| <span data-ttu-id="2d3bc-190">Dimensión de puesto de trabajo</span><span class="sxs-lookup"><span data-stu-id="2d3bc-190">Job Position Dimension</span></span> | <span data-ttu-id="2d3bc-191">cdm_jobpositiondimension</span><span class="sxs-lookup"><span data-stu-id="2d3bc-191">cdm_jobpositiondimension</span></span>|
| <span data-ttu-id="2d3bc-192">Tipo de trabajo</span><span class="sxs-lookup"><span data-stu-id="2d3bc-192">Job Type</span></span> | <span data-ttu-id="2d3bc-193">cdm_jobtype</span><span class="sxs-lookup"><span data-stu-id="2d3bc-193">cdm_jobtype</span></span> |
| <span data-ttu-id="2d3bc-194">Idioma</span><span class="sxs-lookup"><span data-stu-id="2d3bc-194">Language</span></span> | <span data-ttu-id="2d3bc-195">cdm_language</span><span class="sxs-lookup"><span data-stu-id="2d3bc-195">cdm_language</span></span> |
| <span data-ttu-id="2d3bc-196">Cargo</span><span class="sxs-lookup"><span data-stu-id="2d3bc-196">Title</span></span> | <span data-ttu-id="2d3bc-197">cdm_title</span><span class="sxs-lookup"><span data-stu-id="2d3bc-197">cdm_title</span></span> |

> [!NOTE]
> <span data-ttu-id="2d3bc-198">Dimensiones financieras para **Tipo de puesto**, **Asignación de puesto de trabajador** y **Empleo** proporcionan integración unidireccional a Dataverse.</span><span class="sxs-lookup"><span data-stu-id="2d3bc-198">Financial dimensions for **Position Type**, **Position Worker Assignment**, and **Employment** provide one-direction integration to Dataverse.</span></span> <span data-ttu-id="2d3bc-199">Actualmente las actualizaciones de dimensiones financieras no se pueden sincronizar desde Dataverse a Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2d3bc-199">Financial dimensions updates currently can't synchronize from Dataverse to Human Resources.</span></span> 

## <a name="leave-and-absence-tables"></a><span data-ttu-id="2d3bc-200">Tablas de permisos y ausencias</span><span class="sxs-lookup"><span data-stu-id="2d3bc-200">Leave and absence tables</span></span>

| <span data-ttu-id="2d3bc-201">Nombre</span><span class="sxs-lookup"><span data-stu-id="2d3bc-201">Name</span></span> | <span data-ttu-id="2d3bc-202">Tabla</span><span class="sxs-lookup"><span data-stu-id="2d3bc-202">Table</span></span> |
| --- | --- |
| <span data-ttu-id="2d3bc-203">Transacción bancaria de bajas</span><span class="sxs-lookup"><span data-stu-id="2d3bc-203">Leave Bank Transaction</span></span> | <span data-ttu-id="2d3bc-204">cdm_leavebanktransaction</span><span class="sxs-lookup"><span data-stu-id="2d3bc-204">cdm_leavebanktransaction</span></span> |
| <span data-ttu-id="2d3bc-205">Inscripción de baja</span><span class="sxs-lookup"><span data-stu-id="2d3bc-205">Leave Enrollment</span></span> | <span data-ttu-id="2d3bc-206">cdm_leaveenrollment</span><span class="sxs-lookup"><span data-stu-id="2d3bc-206">cdm_leaveenrollment</span></span> |
| <span data-ttu-id="2d3bc-207">Plan de bajas</span><span class="sxs-lookup"><span data-stu-id="2d3bc-207">Leave Plan</span></span> | <span data-ttu-id="2d3bc-208">cdm_leaveplan</span><span class="sxs-lookup"><span data-stu-id="2d3bc-208">cdm_leaveplan</span></span> |
| <span data-ttu-id="2d3bc-209">Solicitud de baja</span><span class="sxs-lookup"><span data-stu-id="2d3bc-209">Leave Request</span></span> | <span data-ttu-id="2d3bc-210">cdm_leaverequest</span><span class="sxs-lookup"><span data-stu-id="2d3bc-210">cdm_leaverequest</span></span> |
| <span data-ttu-id="2d3bc-211">Detalles de solicitud de baja</span><span class="sxs-lookup"><span data-stu-id="2d3bc-211">Leave Request Detail</span></span> | <span data-ttu-id="2d3bc-212">cdm_leaverequestdetail</span><span class="sxs-lookup"><span data-stu-id="2d3bc-212">cdm_leaverequestdetail</span></span> |
| <span data-ttu-id="2d3bc-213">Tipo de baja</span><span class="sxs-lookup"><span data-stu-id="2d3bc-213">Leave Type</span></span> | <span data-ttu-id="2d3bc-214">cdm_leavetype</span><span class="sxs-lookup"><span data-stu-id="2d3bc-214">cdm_leavetype</span></span> |
| <span data-ttu-id="2d3bc-215">Código de auditoría de tipo de baja</span><span class="sxs-lookup"><span data-stu-id="2d3bc-215">Leave Type Reason Code</span></span> | <span data-ttu-id="2d3bc-216">cdm_leavetypereasoncode</span><span class="sxs-lookup"><span data-stu-id="2d3bc-216">cdm_leavetypereasoncode</span></span> |

## <a name="payroll-tables"></a><span data-ttu-id="2d3bc-217">Tablas de nómina</span><span class="sxs-lookup"><span data-stu-id="2d3bc-217">Payroll tables</span></span>

| <span data-ttu-id="2d3bc-218">Nombre</span><span class="sxs-lookup"><span data-stu-id="2d3bc-218">Name</span></span> | <span data-ttu-id="2d3bc-219">Tabla</span><span class="sxs-lookup"><span data-stu-id="2d3bc-219">Table</span></span> |
| --- | --- |
| <span data-ttu-id="2d3bc-220">Ciclo de pago</span><span class="sxs-lookup"><span data-stu-id="2d3bc-220">Pay Cycle</span></span> | <span data-ttu-id="2d3bc-221">cdm_paycycle</span><span class="sxs-lookup"><span data-stu-id="2d3bc-221">cdm_paycycle</span></span> |
| <span data-ttu-id="2d3bc-222">Período de pago</span><span class="sxs-lookup"><span data-stu-id="2d3bc-222">Pay Period</span></span> | <span data-ttu-id="2d3bc-223">cdm_payperiod</span><span class="sxs-lookup"><span data-stu-id="2d3bc-223">cdm_payperiod</span></span> |
| <span data-ttu-id="2d3bc-224">Código de ganancias de nómina</span><span class="sxs-lookup"><span data-stu-id="2d3bc-224">Payroll Earning Code</span></span> | <span data-ttu-id="2d3bc-225">cdm_payrollearningcode</span><span class="sxs-lookup"><span data-stu-id="2d3bc-225">cdm_payrollearningcode</span></span> |
| <span data-ttu-id="2d3bc-226">Desembolso de cuenta bancaria</span><span class="sxs-lookup"><span data-stu-id="2d3bc-226">Bank Account Disbursement</span></span> | <span data-ttu-id="2d3bc-227">cdm_bankaccountdisbursement</span><span class="sxs-lookup"><span data-stu-id="2d3bc-227">cdm_bankaccountdisbursement</span></span> |
| <span data-ttu-id="2d3bc-228">Región de impuestos</span><span class="sxs-lookup"><span data-stu-id="2d3bc-228">Tax Region</span></span> | <span data-ttu-id="2d3bc-229">cdm_taxregion</span><span class="sxs-lookup"><span data-stu-id="2d3bc-229">cdm_taxregion</span></span> |

## <a name="worker-tables"></a><span data-ttu-id="2d3bc-230">Tablas de trabajador</span><span class="sxs-lookup"><span data-stu-id="2d3bc-230">Worker tables</span></span>

| <span data-ttu-id="2d3bc-231">Nombre</span><span class="sxs-lookup"><span data-stu-id="2d3bc-231">Name</span></span> | <span data-ttu-id="2d3bc-232">Tabla</span><span class="sxs-lookup"><span data-stu-id="2d3bc-232">Table</span></span> |
| --- | --- |
| <span data-ttu-id="2d3bc-233">Trabajador</span><span class="sxs-lookup"><span data-stu-id="2d3bc-233">Worker</span></span> | <span data-ttu-id="2d3bc-234">cdm_worker</span><span class="sxs-lookup"><span data-stu-id="2d3bc-234">cdm_worker</span></span> |
| <span data-ttu-id="2d3bc-235">Dirección del trabajador</span><span class="sxs-lookup"><span data-stu-id="2d3bc-235">Worker Address</span></span> | <span data-ttu-id="2d3bc-236">cdm_workeraddress</span><span class="sxs-lookup"><span data-stu-id="2d3bc-236">cdm_workeraddress</span></span> |
| <span data-ttu-id="2d3bc-237">Detalle personal del trabajador</span><span class="sxs-lookup"><span data-stu-id="2d3bc-237">Worker Personal Detail</span></span> | <span data-ttu-id="2d3bc-238">cdm_workerpersonaldetail</span><span class="sxs-lookup"><span data-stu-id="2d3bc-238">cdm_workerpersonaldetail</span></span> |
| <span data-ttu-id="2d3bc-239">Número de identificación de persona del trabajador</span><span class="sxs-lookup"><span data-stu-id="2d3bc-239">Worker Person Identification Number</span></span> | <span data-ttu-id="2d3bc-240">cdm_workerpersonidentificationnumber</span><span class="sxs-lookup"><span data-stu-id="2d3bc-240">cdm_workerpersonidentificationnumber</span></span> |
| <span data-ttu-id="2d3bc-241">Tipo de identificación de persona del trabajador</span><span class="sxs-lookup"><span data-stu-id="2d3bc-241">Worker Person Identification Type</span></span> | <span data-ttu-id="2d3bc-242">cdm_workerpersonidentificationtype</span><span class="sxs-lookup"><span data-stu-id="2d3bc-242">cdm_workerpersonidentificationtype</span></span> |
| <span data-ttu-id="2d3bc-243">Calendario de trabajo</span><span class="sxs-lookup"><span data-stu-id="2d3bc-243">Work Calendar</span></span> | <span data-ttu-id="2d3bc-244">cdm_workcalendar</span><span class="sxs-lookup"><span data-stu-id="2d3bc-244">cdm_workcalendar</span></span> |
| <span data-ttu-id="2d3bc-245">Día de calendario de trabajo</span><span class="sxs-lookup"><span data-stu-id="2d3bc-245">Work Calendar Day</span></span> | <span data-ttu-id="2d3bc-246">cdm_workcalendarday</span><span class="sxs-lookup"><span data-stu-id="2d3bc-246">cdm_workcalendarday</span></span> |
| <span data-ttu-id="2d3bc-247">Vacaciones calendario de trabajo</span><span class="sxs-lookup"><span data-stu-id="2d3bc-247">Work Calendar Holiday</span></span> |<span data-ttu-id="2d3bc-248">cdm_workcalendarholiday</span><span class="sxs-lookup"><span data-stu-id="2d3bc-248">cdm_workcalendarholiday</span></span> |
| <span data-ttu-id="2d3bc-249">Línea de festivo del calendario de trabajo</span><span class="sxs-lookup"><span data-stu-id="2d3bc-249">Work Calendar Holiday Line</span></span> | <span data-ttu-id="2d3bc-250">cdm_workcalendarholidayline</span><span class="sxs-lookup"><span data-stu-id="2d3bc-250">cdm_workcalendarholidayline</span></span> |
| <span data-ttu-id="2d3bc-251">Intervalo de tiempo del calendario de trabajo</span><span class="sxs-lookup"><span data-stu-id="2d3bc-251">Work Calendar Time Interval</span></span> | <span data-ttu-id="2d3bc-252">cdm_workcalendartimeinterval (No habilitada para la compatibilidad de campos personalizados)</span><span class="sxs-lookup"><span data-stu-id="2d3bc-252">cdm_workcalendartimeinterval (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="2d3bc-253">Cuenta bancaria de trabajador</span><span class="sxs-lookup"><span data-stu-id="2d3bc-253">Worker Bank Account</span></span> | <span data-ttu-id="2d3bc-254">cdm_workerbankaccount</span><span class="sxs-lookup"><span data-stu-id="2d3bc-254">cdm_workerbankaccount</span></span> |

## <a name="worker-setup-tables"></a><span data-ttu-id="2d3bc-255">Tablas de configuración de trabajador</span><span class="sxs-lookup"><span data-stu-id="2d3bc-255">Worker setup tables</span></span>

| <span data-ttu-id="2d3bc-256">Nombre</span><span class="sxs-lookup"><span data-stu-id="2d3bc-256">Name</span></span> | <span data-ttu-id="2d3bc-257">Tabla</span><span class="sxs-lookup"><span data-stu-id="2d3bc-257">Table</span></span> |
| --- | --- |
| <span data-ttu-id="2d3bc-258">Estado de excombatiente</span><span class="sxs-lookup"><span data-stu-id="2d3bc-258">Veteran Status</span></span> | <span data-ttu-id="2d3bc-259">cdm_veteranstatus</span><span class="sxs-lookup"><span data-stu-id="2d3bc-259">cdm_veteranstatus</span></span> |
| <span data-ttu-id="2d3bc-260">Origen étnico</span><span class="sxs-lookup"><span data-stu-id="2d3bc-260">Ethnic Origin</span></span> | <span data-ttu-id="2d3bc-261">cdm_ethnicorigin</span><span class="sxs-lookup"><span data-stu-id="2d3bc-261">cdm_ethnicorigin</span></span> |
| <span data-ttu-id="2d3bc-262">Código de motivo</span><span class="sxs-lookup"><span data-stu-id="2d3bc-262">Reason Code</span></span> | <span data-ttu-id="2d3bc-263">cdm_reasoncode</span><span class="sxs-lookup"><span data-stu-id="2d3bc-263">cdm_reasoncode</span></span> |
| <span data-ttu-id="2d3bc-264">Agencia emisora de identificación de personas</span><span class="sxs-lookup"><span data-stu-id="2d3bc-264">Person Identification Issuing Agency</span></span> | <span data-ttu-id="2d3bc-265">cdm_personidentificationissuingagency</span><span class="sxs-lookup"><span data-stu-id="2d3bc-265">cdm_personidentificationissuingagency</span></span> |

## <a name="competency-tables"></a><span data-ttu-id="2d3bc-266">Tablas de competencia</span><span class="sxs-lookup"><span data-stu-id="2d3bc-266">Competency tables</span></span>

| <span data-ttu-id="2d3bc-267">Nombre</span><span class="sxs-lookup"><span data-stu-id="2d3bc-267">Name</span></span> | <span data-ttu-id="2d3bc-268">Tabla</span><span class="sxs-lookup"><span data-stu-id="2d3bc-268">Table</span></span> |
| --- | --- |
| <span data-ttu-id="2d3bc-269">Tipo de aptitud</span><span class="sxs-lookup"><span data-stu-id="2d3bc-269">Skill Type</span></span> | <span data-ttu-id="2d3bc-270">cdm_skilltype</span><span class="sxs-lookup"><span data-stu-id="2d3bc-270">cdm_skilltype</span></span> |

## <a name="table-relationship-models"></a><span data-ttu-id="2d3bc-271">Modelos de relación de tabla</span><span class="sxs-lookup"><span data-stu-id="2d3bc-271">Table relationship models</span></span>

### <a name="worker"></a><span data-ttu-id="2d3bc-272">Trabajador</span><span class="sxs-lookup"><span data-stu-id="2d3bc-272">Worker</span></span>

![Trabajador](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a><span data-ttu-id="2d3bc-274">Trabajo y puesto de trabajo</span><span class="sxs-lookup"><span data-stu-id="2d3bc-274">Job and Job Position</span></span>

![Trabajo y puesto de trabajo](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a><span data-ttu-id="2d3bc-276">Prestaciones</span><span class="sxs-lookup"><span data-stu-id="2d3bc-276">Benefits</span></span>

![Prestaciones](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a><span data-ttu-id="2d3bc-278">Compensación</span><span class="sxs-lookup"><span data-stu-id="2d3bc-278">Compensation</span></span>

![Compensación](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a><span data-ttu-id="2d3bc-280">Dejar</span><span class="sxs-lookup"><span data-stu-id="2d3bc-280">Leave</span></span>

![Dejar](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a><span data-ttu-id="2d3bc-282">Calendario de trabajo</span><span class="sxs-lookup"><span data-stu-id="2d3bc-282">Work Calendar</span></span>

![Calendario de trabajo](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a><span data-ttu-id="2d3bc-284">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2d3bc-284">See also</span></span>

[<span data-ttu-id="2d3bc-285">Elegir una tecnología de integración de datos</span><span class="sxs-lookup"><span data-stu-id="2d3bc-285">Choose a data integration technology</span></span>](hr-admin-integration-choose-technology.md)<br>
[<span data-ttu-id="2d3bc-286">Configurar la integración de Dataverse</span><span class="sxs-lookup"><span data-stu-id="2d3bc-286">Configure Dataverse integration</span></span>](hr-admin-integration-common-data-service.md)<br>
[<span data-ttu-id="2d3bc-287">Configurar tablas virtuales de Dataverse</span><span class="sxs-lookup"><span data-stu-id="2d3bc-287">Configure Dataverse virtual tables</span></span>](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[<span data-ttu-id="2d3bc-288">Preguntas frecuentes sobre tablas virtuales para Human Resources</span><span class="sxs-lookup"><span data-stu-id="2d3bc-288">Human Resources virtual tables FAQ</span></span>](hr-admin-virtual-entity-faq.md)<br>
[<span data-ttu-id="2d3bc-289">¿Qué es Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="2d3bc-289">What is Microsoft Dataverse?</span></span>](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)<br>
[<span data-ttu-id="2d3bc-290">Actualizaciones de terminología</span><span class="sxs-lookup"><span data-stu-id="2d3bc-290">Terminology updates</span></span>](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]