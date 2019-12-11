---
title: Habilitar la detección de tienda según la ubicación
description: Este tema describe cómo activar la detección de tienda basada en ubicación para su sitio de Dynamics 365 Commerce.
author: brianshook
manager: annbe
ms.date: 10/01/2019
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
ms.openlocfilehash: a542d6987280451910b4ff3bcfb3a109a0e028c6
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697621"
---
# <a name="enable-location-based-store-detection"></a><span data-ttu-id="ff66c-103">Habilitar la detección de tienda según la ubicación</span><span class="sxs-lookup"><span data-stu-id="ff66c-103">Enable location-based store detection</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="ff66c-104">Este tema describe cómo activar la detección de tienda basada en ubicación para su sitio de Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ff66c-104">This topic describes how to turn on location-based store detection for your Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="ff66c-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="ff66c-105">Overview</span></span>

<span data-ttu-id="ff66c-106">La detección de tienda basada en ubicación le permite proporcionar el contenido del sitio relevante a los clientes, en función de su ubicación.</span><span class="sxs-lookup"><span data-stu-id="ff66c-106">Location-based store detection in Commerce lets you provide relevant site content to customers, based on their location.</span></span> <span data-ttu-id="ff66c-107">Cuando se activa la detección de tienda basada en tienda, el servicio de representación de Commerce utiliza información de país o región de la dirección IP del explorador web del cliente para dirigir al cliente a la mejor configuración de sitio geográfico que esté disponible.</span><span class="sxs-lookup"><span data-stu-id="ff66c-107">When location-based store detection is turned on, the Commerce rendering service uses the country/region information from the IP address of the customer's web browser to direct the customer to the best geographical site configuration that is available.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="ff66c-108">Aviso de privacidad</span><span class="sxs-lookup"><span data-stu-id="ff66c-108">Privacy notice</span></span>

<span data-ttu-id="ff66c-109">Si activa la función de detección de tienda basada en ubicación, la información del explorador del cliente se envía un servicio de ubicación de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ff66c-109">If you turn on the location-based store detection feature, information from the customer's browser is sent to a Microsoft location service.</span></span> <span data-ttu-id="ff66c-110">Esta información se usa a continuación para proporcionar contenido del cliente que sea relevante para su ubicación.</span><span class="sxs-lookup"><span data-stu-id="ff66c-110">This information is then used to provide the customer content that is relevant to his or her location.</span></span> <span data-ttu-id="ff66c-111">Tanto la información que se envía desde el explorador del cliente como la información basada en la ubicación que se devuelve al cliente están sujetas a directivas de cumplimiento de cookies y privacidad.</span><span class="sxs-lookup"><span data-stu-id="ff66c-111">Both the information that is sent from the customer's browser and the location-based information that is returned to the customer are subject to privacy and cookie compliance policies.</span></span>

## <a name="turn-on-location-based-store-detection"></a><span data-ttu-id="ff66c-112">Activar la detección de tienda según la ubicación</span><span class="sxs-lookup"><span data-stu-id="ff66c-112">Turn on location-based store detection</span></span>

<span data-ttu-id="ff66c-113">Para activar la detección de tienda según la ubicación en Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ff66c-113">To turn on location-based store detection in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="ff66c-114">En la herramienta de creación, vaya al sitio.</span><span class="sxs-lookup"><span data-stu-id="ff66c-114">In the authoring tool, go to your site.</span></span>
1. <span data-ttu-id="ff66c-115">En el panel de navegación de la izquierda, seleccione **Administración de sitios**.</span><span class="sxs-lookup"><span data-stu-id="ff66c-115">In the navigation pane on the left, select **Site Management**.</span></span>
1. <span data-ttu-id="ff66c-116">Seleccione **Valores de configuración de sitio**.</span><span class="sxs-lookup"><span data-stu-id="ff66c-116">Select **Site Settings**.</span></span>
1. <span data-ttu-id="ff66c-117">Establezca la opción **Habilitar la detección de tienda según la ubicación** en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="ff66c-117">Set the **Enable location based store detection** option to **On**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ff66c-118">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="ff66c-118">Additional resources</span></span>

[<span data-ttu-id="ff66c-119">Visión general de la tienda en línea</span><span class="sxs-lookup"><span data-stu-id="ff66c-119">Online store overview</span></span>](online-store-overview.md)

[<span data-ttu-id="ff66c-120">Crear un sitio de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="ff66c-120">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="ff66c-121">Implementar un sitio nuevo de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="ff66c-121">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="ff66c-122">Asociar un sitio en línea con un canal</span><span class="sxs-lookup"><span data-stu-id="ff66c-122">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="ff66c-123">Configurar su nombre de dominio</span><span class="sxs-lookup"><span data-stu-id="ff66c-123">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="ff66c-124">Agregar soporte para una red de entrega de contenido (CDN)</span><span class="sxs-lookup"><span data-stu-id="ff66c-124">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="ff66c-125">Configurar páginas personalizadas para inicios de sesión de usuario</span><span class="sxs-lookup"><span data-stu-id="ff66c-125">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)
