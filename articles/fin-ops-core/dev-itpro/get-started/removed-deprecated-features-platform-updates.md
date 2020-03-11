---
title: Características de Platform quitadas u obsoletas
description: En este tema se describen las características que se han eliminado, o que está previsto que se eliminen en las Platform updates de las aplicaciones de Finance and Operations.
author: sericks007
manager: AnnBe
ms.date: 02/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 66e1420c7053c0df9f42b15c55aba1a8c869f02a
ms.sourcegitcommit: 2cc3b89efdd90f8d80883b7a271d7885282ba3e8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "3087892"
---
# <a name="removed-or-deprecated-platform-features"></a><span data-ttu-id="3b635-103">Características de Platform quitadas u obsoletas</span><span class="sxs-lookup"><span data-stu-id="3b635-103">Removed or deprecated platform features</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3b635-104">En este tema se describen las características que se han eliminado, o que está previsto que se eliminen en las Platform updates de las aplicaciones de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3b635-104">This topic describes features that have been removed, or that are planned for removal in platform updates of Finance and Operations apps.</span></span>

- <span data-ttu-id="3b635-105">Una función *quitada* dejará de estar disponible en el producto.</span><span class="sxs-lookup"><span data-stu-id="3b635-105">A *removed* feature is no longer available in the product.</span></span>
- <span data-ttu-id="3b635-106">Una función *en desuso* no está en el desarrollo activo y se podría quitar en una actualización futura.</span><span class="sxs-lookup"><span data-stu-id="3b635-106">A *deprecated* feature is not in active development and may be removed in a future update.</span></span>

<span data-ttu-id="3b635-107">Esta lista está pensada para ayudarle a tener en cuenta estas eliminaciones y deprecaciones para su propia planificación.</span><span class="sxs-lookup"><span data-stu-id="3b635-107">This list is intended to help you consider these removals and deprecations for your own planning.</span></span> 

> [!NOTE]
> <span data-ttu-id="3b635-108">La información detallada sobre los objetos de aplicaciones Finance and Operations se puede encontrar en los [Informes de referencia técnica](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span><span class="sxs-lookup"><span data-stu-id="3b635-108">Detailed information about objects in Finance and Operations apps can be found in the [Technical reference reports](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span></span> <span data-ttu-id="3b635-109">Se pueden comparar las diferentes versiones de estos informes para conocer los objetos que se han modificado o quitado en cada versión de aplicaciones Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3b635-109">You can compare the different versions of these reports to learn about objects that have changed or been removed in each version of Finance and Operations apps.</span></span>

## <a name="platform-update-32"></a><span data-ttu-id="3b635-110">Actualización 32 de la plataforma</span><span class="sxs-lookup"><span data-stu-id="3b635-110">Platform update 32</span></span>

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a><span data-ttu-id="3b635-111">El cuadro de diálogo de cambio de solicitud de flujo de trabajo ya no incluye la lista desplegable de selección de usuario</span><span class="sxs-lookup"><span data-stu-id="3b635-111">Workflow request change dialog box no longer includes user selection drop-down list</span></span>
|   |  |
|------------|--------------------|
| <span data-ttu-id="3b635-112">**Motivo de la depreciación/eliminación**</span><span class="sxs-lookup"><span data-stu-id="3b635-112">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="3b635-113">Este era un problema de seguridad porque la solicitud de cambio se podía enviar a un usuario no deseado.</span><span class="sxs-lookup"><span data-stu-id="3b635-113">This was a security issue because the request for change could be sent to an unintended user.</span></span> <span data-ttu-id="3b635-114">Esto también fue un problema de usabilidad porque obligó al usuario a determinar quién era el creador del flujo de trabajo y seleccionarlos manualmente.</span><span class="sxs-lookup"><span data-stu-id="3b635-114">This was also a usability issue because it forced the user to determine who the workflow originator was and manually select them.</span></span>  |
| <span data-ttu-id="3b635-115">**¿Reemplazado por otra característica?**</span><span class="sxs-lookup"><span data-stu-id="3b635-115">**Replaced by another feature?**</span></span>   | <span data-ttu-id="3b635-116">No</span><span class="sxs-lookup"><span data-stu-id="3b635-116">No</span></span> |
| <span data-ttu-id="3b635-117">**Áreas de producto afectadas**</span><span class="sxs-lookup"><span data-stu-id="3b635-117">**Product areas affected**</span></span>         | <span data-ttu-id="3b635-118">Flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="3b635-118">Workflow</span></span> |
| <span data-ttu-id="3b635-119">**Opción de implementación**</span><span class="sxs-lookup"><span data-stu-id="3b635-119">**Deployment option**</span></span>              | <span data-ttu-id="3b635-120">Todas</span><span class="sxs-lookup"><span data-stu-id="3b635-120">All</span></span> |
| <span data-ttu-id="3b635-121">**Estado**</span><span class="sxs-lookup"><span data-stu-id="3b635-121">**Status**</span></span>                         | <span data-ttu-id="3b635-122">La lista desplegable de selección de usuario se eliminó del cuadro de diálogo de solicitud de cambio en la Platform update 32.</span><span class="sxs-lookup"><span data-stu-id="3b635-122">The user selection drop-down list was removed from the request change dialog box in Platform update 32.</span></span> <span data-ttu-id="3b635-123">Las solicitudes de cambio de solicitud se enviarán automáticamente al originador según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="3b635-123">Request change requests will be automatically sent to the originator as intended.</span></span> <span data-ttu-id="3b635-124">Para obtener más información sobre esta funcionalidad, vea [Acciones en procesos de aprobación de flujo de trabajo](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/workflow-actions?toc=%2Fdynamics365%2Fcommerce%2Ftoc.json#request-change).</span><span class="sxs-lookup"><span data-stu-id="3b635-124">For more information about this functionality, see [Actions in workflow approval processes](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/workflow-actions?toc=%2Fdynamics365%2Fcommerce%2Ftoc.json#request-change).</span></span> |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a><span data-ttu-id="3b635-125">Anuncios anteriores sobre funciones quitadas u obsoletas</span><span class="sxs-lookup"><span data-stu-id="3b635-125">Previous announcements about removed or deprecated features</span></span>
<span data-ttu-id="3b635-126">Para obtener más información sobre las funciones que se han eliminado o desaprobado en versiones anteriores, consulte [Funciones eliminadas o en desuso en versiones anteriores](../migration-upgrade/deprecated-features.md).</span><span class="sxs-lookup"><span data-stu-id="3b635-126">To learn more about features that have been removed or deprecated in previous releases, see [Removed or deprecated features in previous releases](../migration-upgrade/deprecated-features.md).</span></span>

