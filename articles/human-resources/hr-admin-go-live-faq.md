---
title: Preguntas frecuentes sobre la publicación
description: Este tema enumera las preguntas frecuentes sobre cómo poner en marcha un proyecto de implementación de Dynamics 365 Human Resources.
author: rachel-profitt
manager: tfehr
ms.date: 10/13/2020
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
ms.author: raprofit
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d667d94983d5c8f8e6140259922396d4299a15e3
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467609"
---
# <a name="go-live-faq"></a><span data-ttu-id="eade2-103">Preguntas frecuentes sobre la publicación</span><span class="sxs-lookup"><span data-stu-id="eade2-103">Go-live FAQ</span></span> 

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="eade2-104">Este tema enumera las preguntas frecuentes sobre cómo poner en marcha un proyecto de implementación de Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="eade2-104">This topic lists frequently asked questions about how to go live with a Dynamics 365 Human Resources implementation project.</span></span> 

## <a name="when-can-i-configure-and-request-my-production-environment"></a><span data-ttu-id="eade2-105">¿Cuándo puedo configurar y solicitar mi entorno de producción?</span><span class="sxs-lookup"><span data-stu-id="eade2-105">When can I configure and request my production environment?</span></span> 

<span data-ttu-id="eade2-106">Normalmente, un entorno de producción se implementa cuando cumple con los siguientes criterios:</span><span class="sxs-lookup"><span data-stu-id="eade2-106">Typically, a production environment is deployed after meeting the following criteria:</span></span>

- <span data-ttu-id="eade2-107">Se ha completado el código de todas las personalizaciones.</span><span class="sxs-lookup"><span data-stu-id="eade2-107">All customizations are code-complete.</span></span>
- <span data-ttu-id="eade2-108">Se ha completado la prueba de aceptación de usuarios (UAT).</span><span class="sxs-lookup"><span data-stu-id="eade2-108">User acceptance testing (UAT) is complete.</span></span>
- <span data-ttu-id="eade2-109">El cliente ha aprobado la solución.</span><span class="sxs-lookup"><span data-stu-id="eade2-109">The customer has signed off on the solution.</span></span>
- <span data-ttu-id="eade2-110">No hay problemas que impidan la puesta en marcha.</span><span class="sxs-lookup"><span data-stu-id="eade2-110">There are no blocking issues for go-live.</span></span> 

<span data-ttu-id="eade2-111">Cuando los clientes cualificados se encuentren en esta etapa, el equipo de Microsoft FastTrack trabajará con el equipo del proyecto para realizar una evaluación de puesta en marcha.</span><span class="sxs-lookup"><span data-stu-id="eade2-111">When qualified customers are at this stage, the Microsoft FastTrack team will work with the project team to do a go-live assessment.</span></span> 

## <a name="what-are-the-prerequisites-to-deploying-a-production-environment"></a><span data-ttu-id="eade2-112">¿Cuáles son los requisitos previos para implementar un entorno de producción?</span><span class="sxs-lookup"><span data-stu-id="eade2-112">What are the prerequisites to deploying a production environment?</span></span> 

<span data-ttu-id="eade2-113">Para obtener una lista de requisitos previos, consulte [Prepararse para la puesta en marcha](hr-admin-go-live-prepare.md).</span><span class="sxs-lookup"><span data-stu-id="eade2-113">For a list of the prerequisites, see [Prepare for go-live](hr-admin-go-live-prepare.md).</span></span> 

## <a name="what-is-a-go-live-assessment"></a><span data-ttu-id="eade2-114">¿Qué es una evaluación de puesta en marcha?</span><span class="sxs-lookup"><span data-stu-id="eade2-114">What is a go-live assessment?</span></span>  

<span data-ttu-id="eade2-115">La evaluación de puesta en marcha es parte del [programa Microsoft FastTrack](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/fasttrack-dynamics-365-overview).</span><span class="sxs-lookup"><span data-stu-id="eade2-115">The go-live assessment is part of the [Microsoft FastTrack program](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/fasttrack-dynamics-365-overview).</span></span> <span data-ttu-id="eade2-116">Durante esta revisión, un arquitecto de soluciones evalúa si un proyecto de implementación está listo para su transferencia y puesta en marcha.</span><span class="sxs-lookup"><span data-stu-id="eade2-116">During this review, a solution architect assesses whether an implementation project is ready for a successful cutover and go-live.</span></span> <span data-ttu-id="eade2-117">Esta revisión es obligatoria para todos los proyectos de implementación para los que se quiera solicitar la puesta en marcha en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="eade2-117">This review is mandatory for every implementation project before you can request to go live in a production environment.</span></span> 

## <a name="our-sandbox-environments-are-deployed-in-the-central-us-datacenter-we-want-our-production-environments-to-be-deployed-in-the-west-us-datacenter-can-i-select-west-us-as-the-datacenter-in-my-production-configuration"></a><span data-ttu-id="eade2-118">Nuestros entornos de espacio aislado se implementan en el centro de datos de EE. UU. Central.</span><span class="sxs-lookup"><span data-stu-id="eade2-118">Our Sandbox environments are deployed in the Central US datacenter.</span></span> <span data-ttu-id="eade2-119">Queremos que nuestros entornos de producción se implementen en el centro de datos del Oeste de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="eade2-119">We want our Production environments to be deployed in the West US datacenter.</span></span> <span data-ttu-id="eade2-120">¿Puedo seleccionar el Este de EE. UU. como centro de datos en mi configuración de producción?</span><span class="sxs-lookup"><span data-stu-id="eade2-120">Can I select West US as the datacenter in my Production configuration?</span></span> 

<span data-ttu-id="eade2-121">LCS no le impide seleccionar un centro de datos diferente al implementar un entorno de Recursos Humanos, pero le recomendamos encarecidamente que no seleccione un centro de datos diferente.</span><span class="sxs-lookup"><span data-stu-id="eade2-121">LCS doesn't restrict you from selecting a different data center when you deploy a Human Resources environment, but we strongly recommend not selecting a different data center.</span></span>  

<span data-ttu-id="eade2-122">Si desea que su entorno de producción esté en el centro de datos del Oeste de EE. UU., primero debe volver a implementar sus entornos de espacio aislado en el centro de datos del Oeste de EE. UU., probarlos y aprobarlos.</span><span class="sxs-lookup"><span data-stu-id="eade2-122">If you want your Production environment to be in the West US datacenter, you should first redeploy your Sandbox environments to the West US datacenter, test them, and sign off.</span></span> 

<span data-ttu-id="eade2-123">Para obtener información sobre cómo seleccionar el centro de datos correcto, consulte [Requisitos de red](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/system-requirements#network-requirements).</span><span class="sxs-lookup"><span data-stu-id="eade2-123">For information about selecting the correct datacenter, see [Network requirements](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/system-requirements#network-requirements).</span></span> 

## <a name="what-level-of-access-do-i-have-to-the-azure-resources-for-my-human-resources-environments"></a><span data-ttu-id="eade2-124">¿Qué nivel de acceso tengo a los recursos de Azure para mis entornos de Human Resources?</span><span class="sxs-lookup"><span data-stu-id="eade2-124">What level of access do I have to the Azure resources for my Human Resources environments?</span></span>  

<span data-ttu-id="eade2-125">El acceso a los entornos de Human Resources es limitado.</span><span class="sxs-lookup"><span data-stu-id="eade2-125">Access to the Human Resources environments is limited.</span></span> <span data-ttu-id="eade2-126">No puede acceder a la máquina virtual (VM) ni a Microsoft Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="eade2-126">You can't access the virtual machine (VM) or Microsoft Internet Information Services (IIS).</span></span> <span data-ttu-id="eade2-127">Tampoco puede acceder a la base de datos a través de Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="eade2-127">You also can't access the database through Microsoft SQL Server Management Studio.</span></span> 

<span data-ttu-id="eade2-128">Aunque no puede se acceder a los recursos de Azure ni al entorno de Dynamics 365 Human Resources directamente, existen otras características que puede utilizar para acceder a sus datos:</span><span class="sxs-lookup"><span data-stu-id="eade2-128">Although you can't access your Azure resources or Dynamics 365 Human Resources environment directly, there are additional features you can use to access your data:</span></span>

- <span data-ttu-id="eade2-129">Puede implementar una base de datos de Azure SQL en su propio inquilino de Azure y usar la característica Usar su propia base de datos (BYOD) para sincronizar los datos.</span><span class="sxs-lookup"><span data-stu-id="eade2-129">You can deploy an Azure SQL database in your own Azure tenant and use the Bring Your Own Database (BYOD) feature to synchronize data.</span></span> <span data-ttu-id="eade2-130">Para obtener más información, consulte [Usar su propia base de datos (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database).</span><span class="sxs-lookup"><span data-stu-id="eade2-130">For more information, see [Bring your own database (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database).</span></span>

- <span data-ttu-id="eade2-131">Puedes usar la integración de Dataverse para sincronizar entidades de selección en la base de datos de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="eade2-131">You can use Dataverse integration to synchronize select entities into the Dataverse database.</span></span> <span data-ttu-id="eade2-132">Para obtener más información, consulte las [Tablas de Dataverse](hr-developer-entities.md).</span><span class="sxs-lookup"><span data-stu-id="eade2-132">For more information, see [Dataverse tables](hr-developer-entities.md).</span></span> 

## <a name="how-often-is-my-production-database-backed-up"></a><span data-ttu-id="eade2-133">¿Con qué frecuencia se realiza una copia de seguridad de mi base de datos de producción?</span><span class="sxs-lookup"><span data-stu-id="eade2-133">How often is my production database backed up?</span></span> 

<span data-ttu-id="eade2-134">Las bases de datos se protegen mediante copias de seguridad automáticas que se realizan con las siguientes frecuencias:</span><span class="sxs-lookup"><span data-stu-id="eade2-134">Databases are protected by automatic backups at the following frequencies:</span></span>

| <span data-ttu-id="eade2-135">Tipo de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="eade2-135">Type of backup</span></span> | <span data-ttu-id="eade2-136">Frecuencia</span><span class="sxs-lookup"><span data-stu-id="eade2-136">Frequency</span></span> |
| --- | --- |
| <span data-ttu-id="eade2-137">Copia de seguridad completa de base de datos</span><span class="sxs-lookup"><span data-stu-id="eade2-137">Full database backup</span></span> | <span data-ttu-id="eade2-138">Semanal</span><span class="sxs-lookup"><span data-stu-id="eade2-138">Weekly</span></span> |
| <span data-ttu-id="eade2-139">Copia de seguridad diferencia de base de datos</span><span class="sxs-lookup"><span data-stu-id="eade2-139">Differential database backup</span></span> | <span data-ttu-id="eade2-140">Cada 12-24 horas</span><span class="sxs-lookup"><span data-stu-id="eade2-140">Every 12-24 hours</span></span> |
| <span data-ttu-id="eade2-141">Copia de seguridad de registro de transacciones</span><span class="sxs-lookup"><span data-stu-id="eade2-141">Transaction log backup</span></span> | <span data-ttu-id="eade2-142">Cada 5-10 minutos</span><span class="sxs-lookup"><span data-stu-id="eade2-142">Every 5 to 10 minutes</span></span> |

<span data-ttu-id="eade2-143">Microsoft conserva suficientes copias de seguridad para permitir la Restauración a un momento dado (PITR) de los últimos 14 días.</span><span class="sxs-lookup"><span data-stu-id="eade2-143">Microsoft retains sufficient backups to allow for Point in Time Restore (PITR) within the last 14 days.</span></span> 

<span data-ttu-id="eade2-144">Para obtener más información sobre copias de seguridad, consulte  [Obtener información sobre las copias de seguridad automáticas de SQL Database](https://docs.microsoft.com/azure/azure-sql/database/automated-backups-overview?tabs=single-database).</span><span class="sxs-lookup"><span data-stu-id="eade2-144">For more information, see [Learn about automatic SQL Database backups](https://docs.microsoft.com/azure/azure-sql/database/automated-backups-overview?tabs=single-database).</span></span> 

## <a name="can-i-request-a-copy-of-the-backup-of-my-production-database"></a><span data-ttu-id="eade2-145">¿Puedo solicitar una copia de la copia de seguridad de mi base de datos de producción?</span><span class="sxs-lookup"><span data-stu-id="eade2-145">Can I request a copy of the backup of my production database?</span></span> 

<span data-ttu-id="eade2-146">Nº</span><span class="sxs-lookup"><span data-stu-id="eade2-146">No.</span></span> <span data-ttu-id="eade2-147">Puede enviar una solicitud de servicio de actualización de base de datos para copiar su entorno de producción en su entorno de espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="eade2-147">You can submit a database refresh service request to copy your Production environment to your Sandbox environment, however.</span></span> <span data-ttu-id="eade2-148">Puede implementar una base de datos de Azure SQL en su propio inquilino de Azure y usar la característica BYOD para sincronizar los datos de su entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="eade2-148">You can deploy an Azure SQL database in your own Azure tenant and use the BYOD feature to synchronize data from your Production environment.</span></span> <span data-ttu-id="eade2-149">Para obtener más información, consulte [Usar su propia base de datos (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database).</span><span class="sxs-lookup"><span data-stu-id="eade2-149">For more information, see [Bring your own database (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database).</span></span> 

## <a name="how-do-i-move-my-sandbox-environment-to-production-for-go-live"></a><span data-ttu-id="eade2-150">¿Cómo paso mi entorno de espacio aislado a producción para la puesta en marcha?</span><span class="sxs-lookup"><span data-stu-id="eade2-150">How do I move my Sandbox environment to Production for go-live?</span></span> 

<span data-ttu-id="eade2-151">Como no está disponible una característica de copia para pasar de un entorno de espacio aislado a un entorno de producción, debe usar paquetes de datos para mover datos a su entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="eade2-151">Because a copy feature isn't available to move your environment from a Sandbox to a Production environment, you must use data packages to move data into your Production environment.</span></span>  

<span data-ttu-id="eade2-152">Recomendamos mantener una lista clara de entidades configuradas en el espacio aislado durante todo el proyecto.</span><span class="sxs-lookup"><span data-stu-id="eade2-152">We recommend maintaining a clear list of entities configured in your Sandbox throughout the project.</span></span> <span data-ttu-id="eade2-153">A continuación, pruebe el proceso de transferencia y migración de los paquetes de datos necesarios para la puesta en marcha.</span><span class="sxs-lookup"><span data-stu-id="eade2-153">Then test the process of cutover and migration of any data packages needed for your go-live.</span></span> <span data-ttu-id="eade2-154">Debe mover manualmente los paquetes de datos al entorno de producción cuando esté listo para la puesta en marcha.</span><span class="sxs-lookup"><span data-stu-id="eade2-154">You must manually move any data packages into the Production environment when you are ready to go live.</span></span> 

## <a name="what-should-i-do-if-my-production-environment-is-down"></a><span data-ttu-id="eade2-155">¿Qué hago si mi entorno de producción no funciona?</span><span class="sxs-lookup"><span data-stu-id="eade2-155">What should I do if my Production environment is down?</span></span> 

<span data-ttu-id="eade2-156">Para notificar una interrupción del entorno de producción, siga el proceso descrito en  [Notificar una interrupción de la producción](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/report-production-outage).</span><span class="sxs-lookup"><span data-stu-id="eade2-156">To report a Production outage, follow the process described in [Report a production outage](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/report-production-outage).</span></span> 

 ## <a name="see-also"></a><span data-ttu-id="eade2-157">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eade2-157">See also</span></span>

 [<span data-ttu-id="eade2-158">Prepararse para la publicación</span><span class="sxs-lookup"><span data-stu-id="eade2-158">Prepare for go-live</span></span>](hr-admin-go-live-prepare.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]