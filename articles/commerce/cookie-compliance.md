---
title: Cumplimiento de cookies
description: Este tema describe consideraciones para el cumplimiento de cookies y las políticas predeterminadas que se incluyen en Microsoft Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 06/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e1fa016dc9f46b048220f0f83e4b0783087de91e
ms.sourcegitcommit: c66c4c67a21e7d7d3a94a3fd766c3184b6e65c4e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/12/2020
ms.locfileid: "3446922"
---
# <a name="cookie-compliance"></a><span data-ttu-id="f8b16-103">Cumplimiento de cookies</span><span class="sxs-lookup"><span data-stu-id="f8b16-103">Cookie compliance</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f8b16-104">Este tema describe consideraciones para el cumplimiento de cookies y las políticas predeterminadas que se incluyen en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f8b16-104">This topic describes considerations for cookie compliance and the default policies that are included in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="f8b16-105">Información general</span><span class="sxs-lookup"><span data-stu-id="f8b16-105">Overview</span></span>

<span data-ttu-id="f8b16-106">La privacidad es un factor importante cuando se utilizan tecnologías de seguimiento que afectan a los clientes de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="f8b16-106">Privacy is an important factor when tracking technologies that affect e-Commerce customers.</span></span> <span data-ttu-id="f8b16-107">Debido a los estándares de cumplimiento de privacidad, como el Reglamento General de Protección de Datos (GDPR) en la Unión Europea (UE), se deben tener en cuenta las pautas de privacidad electrónica para cualquier sitio que esté activo en la actualidad.</span><span class="sxs-lookup"><span data-stu-id="f8b16-107">Because of privacy compliance standards such as the General Data Protection Regulation (GDPR) in the European Union (EU), electronic privacy guidelines must be considered for any site that is active today.</span></span> <span data-ttu-id="f8b16-108">Debido a que muchos sitios de comercio electrónico son accesibles globalmente de manera predeterminada, es importante que revise los estándares de cumplimiento para su sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="f8b16-108">Because many e-Commerce sites are globally accessible by default, it's important that you review the compliance standards for your e-Commerce site.</span></span>

<span data-ttu-id="f8b16-109">Para obtener más información sobre los principios básicos que utiliza Microsoft para el cumplimiento de cookies, visite el [Centro de confianza de Microsoft](https://www.microsoft.com/trust-center).</span><span class="sxs-lookup"><span data-stu-id="f8b16-109">To learn more about the basic principles that Microsoft uses for cookie compliance, visit the [Microsoft Trust Center](https://www.microsoft.com/trust-center).</span></span> <span data-ttu-id="f8b16-110">En ese sitio, también puede obtener más información sobre las áreas de cumplimiento y privacidad.</span><span class="sxs-lookup"><span data-stu-id="f8b16-110">On that site, you can also get more information about areas of compliance and privacy.</span></span>

<span data-ttu-id="f8b16-111">La siguiente tabla muestra la lista de referencia actual de cookies colocadas por sitios de Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f8b16-111">The following table shows the current reference list of cookies placed by Dynamics 365 Commerce sites.</span></span>

| <span data-ttu-id="f8b16-112">Nombre de la cookie</span><span class="sxs-lookup"><span data-stu-id="f8b16-112">Cookie name</span></span>                               | <span data-ttu-id="f8b16-113">Uso</span><span class="sxs-lookup"><span data-stu-id="f8b16-113">Usage</span></span>                                                        |
| ------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="f8b16-114">.AspNet.Cookies</span><span class="sxs-lookup"><span data-stu-id="f8b16-114">.AspNet.Cookies</span></span>                             | <span data-ttu-id="f8b16-115">Almacena las cookies de autenticación de Microsoft Azure Active Directory (Azure AD) para el inicio de sesión único (SSO).</span><span class="sxs-lookup"><span data-stu-id="f8b16-115">Store Microsoft Azure Active Directory (Azure AD) authentication cookies for single sign-on (SSO).</span></span> <span data-ttu-id="f8b16-116">Almacena la información principal del usuario cifrada (nombre, apellidos, correo electrónico).</span><span class="sxs-lookup"><span data-stu-id="f8b16-116">Stores encrypted user principal information (name, surname, email).</span></span> |
| <span data-ttu-id="f8b16-117">&#95;msdyn365___cart&#95;</span><span class="sxs-lookup"><span data-stu-id="f8b16-117">&#95;msdyn365___cart&#95;</span></span>                           | <span data-ttu-id="f8b16-118">Almacene el identificador del carrito de la compra para obtener la lista de productos agregados a la instancia del carrito.</span><span class="sxs-lookup"><span data-stu-id="f8b16-118">Store cart ID used to obtain list of products added to cart instance.</span></span> |
| <span data-ttu-id="f8b16-119">&#95;msdyn365___ucc&#95;</span><span class="sxs-lookup"><span data-stu-id="f8b16-119">&#95;msdyn365___ucc&#95;</span></span>                            | <span data-ttu-id="f8b16-120">Seguimiento del consentimiento del cumplimiento de cookies.</span><span class="sxs-lookup"><span data-stu-id="f8b16-120">Cookie compliance consent tracking.</span></span>                          |
| <span data-ttu-id="f8b16-121">ai_session</span><span class="sxs-lookup"><span data-stu-id="f8b16-121">ai_session</span></span>                                  | <span data-ttu-id="f8b16-122">Detecta cuántas sesiones de actividad del usuario han incluido ciertas páginas y características de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f8b16-122">Detects how many sessions of user activity have included certain pages and features of the app.</span></span> |
| <span data-ttu-id="f8b16-123">ai_user</span><span class="sxs-lookup"><span data-stu-id="f8b16-123">ai_user</span></span>                                     | <span data-ttu-id="f8b16-124">Detecta cuántas personas usaron la aplicación y sus características.</span><span class="sxs-lookup"><span data-stu-id="f8b16-124">Detects how many people used the app and its features.</span></span> <span data-ttu-id="f8b16-125">Los usuarios se cuentan utilizando identificaciones anónimos.</span><span class="sxs-lookup"><span data-stu-id="f8b16-125">Users are counted using anonymous IDs.</span></span> |
| <span data-ttu-id="f8b16-126">b2cru</span><span class="sxs-lookup"><span data-stu-id="f8b16-126">b2cru</span></span>                                       | <span data-ttu-id="f8b16-127">Almacena de forma dinámica las URL de redireccionamiento.</span><span class="sxs-lookup"><span data-stu-id="f8b16-127">Stores redirect URL dynamically.</span></span>                              |
| <span data-ttu-id="f8b16-128">JSESSIONID</span><span class="sxs-lookup"><span data-stu-id="f8b16-128">JSESSIONID</span></span>                                  | <span data-ttu-id="f8b16-129">Utilizado por el conector de pago Adyen para almacenar la sesión del usuario.</span><span class="sxs-lookup"><span data-stu-id="f8b16-129">Used by payment connector Adyen to store user session.</span></span>       |
| <span data-ttu-id="f8b16-130">OpenIdConnect.nonce.&#42;</span><span class="sxs-lookup"><span data-stu-id="f8b16-130">OpenIdConnect.nonce.&#42;</span></span>                       | <span data-ttu-id="f8b16-131">Autentificación</span><span class="sxs-lookup"><span data-stu-id="f8b16-131">Authentication</span></span>                                               |
| <span data-ttu-id="f8b16-132">x-ms-cpim-cache:.&#42;</span><span class="sxs-lookup"><span data-stu-id="f8b16-132">x-ms-cpim-cache:.&#42;</span></span>                          | <span data-ttu-id="f8b16-133">Se utiliza para mantener el estado de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="f8b16-133">Used for maintaining the request state.</span></span>                      |
| <span data-ttu-id="f8b16-134">x-ms-cpim-csrf</span><span class="sxs-lookup"><span data-stu-id="f8b16-134">x-ms-cpim-csrf</span></span>                              | <span data-ttu-id="f8b16-135">Token de falsificación de solicitud entre sitios (CRSF) utilizado para la protección contra CRSF.</span><span class="sxs-lookup"><span data-stu-id="f8b16-135">Cross-site request forgery (CRSF) token used for protection from CRSF.</span></span>     |
| <span data-ttu-id="f8b16-136">x-ms-cpim-dc</span><span class="sxs-lookup"><span data-stu-id="f8b16-136">x-ms-cpim-dc</span></span>                                | <span data-ttu-id="f8b16-137">Se utiliza para enrutar solicitudes a la instancia del servidor de autenticación de producción adecuada.</span><span class="sxs-lookup"><span data-stu-id="f8b16-137">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="f8b16-138">x-ms-cpim-rc.&#42;</span><span class="sxs-lookup"><span data-stu-id="f8b16-138">x-ms-cpim-rc.&#42;</span></span>                              | <span data-ttu-id="f8b16-139">Se utiliza para enrutar solicitudes a la instancia del servidor de autenticación de producción adecuada.</span><span class="sxs-lookup"><span data-stu-id="f8b16-139">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="f8b16-140">x-ms-cpim-slice</span><span class="sxs-lookup"><span data-stu-id="f8b16-140">x-ms-cpim-slice</span></span>                             | <span data-ttu-id="f8b16-141">Se utiliza para enrutar solicitudes a la instancia del servidor de autenticación de producción adecuada.</span><span class="sxs-lookup"><span data-stu-id="f8b16-141">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="f8b16-142">x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0</span><span class="sxs-lookup"><span data-stu-id="f8b16-142">x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0</span></span> | <span data-ttu-id="f8b16-143">Se usa para mantener la sesión SSO.</span><span class="sxs-lookup"><span data-stu-id="f8b16-143">Used for maintaining the SSO session.</span></span>                        |
| <span data-ttu-id="f8b16-144">x-ms-cpim-trans</span><span class="sxs-lookup"><span data-stu-id="f8b16-144">x-ms-cpim-trans</span></span>                             | <span data-ttu-id="f8b16-145">Se utiliza para llevar el seguimiento de transacciones (el número de pestañas abiertas que se autentican en un sitio de empresa a cliente (B2C)), incluida la transacción actual.</span><span class="sxs-lookup"><span data-stu-id="f8b16-145">Used for tracking transactions (the number of open tabs authenticating against a business-to-consumer (B2C) site), including the current transaction.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="f8b16-146">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="f8b16-146">Additional resources</span></span>

[<span data-ttu-id="f8b16-147">Características y funcionalidades de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="f8b16-147">Accessibility features and capabilities</span></span>](accessibility.md)

[<span data-ttu-id="f8b16-148">Información general sobre cumplimiento</span><span class="sxs-lookup"><span data-stu-id="f8b16-148">Compliance overview</span></span>](compliance-overview.md)

[<span data-ttu-id="f8b16-149">Agregar una página de directivas de privacidad</span><span class="sxs-lookup"><span data-stu-id="f8b16-149">Add a privacy policy page</span></span>](add-privacy-page.md)

[<span data-ttu-id="f8b16-150">Reemplazar id. de usuario asociado con cambios de contenido con seguimiento</span><span class="sxs-lookup"><span data-stu-id="f8b16-150">Replace user IDs associated with tracked content changes</span></span>](replace-IDs-tracked-changes.md)
