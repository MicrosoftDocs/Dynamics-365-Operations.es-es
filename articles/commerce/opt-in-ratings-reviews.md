---
title: Optar por usar clasificaciones y revisiones de usuario
description: Este tema explica cómo optar por usar clasificaciones y revisiones en su sitio de Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 01/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6c54a8fa01badb6a383c41dc979e71d82a25ef97
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5251244"
---
# <a name="opt-in-to-use-ratings-and-reviews"></a><span data-ttu-id="18bc3-103">Optar por usar clasificaciones y revisiones de usuario</span><span class="sxs-lookup"><span data-stu-id="18bc3-103">Opt in to use ratings and reviews</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="18bc3-104">Este tema explica cómo optar por usar clasificaciones y revisiones en su sitio de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="18bc3-104">This topic explains how to opt in to use ratings and reviews on your Microsoft Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="18bc3-105">Información general</span><span class="sxs-lookup"><span data-stu-id="18bc3-105">Overview</span></span>

<span data-ttu-id="18bc3-106">La solución de clasificaciones y revisiones es una solución omnicanal que puede hacer que esté disponible en Dynamics 365 Commerce mediante Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="18bc3-106">The ratings and reviews solution is an omni-channel solution that you can make available in Dynamics 365 Commerce by using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="18bc3-107">LCS es un portal de administración que los minoristas usan para administrar sus entornos del aprovisionamiento a la retirada.</span><span class="sxs-lookup"><span data-stu-id="18bc3-107">LCS is an administration portal that retailers use to manage their environments from provisioning to decommissioning.</span></span>

<span data-ttu-id="18bc3-108">Si desea utilizar la solución de clasificaciones y revisiones en su sitio web de Commerce, debe optar por las clasificaciones y revisiones durante la implementación de su sitio de comercio electrónico en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="18bc3-108">If you want to use the ratings and reviews solution on your Commerce website, you must opt in for ratings and reviews during deployment of your e-Commerce site on Dynamics 365 Commerce.</span></span>

## <a name="opt-in-to-use-ratings-and-reviews"></a><span data-ttu-id="18bc3-109">Optar por usar clasificaciones y revisiones de usuario</span><span class="sxs-lookup"><span data-stu-id="18bc3-109">Opt in to use ratings and reviews</span></span>

<span data-ttu-id="18bc3-110">Para optar por usar las clasificaciones y revisiones en su sitio, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="18bc3-110">To opt in to use ratings and reviews on your site, follow these steps.</span></span>

1. <span data-ttu-id="18bc3-111">Siga los pasos de [Implementar un sitio nuevo de comercio electrónico](deploy-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="18bc3-111">Follow the steps in [Deploy a new e-Commerce site](deploy-ecommerce-site.md).</span></span>
1. <span data-ttu-id="18bc3-112">Mientras se encuentre todavía en LCS, vaya a **Configuración de implementación de Retail \> Otra configuración**.</span><span class="sxs-lookup"><span data-stu-id="18bc3-112">While you're still in LCS, go to **Retail deployment setup \> Other settings**.</span></span>
1. <span data-ttu-id="18bc3-113">Establezca la opción **Habilitar el servicio de clasificaciones y revisiones** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="18bc3-113">Set the **Enable ratings and reviews service** option to **Yes**.</span></span>
1. <span data-ttu-id="18bc3-114">En el campo **Grupo de seguridad de AAD para moderador de clasificaciones y revisiones (id. de objeto del grupo de seguridad)**, especifique el id. del grupo de seguridad de Microsoft Azure Active Directory (Azure AD) que incluye los moderadores de clasificaciones y revisiones.</span><span class="sxs-lookup"><span data-stu-id="18bc3-114">In the **AAD security group for ratings and review moderator (security group object id)** field, enter the ID of the Microsoft Azure Active Directory (Azure AD) security group that includes the ratings and reviews moderators.</span></span>

    ![Optar por usar clasificaciones y revisiones de usuario](media/LCS_RnR_Preference.png)

1. <span data-ttu-id="18bc3-116">Complete el proceso de inicialización de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="18bc3-116">Complete the e-Commerce initialization process.</span></span>

> [!NOTE] 
> <span data-ttu-id="18bc3-117">Si eres un cliente de Dynamics 365 Commerce existente que ya ha implementado un sitio de comercio electrónico sin haber optado por participar en clasificaciones y revisiones, y ahora desea usar las clasificaciones y revisiones del paquete de Dynamics 365 Commerce, envíe una solicitud de servicio.</span><span class="sxs-lookup"><span data-stu-id="18bc3-117">If you are an existing Dynamics 365 Commerce customer who has already deployed an e-Commerce site without having opted in for ratings and reviews and now want to use ratings and reviews from the Dynamics 365 Commerce package, please submit a service request.</span></span> <span data-ttu-id="18bc3-118">Para obtener información acerca de cómo enviar una solicitud de servicio, consulte [Enviar proceso de solicitudes de servicio](../fin-ops-core/dev-itpro/lifecycle-services/submit-request-dynamics-service-engineering-team.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="18bc3-118">For information about how to submit a service request, see [Submit service requests process](../fin-ops-core/dev-itpro/lifecycle-services/submit-request-dynamics-service-engineering-team.md?toc=/dynamics365/commerce/toc.json).</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="18bc3-119">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="18bc3-119">Additional resources</span></span>

[<span data-ttu-id="18bc3-120">Visión general de clasificaciones y revisiones</span><span class="sxs-lookup"><span data-stu-id="18bc3-120">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="18bc3-121">Administrar clasificaciones y revisiones</span><span class="sxs-lookup"><span data-stu-id="18bc3-121">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="18bc3-122">Configurar clasificaciones y revisiones</span><span class="sxs-lookup"><span data-stu-id="18bc3-122">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)

[<span data-ttu-id="18bc3-123">Sincronizar clasificaciones de productos en Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="18bc3-123">Sync product ratings in Dynamics 365 Commerce</span></span>](sync-product-ratings.md)




[!INCLUDE[footer-include](../includes/footer-banner.md)]