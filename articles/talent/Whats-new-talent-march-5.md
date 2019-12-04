---
title: Novedades y cambios en Dynamics 365 Talent (5 de marzo de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 03/05/2019
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
ms.search.validFrom: 2019-03-05
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 561b6fad0facad86e9a7bc8f36218ab98fcec73c
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773274"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-march-5-2019"></a><span data-ttu-id="d5858-103">Novedades y cambios en Dynamics 365 Talent (5 de marzo de 2019)</span><span class="sxs-lookup"><span data-stu-id="d5858-103">What's new or changed in Dynamics 365 Talent (March 5, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d5858-104">Este tema describe las características que son nuevas o que se han cambiado en Talent.</span><span class="sxs-lookup"><span data-stu-id="d5858-104">This topic describes features that are either new or changed in Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="d5858-105">Cambios en Attract</span><span class="sxs-lookup"><span data-stu-id="d5858-105">Changes in Attract</span></span>

### <a name="extending-option-sets-in-attract"></a><span data-ttu-id="d5858-106">Ampliación de conjuntos de opciones en Attract</span><span class="sxs-lookup"><span data-stu-id="d5858-106">Extending option sets in Attract</span></span>

<span data-ttu-id="d5858-107">En Attract, hay varios campos que son conjuntos de opciones en Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="d5858-107">In Attract, there are multiple fields that are option sets within the Common Data Service.</span></span> <span data-ttu-id="d5858-108">Se han introducido nuevas capacidades para extender los conjuntos de opciones, comenzando por el campo de motivo **Rechazo**, el campo **Tipo de empleo** , y el campo **Tipo de la antigüedad**.</span><span class="sxs-lookup"><span data-stu-id="d5858-108">New capabilities have been introduced to extend the option sets, beginning with the **Rejection** reason field, **Employment type** field, and **Seniority type** field.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d5858-109">La propuesta de empleo en la funcionalidad de LinkedIn requiere el uso de los campos **Tipo de empleo** y **Tipo de antigüedad** en la página **Detalles del trabajo**.</span><span class="sxs-lookup"><span data-stu-id="d5858-109">The job posting to LinkedIn functionality requires the use of the **Employment type** and **Seniority type** fields on the **Job details** page.</span></span> <span data-ttu-id="d5858-110">Los valores predeterminados de estos campos son compatibles con LinkedIn y se visualizan cuando se registra el trabajo.</span><span class="sxs-lookup"><span data-stu-id="d5858-110">The default values in these fields are supported by LinkedIn and are displayed when the job is posted.</span></span> <span data-ttu-id="d5858-111">Si va a publicar trabajos en LinkedIn y modifica los valores del conjunto de opciones existente para estos campos, el trabajo seguirá publicado, pero LinkedIn no mostrará los valores de **Tipo de empleo** y **Tipo de la antigüedad** personalizados.</span><span class="sxs-lookup"><span data-stu-id="d5858-111">If you are posting jobs to LinkedIn and you modify the existing option set values for these fields, the job will still post, but LinkedIn will not display the custom **Employment type** and **Seniority type** values.</span></span>

## <a name="changes-in-onboarding"></a><span data-ttu-id="d5858-112">Cambios en Onboarding</span><span class="sxs-lookup"><span data-stu-id="d5858-112">Changes in Onboarding</span></span>

### <a name="private-preview-for-onboard-teams"></a><span data-ttu-id="d5858-113">Versión preliminar privada para los equipos Onboard</span><span class="sxs-lookup"><span data-stu-id="d5858-113">Private preview for Onboard teams</span></span>
<span data-ttu-id="d5858-114">Ahora puede compartir y colaborar fácilmente en las plantillas de toda la organización.</span><span class="sxs-lookup"><span data-stu-id="d5858-114">You can now easily share and collaborate on templates across your entire organization.</span></span> <span data-ttu-id="d5858-115">Para obtener más información, consulte [Compartir prácticas recomendadas en toda la organización mediante los equipos de Onboard](https://docs.microsoft.com/business-applications-release-notes/April19/dynamics365-talent/onboard/share-best-practices-teams).</span><span class="sxs-lookup"><span data-stu-id="d5858-115">For more information, see [Share best practices across your organization using Onboard Teams](https://docs.microsoft.com/business-applications-release-notes/April19/dynamics365-talent/onboard/share-best-practices-teams).</span></span>

### <a name="private-preview-for-assignee-placeholders"></a><span data-ttu-id="d5858-116">Vista previa privada para marcadores asignados</span><span class="sxs-lookup"><span data-stu-id="d5858-116">Private preview for assignee placeholders</span></span>
<span data-ttu-id="d5858-117">Puede enriquecer las plantillas asignando actividades a roles en lugar de personas.</span><span class="sxs-lookup"><span data-stu-id="d5858-117">You can enrich your templates by assigning activities to roles instead of individuals.</span></span> <span data-ttu-id="d5858-118">Los roles se asignan a individuos en el momento de la creación de la Guía.</span><span class="sxs-lookup"><span data-stu-id="d5858-118">Roles are then assigned to individuals at the time of guide creation.</span></span> <span data-ttu-id="d5858-119">Para obtener más información, consulte [Optimizar la administración de guías asignando actividades a roles](https://docs.microsoft.com/business-applications-release-notes/April19/dynamics365-talent/onboard/assign-activities-roles)</span><span class="sxs-lookup"><span data-stu-id="d5858-119">For more information, see [Streamline guide administration by assigning activities to roles](https://docs.microsoft.com/business-applications-release-notes/April19/dynamics365-talent/onboard/assign-activities-roles).</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="d5858-120">Cambios en Core HR</span><span class="sxs-lookup"><span data-stu-id="d5858-120">Changes in Core HR</span></span>
<span data-ttu-id="d5858-121">**Compilación 8.1.2178**</span><span class="sxs-lookup"><span data-stu-id="d5858-121">**Build 8.1.2178**</span></span>

### <a name="configure-workflow-to-auto-approve-or-follow-workflow-when-an-hr-or-line-manager-submits-or-updates-time-off-requests"></a><span data-ttu-id="d5858-122">Configuración del flujo de trabajo para la aprobación automática o para seguir un flujo de trabajo cuando un director de RR.HH o de línea envía o actualiza solicitudes de licencia</span><span class="sxs-lookup"><span data-stu-id="d5858-122">Configure workflow to auto-approve or follow workflow when an HR or line manager submits or updates time off requests</span></span>
<span data-ttu-id="d5858-123">Se han agregado nuevas condiciones de flujo de trabajo para permitir que las solicitudes de la licencia automáticamente sean aprobadas si las envía el jefe de un empleado o RR.HH.</span><span class="sxs-lookup"><span data-stu-id="d5858-123">New workflow conditions have been added to allow for leave requests to be automatically approved if submitted by an employee’s manager or by HR.</span></span> <span data-ttu-id="d5858-124">Una forma de conseguir esta aprobación automática en un flujo de trabajo es habilitar una acción automática en la aprobación de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d5858-124">One way to achieve this auto-approval on a workflow is to enable an automatic action on the workflow approval.</span></span>

<span data-ttu-id="d5858-125">Las condiciones que se han agregado son:</span><span class="sxs-lookup"><span data-stu-id="d5858-125">The conditions that have been added include:</span></span>

- <span data-ttu-id="d5858-126">Registrado por - utilizado para evaluar el Id. de usuario del sistema del usuario que envió la solicitud al flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d5858-126">Submitted by - Used to evaluate the system user ID of the user who submitted the request to workflow.</span></span>
- <span data-ttu-id="d5858-127">Registrado en nombre de - utilizado para evaluar si la solicitud de licencia se muestra en nombre del trabajador asociado a la solicitud.</span><span class="sxs-lookup"><span data-stu-id="d5858-127">Submitted on behalf of - Used to evaluate if the leave request was submitted on behalf of the worker associated to the request.</span></span>
- <span data-ttu-id="d5858-128">Registrado por recursos humanos - utilizado para evaluar si el usuario del sistema que envió la solicitud al flujo de trabajo tiene un rol de recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="d5858-128">Submitted by human resources - Used to evaluate if the system user who submitted the request to workflow is in a Human Resources role.</span></span>
- <span data-ttu-id="d5858-129">Registrado por el administrador - utilizado para evaluar si el usuario que envió la solicitud de la licencia al flujo de trabajo es administrador de la jerarquía de la línea del trabajador asociado a la solicitud.</span><span class="sxs-lookup"><span data-stu-id="d5858-129">Submitted by manager - Used to evaluate if the user who submitted the leave request to workflow is a line hierarchy manager of the worker associated to the request.</span></span>

### <a name="enable-employee-fixed-compensation-for-future-position-assignments"></a><span data-ttu-id="d5858-130">Habilitación de la compensación fija del empleado para asignaciones de puesto futuras</span><span class="sxs-lookup"><span data-stu-id="d5858-130">Enable employee fixed compensation for future position assignments</span></span>
<span data-ttu-id="d5858-131">Es típico que los empleados entren en una organización con una fecha de inicio futura.</span><span class="sxs-lookup"><span data-stu-id="d5858-131">It is typical for employees to join an organization with a future start date.</span></span> <span data-ttu-id="d5858-132">Este cambio permite definir la compensación fija para los empleados que tienen asignaciones de puesto futuras.</span><span class="sxs-lookup"><span data-stu-id="d5858-132">This change enables defining fixed compensation for employees with future position assignments.</span></span>

### <a name="position-payroll-fields-are-blank-when-editing-the-position"></a><span data-ttu-id="d5858-133">Los campos de nóminas del puesto están en blanco al editar el puesto</span><span class="sxs-lookup"><span data-stu-id="d5858-133">Position Payroll fields are blank when editing the position</span></span>
<span data-ttu-id="d5858-134">Con este cambio, al solicitar cambios en puestos ya existentes, los campos de nóminas ahora toman como valor predeterminado los valores actuales.</span><span class="sxs-lookup"><span data-stu-id="d5858-134">With this change, when requesting changes to existing positions, the payroll fields will now default to the current values.</span></span>

### <a name="other-miscellaneous-bug-fixes"></a><span data-ttu-id="d5858-135">Otras correcciones de errores diferentes</span><span class="sxs-lookup"><span data-stu-id="d5858-135">Other miscellaneous bug fixes</span></span>
<span data-ttu-id="d5858-136">En esta versión se incluyen otras correcciones de errores menores.</span><span class="sxs-lookup"><span data-stu-id="d5858-136">Other minor bug fixes are included with this release.</span></span>

### <a name="upgrade-to-common-data-service"></a><span data-ttu-id="d5858-137">Actualice a Common Data Service</span><span class="sxs-lookup"><span data-stu-id="d5858-137">Upgrade to Common Data Service</span></span>
<span data-ttu-id="d5858-138">Las fechas límites para actualizarse a Common Data Service se acercan rápidamente.</span><span class="sxs-lookup"><span data-stu-id="d5858-138">Deadlines to upgrade to Common Data Service are quickly approaching.</span></span> <span data-ttu-id="d5858-139">Inicie sesión en el centro de gestión de Power Apps para determinar si su base de datos debe actualizarse.</span><span class="sxs-lookup"><span data-stu-id="d5858-139">Sign in to the Power Apps Admin center to determine if your database needs to be upgraded.</span></span> <span data-ttu-id="d5858-140">Para obtener más información acerca de las fechas límites y de los pasos necesarios para realizar la actualización, consulte [Actualizar a Common Data Service](https://docs.microsoft.com/common-data-service/upgradecds/introduction-upgrade-cds).</span><span class="sxs-lookup"><span data-stu-id="d5858-140">For more information about deadlines and necessary steps to upgrade, see [Upgrade to Common Data Service](https://docs.microsoft.com/common-data-service/upgradecds/introduction-upgrade-cds).</span></span>

## <a name="coming-soon"></a><span data-ttu-id="d5858-141">Próximamente</span><span class="sxs-lookup"><span data-stu-id="d5858-141">Coming soon</span></span>

###  <a name="advanced-compensation-security-fixed-and-variable"></a><span data-ttu-id="d5858-142">Seguridad de compensación avanzada (fija y variable)</span><span class="sxs-lookup"><span data-stu-id="d5858-142">Advanced compensation security (fixed and variable)</span></span>
<span data-ttu-id="d5858-143">En muchas organizaciones, los administradores de compensación y prestaciones solo pueden acceder a ciertos registros de compensación, como registros para los ejecutivos o los empleados basados en regiones.</span><span class="sxs-lookup"><span data-stu-id="d5858-143">In many organizations, compensation and benefits managers can only access certain compensation records, such as records for executives or regional-based employees.</span></span> <span data-ttu-id="d5858-144">Con este cambio, puede administrar y mantener los planes de compensación para distintos grupos de empleados en la organización.</span><span class="sxs-lookup"><span data-stu-id="d5858-144">With this change, you can manage and maintain the compensation plans for different employee populations in the organization.</span></span> <span data-ttu-id="d5858-145">Se pueden asignar roles de seguridad a los planes fijos y variables, lo que determinará el acceso a los planes y los datos del empleado relacionados con los planes, como el salario y los registros de bonificaciones.</span><span class="sxs-lookup"><span data-stu-id="d5858-145">Fixed and variable plans can be assigned security roles, which will determine the access to the plans and the employee data related to the plans, such as salary or bonus records.</span></span> <span data-ttu-id="d5858-146">Solo los roles con acceso podrán procesar la compensación para dichos empleados.</span><span class="sxs-lookup"><span data-stu-id="d5858-146">Only the roles with the given access will be able to process compensation for those employees.</span></span>

###  <a name="platform-update-24-for-finance-and-operations"></a><span data-ttu-id="d5858-147">Platform update 24 para Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d5858-147">Platform update 24 for Finance and Operations</span></span>
<span data-ttu-id="d5858-148">Para obtener detalles adicionales sobre la Platform update 24 for Finance and Operations, consulte [Novedades o cambios en la Platform update 24 para Finance and Operations (marzo de 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-24)</span><span class="sxs-lookup"><span data-stu-id="d5858-148">For additional details about Platform update 24 for Finance and Operations, see [What's new or changed in Finance and Operations platform update 24 (March 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-24).</span></span>
