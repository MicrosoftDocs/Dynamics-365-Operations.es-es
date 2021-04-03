---
title: El enlace de inicio de sesión redirige a un sitio de comercio electrónico
description: Este tema proporciona una guía para la resolución de problemas que puede ayudar cuando un enlace de inicio de sesión redirige al sitio de comercio electrónico en lugar de ir a la página de inicio de sesión.
author: Reza-Assadi
manager: AnnBe
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
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
ms.openlocfilehash: 36f10c9f68570a6c67da6b4b6e4155f4634f633a
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585511"
---
# <a name="sign-in-link-redirects-back-to-an-e-commerce-site"></a><span data-ttu-id="73a4a-103">El enlace de inicio de sesión redirige a un sitio de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="73a4a-103">Sign-in link redirects back to an e-commerce site</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="73a4a-104">Este tema proporciona una guía para la resolución de problemas que puede ayudar cuando un enlace de inicio de sesión redirige al sitio de comercio electrónico en lugar de ir a la página de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="73a4a-104">This topic provides troubleshooting guidance that can help when a sign-in link redirects back to the e-commerce site instead of going to the sign-in page.</span></span>

## <a name="description"></a><span data-ttu-id="73a4a-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="73a4a-105">Description</span></span>

<span data-ttu-id="73a4a-106">Después de configurar un nuevo inquilino de Microsoft Azure Active Directory B2C (Azure AD B2C) en el creador de sitios de Commerceo, los usuarios que seleccionan el enlace **Iniciar sesión** se redirigen a la página de aterrizaje principal del comercio electrónico sin ir a la página de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="73a4a-106">After you configure a new Microsoft Azure Active Directory B2C (Azure AD B2C) tenant in Commerce site builder, users who select the **Sign in** link are redirected back to the main e-commerce landing page without going to the sign-in page.</span></span>

## <a name="resolution"></a><span data-ttu-id="73a4a-107">Resolución</span><span class="sxs-lookup"><span data-stu-id="73a4a-107">Resolution</span></span>

### <a name="confirm-that-the-reply-url-is-correctly-configured-in-the-azure-ad-b2c-application"></a><span data-ttu-id="73a4a-108">Confirmar que la URL de respuesta esté configurada correctamente en la aplicación Azure AD B2C</span><span class="sxs-lookup"><span data-stu-id="73a4a-108">Confirm that the reply URL is correctly configured in the Azure AD B2C application</span></span>

<span data-ttu-id="73a4a-109">Para confirmar que la URL de respuesta esté configurada correctamente en la aplicación Azure AD B2C, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="73a4a-109">To confirm that the reply URL is correctly configured in the Azure AD B2C application, follow these steps.</span></span>

1. <span data-ttu-id="73a4a-110">Vaya a [Azure Portal](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="73a4a-110">Go to the [Azure portal](https://portal.azure.com/).</span></span>
1. <span data-ttu-id="73a4a-111">Seleccione la aplicación Azure AD B2C que creó para el acceso a su sitio.</span><span class="sxs-lookup"><span data-stu-id="73a4a-111">Select the Azure AD B2C application that you created for your site access.</span></span>
1. <span data-ttu-id="73a4a-112">Seleccione la aplicación que creó durante la configuración de Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="73a4a-112">Select the application that you created during the Azure AD B2C setup.</span></span>
1. <span data-ttu-id="73a4a-113">En **URL de respuesta**, asegúrese de que la lista incluya entradas tanto para la URL del dominio del sitio como para la URL generada por comercio electrónico, como se muestra en el ejemplo de la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="73a4a-113">Under **Reply URL**, make sure that the list includes entries for both the site domain URL and the e-commerce-generated URL, as shown in the example in the following illustration.</span></span>

    ![Entradas de URL de respuesta de Azure AD B2C](media/aad-b2c-reply-url.jpg)

> [!NOTE]
> <span data-ttu-id="73a4a-115">Tanto la URL del dominio del sitio como la URL generada por comercio electrónico deben tener un formato de URL válido que no incluya barras al principio ni al final.</span><span class="sxs-lookup"><span data-stu-id="73a4a-115">Both the site domain URL and the e-commerce-generated URL must be in a valid URL format that doesn't include leading or trailing slashes.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="73a4a-116">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="73a4a-116">Additional resources</span></span>

[<span data-ttu-id="73a4a-117">Registrar una aplicación conectada en Azure Active Directory B2C</span><span class="sxs-lookup"><span data-stu-id="73a4a-117">Register a web application in Azure Active Directory B2C</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/tutorial-register-applications?tabs=app-reg-ga#register-a-web-application)

[<span data-ttu-id="73a4a-118">Configurar un inquilino B2C en Commerce</span><span class="sxs-lookup"><span data-stu-id="73a4a-118">Set up a B2C tenant in Commerce</span></span>](../set-up-b2c-tenant.md)
