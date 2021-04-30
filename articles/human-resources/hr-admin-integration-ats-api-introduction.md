---
title: Introducción a la API de integración del sistema de seguimiento de candidatos
description: Este tema describe la API de integración del sistema de seguimiento de candidatos (ATS) de Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f70e377d6844b5c4f9201f0a561ad9cfcab2eda1
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5890134"
---
# <a name="applicant-tracking-system-integration-api-introduction"></a><span data-ttu-id="11d29-103">Introducción a la API de integración del sistema de seguimiento de candidatos</span><span class="sxs-lookup"><span data-stu-id="11d29-103">Applicant Tracking System integration API introduction</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="11d29-104">Este tema describe la API de integración del sistema de seguimiento de candidatos (ATS) de Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="11d29-104">This topic describes the Dynamics 365 Human Resources Applicant Tracking System (ATS) integration API.</span></span> <span data-ttu-id="11d29-105">La intención de la API es permitir integraciones optimizadas entre Dynamics 365 Human Resources y los ATS asociados.</span><span class="sxs-lookup"><span data-stu-id="11d29-105">The intent of the API is to enable streamlined integrations between Dynamics 365 Human Resources and partnering ATSs.</span></span>

![Flujo de integración con ATS](media/hr-admin-integration-ats-api-introduction-flow.png)

<span data-ttu-id="11d29-107">La experiencia integrada comienza en Recursos Humanos, cuando un gerente de contratación crea una solicitud de contratación.</span><span class="sxs-lookup"><span data-stu-id="11d29-107">The integrated experience begins in Human Resources when a hiring manager creates a recruiting request.</span></span> <span data-ttu-id="11d29-108">Cuando se activa la solicitud, el ATS extrae el detalle de la solicitud para crear un proyecto de contratación.</span><span class="sxs-lookup"><span data-stu-id="11d29-108">When the request is activated, the ATS pulls the detail for the request to create a recruiting project.</span></span> <span data-ttu-id="11d29-109">Luego sigue el proceso de contratación para seleccionar y contratar candidatos para los puestos.</span><span class="sxs-lookup"><span data-stu-id="11d29-109">Then it follows the recruiting pipeline to select and hire a candidate for the position(s).</span></span> <span data-ttu-id="11d29-110">Finalmente, el ATS completa la integración de ida y vuelta enviando el registro del candidato seleccionado a Recursos Humanos.</span><span class="sxs-lookup"><span data-stu-id="11d29-110">Finally, the ATS completes the round-trip integration by sending the selected candidate’s record into Human Resources.</span></span> <span data-ttu-id="11d29-111">El registro de candidato puede luego pasar por más validaciones de incorporación y flujos de trabajo para crear el registro de empleado.</span><span class="sxs-lookup"><span data-stu-id="11d29-111">The candidate record can then go through more onboarding validations and workflows to create the employee record.</span></span>

<span data-ttu-id="11d29-112">Para habilitar la integración, Recursos Humanos ha agregado los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="11d29-112">To enable the integration, Human Resources has added the following components:</span></span>

1.  <span data-ttu-id="11d29-113">Funcionalidad para crear una solicitud de contratación.</span><span class="sxs-lookup"><span data-stu-id="11d29-113">Functionality to create a recruiting request.</span></span>
2.  <span data-ttu-id="11d29-114">Un perfil de candidato ampliado y flujos de trabajo relacionados.</span><span class="sxs-lookup"><span data-stu-id="11d29-114">An expanded candidate profile and related workflows.</span></span>
3.  <span data-ttu-id="11d29-115">Una API de integración que abre la nueva funcionalidad para integrar aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="11d29-115">An integration API opening up the new functionality to integrating applications.</span></span>

<span data-ttu-id="11d29-116">Para obtener más información sobre cómo configurar y utilizar la funcionalidad de solicitud de contratación y candidatos, consulte [Contratar candidatos para el trabajo](hr-personnel-recruit.md).</span><span class="sxs-lookup"><span data-stu-id="11d29-116">For more information about setting up and using the recruiting request and candidate functionality, see [Recruit job candidates](hr-personnel-recruit.md).</span></span>

## <a name="microsoft-dataverse"></a><span data-ttu-id="11d29-117">Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="11d29-117">Microsoft Dataverse</span></span>

<span data-ttu-id="11d29-118">Esta API se basa en Microsoft Dataverse (antes Common Data Service).</span><span class="sxs-lookup"><span data-stu-id="11d29-118">This API is built on Microsoft Dataverse (formerly Common Data Service).</span></span> <span data-ttu-id="11d29-119">Toda la interacción RESTful con esta API se realiza a través de la API web Microsoft Dataverse, que utiliza OData.</span><span class="sxs-lookup"><span data-stu-id="11d29-119">All RESTful interaction with this API is done via the Microsoft Dataverse Web API, which uses OData.</span></span> <span data-ttu-id="11d29-120">Esta API es un subconjunto de la API web de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="11d29-120">This API is a subset of the Dataverse Web API.</span></span> <span data-ttu-id="11d29-121">La API web de Dataverse define características como autenticación, SLA, lotes, control de concurrencia y manejo de errores.</span><span class="sxs-lookup"><span data-stu-id="11d29-121">The Dataverse Web API defines characteristics such as authentication, SLAs, batch, concurrency control, and error handling.</span></span>

<span data-ttu-id="11d29-122">Para obtener más información general acerca de la API web de Microsoft Dataverse, consulte:</span><span class="sxs-lookup"><span data-stu-id="11d29-122">For more general information about the Microsoft Dataverse Web API, see:</span></span>

- [<span data-ttu-id="11d29-123">¿Qué es Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="11d29-123">What is Microsoft Dataverse?</span></span>](/powerapps/maker/data-platform/data-platform-intro)
- [<span data-ttu-id="11d29-124">Utilizar la API web de Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="11d29-124">Use the Microsoft Dataverse Web API</span></span>](/powerapps/developer/data-platform/webapi/overview)
- [<span data-ttu-id="11d29-125">Guía de desarrollador de Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="11d29-125">Microsoft Dataverse developer guide</span></span>](/powerapps/developer/data-platform)

<span data-ttu-id="11d29-126">La documentación anterior incluye detalles y orientación para desarrolladores sobre el uso de la API web de Dataverse, como [gestionar la autenticación](/powerapps/developer/data-platform/webapi/authenticate-web-api), [realizar operaciones](/powerapps/developer/data-platform/webapi/perform-operations-web-api), [uso de Postman con la API](/powerapps/developer/data-platform/webapi/use-postman-web-api) y [uso de seguimiento de cambios o tokens delta](/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems) con la API.</span><span class="sxs-lookup"><span data-stu-id="11d29-126">The above documentation includes detail and developer guidance on using the Dataverse Web API, such as [managing authentication](/powerapps/developer/data-platform/webapi/authenticate-web-api), [performing operations](/powerapps/developer/data-platform/webapi/perform-operations-web-api), [using Postman with the API](/powerapps/developer/data-platform/webapi/use-postman-web-api), and [using change tracking or delta tokens](/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems) with the API.</span></span>

### <a name="option-sets"></a><span data-ttu-id="11d29-127">Conjuntos de opciones</span><span class="sxs-lookup"><span data-stu-id="11d29-127">Option sets</span></span>

<span data-ttu-id="11d29-128">El modelo de datos para la API de integración ATS descrito en este documento incluye conjuntos de opciones que proporcionan valores enumerados asociados con las propiedades de la entidad.</span><span class="sxs-lookup"><span data-stu-id="11d29-128">The data model for the ATS integration API described in this document includes option sets that provide enumerated values associated with entity properties.</span></span> <span data-ttu-id="11d29-129">Para obtener detalles sobre cómo trabajar con conjuntos de opciones en la API web de Dataverse, consulte [Crear y actualizar conjuntos de opciones usando la API web](/powerapps/developer/data-platform/webapi/create-update-optionsets).</span><span class="sxs-lookup"><span data-stu-id="11d29-129">For detail on working with option sets in the Dataverse Web API, see [Create and update option sets using the Web API](/powerapps/developer/data-platform/webapi/create-update-optionsets).</span></span> <span data-ttu-id="11d29-130">Los conjuntos de opciones se definen para cada entorno de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="11d29-130">Option sets are defined for each Dataverse environment.</span></span>

### <a name="virtual-tables-for-human-resources-in-dataverse"></a><span data-ttu-id="11d29-131">Tablas virtuales para Recursos Humanos en Dataverse</span><span class="sxs-lookup"><span data-stu-id="11d29-131">Virtual tables for Human Resources in Dataverse</span></span>

<span data-ttu-id="11d29-132">Los puntos de conexión de la API de integración ATS utilizan las capacidades de la plataforma de tabla virtual de Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="11d29-132">The endpoints for the ATS integration API use the virtual table platform capabilities of Microsoft Dataverse.</span></span> <span data-ttu-id="11d29-133">De forma predeterminada, las tablas virtuales y sus puntos de conexión de API asociados no se implementan para entornos de Recursos Humanos, lo que permite a las organizaciones determinar qué punto de conexión estarán expuestos para el entorno.</span><span class="sxs-lookup"><span data-stu-id="11d29-133">By default, the virtual tables and their associated API endpoints are not deployed for Human Resources environments, enabling organizations to determine which OData endpoints will be exposed for the environment.</span></span> <span data-ttu-id="11d29-134">Para utilizar la API, se deben generar las tablas virtuales para las entidades de Recursos Humanos para el entorno.</span><span class="sxs-lookup"><span data-stu-id="11d29-134">To use the API, the virtual tables for the Human Resources entities must be generated for the environment.</span></span> 

<span data-ttu-id="11d29-135">Para obtener información sobre la generación de tablas virtuales para la API, consulte [Configurar tablas virtuales de Dataverse](./hr-admin-integration-common-data-service-virtual-entities.md).</span><span class="sxs-lookup"><span data-stu-id="11d29-135">For information on generating the virtual tables for the API, see [Configure Dataverse virtual tables](./hr-admin-integration-common-data-service-virtual-entities.md).</span></span>

## <a name="data-model"></a><span data-ttu-id="11d29-136">Modelo de datos</span><span class="sxs-lookup"><span data-stu-id="11d29-136">Data model</span></span>

<span data-ttu-id="11d29-137">El modelo de datos se centra en dos entidades principales:</span><span class="sxs-lookup"><span data-stu-id="11d29-137">The data model is centered around two main entities:</span></span>

- <span data-ttu-id="11d29-138">**RecruitingRequest** representa una solicitud a un ATS de contratar para una o más posiciones abiertas. Para una consulta de ejemplo, vea [Consulta de ejemplo para solicitud de contratación](hr-admin-integration-ats-api-recruiting-request-example-query.md).</span><span class="sxs-lookup"><span data-stu-id="11d29-138">**RecruitingRequest** represents a request to an ATS to recruit for one or more open positions.For an example query, see [Example query for Recruiting request](hr-admin-integration-ats-api-recruiting-request-example-query.md).</span></span>
- <span data-ttu-id="11d29-139">**CandidateToHire** representa detalles de un candidato que ha aceptado una oferta para un puesto.</span><span class="sxs-lookup"><span data-stu-id="11d29-139">**CandidateToHire** represents details of a candidate who has accepted an offer for a position.</span></span> <span data-ttu-id="11d29-140">**Persona** representa al individuo que es el candidato.</span><span class="sxs-lookup"><span data-stu-id="11d29-140">**Person** represents the individual who is the candidate.</span></span> <span data-ttu-id="11d29-141">Una persona puede tener varios roles en la empresa, como candidato, trabajador, empleado o contratista.</span><span class="sxs-lookup"><span data-stu-id="11d29-141">A person can have multiple roles in the company, such as candidate, worker, employee, or contractor.</span></span> <span data-ttu-id="11d29-142">Para obtener una consulta de ejemplo, consulte [Consulta de ejemplo para candidato a contratar](hr-admin-integration-ats-api-candidate-to-hire-example-query.md).</span><span class="sxs-lookup"><span data-stu-id="11d29-142">For an example query, see [Example query for Candidate to hire](hr-admin-integration-ats-api-candidate-to-hire-example-query.md).</span></span>

<span data-ttu-id="11d29-143">El siguiente diagrama ilustra las relaciones dentro de la API.</span><span class="sxs-lookup"><span data-stu-id="11d29-143">The following diagram illustrates relationships within the API.</span></span> <span data-ttu-id="11d29-144">Diversos tipos tienen claves extranjeras para otras entidades preexistentes en Recursos Humanos que no se ilustran aquí.</span><span class="sxs-lookup"><span data-stu-id="11d29-144">Several types have foreign keys to other, pre-existing entities in Human Resources that aren't illustrated here.</span></span> <span data-ttu-id="11d29-145">Este documento proporciona información sobre las entidades específicas para los escenarios de integración de contratación.</span><span class="sxs-lookup"><span data-stu-id="11d29-145">This document provides information on entities that are specific to recruiting integration scenarios.</span></span> <span data-ttu-id="11d29-146">Sin embargo, hay muchas otras entidades en la API web de Dataverse para Dynamics 365 Human Resources que también pueden ser relevantes para su integración.</span><span class="sxs-lookup"><span data-stu-id="11d29-146">However, there are many other entities in the Dataverse Web API for Dynamics 365 Human Resources that may also be relevant to your integration.</span></span> <span data-ttu-id="11d29-147">Por ejemplo, es posible que también necesite detalles para trabajadores, trabajos, puestos u otras entidades no definidas aquí.</span><span class="sxs-lookup"><span data-stu-id="11d29-147">For example, you may also need detail for workers, jobs, positions, or other entities not defined here.</span></span> <span data-ttu-id="11d29-148">Muchas de estas entidades están referenciadas en relaciones de clave externa o propiedades de navegación.</span><span class="sxs-lookup"><span data-stu-id="11d29-148">Many of these entities are referenced in foreign key relationships or navigation properties.</span></span>

![Modelo de datos de API de integración de ATS](media/hr-admin-integration-ats-api-data-model.png)

## <a name="recruiting-request-and-related-entities-and-option-sets"></a><span data-ttu-id="11d29-150">Solicitud de contratación, entidades relacionadas y conjuntos de opciones</span><span class="sxs-lookup"><span data-stu-id="11d29-150">Recruiting request and related entities and option sets</span></span>

<span data-ttu-id="11d29-151">Consulta de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="11d29-151">Example query:</span></span> 

- [<span data-ttu-id="11d29-152">Consulta de ejemplo para solicitud de contratación</span><span class="sxs-lookup"><span data-stu-id="11d29-152">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)

<span data-ttu-id="11d29-153">Entidades:</span><span class="sxs-lookup"><span data-stu-id="11d29-153">Entities:</span></span>

- [<span data-ttu-id="11d29-154">Solicitud de contratación</span><span class="sxs-lookup"><span data-stu-id="11d29-154">Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request.md)
- [<span data-ttu-id="11d29-155">Puesto de solicitud de contratación</span><span class="sxs-lookup"><span data-stu-id="11d29-155">Recruiting request position</span></span>](hr-admin-integration-ats-api-recruiting-request-position.md)
- [<span data-ttu-id="11d29-156">Capacidad de solicitud de contratación</span><span class="sxs-lookup"><span data-stu-id="11d29-156">Recruiting request skill</span></span>](hr-admin-integration-ats-api-recruiting-request-skill.md)
- [<span data-ttu-id="11d29-157">Educación de solicitud de contratación</span><span class="sxs-lookup"><span data-stu-id="11d29-157">Recruiting request education</span></span>](hr-admin-integration-ats-api-recruiting-request-education.md)
- [<span data-ttu-id="11d29-158">Ubicación de la solicitud de contratación</span><span class="sxs-lookup"><span data-stu-id="11d29-158">Recruiting request location</span></span>](hr-admin-integration-ats-api-recruiting-request-location.md)

<span data-ttu-id="11d29-159">Conjuntos de opciones:</span><span class="sxs-lookup"><span data-stu-id="11d29-159">Option sets:</span></span>

- [<span data-ttu-id="11d29-160">Estado de exención de trabajo</span><span class="sxs-lookup"><span data-stu-id="11d29-160">Job exempt status</span></span>](hr-admin-integration-ats-api-job-exempt-status.md)
- [<span data-ttu-id="11d29-161">Estado de posición de solicitud de contratación</span><span class="sxs-lookup"><span data-stu-id="11d29-161">Recruiting request position status</span></span>](hr-admin-integration-ats-api-recruiting-request-position-status.md)
- [<span data-ttu-id="11d29-162">Estado de solicitud de contratación</span><span class="sxs-lookup"><span data-stu-id="11d29-162">Recruiting request status</span></span>](hr-admin-integration-ats-api-recruiting-request-status.md)
- [<span data-ttu-id="11d29-163">Categoría de trabajo reglamentaria</span><span class="sxs-lookup"><span data-stu-id="11d29-163">Regulatory job category</span></span>](hr-admin-integration-ats-api-regulatory-job-category.md)

## <a name="candidate-to-hire-and-related-entities-and-option-sets"></a><span data-ttu-id="11d29-164">Candidato a contratar, entidades relacionadas y conjuntos de opciones</span><span class="sxs-lookup"><span data-stu-id="11d29-164">Candidate to hire and related entities and option sets</span></span>

<span data-ttu-id="11d29-165">Consulta de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="11d29-165">Example query:</span></span>

- [<span data-ttu-id="11d29-166">Consulta de ejemplo para candidato a contratar</span><span class="sxs-lookup"><span data-stu-id="11d29-166">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)

<span data-ttu-id="11d29-167">Entidades:</span><span class="sxs-lookup"><span data-stu-id="11d29-167">Entities:</span></span>

- [<span data-ttu-id="11d29-168">Candidato a contratar</span><span class="sxs-lookup"><span data-stu-id="11d29-168">Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire.md)
- [<span data-ttu-id="11d29-169">Persona</span><span class="sxs-lookup"><span data-stu-id="11d29-169">Person</span></span>](hr-admin-integration-ats-api-person.md)
- [<span data-ttu-id="11d29-170">Educación personal</span><span class="sxs-lookup"><span data-stu-id="11d29-170">Person education</span></span>](hr-admin-integration-ats-api-person-education.md)
- [<span data-ttu-id="11d29-171">Experiencia profesional personal</span><span class="sxs-lookup"><span data-stu-id="11d29-171">Person professional experience</span></span>](hr-admin-integration-ats-api-person-professional-experience.md)
- [<span data-ttu-id="11d29-172">Dirección de la persona</span><span class="sxs-lookup"><span data-stu-id="11d29-172">Person address</span></span>](hr-admin-integration-ats-api-person-address.md)
- [<span data-ttu-id="11d29-173">Contacto de parte</span><span class="sxs-lookup"><span data-stu-id="11d29-173">Party contact</span></span>](hr-admin-integration-ats-api-party-contact.md)
- [<span data-ttu-id="11d29-174">Habilidad de la persona</span><span class="sxs-lookup"><span data-stu-id="11d29-174">Person skill</span></span>](hr-admin-integration-ats-api-person-skill.md)
- [<span data-ttu-id="11d29-175">Nivel de evaluación</span><span class="sxs-lookup"><span data-stu-id="11d29-175">Rating level</span></span>](hr-admin-integration-ats-api-rating-level.md)
- [<span data-ttu-id="11d29-176">Certificado de la persona</span><span class="sxs-lookup"><span data-stu-id="11d29-176">Person certificate</span></span>](hr-admin-integration-ats-api-person-certificate.md)
- [<span data-ttu-id="11d29-177">Tipo de certificado</span><span class="sxs-lookup"><span data-stu-id="11d29-177">Certificate type</span></span>](hr-admin-integration-ats-api-certificate-type.md)
- [<span data-ttu-id="11d29-178">Filtrado de persona</span><span class="sxs-lookup"><span data-stu-id="11d29-178">Person screening</span></span>](hr-admin-integration-ats-api-person-screening.md)
- [<span data-ttu-id="11d29-179">Tipos de filtrado</span><span class="sxs-lookup"><span data-stu-id="11d29-179">Screening types</span></span>](hr-admin-integration-ats-api-screening-types.md)
- [<span data-ttu-id="11d29-180">Número de identificación de persona</span><span class="sxs-lookup"><span data-stu-id="11d29-180">Person identification number</span></span>](hr-admin-integration-ats-api-person-identification-number.md)

<span data-ttu-id="11d29-181">Conjuntos de opciones:</span><span class="sxs-lookup"><span data-stu-id="11d29-181">Option sets:</span></span>

- [<span data-ttu-id="11d29-182">Resultado de integración de candidatos</span><span class="sxs-lookup"><span data-stu-id="11d29-182">Applicant integration result</span></span>](hr-admin-integration-ats-api-applicant-integration-result.md)
- [<span data-ttu-id="11d29-183">En blanco Sí No</span><span class="sxs-lookup"><span data-stu-id="11d29-183">Blank Yes No</span></span>](hr-admin-integration-ats-api-blank-yes-no.md)
- [<span data-ttu-id="11d29-184">Estado de finalización</span><span class="sxs-lookup"><span data-stu-id="11d29-184">Completion status</span></span>](hr-admin-integration-ats-api-completion-status.md)
- [<span data-ttu-id="11d29-185">Tipo de contacto</span><span class="sxs-lookup"><span data-stu-id="11d29-185">Contact type</span></span>](hr-admin-integration-ats-api-contact-type.md)
- [<span data-ttu-id="11d29-186">Base de crédito educativo</span><span class="sxs-lookup"><span data-stu-id="11d29-186">Education credit basis</span></span>](hr-admin-integration-ats-api-education-credit-basis.md)
- [<span data-ttu-id="11d29-187">Género</span><span class="sxs-lookup"><span data-stu-id="11d29-187">Gender</span></span>](hr-admin-integration-ats-api-gender.md)
- [<span data-ttu-id="11d29-188">Estado civil</span><span class="sxs-lookup"><span data-stu-id="11d29-188">Marital status</span></span>](hr-admin-integration-ats-api-marital-status.md)
- [<span data-ttu-id="11d29-189">Meses del año</span><span class="sxs-lookup"><span data-stu-id="11d29-189">Months of year</span></span>](hr-admin-integration-ats-api-months-of-year.md)
- [<span data-ttu-id="11d29-190">No Sí</span><span class="sxs-lookup"><span data-stu-id="11d29-190">No Yes</span></span>](hr-admin-integration-ats-api-no-yes.md)
- [<span data-ttu-id="11d29-191">Unidad del período</span><span class="sxs-lookup"><span data-stu-id="11d29-191">Period unit</span></span>](hr-admin-integration-ats-api-period-unit.md)
- [<span data-ttu-id="11d29-192">Frecuencia de cribado</span><span class="sxs-lookup"><span data-stu-id="11d29-192">Screening frequency</span></span>](hr-admin-integration-ats-api-screening-frequency.md)
- [<span data-ttu-id="11d29-193">Origen de generación de la frecuencia de cribado</span><span class="sxs-lookup"><span data-stu-id="11d29-193">Screening frequency generate from</span></span>](hr-admin-integration-ats-api-screening-frequency-generate-from.md)
- [<span data-ttu-id="11d29-194">Tipo de nivel de capacidad</span><span class="sxs-lookup"><span data-stu-id="11d29-194">Skill level type</span></span>](hr-admin-integration-ats-api-skill-level-type.md)

## <a name="see-also"></a><span data-ttu-id="11d29-195">Consulte también</span><span class="sxs-lookup"><span data-stu-id="11d29-195">See also</span></span>

[<span data-ttu-id="11d29-196">Contratar candidatos de trabajo</span><span class="sxs-lookup"><span data-stu-id="11d29-196">Recruit job candidates</span></span>](hr-personnel-recruit.md)<br>
[<span data-ttu-id="11d29-197">¿Qué es Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="11d29-197">What is Microsoft Dataverse?</span></span>](/powerapps/maker/data-platform/data-platform-intro)<br>
[<span data-ttu-id="11d29-198">Utilizar la API web de Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="11d29-198">Use the Microsoft Dataverse Web API</span></span>](/powerapps/developer/data-platform/webapi/overview)<br>
[<span data-ttu-id="11d29-199">Crear y actualizar conjuntos de opciones usando la API web</span><span class="sxs-lookup"><span data-stu-id="11d29-199">Create and update option sets using the Web API</span></span>](/powerapps/developer/data-platform/webapi/create-update-optionsets)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]