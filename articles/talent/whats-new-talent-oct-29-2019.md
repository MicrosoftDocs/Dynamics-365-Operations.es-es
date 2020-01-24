---
title: Novedades y cambios en Dynamics 365 Talent (29 de octubre de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 10/29/2019
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
ms.search.validFrom: 2019-10-29
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e2d79ee9e182df4a4efe65beb685567b1e7446ce
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897451"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-october-29-2019"></a><span data-ttu-id="e6758-103">Novedades y cambios en Dynamics 365 Talent (29 de octubre de 2019)</span><span class="sxs-lookup"><span data-stu-id="e6758-103">What's new or changed in Dynamics 365 Talent (October 29, 2019)</span></span>

<span data-ttu-id="e6758-104">Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="e6758-104">This topic describes features that are either new or changed in Dynamics 365 Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="e6758-105">Cambios en Attract</span><span class="sxs-lookup"><span data-stu-id="e6758-105">Changes in Attract</span></span>

<span data-ttu-id="e6758-106">Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="e6758-106">This release includes minor bug fixes for Dynamics 365 Talent: Attract.</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="e6758-107">Cambios en Onboard</span><span class="sxs-lookup"><span data-stu-id="e6758-107">Changes in Onboard</span></span>

<span data-ttu-id="e6758-108">Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="e6758-108">This release includes minor bug fixes for Dynamics 365 Talent: Onboard.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="e6758-109">Cambios en Core HR</span><span class="sxs-lookup"><span data-stu-id="e6758-109">Changes in Core HR</span></span>

<span data-ttu-id="e6758-110">Los cambios que se describen en esta sección se aplican a la compilación número 8.1.2586.</span><span class="sxs-lookup"><span data-stu-id="e6758-110">Changes described in this section apply to build number 8.1.2586.</span></span> <span data-ttu-id="e6758-111">Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="e6758-111">The numbers in parentheses in some headings refer to support numbers in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

### <a name="delete-parties-with-no-roles-should-be-on-by-default-371233"></a><span data-ttu-id="e6758-112">Eliminar partes sin roles estará activada solo de forma predeterminada (371233)</span><span class="sxs-lookup"><span data-stu-id="e6758-112">Delete parties with no roles should be on by default (371233)</span></span>

<span data-ttu-id="e6758-113">Al aprovisionar un nuevo entorno en Talent, **Eliminar partes si no hay roles** está activada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e6758-113">When you provision a new environment in Talent, **Delete parties if no roles exist** is turned on by default.</span></span> <span data-ttu-id="e6758-114">Al eliminar un trabajador, la parte asociada al trabajador no se quita a menos que esta configuración esté activada.</span><span class="sxs-lookup"><span data-stu-id="e6758-114">When you delete a worker, the party associated with the worker is not removed unless this setting is on.</span></span> <span data-ttu-id="e6758-115">Este cambio limita los registros duplicados en la libreta de direcciones global cuando necesite importar, cambia o volver a importar trabajadores.</span><span class="sxs-lookup"><span data-stu-id="e6758-115">This change limits duplicate records in the global address book when you need to import, change, or reimport workers.</span></span>

### <a name="draft-and-cancelled-leave-requests-should-be-allowed-to-be-deleted-in-common-data-service-376999"></a><span data-ttu-id="e6758-116">El borrador y solicitudes canceladas de licencia se deben permitir ser eliminado en Common Data Service (376999)</span><span class="sxs-lookup"><span data-stu-id="e6758-116">Draft and cancelled leave requests should be allowed to be deleted in Common Data Service (376999)</span></span>

<span data-ttu-id="e6758-117">Con este cambio, ahora puede eliminar solicitudes de ausencia con un estado **Borrador** o **Cancelado** en Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="e6758-117">With this change, you can now delete leave requests with a status of **Draft** or **Cancelled** in Common Data Service.</span></span>

### <a name="additional-list-values-in-custom-fields-arent-reflected-in-common-data-service-after-clicking-apply-on-the-custom-fields-form-379599"></a><span data-ttu-id="e6758-118">Los valores adicionales de la lista en campos personalizados no se reflejen en Common Data Service después de hacer clic en Aplicar en el formulario Campos personalizados (379599)</span><span class="sxs-lookup"><span data-stu-id="e6758-118">Additional list values in custom fields aren't reflected in Common Data Service after clicking Apply on the Custom fields form (379599)</span></span>

<span data-ttu-id="e6758-119">Al agregar nuevos valores de la lista a un campo personalizado existente que ya se ha sincronizado con Common Data Service, estarán ahora disponibles Common Data Service después de que aplique los cambios en el formulario **Campos personalizados**.</span><span class="sxs-lookup"><span data-stu-id="e6758-119">When you add new list values to an existing custom field that has already synchronized with Common Data Service, they're now available in Common Data Serivce after you apply your changes in the **Custom fields** form.</span></span>

### <a name="apply-onboarding-checklists-across-legal-entities-when-more-than-one-employment-exists-371270"></a><span data-ttu-id="e6758-120">Aplicar las listas de comprobación de incorporación en entidades jurídicas cuando haya más de un empleado (371270)</span><span class="sxs-lookup"><span data-stu-id="e6758-120">Apply onboarding checklists across legal entities when more than one employment exists (371270)</span></span>

<span data-ttu-id="e6758-121">En la versión de esta semana, puede aplicar listas de comprobación a los empleados con más de un empleo en **Formulario de trabajador > Listas de comprobación**.</span><span class="sxs-lookup"><span data-stu-id="e6758-121">In this week's release, you can apply checklists to employees with more than one employment in **Worker form > Checklists**.</span></span>

### <a name="benefits-open-enrollment-preview-feature-has-been-removed"></a><span data-ttu-id="e6758-122">Se ha quitado la característica de vista previa de inscripción abierta de beneficios</span><span class="sxs-lookup"><span data-stu-id="e6758-122">Benefits open enrollment preview feature has been removed</span></span>

<span data-ttu-id="e6758-123">Junto con nuestro anuncio en la entrada de blog de [inversiones estratégica en la excelencia operativa de Core HR](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/10/02/strategic-investments-in-core-hr-drive-operational-excellence), Microsoft ha quitado la característica de inscripción abierta de beneficios de la versión preliminar pública.</span><span class="sxs-lookup"><span data-stu-id="e6758-123">In conjunction with our announcement in the [Strategic investments in core HR drive operational excellence](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/10/02/strategic-investments-in-core-hr-drive-operational-excellence) blog post, Microsoft has removed the benefits open enrollment feature from public preview.</span></span> <span data-ttu-id="e6758-124">La nueva funcionalidad se publicará en el futuro.</span><span class="sxs-lookup"><span data-stu-id="e6758-124">New functionality will be released in the future.</span></span> <span data-ttu-id="e6758-125">El uso de producción de la función vista previa de inscripción abierta de beneficios no se admite.</span><span class="sxs-lookup"><span data-stu-id="e6758-125">Production use of the benefits open enrollment feature isn't be supported.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="e6758-126">Próximamente</span><span class="sxs-lookup"><span data-stu-id="e6758-126">Coming soon</span></span>

### <a name="print-performance-reviews"></a><span data-ttu-id="e6758-127">Imprimir evaluaciones del rendimiento</span><span class="sxs-lookup"><span data-stu-id="e6758-127">Print performance reviews</span></span>

<span data-ttu-id="e6758-128">Consulte [Imprimir evaluaciones del rendimiento](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) en el plan de la oleada 2 de la versión Dynamics 365: 2019.</span><span class="sxs-lookup"><span data-stu-id="e6758-128">See [Print performance reviews](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) in the Dynamics 365: 2019 release wave 2 plan.</span></span>

### <a name="feature-management-workspace"></a><span data-ttu-id="e6758-129">Espacio de trabajo Administración de características.</span><span class="sxs-lookup"><span data-stu-id="e6758-129">Feature management workspace</span></span>

<span data-ttu-id="e6758-130">Las características se suman y se actualizan en cada versión.</span><span class="sxs-lookup"><span data-stu-id="e6758-130">Features are added and updated in every release.</span></span> <span data-ttu-id="e6758-131">La experiencia de administración de características proporciona un espacio de trabajo en el que puede ver una lista de características que se han entregado en cada versión.</span><span class="sxs-lookup"><span data-stu-id="e6758-131">The feature management experience provides a workspace where you can view a list of features that have been delivered in each release.</span></span> <span data-ttu-id="e6758-132">De forma predeterminada, las nuevas características están desactivadas.</span><span class="sxs-lookup"><span data-stu-id="e6758-132">By default, new features are turned off.</span></span> <span data-ttu-id="e6758-133">Puede usar el espacio de trabajo para activarlas y ver su documentación.</span><span class="sxs-lookup"><span data-stu-id="e6758-133">You can use the workspace to turn them on and view the documentation for them.</span></span>

<span data-ttu-id="e6758-134">Para obtener más información acerca de los cambios que se incluyen con la administración de características, consulte [Visión general de la administración de características](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span><span class="sxs-lookup"><span data-stu-id="e6758-134">To learn more about the changes coming with feature management, see [Feature management overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span></span>
