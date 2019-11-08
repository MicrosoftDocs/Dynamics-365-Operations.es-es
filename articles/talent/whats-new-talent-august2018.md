---
title: Novedades y cambios en Dynamics 365 Talent - Core HR (agosto de 2018)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 08/27/2018
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
ms.search.validFrom: 2018-08-27
ms.dyn365.ops.version: Talent August 2018 update
ms.openlocfilehash: 14dc4d2a1b69f58d6d9c2466b2bcaf4f9185931e
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550283"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-august-2018"></a><span data-ttu-id="cd2df-103">Novedades y cambios en Dynamics 365 Talent - Core HR (agosto de 2018)</span><span class="sxs-lookup"><span data-stu-id="cd2df-103">What's new or changed in Dynamics 365 Talent - Core HR (August 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="cd2df-104">**Compilación 8.1.104**</span><span class="sxs-lookup"><span data-stu-id="cd2df-104">**Build 8.1.104**</span></span>

<span data-ttu-id="cd2df-105">Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 Talent: Core HR.</span><span class="sxs-lookup"><span data-stu-id="cd2df-105">This topic describes features that are either new or changed in Dynamics 365 Talent: Core HR.</span></span>

## <a name="view-expiring-records-in-manager-self-service"></a><span data-ttu-id="cd2df-106">Ver registros con fecha de vencimiento en autoservicio de directores</span><span class="sxs-lookup"><span data-stu-id="cd2df-106">View expiring records in Manager self service</span></span>

<span data-ttu-id="cd2df-107">Ahora se pueden ver los registros con fecha de vencimiento en el autoservicio de directores.</span><span class="sxs-lookup"><span data-stu-id="cd2df-107">You can now view expiring records in Manager self-service.</span></span> <span data-ttu-id="cd2df-108">Las nuevas opciones le permiten configurar qué información estará disponible para que la vean los administradores.</span><span class="sxs-lookup"><span data-stu-id="cd2df-108">New options are allow you to configure what information will be available for managers to view.</span></span> <span data-ttu-id="cd2df-109">Entre estos valores se incluyen:</span><span class="sxs-lookup"><span data-stu-id="cd2df-109">These include:</span></span>

-   <span data-ttu-id="cd2df-110">Certificados</span><span class="sxs-lookup"><span data-stu-id="cd2df-110">Certificates</span></span>

-   <span data-ttu-id="cd2df-111">Números de identificación</span><span class="sxs-lookup"><span data-stu-id="cd2df-111">Identification numbers</span></span>

-   <span data-ttu-id="cd2df-112">Períodos de prueba</span><span class="sxs-lookup"><span data-stu-id="cd2df-112">Probation periods</span></span>

-   <span data-ttu-id="cd2df-113">Filtrados</span><span class="sxs-lookup"><span data-stu-id="cd2df-113">Screenings</span></span>

-   <span data-ttu-id="cd2df-114">Pruebas</span><span class="sxs-lookup"><span data-stu-id="cd2df-114">Tests</span></span>

<span data-ttu-id="cd2df-115">Esta función también proporciona la capacidad para especificar el intervalo de días en los que buscar los registros que vencen.</span><span class="sxs-lookup"><span data-stu-id="cd2df-115">This feature also gives you the ability to specify the range of days in which to look for expiring records.</span></span>

## <a name="configurable-transfer-actions"></a><span data-ttu-id="cd2df-116">Acciones configurables de transferencia</span><span class="sxs-lookup"><span data-stu-id="cd2df-116">Configurable transfer actions</span></span>

<span data-ttu-id="cd2df-117">Puede configurar por rol las opciones que estarán disponibles durante la entrada de una solicitud de transferencia.</span><span class="sxs-lookup"><span data-stu-id="cd2df-117">You can configure by role the options that will be available during the entry of a transfer request.</span></span> <span data-ttu-id="cd2df-118">Esta característica añade flexibilidad a través de las funciones de una organización.</span><span class="sxs-lookup"><span data-stu-id="cd2df-118">This feature provides additional flexibility across the roles in an organization.</span></span>

<span data-ttu-id="cd2df-119">Por ejemplo, los administradores que solicitan transferencias de empleado pueden no tener acceso para realizar sugerencias o para especificar importes de compensación asociados a la solicitud de transferencia.</span><span class="sxs-lookup"><span data-stu-id="cd2df-119">For example, managers requesting employee transfers may not have access to suggest or enter compensation amounts or select the task lists that will be associated with the transfer request.</span></span> <span data-ttu-id="cd2df-120">En este caso, los administradores pueden crear y enviar solicitudes de transferencia pero no se les permite especificar asignaciones de compensación o de la lista de tareas.</span><span class="sxs-lookup"><span data-stu-id="cd2df-120">In this case, managers can create and submit transfer requests but are not allowed to enter compensation or task list assignments.</span></span> <span data-ttu-id="cd2df-121">En esta misma configuración, RR. HH. podrá asignar nuevos valores de compensación así como asignar cualquier lista de comprobación adicional que se completará como resultado de completar la transferencia.</span><span class="sxs-lookup"><span data-stu-id="cd2df-121">In this same configuration, HR will be able to assign the new compensation values as well as assign any additional checklists to be completed as a result of the transfer completing.</span></span>

<span data-ttu-id="cd2df-122">De forma predeterminada, las nuevas opciones de configuración se establecen para no cambiar las capacidades antes de la actualización.</span><span class="sxs-lookup"><span data-stu-id="cd2df-122">By default, the new configuration options are set to not change the capabilities prior to this update.</span></span>

## <a name="leave-and-absence"></a><span data-ttu-id="cd2df-123">Bajas y ausencias</span><span class="sxs-lookup"><span data-stu-id="cd2df-123">Leave and absence</span></span>

<span data-ttu-id="cd2df-124">Ahora hay campos de fecha adicionales disponibles en licencia y ausencia.</span><span class="sxs-lookup"><span data-stu-id="cd2df-124">There are now additional Date fields available in Leave and Absence.</span></span>

<span data-ttu-id="cd2df-125">Con esta función puede establecer la base del período de acumulación en el nivel de plan para usar las fechas específicas del empleado.</span><span class="sxs-lookup"><span data-stu-id="cd2df-125">With this feature you can set the accrual period basis at the plan level to use specific employee dates.</span></span> <span data-ttu-id="cd2df-126">Esto permite usar fechas distintas de la fecha inicial del plan durante el proceso de acumulación de bajas.</span><span class="sxs-lookup"><span data-stu-id="cd2df-126">This allows for dates other than the plan start date to be used during the leave accrual process.</span></span> <span data-ttu-id="cd2df-127">Las opciones para fechas específicas del empleado incluyen los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="cd2df-127">Options for employee specific dates include the following values:</span></span>

-   <span data-ttu-id="cd2df-128">Aduana (disponible antes de la actualización)</span><span class="sxs-lookup"><span data-stu-id="cd2df-128">Custom (available prior to this update)</span></span>

-   <span data-ttu-id="cd2df-129">Fecha de aniversario</span><span class="sxs-lookup"><span data-stu-id="cd2df-129">Anniversary date</span></span>

-   <span data-ttu-id="cd2df-130">Fecha de contratación original</span><span class="sxs-lookup"><span data-stu-id="cd2df-130">Original hire date</span></span>

-   <span data-ttu-id="cd2df-131">Antigüedad</span><span class="sxs-lookup"><span data-stu-id="cd2df-131">Seniority date</span></span>

-   <span data-ttu-id="cd2df-132">Fecha inicial ajustada del trabajador</span><span class="sxs-lookup"><span data-stu-id="cd2df-132">Worker’s adjusted start date</span></span>

-   <span data-ttu-id="cd2df-133">Primer día de trabajo del trabajador</span><span class="sxs-lookup"><span data-stu-id="cd2df-133">Worker’s start date</span></span>

<span data-ttu-id="cd2df-134">Cuando está configurado para utilizar una de las fechas específicas de un empleado, el proceso de inscripción utilizará la fecha especificada para calcular los períodos de acumulación.</span><span class="sxs-lookup"><span data-stu-id="cd2df-134">When configured to use one of the employee specific dates, the enrollment process will use the specified date to calculate the accrual periods.</span></span> <span data-ttu-id="cd2df-135">La función del período de acumulación también se muestra en la inscripción del plan del empleado para ayudarle a comprender qué se está utilizando durante el proceso de acumulación.</span><span class="sxs-lookup"><span data-stu-id="cd2df-135">The accrual period basis is also displayed on the employee’s plan enrollment to help you understand what’s being used during the accrual process.</span></span>

## <a name="microsoft-word-integration"></a><span data-ttu-id="cd2df-136">Integración de Microsoft Word</span><span class="sxs-lookup"><span data-stu-id="cd2df-136">Microsoft Word integration</span></span>

<span data-ttu-id="cd2df-137">Las plantillas de documento se han habilitado en todo Core HR.</span><span class="sxs-lookup"><span data-stu-id="cd2df-137">Document templates have been enabled throughout Core HR.</span></span> <span data-ttu-id="cd2df-138">Esta función permite crear cartas e informes basados en las plantillas de Word que cree.</span><span class="sxs-lookup"><span data-stu-id="cd2df-138">This feature allows you to create letters and reports based on Word templates that you create.</span></span>

<span data-ttu-id="cd2df-139">La información adicional sobre esta característica está disponible en [Tutorial de integración de Office](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/office-integration/office-integration-tutorial?toc=/dynamics365/unified-operations/talent/toc.json).</span><span class="sxs-lookup"><span data-stu-id="cd2df-139">Additional information about this feature is available in the [Office integration tutorial](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/office-integration/office-integration-tutorial?toc=/dynamics365/unified-operations/talent/toc.json).</span></span>


## <a name="other-fixes"></a><span data-ttu-id="cd2df-140">Otras correcciones</span><span class="sxs-lookup"><span data-stu-id="cd2df-140">Other fixes</span></span>

<span data-ttu-id="cd2df-141">Este lanzamiento también incluye varias correcciones de errores, la adición de nuevas entidades, correcciones a las entidades existentes, y cambios de etiquetas localizados.</span><span class="sxs-lookup"><span data-stu-id="cd2df-141">This release also includes a number of bug fixes, the addition of new entities, fixes to existing entities, and localized label changes.</span></span>
