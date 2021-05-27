---
title: Restringir el acceso a un escaparate durante las pruebas o el desarrollo
description: Este tema explica cómo restringir el acceso a un escaparate de Microsoft Dynamics 365 Commerce mientras se realizan las pruebas internas o el desarrollo.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: cdc9b6af55bcba98f5ea7607bb1847f61a707778
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018347"
---
# <a name="restrict-access-to-a-storefront-during-testing-or-development"></a><span data-ttu-id="33ee7-103">Restringir el acceso a un escaparate durante las pruebas o el desarrollo</span><span class="sxs-lookup"><span data-stu-id="33ee7-103">Restrict access to a storefront during testing or development</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="33ee7-104">Este tema explica cómo restringir el acceso a un escaparate de Microsoft Dynamics 365 Commerce mientras se realizan las pruebas internas o el desarrollo.</span><span class="sxs-lookup"><span data-stu-id="33ee7-104">This topic explains how to restrict access to a Microsoft Dynamics 365 Commerce storefront while internal testing or development is occurring.</span></span>

## <a name="description"></a><span data-ttu-id="33ee7-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="33ee7-105">Description</span></span>

<span data-ttu-id="33ee7-106">Durante las pruebas internas o el desarrollo activo, es posible que desee restringir el acceso a su sitio para evitar que los usuarios externos accedan a las páginas publicadas del escaparate.</span><span class="sxs-lookup"><span data-stu-id="33ee7-106">During internal testing or active development, you might want to restrict access to your site to prevent external users from accessing the published storefront pages.</span></span>

## <a name="resolution"></a><span data-ttu-id="33ee7-107">Resolución</span><span class="sxs-lookup"><span data-stu-id="33ee7-107">Resolution</span></span>

### <a name="set-up-azure-ad-b2c-by-using-standard-user-flows"></a><span data-ttu-id="33ee7-108">Configurar Azure AD B2C mediante el uso de flujos de usuarios estándar</span><span class="sxs-lookup"><span data-stu-id="33ee7-108">Set up Azure AD B2C by using standard user flows</span></span>

<span data-ttu-id="33ee7-109">Para obtener información sobre cómo configurar Azure Active Directory B2C (Azure AD B2C) para su sitio de comercio electrónico, consulte [Configurar un inquilino B2C en Commerce](../set-up-b2c-tenant.md).</span><span class="sxs-lookup"><span data-stu-id="33ee7-109">For information about how to configure Azure Active Directory B2C (Azure AD B2C) for your e-commerce site, see [Set up a B2C tenant in Commerce](../set-up-b2c-tenant.md).</span></span>

### <a name="restrict-user-access-to-storefront-pages-and-block-the-creation-of-new-users"></a><span data-ttu-id="33ee7-110">Restrinja el acceso de los usuarios a las páginas del escaparate y bloquee la creación de nuevos usuarios</span><span class="sxs-lookup"><span data-stu-id="33ee7-110">Restrict user access to storefront pages and block the creation of new users</span></span>

<span data-ttu-id="33ee7-111">Para restringir el acceso de los usuarios a las páginas del escaparate en el creador de sitios de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="33ee7-111">To restrict user access to storefront pages in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="33ee7-112">Vaya a su sitio.</span><span class="sxs-lookup"><span data-stu-id="33ee7-112">Go to your site.</span></span>
1. <span data-ttu-id="33ee7-113">Seleccione **Paginas** y luego seleccione la página a la que restringir el acceso de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="33ee7-113">Select **Pages**, and then select the page to restrict user access for.</span></span>
1. <span data-ttu-id="33ee7-114">Seleccione el módulo o el espacio de fragmentos y luego seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="33ee7-114">Select the module or fragment slot, and then select **Edit**.</span></span>
1. <span data-ttu-id="33ee7-115">En el panel de propiedades, seleccione **¿Requiere iniciar sesión?** y luego seleccione **Terminar de editar**.</span><span class="sxs-lookup"><span data-stu-id="33ee7-115">In the properties pane, select **Requires sign-in?**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="33ee7-116">Seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="33ee7-116">Select **Publish**.</span></span>

<span data-ttu-id="33ee7-117">Para bloquear la creación de nuevos usuarios en Azure AD, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="33ee7-117">To block the creation of new users in Azure AD, follow these steps.</span></span>

1. <span data-ttu-id="33ee7-118">Vaya a [Azure Portal](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="33ee7-118">Go to the [Azure portal](https://portal.azure.com/).</span></span>
1. <span data-ttu-id="33ee7-119">Seleccione la aplicación Azure AD B2C que creó para el acceso a su sitio.</span><span class="sxs-lookup"><span data-stu-id="33ee7-119">Select the Azure AD B2C application that you created for your site access.</span></span>
1. <span data-ttu-id="33ee7-120">En el panel de navegación izquierdo, seleccione **Flujos de usuarios**.</span><span class="sxs-lookup"><span data-stu-id="33ee7-120">In the left navigation, select **User flows**.</span></span>
1. <span data-ttu-id="33ee7-121">En la parte superior de **Flujos de usuarios**, seleccione **Nuevo flujo de usuario**.</span><span class="sxs-lookup"><span data-stu-id="33ee7-121">At the top of the **User Flows** page, select **New user flow**.</span></span>
1. <span data-ttu-id="33ee7-122">En la página **Seleccionar un tipo de flujo de usuario**, seleccione **Versión preliminar**.</span><span class="sxs-lookup"><span data-stu-id="33ee7-122">On the **Select a user flow type** page, select **Preview**.</span></span>
1. <span data-ttu-id="33ee7-123">En el medio de la página, seleccione **iniciar sesión v2**.</span><span class="sxs-lookup"><span data-stu-id="33ee7-123">In the middle of the page, select **Sign in v2**.</span></span> <span data-ttu-id="33ee7-124">Luego, siga los pasos en [Configurar un inquilino B2C en Commerce](../set-up-b2c-tenant.md) para configurar el flujo como el flujo de usuario estándar de su sitio para Azure AD B2C durante las pruebas o el desarrollo.</span><span class="sxs-lookup"><span data-stu-id="33ee7-124">Then follow the steps in [Set up a B2C tenant in Commerce](../set-up-b2c-tenant.md) to configure the flow as your site's standard user flow for Azure AD B2C during testing or development.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="33ee7-125">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="33ee7-125">Additional resources</span></span>

[<span data-ttu-id="33ee7-126">Configurar un inquilino B2C en Commerce</span><span class="sxs-lookup"><span data-stu-id="33ee7-126">Set up a B2C tenant in Commerce</span></span>](../set-up-b2c-tenant.md)

[<span data-ttu-id="33ee7-127">Configurar páginas personalizadas para inicios de sesión de usuario</span><span class="sxs-lookup"><span data-stu-id="33ee7-127">Set up custom pages for user sign-ins</span></span>](../custom-pages-user-logins.md)
