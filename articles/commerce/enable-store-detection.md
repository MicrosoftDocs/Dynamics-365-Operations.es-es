---
title: Habilitar la detección de tienda según la ubicación
description: Este tema describe cómo activar la detección de tienda basada en ubicación para su sitio de Dynamics 365 Commerce.
author: brianshook
manager: annbe
ms.date: 03/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 66ffe56f9d969c9d62ed4ff49f0848fab7e58a56
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/03/2020
ms.locfileid: "3096878"
---
# <a name="enable-location-based-store-detection"></a><span data-ttu-id="62097-103">Habilitar la detección de tienda según la ubicación</span><span class="sxs-lookup"><span data-stu-id="62097-103">Enable location-based store detection</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="62097-104">Este tema describe cómo activar la detección de tienda basada en ubicación para su sitio de Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="62097-104">This topic describes how to turn on location-based store detection for your Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="62097-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="62097-105">Overview</span></span>

<span data-ttu-id="62097-106">La detección de tienda basada en ubicación le permite proporcionar el contenido del sitio relevante a los clientes, en función de su ubicación.</span><span class="sxs-lookup"><span data-stu-id="62097-106">Location-based store detection in Commerce lets you provide relevant site content to customers, based on their location.</span></span> <span data-ttu-id="62097-107">Cuando se activa la detección de tienda basada en tienda, el servicio de representación de Commerce utiliza información de país o región de la dirección IP del explorador web del cliente para dirigir al cliente a la mejor configuración de sitio geográfico que esté disponible.</span><span class="sxs-lookup"><span data-stu-id="62097-107">When location-based store detection is turned on, the Commerce rendering service uses the country/region information from the IP address of the customer's web browser to direct the customer to the best geographical site configuration that is available.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="62097-108">Aviso de privacidad</span><span class="sxs-lookup"><span data-stu-id="62097-108">Privacy notice</span></span>

<span data-ttu-id="62097-109">Si activa la función de detección de tienda basada en ubicación, la información del explorador del cliente se envía un servicio de ubicación de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="62097-109">If you turn on the location-based store detection feature, information from the customer's browser is sent to a Microsoft location service.</span></span> <span data-ttu-id="62097-110">Esta información se usa a continuación para proporcionar contenido del cliente que sea relevante para su ubicación.</span><span class="sxs-lookup"><span data-stu-id="62097-110">This information is then used to provide the customer content that is relevant to his or her location.</span></span> <span data-ttu-id="62097-111">Tanto la información que se envía desde el explorador del cliente como la información basada en la ubicación que se devuelve al cliente están sujetas a directivas de cumplimiento de cookies y privacidad.</span><span class="sxs-lookup"><span data-stu-id="62097-111">Both the information that is sent from the customer's browser and the location-based information that is returned to the customer are subject to privacy and cookie compliance policies.</span></span>

## <a name="turn-on-location-based-store-detection"></a><span data-ttu-id="62097-112">Activar la detección de tienda según la ubicación</span><span class="sxs-lookup"><span data-stu-id="62097-112">Turn on location-based store detection</span></span>

<span data-ttu-id="62097-113">Para activar la detección de tienda según la ubicación en Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="62097-113">To turn on location-based store detection in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="62097-114">En la herramienta de creación, vaya al sitio.</span><span class="sxs-lookup"><span data-stu-id="62097-114">In the authoring tool, go to your site.</span></span>
1. <span data-ttu-id="62097-115">En el panel de navegación de la izquierda, seleccione **Administración de sitios**.</span><span class="sxs-lookup"><span data-stu-id="62097-115">In the navigation pane on the left, select **Site Management**.</span></span>
1. <span data-ttu-id="62097-116">Seleccione **Valores de configuración de sitio**.</span><span class="sxs-lookup"><span data-stu-id="62097-116">Select **Site Settings**.</span></span>
1. <span data-ttu-id="62097-117">Establezca la opción **Habilitar la detección de tienda según la ubicación** en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="62097-117">Set the **Enable location based store detection** option to **On**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="62097-118">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="62097-118">Additional resources</span></span>

[<span data-ttu-id="62097-119">Configurar su nombre de dominio</span><span class="sxs-lookup"><span data-stu-id="62097-119">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="62097-120">Implementar un sitio nuevo de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="62097-120">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="62097-121">Configurar un canal de la tienda en línea</span><span class="sxs-lookup"><span data-stu-id="62097-121">Set up an online store channel</span></span>](online-stores.md)

[<span data-ttu-id="62097-122">Crear un sitio de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="62097-122">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="62097-123">Asociar un sitio en línea con un canal</span><span class="sxs-lookup"><span data-stu-id="62097-123">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="62097-124">Administrar archivos robots.txt</span><span class="sxs-lookup"><span data-stu-id="62097-124">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="62097-125">Subir redireccionamientos de URL en grandes cantidades</span><span class="sxs-lookup"><span data-stu-id="62097-125">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="62097-126">Configurar un inquilino B2C en Commerce</span><span class="sxs-lookup"><span data-stu-id="62097-126">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="62097-127">Configurar páginas personalizadas para inicios de sesión de usuario</span><span class="sxs-lookup"><span data-stu-id="62097-127">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="62097-128">Configurar múltiples inquilinos B2C en un entorno de Commerce</span><span class="sxs-lookup"><span data-stu-id="62097-128">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="62097-129">Agregar soporte para una red de entrega de contenido (CDN)</span><span class="sxs-lookup"><span data-stu-id="62097-129">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)
