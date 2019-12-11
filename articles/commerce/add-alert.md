---
title: Módulo de alerta
description: En este tema se tratan los módulos de alerta y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 82138dd7f0934f732215f67a3726638eb87075d4
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785361"
---
# <a name="alert-module"></a><span data-ttu-id="148fd-103">Módulo de alerta</span><span class="sxs-lookup"><span data-stu-id="148fd-103">Alert module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="148fd-104">En este tema se tratan los módulos de alerta y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="148fd-104">This topic covers alert modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="148fd-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="148fd-105">Overview</span></span>

<span data-ttu-id="148fd-106">Un módulo de alerta se usa para mostrar mensajes informativos en línea en una página.</span><span class="sxs-lookup"><span data-stu-id="148fd-106">An alert module is used to show inline informational messages on a page.</span></span> <span data-ttu-id="148fd-107">Los módulos alertas admiten un mensaje de texto y un vínculo.</span><span class="sxs-lookup"><span data-stu-id="148fd-107">Alert modules support a text message and a link.</span></span> <span data-ttu-id="148fd-108">Se pueden utilizar para mostrar las promociones en todo el sitio que aparecen en todas las páginas de un sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="148fd-108">They can be used to show site-wide promotions that appear on all pages of an e-Commerce site.</span></span> 

<span data-ttu-id="148fd-109">Los módulos de alerta se controlan por datos desde el sistema de gestión de contenidos (CMS) y se pueden colocar en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="148fd-109">Alert modules are driven by data from the content management system (CMS) and can be put on any page.</span></span>

## <a name="examples-of-alert-modules-in-e-commerce"></a><span data-ttu-id="148fd-110">Ejemplos de módulos de alerta en comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="148fd-110">Examples of alert modules in e-Commerce</span></span>

<span data-ttu-id="148fd-111">Los módulos de alerta se pueden usar en el encabezado del sitio para indicar promociones o mensajes en todo el sitio.</span><span class="sxs-lookup"><span data-stu-id="148fd-111">Alert modules can be used in the site header to indicate site-wide promotions or messages.</span></span> <span data-ttu-id="148fd-112">A continuación se incluyen algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="148fd-112">Here are some examples:</span></span>

<span data-ttu-id="148fd-113">“La venta anual finaliza en 10 días”</span><span class="sxs-lookup"><span data-stu-id="148fd-113">"Annual sale ends in 10 days"</span></span>

<span data-ttu-id="148fd-114">“Ahorre a lo grande con la oferta de la vuelta al cole.</span><span class="sxs-lookup"><span data-stu-id="148fd-114">"Save big with back to school sale.</span></span> <span data-ttu-id="148fd-115">Compre ahora."</span><span class="sxs-lookup"><span data-stu-id="148fd-115">Shop Now."</span></span>

## <a name="alert-module-properties"></a><span data-ttu-id="148fd-116">Propiedades del módulo de alerta</span><span class="sxs-lookup"><span data-stu-id="148fd-116">Alert module properties</span></span>

| <span data-ttu-id="148fd-117">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="148fd-117">Property name</span></span>  | <span data-ttu-id="148fd-118">Valor</span><span class="sxs-lookup"><span data-stu-id="148fd-118">Value</span></span>                              | <span data-ttu-id="148fd-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="148fd-119">Description</span></span> |
|----------------|------------------------------------|-------------|
| <span data-ttu-id="148fd-120">Texto</span><span class="sxs-lookup"><span data-stu-id="148fd-120">Text</span></span>           | <span data-ttu-id="148fd-121">Texto</span><span class="sxs-lookup"><span data-stu-id="148fd-121">Text</span></span>                               | <span data-ttu-id="148fd-122">El mensaje de texto que aparece en el módulo de alerta.</span><span class="sxs-lookup"><span data-stu-id="148fd-122">The text message that appears in the alert module.</span></span> |
| <span data-ttu-id="148fd-123">Alineación de texto</span><span class="sxs-lookup"><span data-stu-id="148fd-123">Text alignment</span></span> | <span data-ttu-id="148fd-124">**Derecha**, **Izquierda** o **Centro**</span><span class="sxs-lookup"><span data-stu-id="148fd-124">**Right**, **Left**, or **Center**</span></span> | <span data-ttu-id="148fd-125">Valor que define la manera en que el texto se alinea en el módulo de alerta.</span><span class="sxs-lookup"><span data-stu-id="148fd-125">A value that defines how text is aligned in the alert module.</span></span> |
| <span data-ttu-id="148fd-126">Descartar alerta</span><span class="sxs-lookup"><span data-stu-id="148fd-126">Dismiss alert</span></span>  | <span data-ttu-id="148fd-127">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="148fd-127">**True** or **False**</span></span>              | <span data-ttu-id="148fd-128">Si el valor se establece en **Verdadero**, el cliente puede descartar la alerta.</span><span class="sxs-lookup"><span data-stu-id="148fd-128">If the value is set to **True**, the customer can dismiss the alert.</span></span> |
| <span data-ttu-id="148fd-129">Vincular</span><span class="sxs-lookup"><span data-stu-id="148fd-129">Link</span></span>           | <span data-ttu-id="148fd-130">URL</span><span class="sxs-lookup"><span data-stu-id="148fd-130">URL</span></span>                                | <span data-ttu-id="148fd-131">La dirección URL para un vínculo opcional.</span><span class="sxs-lookup"><span data-stu-id="148fd-131">The URL for an optional link.</span></span> |

## <a name="add-an-alert-module-to-a-page"></a><span data-ttu-id="148fd-132">Agregar un módulo de alerta a una página</span><span class="sxs-lookup"><span data-stu-id="148fd-132">Add an alert module to a page</span></span> 

<span data-ttu-id="148fd-133">Para agregar un módulo de alerta a una página y establecer las propiedades necesarias, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="148fd-133">To add an alert module to a page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="148fd-134">Cree una plantilla de página con el nombre **plantilla de alerta**.</span><span class="sxs-lookup"><span data-stu-id="148fd-134">Create a page template that is named **alert template**.</span></span>
1. <span data-ttu-id="148fd-135">En el espacio **Principal** de la página predeterminada, agregue un módulo de alerta.</span><span class="sxs-lookup"><span data-stu-id="148fd-135">In the **Main** slot of the default page, add an alert module.</span></span>
1. <span data-ttu-id="148fd-136">Proteja la plantilla y publíquela.</span><span class="sxs-lookup"><span data-stu-id="148fd-136">Check in the template, and publish it.</span></span> 
1. <span data-ttu-id="148fd-137">Use la plantilla de alerta que acaba de crear para crear una página que se llame **página de alerta**.</span><span class="sxs-lookup"><span data-stu-id="148fd-137">Use the alert template that you just created to create a page that is named **alert page**.</span></span> 
1. <span data-ttu-id="148fd-138">En el espacio **Principal** de la página nueva, agregue un módulo de alerta.</span><span class="sxs-lookup"><span data-stu-id="148fd-138">In the **Main** slot of the new page, add an alert module.</span></span>
1. <span data-ttu-id="148fd-139">En la configuración para el módulo de alerta, escriba el texto de la alerta.</span><span class="sxs-lookup"><span data-stu-id="148fd-139">In the settings for the alert module, enter the alert text.</span></span> <span data-ttu-id="148fd-140">Puede editar las otras propiedades si desea personalizar más el módulo de alerta.</span><span class="sxs-lookup"><span data-stu-id="148fd-140">You can edit the other properties if you want to customize the alert module further.</span></span>
1. <span data-ttu-id="148fd-141">Guarde la página y obtenga una vista previa de ella.</span><span class="sxs-lookup"><span data-stu-id="148fd-141">Save and preview the page.</span></span> <span data-ttu-id="148fd-142">En la parte superior de la página, debe ver una alerta que tenga el texto que ha agregado.</span><span class="sxs-lookup"><span data-stu-id="148fd-142">At the top of the page, you should see an alert that has the text that you added.</span></span>
1. <span data-ttu-id="148fd-143">Proteja la página y publíquela.</span><span class="sxs-lookup"><span data-stu-id="148fd-143">Check in the page, and publish it.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="148fd-144">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="148fd-144">Additional resources</span></span>

[<span data-ttu-id="148fd-145">Visión general de kit de inicio</span><span class="sxs-lookup"><span data-stu-id="148fd-145">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="148fd-146">Módulo de carrusel</span><span class="sxs-lookup"><span data-stu-id="148fd-146">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="148fd-147">Módulo de bloque de enriquecimiento de contenido</span><span class="sxs-lookup"><span data-stu-id="148fd-147">Content rich block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="148fd-148">Módulo de sustitución de contenido</span><span class="sxs-lookup"><span data-stu-id="148fd-148">Content placement module</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="148fd-149">Módulo de característica</span><span class="sxs-lookup"><span data-stu-id="148fd-149">Feature module</span></span>](add-feature-module.md)

[<span data-ttu-id="148fd-150">Módulo de elemento principal</span><span class="sxs-lookup"><span data-stu-id="148fd-150">Hero module</span></span>](add-hero-module.md)

[<span data-ttu-id="148fd-151">Módulo de reproductor de vídeo</span><span class="sxs-lookup"><span data-stu-id="148fd-151">Video player module</span></span>](add-video-player.md)
