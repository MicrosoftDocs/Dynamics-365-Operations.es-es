---
title: Agregar secuencia de comandos a páginas del sitio para admitir telemetría
description: Este tema describe cómo agregar código de script del lado cliente a las páginas del sitio para admitir la colección de telemetría del cliente.
author: bicyclingfool
manager: annbe
ms.date: 12/12/2019
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
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 79d0e11946f3c6f4704d3a726d33de0378eb53bd
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914548"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a><span data-ttu-id="1dc8a-103">Agregar secuencia de comandos a páginas del sitio para admitir telemetría</span><span class="sxs-lookup"><span data-stu-id="1dc8a-103">Add script code to site pages to support telemetry</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="1dc8a-104">Este tema describe cómo agregar código de script del lado cliente a las páginas del sitio para admitir la colección de telemetría del cliente.</span><span class="sxs-lookup"><span data-stu-id="1dc8a-104">This topic describes how to add client-side script code to your site pages to support the collection of client-side telemetry.</span></span>

## <a name="overview"></a><span data-ttu-id="1dc8a-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="1dc8a-105">Overview</span></span>

<span data-ttu-id="1dc8a-106">Los análisis web son una herramienta esencial cuando desea comprender de qué manera interactúan los clientes con el sitio y toman decisiones que ayudarán a optimizar la experiencia para la conversión máxima.</span><span class="sxs-lookup"><span data-stu-id="1dc8a-106">Web analytics are an essential tool when you want to understand how your customers interact with your site and make decisions that will help optimize the experience for maximum conversion.</span></span> <span data-ttu-id="1dc8a-107">Muchos paquetes de análisis web están disponibles para ayudarle a alcanzar estos objetivos, como Google Analytics, Clicky, Moz Analytics y KISSMetrics.</span><span class="sxs-lookup"><span data-stu-id="1dc8a-107">Many web analytics packages are available to help you achieve these goals, such as Google Analytics, Clicky, Moz Analytics, and KISSMetrics.</span></span> <span data-ttu-id="1dc8a-108">La mayoría de los paquetes de análisis web requieren que agregue código de script del lado cliente en el elemento **\<head\>** del HTML para todas las páginas del sitio.</span><span class="sxs-lookup"><span data-stu-id="1dc8a-108">Most web analytics packages require that you add client-side script code in the **\<head\>** element of the HTML for all pages of your site.</span></span>

> [!NOTE]
> <span data-ttu-id="1dc8a-109">Las directrices de este tema también se aplican a otra funcionalidad del lado cliente personalizada que Microsoft Dynamics 365 Commerce no ofrece de manera nativa.</span><span class="sxs-lookup"><span data-stu-id="1dc8a-109">The instructions in this topic also apply to other custom client-side functionality that Microsoft Dynamics 365 Commerce doesn't natively offer.</span></span>

## <a name="create-a-reusable-fragment-for-your-script-code"></a><span data-ttu-id="1dc8a-110">Crear un fragmento reutilizable para su código de script</span><span class="sxs-lookup"><span data-stu-id="1dc8a-110">Create a reusable fragment for your script code</span></span>

<span data-ttu-id="1dc8a-111">Después de crear un fragmento para su código de script, se puede reutilizar en todas las páginas de su sitio.</span><span class="sxs-lookup"><span data-stu-id="1dc8a-111">After you create a fragment for your script code, it can be reused across all pages on your site.</span></span>

1. <span data-ttu-id="1dc8a-112">Vaya a **Fragmentos \> Nuevo fragmento de página**.</span><span class="sxs-lookup"><span data-stu-id="1dc8a-112">Go to **Fragments \> New page fragment**.</span></span>
2. <span data-ttu-id="1dc8a-113">Seleccione **Script externo**, especifique un nombre para el fragmento y, a continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1dc8a-113">Select **External Script**, enter a name for the fragment, and then select **OK**.</span></span>
3. <span data-ttu-id="1dc8a-114">En la jerarquía del fragmento, seleccione el elemento secundario del módulo **inyector de script** del fragmento que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="1dc8a-114">In the fragment hierarchy, select the **script injector** module child of the fragment that you just created.</span></span>
4. <span data-ttu-id="1dc8a-115">En el panel de propiedades de la derecha, agregue su script del lado cliente y establezca otras opciones de configuración según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="1dc8a-115">In the property pane on the right, add your client-side script, and set other configuration options as you require.</span></span>

## <a name="add-the-fragment-to-templates"></a><span data-ttu-id="1dc8a-116">Agregar el fragmento a plantillas</span><span class="sxs-lookup"><span data-stu-id="1dc8a-116">Add the fragment to templates</span></span>

1. <span data-ttu-id="1dc8a-117">Vaya a **Plantillas** y abra la plantilla para las páginas en las que desea agregar el código de script.</span><span class="sxs-lookup"><span data-stu-id="1dc8a-117">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
2. <span data-ttu-id="1dc8a-118">En el panel izquierdo, expanda la jerarquía de la plantilla para mostrar la franja **Encabezado HTML**.</span><span class="sxs-lookup"><span data-stu-id="1dc8a-118">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
3. <span data-ttu-id="1dc8a-119">Seleccione el botón de puntos suspensivos (**...**) para la franja **Encabezado HTML** y, a continuación, seleccione **Agregar fragmento**.</span><span class="sxs-lookup"><span data-stu-id="1dc8a-119">Select the ellipsis button (**...**) for the **HTML Head** slot, and then select **Add fragment**.</span></span>
4. <span data-ttu-id="1dc8a-120">Seleccione el fragmento que ha creado para su código de script.</span><span class="sxs-lookup"><span data-stu-id="1dc8a-120">Select the fragment that you created for your script code.</span></span>
5. <span data-ttu-id="1dc8a-121">Guarde la plantilla y protéjala.</span><span class="sxs-lookup"><span data-stu-id="1dc8a-121">Save the template, and check it in.</span></span>

> [!NOTE]
> <span data-ttu-id="1dc8a-122">Una vez que haya terminado, debe publicar el fragmento y la plantilla maestra.</span><span class="sxs-lookup"><span data-stu-id="1dc8a-122">After you've finished, you must publish the fragment and the master template.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="1dc8a-123">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="1dc8a-123">Additional resources</span></span>

[<span data-ttu-id="1dc8a-124">Agregar un logotipo</span><span class="sxs-lookup"><span data-stu-id="1dc8a-124">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="1dc8a-125">Seleccionar un tema de sitio</span><span class="sxs-lookup"><span data-stu-id="1dc8a-125">Select a site theme</span></span>](select-site-theme.md)

<span data-ttu-id="1dc8a-126">[Trabajar con archivos de invalidaciones CSS](css-override-files.md) </span><span class="sxs-lookup"><span data-stu-id="1dc8a-126">[Work with CSS override files](css-override-files.md)</span></span>

[<span data-ttu-id="1dc8a-127">Agregar un icono de favoritos</span><span class="sxs-lookup"><span data-stu-id="1dc8a-127">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="1dc8a-128">Agregar un mensaje de bienvenida</span><span class="sxs-lookup"><span data-stu-id="1dc8a-128">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="1dc8a-129">Agregar un aviso de derechos de autor</span><span class="sxs-lookup"><span data-stu-id="1dc8a-129">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="1dc8a-130">Agregar idiomas al sitio</span><span class="sxs-lookup"><span data-stu-id="1dc8a-130">Add languages to your site</span></span>](add-languages-to-site.md)

