---
title: Habilitar la detección de tienda según la ubicación
description: Este tema describe cómo activar la detección de tienda basada en ubicación para su sitio de Dynamics 365 Commerce.
author: brianshook
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 71e523cab20281d5db7efff40b5ef4f7293a4765
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799140"
---
# <a name="enable-location-based-store-detection"></a><span data-ttu-id="2fdd7-103">Habilitar la detección de tienda según la ubicación</span><span class="sxs-lookup"><span data-stu-id="2fdd7-103">Enable location-based store detection</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2fdd7-104">Este tema describe cómo activar la detección de tienda basada en ubicación para su sitio de Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2fdd7-104">This topic describes how to turn on location-based store detection for your Dynamics 365 Commerce site.</span></span>

<span data-ttu-id="2fdd7-105">La detección de tienda basada en ubicación le permite proporcionar el contenido del sitio relevante a los clientes, en función de su ubicación.</span><span class="sxs-lookup"><span data-stu-id="2fdd7-105">Location-based store detection in Commerce lets you provide relevant site content to customers, based on their location.</span></span> <span data-ttu-id="2fdd7-106">Cuando se activa la detección de tienda basada en tienda, el servicio de representación de Commerce utiliza información de país o región de la dirección IP del explorador web del cliente para dirigir al cliente a la mejor configuración de sitio geográfico que esté disponible.</span><span class="sxs-lookup"><span data-stu-id="2fdd7-106">When location-based store detection is turned on, the Commerce rendering service uses the country/region information from the IP address of the customer's web browser to direct the customer to the best geographical site configuration that is available.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="2fdd7-107">Aviso de privacidad</span><span class="sxs-lookup"><span data-stu-id="2fdd7-107">Privacy notice</span></span>

<span data-ttu-id="2fdd7-108">Si activa la función de detección de tienda basada en ubicación, la información del explorador del cliente se envía un servicio de ubicación de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2fdd7-108">If you turn on the location-based store detection feature, information from the customer's browser is sent to a Microsoft location service.</span></span> <span data-ttu-id="2fdd7-109">Esta información se usa a continuación para proporcionar contenido del cliente que sea relevante para su ubicación.</span><span class="sxs-lookup"><span data-stu-id="2fdd7-109">This information is then used to provide the customer content that is relevant to his or her location.</span></span> <span data-ttu-id="2fdd7-110">Tanto la información que se envía desde el explorador del cliente como la información basada en la ubicación que se devuelve al cliente están sujetas a directivas de cumplimiento de cookies y privacidad.</span><span class="sxs-lookup"><span data-stu-id="2fdd7-110">Both the information that is sent from the customer's browser and the location-based information that is returned to the customer are subject to privacy and cookie compliance policies.</span></span>

## <a name="turn-on-location-based-store-detection"></a><span data-ttu-id="2fdd7-111">Activar la detección de tienda según la ubicación</span><span class="sxs-lookup"><span data-stu-id="2fdd7-111">Turn on location-based store detection</span></span>

<span data-ttu-id="2fdd7-112">Para activar la detección de tienda según la ubicación en Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2fdd7-112">To turn on location-based store detection in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="2fdd7-113">En la herramienta de creación, vaya al sitio.</span><span class="sxs-lookup"><span data-stu-id="2fdd7-113">In the authoring tool, go to your site.</span></span>
1. <span data-ttu-id="2fdd7-114">En el panel de navegación de la izquierda, seleccione **Administración de sitios**.</span><span class="sxs-lookup"><span data-stu-id="2fdd7-114">In the navigation pane on the left, select **Site Management**.</span></span>
1. <span data-ttu-id="2fdd7-115">Seleccione **Valores de configuración de sitio**.</span><span class="sxs-lookup"><span data-stu-id="2fdd7-115">Select **Site Settings**.</span></span>
1. <span data-ttu-id="2fdd7-116">Establezca la opción **Habilitar la detección de tienda según la ubicación** en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="2fdd7-116">Set the **Enable location based store detection** option to **On**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2fdd7-117">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="2fdd7-117">Additional resources</span></span>

[<span data-ttu-id="2fdd7-118">Configurar su nombre de dominio</span><span class="sxs-lookup"><span data-stu-id="2fdd7-118">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="2fdd7-119">Implementar un inquilino nuevo de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="2fdd7-119">Deploy a new e-commerce tenant</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="2fdd7-120">Crear un sitio de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="2fdd7-120">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="2fdd7-121">Asociar un sitio de Dynamics 365 Commerce con un canal en línea</span><span class="sxs-lookup"><span data-stu-id="2fdd7-121">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="2fdd7-122">Administrar archivos robots.txt</span><span class="sxs-lookup"><span data-stu-id="2fdd7-122">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="2fdd7-123">Subir redireccionamientos de URL en grandes cantidades</span><span class="sxs-lookup"><span data-stu-id="2fdd7-123">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="2fdd7-124">Configurar un inquilino B2C en Commerce</span><span class="sxs-lookup"><span data-stu-id="2fdd7-124">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="2fdd7-125">Configurar páginas personalizadas para inicios de sesión de usuario</span><span class="sxs-lookup"><span data-stu-id="2fdd7-125">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="2fdd7-126">Configurar múltiples inquilinos B2C en un entorno de Commerce</span><span class="sxs-lookup"><span data-stu-id="2fdd7-126">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="2fdd7-127">Agregar soporte para una red de entrega de contenido (CDN)</span><span class="sxs-lookup"><span data-stu-id="2fdd7-127">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
