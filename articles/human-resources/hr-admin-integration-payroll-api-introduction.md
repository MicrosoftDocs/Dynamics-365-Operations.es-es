---
title: Introducción a la API de integración de nóminas
description: Este tema describe la API de integración de nóminas de Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 61b90c566325bb8d83b09fceebc721cfb14d3fc8
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891135"
---
# <a name="payroll-integration-api-introduction"></a><span data-ttu-id="1ef41-103">Introducción a la API de integración de nóminas</span><span class="sxs-lookup"><span data-stu-id="1ef41-103">Payroll integration API introduction</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="1ef41-104">Este documento describe la API de integración de nóminas de Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="1ef41-104">This document describes the Dynamics 365 Human Resources Payroll integration API.</span></span> <span data-ttu-id="1ef41-105">La API permite integraciones optimizadas de un extremo a otro entre los recursos humanos y los sistemas de nómina asociados.</span><span class="sxs-lookup"><span data-stu-id="1ef41-105">The API enables streamlined end-to-end integrations between Human Resources and partnering payroll systems.</span></span> <span data-ttu-id="1ef41-106">La experiencia integrada comienza en Recursos Humanos con el perfil del empleado, salario y deducción e información de cotización.</span><span class="sxs-lookup"><span data-stu-id="1ef41-106">The integrated experience begins in Human Resources with the employee profile, salary and deduction, and contribution information.</span></span> <span data-ttu-id="1ef41-107">Cuando contrata a un empleado e ingresa el perfil requerido y la información de pago en Recursos Humanos, el sistema de nómina extrae esta información para usarla al procesar la nómina.</span><span class="sxs-lookup"><span data-stu-id="1ef41-107">When you hire an employee and enter the required profile and pay information into Human Resources, the payroll system pulls this information to use when processing payroll.</span></span> <span data-ttu-id="1ef41-108">Cualquier actualización realizada al empleado o la información de pago también se extrae para su uso en ejecuciones de pago posteriores.</span><span class="sxs-lookup"><span data-stu-id="1ef41-108">Any updates made to the employee or pay information are also pulled for use in later pay runs.</span></span>

![Flujo de integración de nóminas](media/hr-admin-integration-payroll-api-introduction-flow.png)

<span data-ttu-id="1ef41-110">Para habilitar la integración, Recursos Humanos incluye los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="1ef41-110">To enable the integration, Human Resources includes the following components:</span></span>

- <span data-ttu-id="1ef41-111">Funcionalidad para marcar a un empleado como listo para pagar</span><span class="sxs-lookup"><span data-stu-id="1ef41-111">Functionality to mark an employee as ready to pay</span></span>
- <span data-ttu-id="1ef41-112">Una API de integración que abre la nueva funcionalidad para integrar aplicaciones</span><span class="sxs-lookup"><span data-stu-id="1ef41-112">An integration API opening up the new functionality to integrating applications</span></span>

## <a name="microsoft-dataverse"></a><span data-ttu-id="1ef41-113">Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="1ef41-113">Microsoft Dataverse</span></span>

<span data-ttu-id="1ef41-114">Esta API se basa en Microsoft Dataverse (antes Common Data Service).</span><span class="sxs-lookup"><span data-stu-id="1ef41-114">This API is built on Microsoft Dataverse (formerly Common Data Service).</span></span> <span data-ttu-id="1ef41-115">Toda la interacción RESTful con esta API se realiza a través de la API web Microsoft Dataverse, que utiliza OData.</span><span class="sxs-lookup"><span data-stu-id="1ef41-115">All RESTful interaction with this API is done via the Microsoft Dataverse Web API, which uses OData.</span></span> <span data-ttu-id="1ef41-116">Esta API es un subconjunto de la API web de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="1ef41-116">This API is a subset of the Dataverse Web API.</span></span> <span data-ttu-id="1ef41-117">La API web de Dataverse define características como autenticación, SLA, lotes, control de concurrencia y manejo de errores.</span><span class="sxs-lookup"><span data-stu-id="1ef41-117">The Dataverse Web API defines characteristics such as authentication, SLAs, batch, concurrency control, and error handling.</span></span>

<span data-ttu-id="1ef41-118">Para obtener más información general acerca de la API web de Microsoft Dataverse, consulte:</span><span class="sxs-lookup"><span data-stu-id="1ef41-118">For more general information about the Microsoft Dataverse Web API, see:</span></span>

- [<span data-ttu-id="1ef41-119">¿Qué es Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="1ef41-119">What is Microsoft Dataverse?</span></span>](/powerapps/maker/data-platform/data-platform-intro)
- [<span data-ttu-id="1ef41-120">Utilizar la API web de Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="1ef41-120">Use the Microsoft Dataverse Web API</span></span>](/powerapps/developer/data-platform/webapi/overview)
- [<span data-ttu-id="1ef41-121">Guía de desarrollador de Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="1ef41-121">Microsoft Dataverse developer guide</span></span>](/powerapps/developer/data-platform)

<span data-ttu-id="1ef41-122">Esta documentación incluye detalles y orientación para desarrolladores sobre el uso de la API web de Dataverse, incluidos los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="1ef41-122">This documentation includes details and developer guidance for using the Dataverse Web API, including the following topics:</span></span>

- [<span data-ttu-id="1ef41-123">Autenticarse en Microsoft Dataverse con la API web</span><span class="sxs-lookup"><span data-stu-id="1ef41-123">Authenticate to Microsoft Dataverse with the Web API</span></span>](/powerapps/developer/data-platform/webapi/authenticate-web-api)
- [<span data-ttu-id="1ef41-124">Realizar operaciones usando la API web</span><span class="sxs-lookup"><span data-stu-id="1ef41-124">Perform operations using the Web API</span></span>](/powerapps/developer/data-platform/webapi/perform-operations-web-api)
- [<span data-ttu-id="1ef41-125">Utilice Postman con la API web</span><span class="sxs-lookup"><span data-stu-id="1ef41-125">Use Postman with the Web API</span></span>](/powerapps/developer/data-platform/webapi/use-postman-web-api)
- [<span data-ttu-id="1ef41-126">Utilice el seguimiento de cambios para sincronizar datos con sistemas externos</span><span class="sxs-lookup"><span data-stu-id="1ef41-126">Use change tracking to synchronize data with external systems</span></span>](/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems)

### <a name="virtual-tables-for-human-resources-in-dataverse"></a><span data-ttu-id="1ef41-127">Tablas virtuales para Recursos Humanos en Dataverse</span><span class="sxs-lookup"><span data-stu-id="1ef41-127">Virtual tables for Human Resources in Dataverse</span></span>

<span data-ttu-id="1ef41-128">Los puntos de conexión de la API de integración de nóminas utilizan las capacidades de la plataforma de tabla virtual de Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="1ef41-128">The endpoints for the Payroll integration API use the virtual table platform capabilities of Microsoft Dataverse.</span></span> <span data-ttu-id="1ef41-129">De forma predeterminada, las tablas virtuales y sus puntos de conexión de API asociados no se implementan para entornos de Recursos Humanos, lo que permite a las organizaciones determinar qué punto de conexión estarán expuestos para el entorno.</span><span class="sxs-lookup"><span data-stu-id="1ef41-129">By default, the virtual tables and their associated API endpoints aren't deployed for Human Resources environments, enabling organizations to determine which OData endpoints will be exposed for the environment.</span></span> <span data-ttu-id="1ef41-130">Para utilizar la API, se deben generar las tablas virtuales para las entidades de Recursos Humanos para el entorno.</span><span class="sxs-lookup"><span data-stu-id="1ef41-130">To use the API, the virtual tables for the Human Resources entities must be generated for the environment.</span></span>

<span data-ttu-id="1ef41-131">Para obtener información sobre la generación de tablas virtuales para la API, consulte [Configurar tablas virtuales de Dataverse](./hr-admin-integration-common-data-service-virtual-entities.md).</span><span class="sxs-lookup"><span data-stu-id="1ef41-131">For information on generating the virtual tables for the API, see [Configure Dataverse virtual tables](./hr-admin-integration-common-data-service-virtual-entities.md).</span></span>

## <a name="data-model"></a><span data-ttu-id="1ef41-132">Modelo de datos</span><span class="sxs-lookup"><span data-stu-id="1ef41-132">Data model</span></span>

<span data-ttu-id="1ef41-133">El siguiente diagrama ilustra las relaciones dentro de la API.</span><span class="sxs-lookup"><span data-stu-id="1ef41-133">The following diagram illustrates relationships within the API.</span></span> <span data-ttu-id="1ef41-134">Diversos tipos tienen claves extranjeras para otras entidades preexistentes en Recursos Humanos que no se ilustran aquí.</span><span class="sxs-lookup"><span data-stu-id="1ef41-134">Several types have foreign keys to other, pre-existing entities in Human Resources that aren't illustrated here.</span></span> <span data-ttu-id="1ef41-135">Este documento proporciona información sobre las entidades específicas para los escenarios de integración de nóminas.</span><span class="sxs-lookup"><span data-stu-id="1ef41-135">This document provides information on entities that are specific to payroll integration scenarios.</span></span> <span data-ttu-id="1ef41-136">Sin embargo, hay muchas otras entidades en la API web de Dataverse para Human Resources que también pueden ser relevantes para su integración.</span><span class="sxs-lookup"><span data-stu-id="1ef41-136">However, there are many other entities in the Dataverse Web API for Human Resources that may also be relevant to your integration.</span></span> <span data-ttu-id="1ef41-137">Algunas de estas entidades están referenciadas en relaciones de clave externa o propiedades de navegación.</span><span class="sxs-lookup"><span data-stu-id="1ef41-137">Some of these entities are referenced in foreign key relationships or navigation properties.</span></span>

![Modelo de datos de API de integración de nóminas](media/hr-admin-payroll-api-data-model.png)

## <a name="payroll-employee-and-related-entities"></a><span data-ttu-id="1ef41-139">Empleado de nómina y entidades relacionadas</span><span class="sxs-lookup"><span data-stu-id="1ef41-139">Payroll employee and related entities</span></span>

<span data-ttu-id="1ef41-140">Entidades:</span><span class="sxs-lookup"><span data-stu-id="1ef41-140">Entities:</span></span>

- [<span data-ttu-id="1ef41-141">Empleado con nómina</span><span class="sxs-lookup"><span data-stu-id="1ef41-141">Payroll employee</span></span>](hr-admin-integration-payroll-api-payroll-employee.md)
- [<span data-ttu-id="1ef41-142">Dirección del trabajador de la nómina</span><span class="sxs-lookup"><span data-stu-id="1ef41-142">Payroll worker address</span></span>](hr-admin-integration-payroll-api-payroll-worker-address.md)
- [<span data-ttu-id="1ef41-143">Plan de compensación fija con nómina</span><span class="sxs-lookup"><span data-stu-id="1ef41-143">Payroll fixed compensation plan</span></span>](hr-admin-integration-ats-api-recruiting-request-education.md)
- [<span data-ttu-id="1ef41-144">Trabajo de puesto de nómina</span><span class="sxs-lookup"><span data-stu-id="1ef41-144">Payroll position job</span></span>](hr-admin-integration-payroll-api-payroll-position-job.md)
- [<span data-ttu-id="1ef41-145">Puesto de nómina</span><span class="sxs-lookup"><span data-stu-id="1ef41-145">Payroll position</span></span>](hr-admin-integration-payroll-api-payroll-position.md)

## <a name="see-also"></a><span data-ttu-id="1ef41-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1ef41-146">See also</span></span>

[<span data-ttu-id="1ef41-147">Generar y revisar entidades de nómina</span><span class="sxs-lookup"><span data-stu-id="1ef41-147">Generate and review payroll entities</span></span>](hr-admin-integration-payroll-api-generate-review-entities.md)<br>
[<span data-ttu-id="1ef41-148">Configurar parámetros de Human Resources</span><span class="sxs-lookup"><span data-stu-id="1ef41-148">Configure Human Resources parameters</span></span>](hr-setup-parameters.md)<br>
[<span data-ttu-id="1ef41-149">Configurar parámetros compartidos de Human Resources</span><span class="sxs-lookup"><span data-stu-id="1ef41-149">Configure Human Resources shared parameters</span></span>](hr-setup-shared-parameters.md)<br>
[<span data-ttu-id="1ef41-150">¿Qué es Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="1ef41-150">What is Microsoft Dataverse?</span></span>](/powerapps/maker/data-platform/data-platform-intro)<br>
[<span data-ttu-id="1ef41-151">Utilizar la API web de Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="1ef41-151">Use the Microsoft Dataverse Web API</span></span>](/powerapps/developer/data-platform/webapi/overview)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]