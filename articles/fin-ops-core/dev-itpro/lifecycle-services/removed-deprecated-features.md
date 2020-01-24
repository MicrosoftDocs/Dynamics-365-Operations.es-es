---
title: Características quitadas u obsoletas en Lifecycle Services (LCS)
description: En este tema se describen las características que se han eliminado, o que está previsto que se eliminen, de Microsoft Dynamics Lifecycle Services (LCS).
author: sericks007
manager: AnnBe
ms.date: 12/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: c792d06e9b0aa42919de924bdcc9118358779b72
ms.sourcegitcommit: 75bbcff474cfb8d2f282be2b9d2d7984d1505fa3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "2885464"
---
# <a name="removed-or-deprecated-features-in-lifecycle-services-lcs"></a><span data-ttu-id="b41e2-103">Características quitadas u obsoletas en Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="b41e2-103">Removed or deprecated features in Lifecycle Services (LCS)</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="b41e2-104">En este tema se describen las características que se han eliminado, o que están en desuso, en Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="b41e2-104">This topic describes features that have been removed or deprecated for Microsoft Dynamics Lifecycle Services (LCS).</span></span>

- <span data-ttu-id="b41e2-105">Una característica *quitada* deja de estar disponible en el servicio.</span><span class="sxs-lookup"><span data-stu-id="b41e2-105">A *removed* feature is no longer available in the service.</span></span>
- <span data-ttu-id="b41e2-106">Una característica *en desuso* no está en desarrollo activo y se podría quitar en una actualización futura.</span><span class="sxs-lookup"><span data-stu-id="b41e2-106">A *deprecated* feature isn't in active development and might be removed in a future update.</span></span>

<span data-ttu-id="b41e2-107">Esta lista se proporciona para ayudarle a tener en cuenta estas eliminaciones y deprecaciones para su propia planificación.</span><span class="sxs-lookup"><span data-stu-id="b41e2-107">This list is provided so that you can consider these removals and deprecations as you do your own planning.</span></span>

## <a name="october-2019-announcements"></a><span data-ttu-id="b41e2-108">Anuncios de octubre de 2019</span><span class="sxs-lookup"><span data-stu-id="b41e2-108">October 2019 announcements</span></span>

### <a name="flowchart-diagrams-in-business-process-modeler"></a><span data-ttu-id="b41e2-109">Diagramas de flujo en el Modelador de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="b41e2-109">Flowchart diagrams in Business process modeler</span></span>

<table>
<tbody>
<tr>
<td><span data-ttu-id="b41e2-110"><strong>Motivo de la depreciación/eliminación</strong></span><span class="sxs-lookup"><span data-stu-id="b41e2-110"><strong>Reason for deprecation/removal</strong></span></span></td>
<td><span data-ttu-id="b41e2-111">Vamos a dejar de usar el componente de diagramas de flujo en el Modelador de procesos empresariales (BPM), ya que el diseño heredado hizo que se usara poco.</span><span class="sxs-lookup"><span data-stu-id="b41e2-111">We are deprecating the flowchart diagrams component in Business process modeler (BPM), because the legacy design caused low usage.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b41e2-112"><strong>¿Reemplazado por otra característica?</strong></span><span class="sxs-lookup"><span data-stu-id="b41e2-112"><strong>Replaced by another feature?</strong></span></span></td>
<td><span data-ttu-id="b41e2-113">No</span><span class="sxs-lookup"><span data-stu-id="b41e2-113">No</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b41e2-114"><strong>Áreas afectadas</strong></span><span class="sxs-lookup"><span data-stu-id="b41e2-114"><strong>Areas affected</strong></span></span></td>
<td><span data-ttu-id="b41e2-115">Modelador de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="b41e2-115">Business process modeler</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b41e2-116"><strong>Estado</strong></span><span class="sxs-lookup"><span data-stu-id="b41e2-116"><strong>Status</strong></span></span></td>
<td><span data-ttu-id="b41e2-117">En desuso: se prevé la eliminación del componente de diagramas de flujo en BPM a principios de febrero de 2020.</span><span class="sxs-lookup"><span data-stu-id="b41e2-117">Deprecated: The flowchart diagrams component in BPM is expected to be removed by early February 2020.</span></span> <span data-ttu-id="b41e2-118">Se quitará la siguiente funcionalidad:</span><span class="sxs-lookup"><span data-stu-id="b41e2-118">The following functionality will be removed:</span></span>
<ul>
<li><span data-ttu-id="b41e2-119">Los diagramas de flujo existentes no se podrán ver ni editar.</span><span class="sxs-lookup"><span data-stu-id="b41e2-119">Existing flowcharts will be unavailable for viewing or editing.</span></span> <span data-ttu-id="b41e2-120">Las propiedades de forma asociadas a las actividades del diagrama de flujo tampoco estarán disponibles, ya que se quitará la pestaña <strong>Diagrama de flujo</strong> completa.</span><span class="sxs-lookup"><span data-stu-id="b41e2-120">The shape properties that are associated with flowchart activities will also be unavailable, because the whole <strong>Flowchart</strong> tab will be removed.</span></span> <span data-ttu-id="b41e2-121">Estos diagramas de flujo incluyen diagramas de flujo predeterminados que se generan automáticamente y diagramas de flujo personalizados que se modifican en función de esos diagramas de flujo predeterminados.</span><span class="sxs-lookup"><span data-stu-id="b41e2-121">These flowcharts include both the default flowcharts that are automatically generated and customized flowcharts that are modified based on those default flowcharts.</span></span></li>
<li><span data-ttu-id="b41e2-122">La característica de análisis de idoneidad/lagunas heredado no estará disponible.</span><span class="sxs-lookup"><span data-stu-id="b41e2-122">The legacy fit/gap analysis feature will be unavailable.</span></span> <span data-ttu-id="b41e2-123">Por lo tanto, no se creará automáticamente una lista de lagunas ni estará disponible para la exportación.</span><span class="sxs-lookup"><span data-stu-id="b41e2-123">Therefore, no gap list will be automatically created or available for export.</span></span>
<p><span data-ttu-id="b41e2-124"><strong>Nota:</strong> esta característica quedó en desuso anteriormente y fue reemplazada por las integraciones de Microsoft Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="b41e2-124"><strong>Note:</strong> This feature had previously been deprecated and replaced by Microsoft Azure DevOps integrations.</span></span></p>
</li>
<li><span data-ttu-id="b41e2-125">El historial de versiones del diagrama de flujo no estará disponible.</span><span class="sxs-lookup"><span data-stu-id="b41e2-125">The version history of the flowchart will be unavailable.</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>
