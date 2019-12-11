---
title: Optar por usar clasificaciones y revisiones de usuario
description: Este tema explica cómo optar por usar clasificaciones y revisiones en su sitio de Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 10e3c33af232fa46df09a103b2e73eae09a909eb
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697989"
---
# <a name="opt-in-to-use-ratings-and-reviews"></a><span data-ttu-id="23d1c-103">Optar por usar clasificaciones y revisiones de usuario</span><span class="sxs-lookup"><span data-stu-id="23d1c-103">Opt in to use ratings and reviews</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="23d1c-104">Este tema explica cómo optar por usar clasificaciones y revisiones en su sitio de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="23d1c-104">This topic explains how to opt in to use ratings and reviews on your Microsoft Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="23d1c-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="23d1c-105">Overview</span></span>

<span data-ttu-id="23d1c-106">La solución de clasificaciones y revisiones es una solución omnicanal que puede hacer que esté disponible en Dynamics 365 Commerce mediante Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="23d1c-106">The ratings and reviews solution is an omnichannel solution that you can make available in Dynamics 365 Commerce by using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="23d1c-107">LCS es un portal de administración que los minoristas usan para administrar sus entornos del aprovisionamiento a la retirada.</span><span class="sxs-lookup"><span data-stu-id="23d1c-107">LCS is an administration portal that retailers use to manage their environments from provisioning to decommissioning.</span></span>

<span data-ttu-id="23d1c-108">Si desea usar la solución de clasificaciones y revisiones en su sitio web de Commerce, primero debe optar por usarla.</span><span class="sxs-lookup"><span data-stu-id="23d1c-108">If you want to use the ratings and reviews solution on your Commerce website, you must first opt in.</span></span>

## <a name="opt-in-to-use-ratings-and-reviews"></a><span data-ttu-id="23d1c-109">Optar por usar clasificaciones y revisiones de usuario</span><span class="sxs-lookup"><span data-stu-id="23d1c-109">Opt in to use ratings and reviews</span></span>

<span data-ttu-id="23d1c-110">Para optar por usar las clasificaciones y revisiones en su sitio, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="23d1c-110">To opt in to use ratings and reviews on your site, follow these steps.</span></span>

1. <span data-ttu-id="23d1c-111">Siga los pasos de [Implementar un sitio nuevo de comercio electrónico](deploy-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="23d1c-111">Follow the steps in [Deploy a new e-Commerce site](deploy-ecommerce-site.md).</span></span>
1. <span data-ttu-id="23d1c-112">Mientras se encuentre todavía en LCS, vaya a **Configuración de implementación de Retail \> Otra configuración**.</span><span class="sxs-lookup"><span data-stu-id="23d1c-112">While you're still in LCS, go to **Retail deployment setup \> Other settings**.</span></span>
1. <span data-ttu-id="23d1c-113">Establezca la opción **Habilitar el servicio de clasificaciones y revisiones** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="23d1c-113">Set the **Enable ratings and reviews service** option to **Yes**.</span></span>
1. <span data-ttu-id="23d1c-114">En el campo **Grupo de seguridad de AAD para moderador de clasificaciones y revisiones (id. de objeto del grupo de seguridad)**, especifique el id. del grupo de seguridad de Microsoft Azure Active Directory (Azure AD) que incluye los moderadores de clasificaciones y revisiones.</span><span class="sxs-lookup"><span data-stu-id="23d1c-114">In the **AAD security group for ratings and review moderator (security group object id)** field, enter the ID of the Microsoft Azure Active Directory (Azure AD) security group that includes the ratings and reviews moderators.</span></span>

    ![Optar por usar clasificaciones y revisiones de usuario](media/LCS_RnR_Preference.png)

1. <span data-ttu-id="23d1c-116">Complete el proceso de inicialización de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="23d1c-116">Complete the e-Commerce initialization process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="23d1c-117">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="23d1c-117">Additional resources</span></span>

[<span data-ttu-id="23d1c-118">Visión general de clasificaciones y revisiones</span><span class="sxs-lookup"><span data-stu-id="23d1c-118">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="23d1c-119">Administrar clasificaciones y revisiones</span><span class="sxs-lookup"><span data-stu-id="23d1c-119">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="23d1c-120">Configurar clasificaciones y revisiones</span><span class="sxs-lookup"><span data-stu-id="23d1c-120">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)

[<span data-ttu-id="23d1c-121">Sincronizar clasificaciones de productos en Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="23d1c-121">Sync product ratings in Dynamics 365 Retail</span></span>](sync-product-ratings.md)
