---
title: No se puede crear un entorno en el centro de administración de Power Apps
description: Este artículo explica qué hacer si el administrador no puede crear un entorno en el centro de administración Microsoft Power Apps.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ec63148364022fe5b8c40d855856eec232af3e48
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "5463969"
---
# <a name="cant-create-an-environment-in-the-power-apps-admin-center"></a><span data-ttu-id="b9f03-103">No se puede crear un entorno en el centro de administración de Power Apps</span><span class="sxs-lookup"><span data-stu-id="b9f03-103">Can't create an environment in the Power Apps Admin center</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="b9f03-104">**Emisión**</span><span class="sxs-lookup"><span data-stu-id="b9f03-104">**Issue**</span></span>

- <span data-ttu-id="b9f03-105">La administración de inquilinos/entorno no puede crear un entorno en el centro de gestión de Microsoft Power Apps.</span><span class="sxs-lookup"><span data-stu-id="b9f03-105">The tenant/environment admin can't create an environment in the Microsoft Power Apps Admin center.</span></span>
- <span data-ttu-id="b9f03-106">El usuario no tiene una licencia que le dé derecho a crear entornos.</span><span class="sxs-lookup"><span data-stu-id="b9f03-106">The user doesn't have a license that gives the right to create environments.</span></span>

<span data-ttu-id="b9f03-107">**Solución**</span><span class="sxs-lookup"><span data-stu-id="b9f03-107">**Solution**</span></span>

<span data-ttu-id="b9f03-108">Asegúrese de que el administrador de inquilinos haya asignado una licencia P2 de Power Apps válida para el usuario que crea el entorno.</span><span class="sxs-lookup"><span data-stu-id="b9f03-108">Make sure the tenant admin has assigned a valid Power Apps P2 license to the user creating the environment.</span></span> <span data-ttu-id="b9f03-109">Los planes de servicio de Microsoft Dynamics siguientes proporcionan permisos para crear entornos:</span><span class="sxs-lookup"><span data-stu-id="b9f03-109">The following Microsoft Dynamics service plans provide permissions to create environments:</span></span>

| <span data-ttu-id="b9f03-110">Referencia de almacén (SKU) global del producto</span><span class="sxs-lookup"><span data-stu-id="b9f03-110">Overall product stockkeeping unit (SKU)</span></span>       | <span data-ttu-id="b9f03-111">Plan de servicio de Power Apps P2</span><span class="sxs-lookup"><span data-stu-id="b9f03-111">Power Apps P2 service plan</span></span>  |
|------------------------------------------------|----------------------------|
| <span data-ttu-id="b9f03-112">Microsoft Dynamics 365 for Operations</span><span class="sxs-lookup"><span data-stu-id="b9f03-112">Microsoft Dynamics 365 for Operations</span></span>          | <span data-ttu-id="b9f03-113">Power Apps para Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="b9f03-113">Power Apps for Dynamics 365</span></span> |
| <span data-ttu-id="b9f03-114">Microsoft Dynamics 365 Plan Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="b9f03-114">Microsoft Dynamics 365 Plan Enterprise Edition</span></span> | <span data-ttu-id="b9f03-115">Power Apps para Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="b9f03-115">Power Apps for Dynamics 365</span></span> |

<span data-ttu-id="b9f03-116">Tenga en cuenta que diversas SKU de Microsoft Office también proporcionan el derecho, junto con SKU de Power Apps Plan 2 independientes.</span><span class="sxs-lookup"><span data-stu-id="b9f03-116">Note that various Microsoft Office SKUs also provide the right, together with standalone Power Apps Plan 2 SKUs.</span></span> <span data-ttu-id="b9f03-117">El aspecto importante es que una de estas SKU debe estar presente.</span><span class="sxs-lookup"><span data-stu-id="b9f03-117">The important point is that one of these SKUs must be present.</span></span>

1. <span data-ttu-id="b9f03-118">Ir a [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span><span class="sxs-lookup"><span data-stu-id="b9f03-118">Go to [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span></span>
2. <span data-ttu-id="b9f03-119">Siga las instrucciones en [Aprovisionar Recursos humanos](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent) para crear los entornos.</span><span class="sxs-lookup"><span data-stu-id="b9f03-119">Create the environments by following the instructions in [Provision Human Resources](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]