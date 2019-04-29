---
title: Novedades y cambios en Dynamics 365 for Talent (7 de febrero de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 02/07/2019
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
ms.search.validFrom: 2019-02-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: b89fc15130755a80b56f26cf7c61674a26f43e36
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2019
ms.locfileid: "858937"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-february-7-2019"></a><span data-ttu-id="9f0fc-103">Novedades y cambios en Dynamics 365 for Talent (7 de febrero de 2019)</span><span class="sxs-lookup"><span data-stu-id="9f0fc-103">What's new or changed in Dynamics 365 for Talent (February 7, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9f0fc-104">Este tema describe las características que son nuevas o que se han cambiado en Talent.</span><span class="sxs-lookup"><span data-stu-id="9f0fc-104">This topic describes features that are either new or changed in Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="9f0fc-105">Cambios en Attract</span><span class="sxs-lookup"><span data-stu-id="9f0fc-105">Changes in Attract</span></span>

### <a name="interview-scheduling-enhancements"></a><span data-ttu-id="9f0fc-106">Mejoras en la programación de la entrevista</span><span class="sxs-lookup"><span data-stu-id="9f0fc-106">Interview scheduling enhancements</span></span>
<span data-ttu-id="9f0fc-107">Se han realizado mejoras en la experiencia completa de la programación de entrevistas.</span><span class="sxs-lookup"><span data-stu-id="9f0fc-107">Improvements have been made to the end-to-end interview scheduling experience.</span></span> <span data-ttu-id="9f0fc-108">Ahora puede ver la disponibilidad del calendario de un candidato interno y usar el calendario del candidato interno para las recomendaciones de la programación.</span><span class="sxs-lookup"><span data-stu-id="9f0fc-108">You can now see the calendar availability of an internal candidate and use the internal candidate’s calendar for schedule recommendations.</span></span> <span data-ttu-id="9f0fc-109">Para obtener más información acerca de la programación, consulte [Programación de entrevista y comentarios](interview-scheduling-feedback.md).</span><span class="sxs-lookup"><span data-stu-id="9f0fc-109">For more information, see [Interview scheduling and feedback](interview-scheduling-feedback.md).</span></span>

### <a name="job-posting-to-linkedin--company-mismatch-issue-fixed"></a><span data-ttu-id="9f0fc-110">Corregido el problema de no concordancia entre la publicación de oferta en LinkedIn y la empresa</span><span class="sxs-lookup"><span data-stu-id="9f0fc-110">Job posting to LinkedIn – company mismatch issue fixed</span></span>
<span data-ttu-id="9f0fc-111">Se ha corregido un problema por el que los trabajos publicados en LinkedIn desde Attract aparecían bajo una empresa incorrecta.</span><span class="sxs-lookup"><span data-stu-id="9f0fc-111">An issue has been fixed where jobs posted to LinkedIn from Attract were appearing under the wrong company name.</span></span> <span data-ttu-id="9f0fc-112">Para obtener más información, consulte [Crear, aprobar y publicar trabajos en Attract](creating-jobs-attract.md).</span><span class="sxs-lookup"><span data-stu-id="9f0fc-112">For more information, see [Create, approve, and post jobs in Attract](creating-jobs-attract.md).</span></span>

### <a name="career-site-url-displayed-in-admin-settings"></a><span data-ttu-id="9f0fc-113">URL del sitio de Proyectos profesionales que se muestra en la configuración de gestión</span><span class="sxs-lookup"><span data-stu-id="9f0fc-113">Career site URL displayed in Admin settings</span></span>
<span data-ttu-id="9f0fc-114">Ahora la dirección URL de la página principal del sitio de Proyectos profesionales se muestra en **Configuración de administrador** en **Gestión del sitio de desarrollo profesional**.</span><span class="sxs-lookup"><span data-stu-id="9f0fc-114">The career site home page URL is now displayed in **Admin Settings** under **Career Site management**.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="9f0fc-115">Cambios en Core HR</span><span class="sxs-lookup"><span data-stu-id="9f0fc-115">Changes in Core HR</span></span>

<span data-ttu-id="9f0fc-116">**Compilación 8.1.2134**</span><span class="sxs-lookup"><span data-stu-id="9f0fc-116">**Build 8.1.2134**</span></span>

### <a name="multiple-compensation-levels-supported-on-jobs"></a><span data-ttu-id="9f0fc-117">Varios niveles de compensación compatibles en trabajos</span><span class="sxs-lookup"><span data-stu-id="9f0fc-117">Multiple compensation levels supported on jobs</span></span>
<span data-ttu-id="9f0fc-118">Este cambio permite que más de un nivel de compensación se defina en un trabajo, lo que habilita intervalos de compensación fija del empleado que pueden variar entre los planes cuando se utiliza el mismo trabajo.</span><span class="sxs-lookup"><span data-stu-id="9f0fc-118">This change allows for more than one compensation level to be defined on a job, enabling employee fixed compensation ranges which may differ between plans when using the same job.</span></span> 

<span data-ttu-id="9f0fc-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9f0fc-119">For example:</span></span>    
<span data-ttu-id="9f0fc-120">*Trabajo* - Administrador de cuentas *Niveles de compensación asociados:* B1 y B2 - Cada nivel tiene un intervalo de valores definidos.</span><span class="sxs-lookup"><span data-stu-id="9f0fc-120">*Job* - Account Manager *Associated compensation levels:* B1 and B2 - Each level has a defined range of values.</span></span> <span data-ttu-id="9f0fc-121">B1 = Min 50 000, Med 60 000, Max 75 000 y B2 = Min 65 000, Med 74 000, Max 85 000.</span><span class="sxs-lookup"><span data-stu-id="9f0fc-121">B1 = Min 50,000, Mid 60,000, Max 75,000 and B2 = Min 65,000, Mid 74,000, Max 85,000.</span></span> <span data-ttu-id="9f0fc-122">Al crear la compensación fija de los empleados, en función de las reglas de idoneidad definidas, ahora cada plan fijo podrá señalar al mismo trabajo y seleccionar diferentes niveles en el trabajo.</span><span class="sxs-lookup"><span data-stu-id="9f0fc-122">When creating fixed compensation for employees, based on the eligibility rules defined, each fixed plan can now point to the same job and to different levels on the job.</span></span> <span data-ttu-id="9f0fc-123">Esto posibilita que los planes estén definidos en varias empresas/regiones y que apunten al mismo trabajo pero a diferentes intervalos sin duplicar trabajos en la cuenta para estas diferencias.</span><span class="sxs-lookup"><span data-stu-id="9f0fc-123">This allows for plans to be defined in different regions/companies and point to the same job but different ranges without duplicating jobs to account for these differences.</span></span>

### <a name="compensation-level-field-has-been-added-to-the-employee-fixed-compensation-entity"></a><span data-ttu-id="9f0fc-124">El campo del nivel de compensación se ha agregado a la entidad de la compensación fija del empleado</span><span class="sxs-lookup"><span data-stu-id="9f0fc-124">Compensation level field has been added to the Employee fixed compensation entity</span></span> 
<span data-ttu-id="9f0fc-125">Con la actualización, se ha actualizado la entidad de compensación fija del empleado para incluir el campo **Nivel de compensación**.</span><span class="sxs-lookup"><span data-stu-id="9f0fc-125">With this update, the employee fixed compensation entity has been updated to include the **Compensation level** field.</span></span> <span data-ttu-id="9f0fc-126">Esta adición facilita actualizar los planes de compensación fija del empleado.</span><span class="sxs-lookup"><span data-stu-id="9f0fc-126">This addition makes it easier to update employee fixed compensation plans.</span></span> 

### <a name="update-job-family-when-updating-and-creating-new-positions"></a><span data-ttu-id="9f0fc-127">Actualización de la familia del trabajo cuando actualiza o crea nuevos puestos</span><span class="sxs-lookup"><span data-stu-id="9f0fc-127">Update Job family when updating and creating new positions</span></span>
<span data-ttu-id="9f0fc-128">Cuando cambie el trabajo de un puesto, **Familia de trabajo** ahora tomará un valor predeterminado basado en el trabajo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="9f0fc-128">When changing the job on a position, **Job family** will now default based on the job selected.</span></span>

### <a name="performance-improvements-when-rendering-workspaces"></a><span data-ttu-id="9f0fc-129">Mejoras del rendimiento al generar espacios de trabajo</span><span class="sxs-lookup"><span data-stu-id="9f0fc-129">Performance improvements when rendering workspaces</span></span>
<span data-ttu-id="9f0fc-130">Las fichas de análisis de zonas de trabajo ahora se cargarán solo cuando se tenga acceso a dichas páginas.</span><span class="sxs-lookup"><span data-stu-id="9f0fc-130">Analytics tabs on workspaces will now load only when accessing those pages.</span></span> <span data-ttu-id="9f0fc-131">Un indicador se mostrará durante la representación inicial de la página en la esquina superior izquierda de la página.</span><span class="sxs-lookup"><span data-stu-id="9f0fc-131">An indicator will display during the initial rendering of the page in the upper-left corner of the page.</span></span>
