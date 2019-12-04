---
title: Novedades y cambios en Dynamics 365 Talent (5 de noviembre de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 11/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-11-05
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e6a81209c3c4a95ee51668533d40d4aecc1d58b9
ms.sourcegitcommit: a46fb06138f7f82e973dca3157d30f9b21d3a70b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2019
ms.locfileid: "2778391"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-november-5-2019"></a><span data-ttu-id="a4916-103">Novedades y cambios en Dynamics 365 Talent (5 de noviembre de 2019)</span><span class="sxs-lookup"><span data-stu-id="a4916-103">What's new or changed in Dynamics 365 Talent (November 5, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a4916-104">Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="a4916-104">This topic describes features that are either new or changed in Dynamics 365 Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="a4916-105">Cambios en Attract</span><span class="sxs-lookup"><span data-stu-id="a4916-105">Changes in Attract</span></span>

<span data-ttu-id="a4916-106">Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="a4916-106">This release includes minor bug fixes for Dynamics 365 Talent: Attract.</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="a4916-107">Cambios en Onboard</span><span class="sxs-lookup"><span data-stu-id="a4916-107">Changes in Onboard</span></span>

<span data-ttu-id="a4916-108">Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="a4916-108">This release includes minor bug fixes for Dynamics 365 Talent: Onboard.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="a4916-109">Cambios en Core HR</span><span class="sxs-lookup"><span data-stu-id="a4916-109">Changes in Core HR</span></span>

<span data-ttu-id="a4916-110">Los cambios que se describen en esta sección se aplican a la compilación número 8.1.2598.</span><span class="sxs-lookup"><span data-stu-id="a4916-110">Changes described in this section apply to build number 8.1.2598.</span></span> <span data-ttu-id="a4916-111">Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="a4916-111">The numbers in parentheses in some headings refer to support numbers in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

### <a name="copy-a-core-hr-instance"></a><span data-ttu-id="a4916-112">Copiar una instancia de Core HR</span><span class="sxs-lookup"><span data-stu-id="a4916-112">Copy a Core HR instance</span></span>

<span data-ttu-id="a4916-113">En la versión de esta semana, puede utilizar los servicios Microsoft Dynamics Lifecycle Services (LCS) para copiar una base de datos de Microsoft Dynamics 365 Talent: Core HR en un entorno de espacio retirado.</span><span class="sxs-lookup"><span data-stu-id="a4916-113">In this week's release, you can use Microsoft Dynamics Lifecycle Services (LCS) to copy a Microsoft Dynamics 365 Talent: Core HR database to a sandbox environment.</span></span> <span data-ttu-id="a4916-114">Si tiene otro entorno de espacio retirado, también puede copiar la base de datos del entorno a un entorno de espacio aislado destinado.</span><span class="sxs-lookup"><span data-stu-id="a4916-114">If you have another sandbox environment, you can also copy the database from that environment to a targeted sandbox environment.</span></span> <span data-ttu-id="a4916-115">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="a4916-115">For more information, see:</span></span>

- <span data-ttu-id="a4916-116">[Una administración de entorno más amplio](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/broader-environment-management) en el plan de la oleada 2 de la versión 2019 de Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="a4916-116">[Broader environment management](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/broader-environment-management) in the Dynamics 365: 2019 release wave 2 plan</span></span>

- <span data-ttu-id="a4916-117">[Copiar una instancia de Core HR](hr-copy-instance.md) en la documentación de Talent</span><span class="sxs-lookup"><span data-stu-id="a4916-117">[Copy a Core HR instance](hr-copy-instance.md) in Talent documentation</span></span>

### <a name="common-data-service-integration-batch-jobs-arent-created-when-common-data-service-integration-is-enabled-388030"></a><span data-ttu-id="a4916-118">Los trabajos por lotes de la integración Common Data Service no se crean cuando está habilitada la integración Common Data Service (388030)</span><span class="sxs-lookup"><span data-stu-id="a4916-118">Common Data Service integration batch jobs aren't created when Common Data Service integration is enabled (388030)</span></span>

<span data-ttu-id="a4916-119">Este cambio creará trabajos por lotes para la integración de Common Data Service cuando esté habilitado.</span><span class="sxs-lookup"><span data-stu-id="a4916-119">This change will create batch jobs for Common Data Service integration when it's enabled.</span></span>

### <a name="the-hcmpersonimageentity-doesnt-resize-the-person-image-when-uploaded-369469"></a><span data-ttu-id="a4916-120">HcmPersonImageEntity no volverá a cambiar el tamaño de imagen de la persona cuando se carga (369469)</span><span class="sxs-lookup"><span data-stu-id="a4916-120">The HcmPersonImageEntity doesn't resize the person image when uploaded (369469)</span></span>

<span data-ttu-id="a4916-121">La versión de esta semana cambia cómo se cambia el tamaño a las imágenes para un mejor rendimiento cuando se importan a través de la gestión de datos.</span><span class="sxs-lookup"><span data-stu-id="a4916-121">This week's release changes how images are resized for better performance when imported through data management.</span></span>

### <a name="a-positions-available-for-assignment-date-can-be-earlier-than-the-activation-date-340103"></a><span data-ttu-id="a4916-122">Una Fecha de disponible para la asignación de un puesto puede ser anterior a la Fecha de activación (340103)</span><span class="sxs-lookup"><span data-stu-id="a4916-122">A position's Available for assignment date can be earlier than the Activation date (340103)</span></span>

<span data-ttu-id="a4916-123">Con este cambio, aparecerá una advertencia si selecciona una **Fecha de disponible para la asignación** que sea anterior a la **Fecha de activación** del puesto.</span><span class="sxs-lookup"><span data-stu-id="a4916-123">With this change, a warning will appear if you select an **Available for assignment date** that's earlier than the position's **Activation date**.</span></span>

### <a name="cant-create-a-compensation-change-request-in-employee-self-service-for-step-based-plans-376872"></a><span data-ttu-id="a4916-124">No puede crear una solicitud de cambio de compensación en el autoservicio del empleado para los planes basados en pasos (376872)</span><span class="sxs-lookup"><span data-stu-id="a4916-124">Can't create a compensation change request in employee self-service for step-based plans (376872)</span></span>

<span data-ttu-id="a4916-125">Esta versión corrige un problema al solicitar cambios de compensación con el autoservicio del empleado para los planes basados en pasos.</span><span class="sxs-lookup"><span data-stu-id="a4916-125">This release corrects an issue when requesting compensation changes through employee self-service for step-based plans.</span></span> 

### <a name="reason-code-doesnt-sync-to-common-data-service-if-the-description-is-longer-than-30-characters-core-hr-allows-60-352682"></a><span data-ttu-id="a4916-126">El código de motivo no se sincroniza con Common Data Service si la descripción tiene más de 30 caracteres, Core HR permite 60 (352682)</span><span class="sxs-lookup"><span data-stu-id="a4916-126">Reason code doesn't sync to Common Data Service if the description is longer than 30 characters, Core HR allows 60 (352682)</span></span>

<span data-ttu-id="a4916-127">Con este cambio, los códigos de motivo con más de 30 caracteres se actualizarán en Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a4916-127">with this change, reason codes with more than 30 characters will be updated in Common Data Service.</span></span> <span data-ttu-id="a4916-128">Los cambios realizados en Common Data Service también se reflejarán en Talent.</span><span class="sxs-lookup"><span data-stu-id="a4916-128">Changes made in Common Data Service will also be reflected back in Talent.</span></span>

### <a name="address-integration-from-talent-to-finance-and-operations-351961"></a><span data-ttu-id="a4916-129">Integración de direcciones de Talent a Finance and Operations (351961)</span><span class="sxs-lookup"><span data-stu-id="a4916-129">Address integration from Talent to Finance and Operations (351961)</span></span>

<span data-ttu-id="a4916-130">Esta versión corrige un problema en las direcciones que se actualizaban en Talent pero no se actualizaban en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a4916-130">This release fixes an issue where addresses updated in Talent weren't updating in Finance and Operations.</span></span> <span data-ttu-id="a4916-131">Los cambios en los bloques de direcciones ahora se actualizarán.</span><span class="sxs-lookup"><span data-stu-id="a4916-131">Changes to address blocks will now update.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="a4916-132">Próximamente</span><span class="sxs-lookup"><span data-stu-id="a4916-132">Coming soon</span></span>

### <a name="print-performance-reviews"></a><span data-ttu-id="a4916-133">Imprimir evaluaciones del rendimiento</span><span class="sxs-lookup"><span data-stu-id="a4916-133">Print performance reviews</span></span>

<span data-ttu-id="a4916-134">Consulte [Imprimir evaluaciones del rendimiento](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) en el plan de la oleada 2 de la versión Dynamics 365: 2019.</span><span class="sxs-lookup"><span data-stu-id="a4916-134">See [Print performance reviews](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) in the Dynamics 365: 2019 release wave 2 plan.</span></span>

### <a name="feature-management-workspace"></a><span data-ttu-id="a4916-135">Espacio de trabajo Administración de características.</span><span class="sxs-lookup"><span data-stu-id="a4916-135">Feature management workspace</span></span>

<span data-ttu-id="a4916-136">Las características se suman y se actualizan en cada versión.</span><span class="sxs-lookup"><span data-stu-id="a4916-136">Features are added and updated in every release.</span></span> <span data-ttu-id="a4916-137">La experiencia de administración de características proporciona un espacio de trabajo en el que puede ver una lista de características que se han entregado en cada versión.</span><span class="sxs-lookup"><span data-stu-id="a4916-137">The feature management experience provides a workspace where you can view a list of features that have been delivered in each release.</span></span> <span data-ttu-id="a4916-138">De forma predeterminada, las nuevas características están desactivadas.</span><span class="sxs-lookup"><span data-stu-id="a4916-138">By default, new features are turned off.</span></span> <span data-ttu-id="a4916-139">Puede usar el espacio de trabajo para activarlas y ver su documentación.</span><span class="sxs-lookup"><span data-stu-id="a4916-139">You can use the workspace to turn them on and view the documentation for them.</span></span>

<span data-ttu-id="a4916-140">Para obtener más información acerca de los cambios que se incluyen con la administración de características, consulte [Visión general de la administración de características](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span><span class="sxs-lookup"><span data-stu-id="a4916-140">To learn more about the changes coming with feature management, see [Feature management overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span></span>
