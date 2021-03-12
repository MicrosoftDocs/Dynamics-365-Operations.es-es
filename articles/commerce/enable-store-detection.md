---
title: Habilitar la detección de tienda según la ubicación
description: Este tema describe cómo activar la detección de tienda basada en ubicación para su sitio de Dynamics 365 Commerce.
author: brianshook
manager: annbe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3f7e9a3acde508f405ce85f125db552c3ae3656b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000737"
---
# <a name="enable-location-based-store-detection"></a><span data-ttu-id="b4718-103">Habilitar la detección de tienda según la ubicación</span><span class="sxs-lookup"><span data-stu-id="b4718-103">Enable location-based store detection</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="b4718-104">Este tema describe cómo activar la detección de tienda basada en ubicación para su sitio de Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b4718-104">This topic describes how to turn on location-based store detection for your Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="b4718-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="b4718-105">Overview</span></span>

<span data-ttu-id="b4718-106">La detección de tienda basada en ubicación le permite proporcionar el contenido del sitio relevante a los clientes, en función de su ubicación.</span><span class="sxs-lookup"><span data-stu-id="b4718-106">Location-based store detection in Commerce lets you provide relevant site content to customers, based on their location.</span></span> <span data-ttu-id="b4718-107">Cuando se activa la detección de tienda basada en tienda, el servicio de representación de Commerce utiliza información de país o región de la dirección IP del explorador web del cliente para dirigir al cliente a la mejor configuración de sitio geográfico que esté disponible.</span><span class="sxs-lookup"><span data-stu-id="b4718-107">When location-based store detection is turned on, the Commerce rendering service uses the country/region information from the IP address of the customer's web browser to direct the customer to the best geographical site configuration that is available.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="b4718-108">Aviso de privacidad</span><span class="sxs-lookup"><span data-stu-id="b4718-108">Privacy notice</span></span>

<span data-ttu-id="b4718-109">Si activa la función de detección de tienda basada en ubicación, la información del explorador del cliente se envía un servicio de ubicación de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b4718-109">If you turn on the location-based store detection feature, information from the customer's browser is sent to a Microsoft location service.</span></span> <span data-ttu-id="b4718-110">Esta información se usa a continuación para proporcionar contenido del cliente que sea relevante para su ubicación.</span><span class="sxs-lookup"><span data-stu-id="b4718-110">This information is then used to provide the customer content that is relevant to his or her location.</span></span> <span data-ttu-id="b4718-111">Tanto la información que se envía desde el explorador del cliente como la información basada en la ubicación que se devuelve al cliente están sujetas a directivas de cumplimiento de cookies y privacidad.</span><span class="sxs-lookup"><span data-stu-id="b4718-111">Both the information that is sent from the customer's browser and the location-based information that is returned to the customer are subject to privacy and cookie compliance policies.</span></span>

## <a name="turn-on-location-based-store-detection"></a><span data-ttu-id="b4718-112">Activar la detección de tienda según la ubicación</span><span class="sxs-lookup"><span data-stu-id="b4718-112">Turn on location-based store detection</span></span>

<span data-ttu-id="b4718-113">Para activar la detección de tienda según la ubicación en Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="b4718-113">To turn on location-based store detection in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="b4718-114">En la herramienta de creación, vaya al sitio.</span><span class="sxs-lookup"><span data-stu-id="b4718-114">In the authoring tool, go to your site.</span></span>
1. <span data-ttu-id="b4718-115">En el panel de navegación de la izquierda, seleccione **Administración de sitios**.</span><span class="sxs-lookup"><span data-stu-id="b4718-115">In the navigation pane on the left, select **Site Management**.</span></span>
1. <span data-ttu-id="b4718-116">Seleccione **Valores de configuración de sitio**.</span><span class="sxs-lookup"><span data-stu-id="b4718-116">Select **Site Settings**.</span></span>
1. <span data-ttu-id="b4718-117">Establezca la opción **Habilitar la detección de tienda según la ubicación** en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="b4718-117">Set the **Enable location based store detection** option to **On**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b4718-118">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="b4718-118">Additional resources</span></span>

[<span data-ttu-id="b4718-119">Configurar su nombre de dominio</span><span class="sxs-lookup"><span data-stu-id="b4718-119">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="b4718-120">Implementar un inquilino nuevo de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="b4718-120">Deploy a new e-commerce tenant</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="b4718-121">Crear un sitio de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="b4718-121">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="b4718-122">Asociar un sitio de Dynamics 365 Commerce con un canal en línea</span><span class="sxs-lookup"><span data-stu-id="b4718-122">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="b4718-123">Administrar archivos robots.txt</span><span class="sxs-lookup"><span data-stu-id="b4718-123">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="b4718-124">Subir redireccionamientos de URL en grandes cantidades</span><span class="sxs-lookup"><span data-stu-id="b4718-124">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="b4718-125">Configurar un inquilino B2C en Commerce</span><span class="sxs-lookup"><span data-stu-id="b4718-125">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="b4718-126">Configurar páginas personalizadas para inicios de sesión de usuario</span><span class="sxs-lookup"><span data-stu-id="b4718-126">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="b4718-127">Configurar múltiples inquilinos B2C en un entorno de Commerce</span><span class="sxs-lookup"><span data-stu-id="b4718-127">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="b4718-128">Agregar soporte para una red de entrega de contenido (CDN)</span><span class="sxs-lookup"><span data-stu-id="b4718-128">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)
