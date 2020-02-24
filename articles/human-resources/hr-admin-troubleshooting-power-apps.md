---
title: No se puede crear un entorno en el centro de administración de Power Apps
description: Este artículo explica qué hacer si el administrador no puede crear un entorno en el centro de administración Microsoft Power Apps.
author: andreabichsel
manager: AnnBe
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
ms.openlocfilehash: f4c75706183a3d6c961852395e464d46ba3ec1f2
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010434"
---
# <a name="cant-create-an-environment-in-the-power-apps-admin-center"></a><span data-ttu-id="e01f0-103">No se puede crear un entorno en el centro de administración de Power Apps</span><span class="sxs-lookup"><span data-stu-id="e01f0-103">Can't create an environment in the Power Apps Admin center</span></span>

<span data-ttu-id="e01f0-104">**Emisión**</span><span class="sxs-lookup"><span data-stu-id="e01f0-104">**Issue**</span></span>

- <span data-ttu-id="e01f0-105">La administración de inquilinos/entorno no puede crear un entorno en el centro de gestión de Microsoft Power Apps.</span><span class="sxs-lookup"><span data-stu-id="e01f0-105">The tenant/environment admin can't create an environment in the Microsoft Power Apps Admin center.</span></span>
- <span data-ttu-id="e01f0-106">Una licencia que da a los usuarios el derecho de realizar el paso de creación del entorno no se ha asignado directamente al usuario que está realizando ese paso.</span><span class="sxs-lookup"><span data-stu-id="e01f0-106">A licence that gives users the right to perform the environment creation step hasn't been assigned directly to the user who is performing that step.</span></span>

<span data-ttu-id="e01f0-107">**Solución**</span><span class="sxs-lookup"><span data-stu-id="e01f0-107">**Solution**</span></span>

<span data-ttu-id="e01f0-108">Asegúrese de que la gestión de arrendatarios haya asignado una licencia válida de Power Apps P2 directamente al usuario que llevará a cabo el paso de la creación del entorno.</span><span class="sxs-lookup"><span data-stu-id="e01f0-108">Make sure that the tenant admin has assigned a valid Power Apps P2 license directly to the user who will perform the environment creation step.</span></span> <span data-ttu-id="e01f0-109">Aquí hay los planes de servicio de Microsoft Dynamics que proporcionan ese derecho.</span><span class="sxs-lookup"><span data-stu-id="e01f0-109">Here are the Microsoft Dynamics service plans that provide that right.</span></span>

| <span data-ttu-id="e01f0-110">Referencia de almacén (SKU) global del producto</span><span class="sxs-lookup"><span data-stu-id="e01f0-110">Overall product stock keeping unit (SKU)</span></span>       | <span data-ttu-id="e01f0-111">Plan de servicio de Power Apps P2</span><span class="sxs-lookup"><span data-stu-id="e01f0-111">Power Apps P2 service plan</span></span>  |
|------------------------------------------------|----------------------------|
| <span data-ttu-id="e01f0-112">Microsoft Dynamics 365 for Operations</span><span class="sxs-lookup"><span data-stu-id="e01f0-112">Microsoft Dynamics 365 for Operations</span></span>          | <span data-ttu-id="e01f0-113">Power Apps para Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="e01f0-113">Power Apps for Dynamics 365</span></span> |
| <span data-ttu-id="e01f0-114">Microsoft Dynamics 365 Plan Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="e01f0-114">Microsoft Dynamics 365 Plan Enterprise Edition</span></span> | <span data-ttu-id="e01f0-115">Power Apps para Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="e01f0-115">Power Apps for Dynamics 365</span></span> |

<span data-ttu-id="e01f0-116">Tenga en cuenta que diversas SKU de Microsoft Office también proporcionan el derecho, junto con SKU de Power Apps Plan 2 independientes.</span><span class="sxs-lookup"><span data-stu-id="e01f0-116">Note that various Microsoft Office SKUs also provide the right, together with standalone Power Apps Plan 2 SKUs.</span></span> <span data-ttu-id="e01f0-117">El aspecto importante es que una de estas SKU debe estar presente.</span><span class="sxs-lookup"><span data-stu-id="e01f0-117">The important point is that one of these SKUs must be present.</span></span>

1. <span data-ttu-id="e01f0-118">Ir a [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span><span class="sxs-lookup"><span data-stu-id="e01f0-118">Go to [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span></span>
2. <span data-ttu-id="e01f0-119">Siga las instrucciones en [Aprovisionar Recursos humanos](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent) para crear los entornos.</span><span class="sxs-lookup"><span data-stu-id="e01f0-119">Create the environments by following the instructions in [Provision Human Resources](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span></span>
