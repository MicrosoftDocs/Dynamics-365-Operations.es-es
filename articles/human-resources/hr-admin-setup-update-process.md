---
title: Actualizar proceso
description: Microsoft Dynamics 365 Human Resources es un verdadero software como servicio (SaaS) que proporciona actualizaciones continuas y sin contacto del servicio para la aplicación y cambios de plataforma.
author: andreabichsel
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-27
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4069e369b1a9f15372d1e29e3809198b90b12c7e
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791542"
---
# <a name="update-process"></a><span data-ttu-id="01bcb-103">Actualizar proceso</span><span class="sxs-lookup"><span data-stu-id="01bcb-103">Update process</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="01bcb-104">Microsoft Dynamics 365 Human Resources es un verdadero software como servicio (SaaS) que proporciona actualizaciones continuas y sin contacto del servicio.</span><span class="sxs-lookup"><span data-stu-id="01bcb-104">Microsoft Dynamics 365 Human Resources is a true software as a service (SaaS) that provides continuous, touchless service updates.</span></span> <span data-ttu-id="01bcb-105">Estas actualizaciones contienen cambios tanto en la aplicación como en la plataforma que a menudo proporcionan mejoras críticas para el servicio, incluidas actualizaciones regulatorias.</span><span class="sxs-lookup"><span data-stu-id="01bcb-105">These updates contain both application and platform changes that often provide critical improvements to the service, including regulatory updates.</span></span>

## <a name="update-policy"></a><span data-ttu-id="01bcb-106">Directiva de actualización</span><span class="sxs-lookup"><span data-stu-id="01bcb-106">Update policy</span></span>

<span data-ttu-id="01bcb-107">Las actualizaciones se lanzan en una cadencia regular en todos los entornos.</span><span class="sxs-lookup"><span data-stu-id="01bcb-107">Updates are released on a regular cadence to all environments.</span></span> <span data-ttu-id="01bcb-108">Human Resources es compatible según la [directiva de ciclo de vida de Microsoft](https://support.microsoft.com/hub/4095338/microsoft-lifecycle-policy), que proporciona directrices coherentes y predecibles para la disponibilidad de la asistencia técnica.</span><span class="sxs-lookup"><span data-stu-id="01bcb-108">Human Resources is supported according to the [Microsoft Lifecycle policy](https://support.microsoft.com/hub/4095338/microsoft-lifecycle-policy), which provides consistent and predictable guidelines for the availability of support.</span></span>

## <a name="release-cadence"></a><span data-ttu-id="01bcb-109">Cadencia de lanzamiento</span><span class="sxs-lookup"><span data-stu-id="01bcb-109">Release cadence</span></span> 

<span data-ttu-id="01bcb-110">Las actualizaciones de Human Resources se aplican a todos los entornos automáticamente.</span><span class="sxs-lookup"><span data-stu-id="01bcb-110">Human Resources updates are applied to all environments automatically.</span></span> <span data-ttu-id="01bcb-111">Human Resources proporciona dos tipos de lanzamientos:</span><span class="sxs-lookup"><span data-stu-id="01bcb-111">Human Resources provides two types of releases:</span></span>

- <span data-ttu-id="01bcb-112">**Actualizaciones de servicio**: las actualizaciones se producen cada dos semanas e incluyen correcciones de errores y nuevas características.</span><span class="sxs-lookup"><span data-stu-id="01bcb-112">**Service updates**: Updates occur every two weeks that include bug fixes and new features.</span></span> <span data-ttu-id="01bcb-113">Las actualizaciones de servicio también incluyen actualizaciones de plataforma aplicables cuando se lanzan.</span><span class="sxs-lookup"><span data-stu-id="01bcb-113">Service updates also include applicable Platform updates when they release.</span></span> <span data-ttu-id="01bcb-114">Para tener una idea de cuándo se lanzan las actualizaciones de la Plataforma, vea [Tabla 3: Lanzamientos de plataforma](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy#table-3-platform-releases).</span><span class="sxs-lookup"><span data-stu-id="01bcb-114">To get an idea of when Platform updates are released, see [Table 3: Platform releases](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy#table-3-platform-releases).</span></span> <span data-ttu-id="01bcb-115">Las actualizaciones quincenales tienen una implementación global por etapas en todas las regiones.</span><span class="sxs-lookup"><span data-stu-id="01bcb-115">Biweekly updates have a staged global rollout across regions.</span></span> <span data-ttu-id="01bcb-116">Para obtener más información sobre las actualizaciones quincenales, vea [Novedades o cambios en Dynamics 365 Human Resources](hr-admin-whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="01bcb-116">For more information about biweekly updates, see [What's new or changed in Dynamics 365 Human Resources](hr-admin-whats-new.md).</span></span>

    <span data-ttu-id="01bcb-117">Todos los centros de datos compatibles se actualizan cada dos semanas, a menos que se indique lo contrario.</span><span class="sxs-lookup"><span data-stu-id="01bcb-117">All supported data centers update every two weeks, unless otherwise noted.</span></span> <span data-ttu-id="01bcb-118">Las regiones de EE. UU., Australia, Europa, Reino Unido, Asia y Canadá se incluyen en las actualizaciones quincenales.</span><span class="sxs-lookup"><span data-stu-id="01bcb-118">US, Australia, Europe, UK, Asia, and Canada regions are included in biweekly updates.</span></span> 

- <span data-ttu-id="01bcb-119">**Actualizaciones de soluciones de Dataverse**: estas actualizaciones se producen aproximadamente cada seis semanas, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="01bcb-119">**Dataverse solution updates**: These updates occur approximately every six weeks, as needed.</span></span> <span data-ttu-id="01bcb-120">Incluyen nuevas entidades y cambios a entidades existentes en Dataverse.</span><span class="sxs-lookup"><span data-stu-id="01bcb-120">They include new entities and changes to existing entities in Dataverse.</span></span> <span data-ttu-id="01bcb-121">Estas actualizaciones se lanzan a las mismas regiones que las actualizaciones quincenales, y tardan aproximadamente seis semanas en replicarse en todos los centros de datos.</span><span class="sxs-lookup"><span data-stu-id="01bcb-121">These updates release to the same regions as the biweekly updates, and they take about six weeks to replicate through all data centers.</span></span> <span data-ttu-id="01bcb-122">Las actualizaciones de la solución pueden o no alinearse con las actualizaciones quincenales del servicio.</span><span class="sxs-lookup"><span data-stu-id="01bcb-122">Solution updates may or may not align with biweekly service updates.</span></span>

> [!NOTE]
> <span data-ttu-id="01bcb-123">Las actualizaciones de la solución están disponibles en todos los centros de datos una vez que se lanzan.</span><span class="sxs-lookup"><span data-stu-id="01bcb-123">Solution updates are available on all data centers once they're released.</span></span> <span data-ttu-id="01bcb-124">Si no desea esperar a que las actualizaciones se repliquen automáticamente, puede aplicarlas manualmente en cualquier entorno en cualquier centro de datos.</span><span class="sxs-lookup"><span data-stu-id="01bcb-124">If you don't want to wait for the updates to replicate automatically, you can manually apply these updates on any environment in any data center.</span></span>

<span data-ttu-id="01bcb-125">Cuando es necesario, Human Resources también proporciona los siguientes tipos de soluciones:</span><span class="sxs-lookup"><span data-stu-id="01bcb-125">When needed, Human Resources also provides the following types of fixes:</span></span>

- <span data-ttu-id="01bcb-126">**Revisión (hotfix)**: correcciones de errores que pueden ocurrir con o sin una versión de actualización de servicio quincenal</span><span class="sxs-lookup"><span data-stu-id="01bcb-126">**Revision (hotfix)**: Bug fixes that can occur either with or apart from a biweekly service update release</span></span>

- <span data-ttu-id="01bcb-127">**Corrección de emergencia**: las revisiones proactivas y reactivas que son de naturaleza independiente, pueden incluir solo cambios de configuración o código para resolver problemas del sitio en vivo, y pueden ocurrir aparte de una versión de actualización de servicio quincenal</span><span class="sxs-lookup"><span data-stu-id="01bcb-127">**Emergency fix**: Proactive and reactive hotfixes that are standalone in nature, can include configuration-only or code changes to resolve live site issues, and can occur apart from a biweekly service update release</span></span>

<span data-ttu-id="01bcb-128">Las versiones se revisan, prueban y validan en un entorno interno.</span><span class="sxs-lookup"><span data-stu-id="01bcb-128">Releases are reviewed, tested, and validated on an internal environment.</span></span> <span data-ttu-id="01bcb-129">Después de que las compilaciones se cierran, se implementan en producción.</span><span class="sxs-lookup"><span data-stu-id="01bcb-129">After builds are signed off, they're then deployed to production.</span></span>

## <a name="release-cadence-exceptions-in-2021"></a><span data-ttu-id="01bcb-130">Liberar excepciones de cadencia en 2021</span><span class="sxs-lookup"><span data-stu-id="01bcb-130">Release cadence exceptions in 2021</span></span>

<span data-ttu-id="01bcb-131">Para tener en cuenta los días festivos, el calendario de lanzamientos para noviembre y diciembre de 2021 es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="01bcb-131">To account for holidays, the release schedule for November and December 2021 is as follows:</span></span>

- <span data-ttu-id="01bcb-132">Lanzamiento de noviembre: 1 de noviembre - 14 de noviembre</span><span class="sxs-lookup"><span data-stu-id="01bcb-132">November release: November 1 - November 14</span></span>
- <span data-ttu-id="01bcb-133">Lanzamiento de diciembre: 29 de noviembre - 12 de diciembre</span><span class="sxs-lookup"><span data-stu-id="01bcb-133">December release: November 29 - December 12</span></span>
 
<span data-ttu-id="01bcb-134">La cadencia de lanzamiento de dos semanas se reanudará como de costumbre el 10 de enero de 2022.</span><span class="sxs-lookup"><span data-stu-id="01bcb-134">The two-week release cadence will resume as usual on January 10, 2022.</span></span>

## <a name="communications"></a><span data-ttu-id="01bcb-135">Comunicaciones</span><span class="sxs-lookup"><span data-stu-id="01bcb-135">Communications</span></span>

<span data-ttu-id="01bcb-136">Puede averiguar qué se está trabajando para Recursos Humanos y qué hemos publicado en las siguientes ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="01bcb-136">You can find out what's in the works for Human Resources and what we've released in the following locations:</span></span>

- [<span data-ttu-id="01bcb-137">Hoja de ruta de Dynamics 365 Human Resources</span><span class="sxs-lookup"><span data-stu-id="01bcb-137">Dynamics 365 Human Resources roadmap</span></span>](https://dynamics.microsoft.com/roadmap/human-resources/)

- [<span data-ttu-id="01bcb-138">Planes de la versión de Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="01bcb-138">Dynamics 365 Release Plans</span></span>](https://docs.microsoft.com/dynamics365/release-plans/)

- [<span data-ttu-id="01bcb-139">Novedades y cambios en Dynamics 365 Human Resources</span><span class="sxs-lookup"><span data-stu-id="01bcb-139">What's new or changed in Dynamics 365 Human Resources</span></span>](hr-admin-whats-new.md)

- <span data-ttu-id="01bcb-140">[Búsqueda de problemas en Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/issue-search-lcs) (solo para errores relacionados con la plataforma)</span><span class="sxs-lookup"><span data-stu-id="01bcb-140">[Issue search in Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/issue-search-lcs) (for Platform-related bugs only)</span></span>

- [<span data-ttu-id="01bcb-141">Blog de Human Resources</span><span class="sxs-lookup"><span data-stu-id="01bcb-141">Human Resources blog</span></span>](https://community.dynamics.com/365/talent/b/dynamics365fortalent)

- [<span data-ttu-id="01bcb-142">Comunidad de Human Resources en Yammer</span><span class="sxs-lookup"><span data-stu-id="01bcb-142">Human Resources Yammer community</span></span>](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=10542230)

## <a name="preview-features-in-a-sandbox-environment"></a><span data-ttu-id="01bcb-143">Vista previa de características en un entorno sandbox</span><span class="sxs-lookup"><span data-stu-id="01bcb-143">Preview features in a sandbox environment</span></span>

<span data-ttu-id="01bcb-144">Puede validar las funciones de vista previa en un entorno de espacio aislado antes de habilitarlas en su entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="01bcb-144">You can validate preview features in a sandbox environment before enabling them in your production environment.</span></span> <span data-ttu-id="01bcb-145">Para obtener más información acerca de la activación nuevas características, consulte [Visión general de la Administración de características](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span><span class="sxs-lookup"><span data-stu-id="01bcb-145">For more information about enabling features, see [Feature management overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span></span>

<span data-ttu-id="01bcb-146">Todas las características nuevas siguen en versión preliminar durante al menos 30 días como mínimo, y normalmente 30-60 días.</span><span class="sxs-lookup"><span data-stu-id="01bcb-146">All new features remain in preview for at least 30 days, and typically 30-60 days.</span></span> <span data-ttu-id="01bcb-147">Las características más importantes están disponibles en octubre y abril de cada año tras el periodo de prueba preliminar.</span><span class="sxs-lookup"><span data-stu-id="01bcb-147">Major features are generally available in October and April of each year following the preview period.</span></span> <span data-ttu-id="01bcb-148">En cuanto vea características nuevas en el espacio de trabajo Administración de características, puede activarlas.</span><span class="sxs-lookup"><span data-stu-id="01bcb-148">As soon as you see new capabilities in the Feature management workspace, you can turn them on.</span></span> <span data-ttu-id="01bcb-149">Algunas características pueden estar activadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="01bcb-149">Some features may be on by default.</span></span>

<span data-ttu-id="01bcb-150">A veces, una característica entera estará activada de forma predeterminada y no se puede desactivar (por ejemplo, el espacio de trabajo Administración de características).</span><span class="sxs-lookup"><span data-stu-id="01bcb-150">At times, an integral feature will be on by default and can't be turned off (for example, the Feature management workspace).</span></span>

<span data-ttu-id="01bcb-151">Cuando una característica esté disponible, se puede activar y desactivar en los entornos de producción.</span><span class="sxs-lookup"><span data-stu-id="01bcb-151">Once a feature is generally available, it may be turned on or off in production environments.</span></span> <span data-ttu-id="01bcb-152">El espacio de trabajo Administración de características indica cuando una característica de versión preliminar pasará a ser obligatoria.</span><span class="sxs-lookup"><span data-stu-id="01bcb-152">The Feature management workspace indicates when a preview feature will become mandatory.</span></span> <span data-ttu-id="01bcb-153">Esta fecha es un el 1 de octubre o el 1 de abril para que se corresponda con los planes semestrales de publicación.</span><span class="sxs-lookup"><span data-stu-id="01bcb-153">This date is usually on October 1 or April 1 to align with the semiannual release plans.</span></span> <span data-ttu-id="01bcb-154">No pueden desactivar características obligatorias.</span><span class="sxs-lookup"><span data-stu-id="01bcb-154">You can't turn off mandatory features.</span></span> <span data-ttu-id="01bcb-155">Hasta que llegue a ser obligatoria, se puede activar y desactivar una característica en todos los entornos.</span><span class="sxs-lookup"><span data-stu-id="01bcb-155">Until it becomes mandatory, you can turn a feature on and off in all environments.</span></span>

<span data-ttu-id="01bcb-156">Recomendamos encarecidamente obtener una vista previa de las características en un entorno de prueba o espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="01bcb-156">We highly recommend previewing features in a sandbox or trial environment.</span></span> <span data-ttu-id="01bcb-157">Es mejor crear una copia de su entorno de producción o base de datos actual en un entorno de espacio aislado para que pueda obtener la experiencia completa de las nuevas funciones con sus datos.</span><span class="sxs-lookup"><span data-stu-id="01bcb-157">It's best to create a copy of your current production environment or database into a sandbox environment so you can get the complete experience of the new features with your data.</span></span>

<span data-ttu-id="01bcb-158">Para obtener más información sobre el aprovisionamiento de un entorno de espacio aislado, vea [Aprovisionar un proyecto de Human Resources](hr-admin-setup-provision.md).</span><span class="sxs-lookup"><span data-stu-id="01bcb-158">For more information about provisioning a sandbox environment, see [Provision a Human Resources project](hr-admin-setup-provision.md).</span></span> <span data-ttu-id="01bcb-159">Para eliminar un entorno de prueba, vea [Eliminar una instancia](hr-admin-setup-remove-instance.md#remove-a-test-drive-environment).</span><span class="sxs-lookup"><span data-stu-id="01bcb-159">To remove a test environment, see [Remove an instance](hr-admin-setup-remove-instance.md#remove-a-test-drive-environment).</span></span> 

## <a name="report-bugs"></a><span data-ttu-id="01bcb-160">Informar de errores</span><span class="sxs-lookup"><span data-stu-id="01bcb-160">Report bugs</span></span>

<span data-ttu-id="01bcb-161">Mientras prueba las funciones de vista previa o prueba nuevas capacidades, puede encontrar elementos que no funcionan como se esperaba.</span><span class="sxs-lookup"><span data-stu-id="01bcb-161">While testing preview features or trying new capabilities, you might find items that don't work as expected.</span></span> <span data-ttu-id="01bcb-162">Informe sobre cualquier error a través del [soporte técnico de Microsoft Dynamics 365](https://dynamics.microsoft.com/support/).</span><span class="sxs-lookup"><span data-stu-id="01bcb-162">Please report any bugs through [Microsoft Dynamics 365 support](https://dynamics.microsoft.com/support/).</span></span>

## <a name="see-also"></a><span data-ttu-id="01bcb-163">Consulte también</span><span class="sxs-lookup"><span data-stu-id="01bcb-163">See also</span></span>

[<span data-ttu-id="01bcb-164">Planes de la versión de Dynamics 365 y Power Platform</span><span class="sxs-lookup"><span data-stu-id="01bcb-164">Dynamics 365 and Power Platform Release Plans</span></span>](https://docs.microsoft.com/dynamics365/release-plans)</br>
[<span data-ttu-id="01bcb-165">Novedades y cambios en Dynamics 365 Human Resources</span><span class="sxs-lookup"><span data-stu-id="01bcb-165">What's new or changed in Dynamics 365 Human Resource</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="01bcb-166">Directiva del ciclo de vida del software</span><span class="sxs-lookup"><span data-stu-id="01bcb-166">Software lifecycle policy</span></span>](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
