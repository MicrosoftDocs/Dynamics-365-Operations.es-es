---
title: Funciones quitadas u obsoletas en Lifecycle Services (LCS)
description: En este tema se describen las funciones que se han eliminado, o que está previsto que se eliminen, de Microsoft Dynamics Lifecycle Services (LCS).
author: AngelMarshall
manager: AnnBe
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: tsmarsha
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: abf7a1a0a75ac3098efeeab3df65481999b69acc
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687887"
---
# <a name="removed-or-deprecated-features-in-lifecycle-services-lcs"></a><span data-ttu-id="3fde3-103">Funciones quitadas u obsoletas en Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="3fde3-103">Removed or deprecated features in Lifecycle Services (LCS)</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="3fde3-104">En este tema se describen las funciones que se han eliminado, o que están en desuso, en Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="3fde3-104">This topic describes features that have been removed or deprecated for Microsoft Dynamics Lifecycle Services (LCS).</span></span>

- <span data-ttu-id="3fde3-105">Una función *quitada* deja de estar disponible en el servicio.</span><span class="sxs-lookup"><span data-stu-id="3fde3-105">A *removed* feature is no longer available in the service.</span></span>
- <span data-ttu-id="3fde3-106">Una función *en desuso* no está en desarrollo activo y se podría quitar en una actualización futura.</span><span class="sxs-lookup"><span data-stu-id="3fde3-106">A *deprecated* feature isn't in active development and might be removed in a future update.</span></span>

<span data-ttu-id="3fde3-107">Esta lista se proporciona para ayudarle a tener en cuenta estas eliminaciones y deprecaciones para su propia planificación.</span><span class="sxs-lookup"><span data-stu-id="3fde3-107">This list is provided so that you can consider these removals and deprecations as you do your own planning.</span></span>

## <a name="october-2019-announcements"></a><span data-ttu-id="3fde3-108">Anuncios de octubre de 2019</span><span class="sxs-lookup"><span data-stu-id="3fde3-108">October 2019 announcements</span></span>

### <a name="flowchart-diagrams-in-business-process-modeler"></a><span data-ttu-id="3fde3-109">Diagramas de flujo en el Modelador de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="3fde3-109">Flowchart diagrams in Business process modeler</span></span>

<table>
<tbody>
<tr>
<td><span data-ttu-id="3fde3-110"><strong>Motivo de la depreciación/eliminación</strong></span><span class="sxs-lookup"><span data-stu-id="3fde3-110"><strong>Reason for deprecation/removal</strong></span></span></td>
<td><span data-ttu-id="3fde3-111">Vamos a dejar de usar el componente de diagramas de flujo en el Modelador de procesos empresariales (BPM), ya que el diseño heredado hizo que se usara poco.</span><span class="sxs-lookup"><span data-stu-id="3fde3-111">We are deprecating the flowchart diagrams component in Business process modeler (BPM), because the legacy design caused low usage.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3fde3-112"><strong>¿Reemplazado por otra función?</strong></span><span class="sxs-lookup"><span data-stu-id="3fde3-112"><strong>Replaced by another feature?</strong></span></span></td>
<td><span data-ttu-id="3fde3-113">No</span><span class="sxs-lookup"><span data-stu-id="3fde3-113">No</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3fde3-114"><strong>Áreas afectadas</strong></span><span class="sxs-lookup"><span data-stu-id="3fde3-114"><strong>Areas affected</strong></span></span></td>
<td><span data-ttu-id="3fde3-115">Modelador de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="3fde3-115">Business process modeler</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3fde3-116"><strong>Estado</strong></span><span class="sxs-lookup"><span data-stu-id="3fde3-116"><strong>Status</strong></span></span></td>
<td><span data-ttu-id="3fde3-117">En desuso: se prevé la eliminación del componente de diagramas de flujo en BPM en 2020.</span><span class="sxs-lookup"><span data-stu-id="3fde3-117">Deprecated: The flowchart diagrams component in BPM is expected to be removed in 2020.</span></span> <span data-ttu-id="3fde3-118">La siguiente funcionalidad no estará disponible:</span><span class="sxs-lookup"><span data-stu-id="3fde3-118">The following functionality will be unavailable:</span></span>
<ul>
<li><span data-ttu-id="3fde3-119">Todos los diagramas de flujo serán de solo lectura y no estarán disponibles para edición.</span><span class="sxs-lookup"><span data-stu-id="3fde3-119">All flowcharts will be read-only and unavailable for editing.</span></span> <span data-ttu-id="3fde3-120">Las propiedades de forma asociadas con las actividades del diagrama de flujo tampoco estarán disponibles.</span><span class="sxs-lookup"><span data-stu-id="3fde3-120">The shape properties that are associated with flowchart activities will also be unavailable.</span></span> <span data-ttu-id="3fde3-121">Estos diagramas de flujo incluyen diagramas de flujo predeterminados que se generan automáticamente y diagramas de flujo personalizados que se modifican en función de esos diagramas de flujo predeterminados.</span><span class="sxs-lookup"><span data-stu-id="3fde3-121">These flowcharts include both the default flowcharts that are automatically generated and customized flowcharts that are modified based on those default flowcharts.</span></span></li>
<li><span data-ttu-id="3fde3-122">Los pasos del proceso serán de solo lectura y no estarán disponibles para edición.</span><span class="sxs-lookup"><span data-stu-id="3fde3-122">The process steps will be read-only and unavailable for editing.</span></span></li>     
<li><span data-ttu-id="3fde3-123">La función de análisis de idoneidad/lagunas heredado no estará disponible.</span><span class="sxs-lookup"><span data-stu-id="3fde3-123">The legacy fit/gap analysis feature will be unavailable.</span></span> <span data-ttu-id="3fde3-124">Por lo tanto, no se creará automáticamente una lista de lagunas ni estará disponible para la exportación.</span><span class="sxs-lookup"><span data-stu-id="3fde3-124">Therefore, no gap list will be automatically created or available for export.</span></span>
<p><span data-ttu-id="3fde3-125"><strong>Nota:</strong> esta función quedó en desuso anteriormente y fue reemplazada por las integraciones de Microsoft Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="3fde3-125"><strong>Note:</strong> This feature had previously been deprecated and replaced by Microsoft Azure DevOps integrations.</span></span></p>
</li>
<li><span data-ttu-id="3fde3-126">El historial de versiones del diagrama de flujo no estará disponible.</span><span class="sxs-lookup"><span data-stu-id="3fde3-126">The version history of the flowchart will be unavailable.</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>
