---
title: Optar por no participar en la recopilación de eventos de actividad web
description: Este tema explica cómo puede permitir que los visitantes de su sitio web opten por no participar en la recopilación de eventos de actividad web en Microsoft Dynamics 365 Commerce.
author: aamiral
manager: AnnBe
ms.date: 05/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4b0e48307527a8fea729d8dfdcdbc6337be0faf1
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415554"
---
# <a name="opt-out-of-web-activity-event-collection"></a><span data-ttu-id="717a2-103">Optar por no participar en la recopilación de eventos de actividad web</span><span class="sxs-lookup"><span data-stu-id="717a2-103">Opt out of web activity event collection</span></span>
[!include [banner](includes/banner.md)]

<span data-ttu-id="717a2-104">Este tema explica cómo puede permitir que los clientes opten por no participar en la recopilación de eventos de actividad web en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="717a2-104">This topic explains how you can let customers opt out of web activity event collection in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="717a2-105">Información general</span><span class="sxs-lookup"><span data-stu-id="717a2-105">Overview</span></span>

<span data-ttu-id="717a2-106">Dynamics 365 Commerce permite a los administradores de sitios analizar la actividad web de los usuarios de sus sitios de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="717a2-106">Dynamics 365 Commerce lets site administrators analyze the web activity of users of their e-commerce sites.</span></span> <span data-ttu-id="717a2-107">De esa manera, pueden conocer mejor cómo se usan sus sitios y pueden optimizar los sitios para proporcionar una experiencia de usuario mejorada y cumplir con los objetivos comerciales.</span><span class="sxs-lookup"><span data-stu-id="717a2-107">In that way, they can better understand how their sites are used, and they can optimize the sites to provide an improved user experience and meet business objectives.</span></span>


## <a name="ways-for-administrators-to-implement-an-opt-out-experience"></a><span data-ttu-id="717a2-108">Maneras para que los administradores implementen una experiencia de no participación</span><span class="sxs-lookup"><span data-stu-id="717a2-108">Ways for administrators to implement an opt-out experience</span></span>

<span data-ttu-id="717a2-109">Los administradores tienen tres maneras de implementar una experiencia de no participación.</span><span class="sxs-lookup"><span data-stu-id="717a2-109">Administrators have three ways to implement an opt-out experience.</span></span>

### <a name="opt-out-on-behalf-of-users"></a><span data-ttu-id="717a2-110">Optar por no participar en nombre de los usuarios</span><span class="sxs-lookup"><span data-stu-id="717a2-110">Opt out on behalf of users</span></span>

<span data-ttu-id="717a2-111">En la gestión de cuentas de la Central de Commerce (HQ), los administradores pueden optar por no participar en nombre de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="717a2-111">In Account management in Commerce headquarters (HQ), administrators can opt out on behalf of users.</span></span>

1. <span data-ttu-id="717a2-112">En el cliente HQ, en la página **Todos los clientes**, busque y seleccione un cliente.</span><span class="sxs-lookup"><span data-stu-id="717a2-112">In the HQ client, on the **All customers** page, search for and select a customer.</span></span>
1. <span data-ttu-id="717a2-113">En la página de detalles del cliente, en la ficha desplegable **Minorista**, en la sección **Privacidad**, establezca la opción **No seguir la actividad web** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="717a2-113">On the customer details page, on the **Retail** FastTab, in the **Privacy** section, set the **Do not track web activity** option to **Yes**.</span></span>

    ![Configuración de privacidad](media/Disablepersonalizationpart2.png)

1. <span data-ttu-id="717a2-115">Haga clic en **Guardar** y, a continuación, cierre la página.</span><span class="sxs-lookup"><span data-stu-id="717a2-115">Select **Save**, and then close the page.</span></span>

### <a name="module-based-opt-out-experience"></a><span data-ttu-id="717a2-116">Experiencia de exclusión voluntaria basada en módulos</span><span class="sxs-lookup"><span data-stu-id="717a2-116">Module-based opt-out experience</span></span>

<span data-ttu-id="717a2-117">Los administradores pueden permitir que los usuarios autenticados opten ellos mismos por no participar en la recopilación de eventos de actividad web.</span><span class="sxs-lookup"><span data-stu-id="717a2-117">Administrators can let authenticated users opt out of web activity event collection by themselves.</span></span> <span data-ttu-id="717a2-118">Para proporcionar esta experiencia de exclusión, agregue el módulo de exclusión del usuario a las páginas de perfil de la cuenta del cliente.</span><span class="sxs-lookup"><span data-stu-id="717a2-118">To provide this opt-out experience, add the user opt-out module to customer account profile pages.</span></span>

### <a name="custom-extensions"></a><span data-ttu-id="717a2-119">Extensiones personalizadas</span><span class="sxs-lookup"><span data-stu-id="717a2-119">Custom extensions</span></span>

<span data-ttu-id="717a2-120">Los administradores pueden crear sus propias extensiones para administrar la experiencia de exclusión voluntaria para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="717a2-120">Administrators can create their own extensions to manage the opt-out experience for users.</span></span> <span data-ttu-id="717a2-121">Para más información, consulte [Llamar a las API de Retail Server](e-commerce-extensibility/call-retail-server-apis.md) y [Extensibilidad de canal en línea](e-commerce-extensibility/overview.md).</span><span class="sxs-lookup"><span data-stu-id="717a2-121">For more information, see [Call Retail Server APIs](e-commerce-extensibility/call-retail-server-apis.md) and [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>
