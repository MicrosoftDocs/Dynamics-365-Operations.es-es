---
title: Novedades o cambios en Dynamics 365 Talent (30 de julio de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 07/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 3676a0a1fa77285d0203e8e49725cb1c1b742d39
ms.sourcegitcommit: 029c1882bef558b6a45843548e94ab8369ed9870
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "2651720"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-july-30-2019"></a><span data-ttu-id="96f65-103">Novedades o cambios en Dynamics 365 Talent (30 de julio de 2019)</span><span class="sxs-lookup"><span data-stu-id="96f65-103">What's new or changed in Dynamics 365 Talent (July 30, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="96f65-104">Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="96f65-104">This topic describes features that are either new or changed in Dynamics 365 Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="96f65-105">Cambios en Attract</span><span class="sxs-lookup"><span data-stu-id="96f65-105">Changes in Attract</span></span>
<span data-ttu-id="96f65-106">Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="96f65-106">This release includes minor bug fixes for Dynamics 365 Talent: Attract.</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="96f65-107">Cambios en Onboard</span><span class="sxs-lookup"><span data-stu-id="96f65-107">Changes in Onboard</span></span>
<span data-ttu-id="96f65-108">Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="96f65-108">This release includes minor bug fixes for Dynamics 365 Talent: Onboard.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="96f65-109">Cambios en Core HR</span><span class="sxs-lookup"><span data-stu-id="96f65-109">Changes in Core HR</span></span>
<span data-ttu-id="96f65-110">Los cambios que se describen en esta sección se aplican a la compilación número 8.1.2409.</span><span class="sxs-lookup"><span data-stu-id="96f65-110">Changes described in this section apply to build number 8.1.2409.</span></span>


### <a name="region-support-for-canada-and-southeast-asia"></a><span data-ttu-id="96f65-111">Compatibilidad de la región para Canadá y el Sudeste asiático</span><span class="sxs-lookup"><span data-stu-id="96f65-111">Region support for Canada and Southeast Asia</span></span>

<span data-ttu-id="96f65-112">Estamos encantados de anunciar que las regiones de Canadá y del Sudeste asiático estarán disponibles para Talent el 1 de agosto de 2019.</span><span class="sxs-lookup"><span data-stu-id="96f65-112">We are pleased to announce that Canada and Southeast Asia regions will be available for Talent on August 1, 2019.</span></span> <span data-ttu-id="96f65-113">Con este cambio, puede crear entornos en las regiones canadienses y asiática, y todos los datos de Talent se mantendrán solo dentro de estas ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="96f65-113">With this change, you can create environments in the Canadian and Asian regions, and all Talent data will be maintained solely within those locations.</span></span> <span data-ttu-id="96f65-114">Puede crear un entorno en estas nuevas regiones seleccionando la ubicación en el diálogo Nuevo entorno y usando dicho entorno para aprovisionar Talent en LCS como se describe en [Aprovisionar Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="96f65-114">You can create an environment in these new regions by selecting the location in the New Environment dialog and use that environment to provision Talent in LCS as described in [Provision Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).</span></span>

<span data-ttu-id="96f65-115">La migración de datos de proyectos existentes de otras regiones a las regiones canadienses y asiática no se admite.</span><span class="sxs-lookup"><span data-stu-id="96f65-115">Data migration of existing projects from other regions to the Canadian and Asian regions is not supported.</span></span> <span data-ttu-id="96f65-116">Solo los nuevos proyectos pueden aprovisionarse en estas nuevas regiones compatibles.</span><span class="sxs-lookup"><span data-stu-id="96f65-116">Only new projects can be provisioned to these new supported regions.</span></span>

### <a name="new-active-positions-list-page"></a><span data-ttu-id="96f65-117">Nueva página de lista de puestos activa</span><span class="sxs-lookup"><span data-stu-id="96f65-117">New Active positions list page</span></span>

<span data-ttu-id="96f65-118">Las opciones para las listas basadas en puestos ahora incluyen: **Todos los puestos**, **Puestos activos**, **Vacantes**, y **Puestos inactivos**.</span><span class="sxs-lookup"><span data-stu-id="96f65-118">The options for position-based lists now include: **All positions**, **Active positions**, **Open positions**, and **Inactive positions**.</span></span> <span data-ttu-id="96f65-119">La nueva página de lista **Puestos activos** sólo muestra aquellos puestos, vacantes o cubiertos, que están activos en la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="96f65-119">The new **Active positions** list page displays only those positions, open or filled, that are active as of the current date.</span></span> 

### <a name="allow-course-participants-to-be-added-to-open-courses"></a><span data-ttu-id="96f65-120">Permitir que los participantes del curso se agreguen a cursos abiertos</span><span class="sxs-lookup"><span data-stu-id="96f65-120">Allow course participants to be added to open courses</span></span>

<span data-ttu-id="96f65-121">Los cambios de esta semana corrigen un problema que hacía que sólo los informes directos se pudiesen registrar para los cursos abiertos.</span><span class="sxs-lookup"><span data-stu-id="96f65-121">This week's changes correct an issue where only direct reports can be registered for open courses.</span></span>

### <a name="fte-analysis-displaying-incorrect-fte-number"></a><span data-ttu-id="96f65-122">Análisis de FTE muestra un número de FTE incorrecto</span><span class="sxs-lookup"><span data-stu-id="96f65-122">FTE Analysis displaying incorrect FTE number</span></span>

<span data-ttu-id="96f65-123">**Análisis de FTE** se ha corregido en la pestaña **Análisis** de **Administración de personal**.</span><span class="sxs-lookup"><span data-stu-id="96f65-123">**FTE analysis** has been corrected on the **Analytics** tab for **Personnel management**.</span></span>

### <a name="final-comments-label-translation"></a><span data-ttu-id="96f65-124">Traducción de la etiqueta de comentarios finales</span><span class="sxs-lookup"><span data-stu-id="96f65-124">Final comments label translation</span></span>

<span data-ttu-id="96f65-125">La etiqueta **Comentarios finales** ahora está traducida en la pantalla de revisión.</span><span class="sxs-lookup"><span data-stu-id="96f65-125">The **Final comments** label is now translated in the review form.</span></span>

## <a name="in-preview"></a><span data-ttu-id="96f65-126">En vista previa</span><span class="sxs-lookup"><span data-stu-id="96f65-126">In preview</span></span>

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a><span data-ttu-id="96f65-127">Las características de la vista previa solo están habilitado en instancias de espacio aislado</span><span class="sxs-lookup"><span data-stu-id="96f65-127">Preview features are enabled only in sandbox instances</span></span>

<span data-ttu-id="96f65-128">Al aprovisionar una nueva instancia de Talent, puede especificar si el tipo de instancia es **Producción** o **Espacio aislado**.</span><span class="sxs-lookup"><span data-stu-id="96f65-128">When you provision a new instance of Talent, you can specify whether the instance type is **Production** or **Sandbox**.</span></span> <span data-ttu-id="96f65-129">Las instancias del tipo **Espacio aislado** permiten la prueba temprana de nuevas características.</span><span class="sxs-lookup"><span data-stu-id="96f65-129">Instances of the **Sandbox** type allow for early testing of new features.</span></span> <span data-ttu-id="96f65-130">Todas las instancias existentes de Talent se actualizarán el tipo de instancia de **Producción**.</span><span class="sxs-lookup"><span data-stu-id="96f65-130">All existing Talent instances will be updated to the **Production** instance type.</span></span> <span data-ttu-id="96f65-131">Si desea que una de las instancias existentes se actualicen al tipo de instancia de **Espacio aislado**, contacte con el [Soporte](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) para iniciar la solicitud de cambio.</span><span class="sxs-lookup"><span data-stu-id="96f65-131">If you want one of your existing instances to be updated to the **Sandbox** instance type, contact [Support](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) to initiate the change request.</span></span>

<span data-ttu-id="96f65-132">Para obtener más información sobre cómo se publican los cambios, consulte [Aprovisionar Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="96f65-132">For more information about how changes are published, see [Provision Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span></span>

### <a name="view-extended-information-for-performance-in-manager-self-service"></a><span data-ttu-id="96f65-133">Ver información ampliada para el rendimiento en autoservicio para directores</span><span class="sxs-lookup"><span data-stu-id="96f65-133">View extended information for performance in manager self-service</span></span>

<span data-ttu-id="96f65-134">Una nueva opción permitirá a los directores ver el rendimiento tanto de los informes directos como de sus informes ampliados.</span><span class="sxs-lookup"><span data-stu-id="96f65-134">A new option will let managers view the performance of both their direct reports and their extended reports.</span></span> <span data-ttu-id="96f65-135">Actualmente, los administradores de línea pueden asignar y actualizar objetivos de rendimiento y emitir nuevos revisiones.</span><span class="sxs-lookup"><span data-stu-id="96f65-135">Currently, line managers can assign and update performance goals and issue new reviews.</span></span> <span data-ttu-id="96f65-136">Además, los administradores directos y sus empleados pueden mantener y actualizar diarios de rendimiento a fin de garantizar que el proceso de evaluación del rendimiento se desarrolla correctamente.</span><span class="sxs-lookup"><span data-stu-id="96f65-136">In addition, direct managers and their employees can maintain and update performance journals to help ensure that the performance review process goes smoothly.</span></span> <span data-ttu-id="96f65-137">Cuando se implementa este cambio, los administradores podrán ver y mantener la información relacionada con el rendimiento en los informes ampliados además de sus informes directos.</span><span class="sxs-lookup"><span data-stu-id="96f65-137">When this change is implemented, managers will be able to view and maintain performance-related information for their extended reports in addition to their direct reports.</span></span>
