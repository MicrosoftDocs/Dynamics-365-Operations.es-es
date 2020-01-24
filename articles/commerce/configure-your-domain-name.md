---
title: Configurar su nombre de dominio
description: Este tema explica cómo configurar un nombre de dominio para un sitio de comercio electrónico de Microsoft Dynamics 365.
author: psimolin
manager: AnnBe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8f73c034563fb1cc6b05091b4c47e2a788d1a8b6
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945545"
---
# <a name="configure-your-domain-name"></a><span data-ttu-id="32bd4-103">Configurar su nombre de dominio</span><span class="sxs-lookup"><span data-stu-id="32bd4-103">Configure your domain name</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="32bd4-104">Este tema explica cómo configurar un nombre de dominio para un sitio de comercio electrónico de Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="32bd4-104">This topic explains how to configure a domain name for a Microsoft Dynamics 365 e-commerce site.</span></span> 

## <a name="add-domains-during-e-commerce-initialization"></a><span data-ttu-id="32bd4-105">Agregar dominios durante la inicialización de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="32bd4-105">Add domains during e-Commerce initialization</span></span>

<span data-ttu-id="32bd4-106">Para asociar dominios con su entorno de comercio electrónico, inicialice el comercio electrónico como se describe en [Implementar un sitio nuevo de comercio electrónico](deploy-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="32bd4-106">To associate domains with your e-commerce environment, initialize e-Commerce as described in [Deploy a new e-Commerce site](deploy-ecommerce-site.md).</span></span> <span data-ttu-id="32bd4-107">Durante la inicialización, se le pide proporcionar información que se usará para aprovisionar su entorno de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="32bd4-107">During initialization, you're asked to provide information that will be used to provision your e-Commerce environment.</span></span> <span data-ttu-id="32bd4-108">En el campo **Nombres de hosts admitidos**, agregue todos los dominios que planea usar con este entorno.</span><span class="sxs-lookup"><span data-stu-id="32bd4-108">In the **Supported host names** field, add all the domains that you plan to use with this environment.</span></span> <span data-ttu-id="32bd4-109">Se deben separar varios dominios con punto y coma.</span><span class="sxs-lookup"><span data-stu-id="32bd4-109">Multiple domains should be separated with semi-colon.</span></span> <span data-ttu-id="32bd4-110">De esta manera, los dominios se configuran en todos los componentes requeridos de comercio electrónico y están listos para usarse al cambiar el tráfico desde su red de entrega de contenido (CDN) o servidor web y lo apunta a los front-ends de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="32bd4-110">In this way, the domains are configured in all the required e-Commerce components, and they are ready to be used when you switch traffic from your content delivery network (CDN) or web server and point it to the e-Commerce front ends.</span></span>

## <a name="add-domains-after-e-commerce-initialization"></a><span data-ttu-id="32bd4-111">Agregar dominios después de la inicialización de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="32bd4-111">Add domains after e-Commerce initialization</span></span>

<span data-ttu-id="32bd4-112">Para asociar dominios nuevos con su entorno de comercio electrónico después de la inicialización de comercio electrónico, debe enviar una solicitud de servicio.</span><span class="sxs-lookup"><span data-stu-id="32bd4-112">To associate new domains with your e-Commerce environment after e-Commerce initialization, you must submit a service request.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="32bd4-113">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="32bd4-113">Additional resources</span></span>

[<span data-ttu-id="32bd4-114">Implementar un sitio nuevo de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="32bd4-114">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="32bd4-115">Crear un sitio de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="32bd4-115">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="32bd4-116">Asociar un sitio en línea con un canal</span><span class="sxs-lookup"><span data-stu-id="32bd4-116">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="32bd4-117">Administrar archivos robots.txt</span><span class="sxs-lookup"><span data-stu-id="32bd4-117">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="32bd4-118">Configurar páginas personalizadas para inicios de sesión de usuario</span><span class="sxs-lookup"><span data-stu-id="32bd4-118">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="32bd4-119">Agregar soporte para una red de entrega de contenido (CDN)</span><span class="sxs-lookup"><span data-stu-id="32bd4-119">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="32bd4-120">Habilitar la detección de tienda según la ubicación</span><span class="sxs-lookup"><span data-stu-id="32bd4-120">Enable location-based store detection</span></span>](enable-store-detection.md)
