---
title: Características quitadas u obsoletas en Lifecycle Services (LCS)
description: En este tema se describen las características que se han eliminado, o que está previsto que se eliminen, de Microsoft Dynamics Lifecycle Services (LCS).
author: AngelMarshall
manager: AnnBe
ms.date: 02/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: tsmarsha
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 96ecd040ef8661765c0a3861d8e07fee3c241161
ms.sourcegitcommit: fb7d0efd97754f1ae0b5aa765d0eeb3f57b8078f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2020
ms.locfileid: "3027989"
---
# <a name="removed-or-deprecated-features-in-lifecycle-services-lcs"></a><span data-ttu-id="bebe9-103">Características quitadas u obsoletas en Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="bebe9-103">Removed or deprecated features in Lifecycle Services (LCS)</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="bebe9-104">En este tema se describen las características que se han eliminado, o que están en desuso, en Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="bebe9-104">This topic describes features that have been removed or deprecated for Microsoft Dynamics Lifecycle Services (LCS).</span></span>

- <span data-ttu-id="bebe9-105">Una característica *quitada* deja de estar disponible en el servicio.</span><span class="sxs-lookup"><span data-stu-id="bebe9-105">A *removed* feature is no longer available in the service.</span></span>
- <span data-ttu-id="bebe9-106">Una característica *en desuso* no está en desarrollo activo y se podría quitar en una actualización futura.</span><span class="sxs-lookup"><span data-stu-id="bebe9-106">A *deprecated* feature isn't in active development and might be removed in a future update.</span></span>

<span data-ttu-id="bebe9-107">Esta lista se proporciona para ayudarle a tener en cuenta estas eliminaciones y deprecaciones para su propia planificación.</span><span class="sxs-lookup"><span data-stu-id="bebe9-107">This list is provided so that you can consider these removals and deprecations as you do your own planning.</span></span>

## <a name="october-2019-announcements"></a><span data-ttu-id="bebe9-108">Anuncios de octubre de 2019</span><span class="sxs-lookup"><span data-stu-id="bebe9-108">October 2019 announcements</span></span>

### <a name="flowchart-diagrams-in-business-process-modeler"></a><span data-ttu-id="bebe9-109">Diagramas de flujo en el Modelador de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="bebe9-109">Flowchart diagrams in Business process modeler</span></span>

<table>
<tbody>
<tr>
<td><span data-ttu-id="bebe9-110"><strong>Motivo de la depreciación/eliminación</strong></span><span class="sxs-lookup"><span data-stu-id="bebe9-110"><strong>Reason for deprecation/removal</strong></span></span></td>
<td><span data-ttu-id="bebe9-111">Vamos a dejar de usar el componente de diagramas de flujo en el Modelador de procesos empresariales (BPM), ya que el diseño heredado hizo que se usara poco.</span><span class="sxs-lookup"><span data-stu-id="bebe9-111">We are deprecating the flowchart diagrams component in Business process modeler (BPM), because the legacy design caused low usage.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bebe9-112"><strong>¿Reemplazado por otra característica?</strong></span><span class="sxs-lookup"><span data-stu-id="bebe9-112"><strong>Replaced by another feature?</strong></span></span></td>
<td><span data-ttu-id="bebe9-113">No</span><span class="sxs-lookup"><span data-stu-id="bebe9-113">No</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bebe9-114"><strong>Áreas afectadas</strong></span><span class="sxs-lookup"><span data-stu-id="bebe9-114"><strong>Areas affected</strong></span></span></td>
<td><span data-ttu-id="bebe9-115">Modelador de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="bebe9-115">Business process modeler</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bebe9-116"><strong>Estado</strong></span><span class="sxs-lookup"><span data-stu-id="bebe9-116"><strong>Status</strong></span></span></td>
<td><span data-ttu-id="bebe9-117">En desuso: se prevé la eliminación del componente de diagramas de flujo en BPM en 2020.</span><span class="sxs-lookup"><span data-stu-id="bebe9-117">Deprecated: The flowchart diagrams component in BPM is expected to be removed in 2020.</span></span> <span data-ttu-id="bebe9-118">Se quitará la siguiente funcionalidad:</span><span class="sxs-lookup"><span data-stu-id="bebe9-118">The following functionality will be removed:</span></span>
<ul>
<li><span data-ttu-id="bebe9-119">Los diagramas de flujo existentes no se podrán ver ni editar.</span><span class="sxs-lookup"><span data-stu-id="bebe9-119">Existing flowcharts will be unavailable for viewing or editing.</span></span> <span data-ttu-id="bebe9-120">Las propiedades de forma asociadas a las actividades del diagrama de flujo tampoco estarán disponibles, ya que se quitará la pestaña <strong>Diagrama de flujo</strong> completa.</span><span class="sxs-lookup"><span data-stu-id="bebe9-120">The shape properties that are associated with flowchart activities will also be unavailable, because the whole <strong>Flowchart</strong> tab will be removed.</span></span> <span data-ttu-id="bebe9-121">Estos diagramas de flujo incluyen diagramas de flujo predeterminados que se generan automáticamente y diagramas de flujo personalizados que se modifican en función de esos diagramas de flujo predeterminados.</span><span class="sxs-lookup"><span data-stu-id="bebe9-121">These flowcharts include both the default flowcharts that are automatically generated and customized flowcharts that are modified based on those default flowcharts.</span></span></li>
<li><span data-ttu-id="bebe9-122">La característica de análisis de idoneidad/lagunas heredado no estará disponible.</span><span class="sxs-lookup"><span data-stu-id="bebe9-122">The legacy fit/gap analysis feature will be unavailable.</span></span> <span data-ttu-id="bebe9-123">Por lo tanto, no se creará automáticamente una lista de lagunas ni estará disponible para la exportación.</span><span class="sxs-lookup"><span data-stu-id="bebe9-123">Therefore, no gap list will be automatically created or available for export.</span></span>
<p><span data-ttu-id="bebe9-124"><strong>Nota:</strong> esta característica quedó en desuso anteriormente y fue reemplazada por las integraciones de Microsoft Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="bebe9-124"><strong>Note:</strong> This feature had previously been deprecated and replaced by Microsoft Azure DevOps integrations.</span></span></p>
</li>
<li><span data-ttu-id="bebe9-125">El historial de versiones del diagrama de flujo no estará disponible.</span><span class="sxs-lookup"><span data-stu-id="bebe9-125">The version history of the flowchart will be unavailable.</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>
