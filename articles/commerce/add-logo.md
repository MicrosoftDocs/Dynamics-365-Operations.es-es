---
title: Agregar un logotipo
description: En este tema se describe cómo agregar un logotipo a su sitio en Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 12/12/2019
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
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 23bac9aae6beb59912bbc9e1f2c6958c007550b0
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914634"
---
# <a name="add-a-logo"></a><span data-ttu-id="5e3de-103">Agregar un logotipo</span><span class="sxs-lookup"><span data-stu-id="5e3de-103">Add a logo</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="5e3de-104">En este tema se describe cómo agregar un logotipo a su sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5e3de-104">This topic describes how to add a logo to your site in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="5e3de-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="5e3de-105">Overview</span></span>

<span data-ttu-id="5e3de-106">Cuando crea su sitio, una de las primeras cosas que probablemente hará es agregar el logotipo de su empresa o marca al encabezado del sitio.</span><span class="sxs-lookup"><span data-stu-id="5e3de-106">When you build your site, one of the first things that you will probably do is add your company or brand logo to the site's header.</span></span> <span data-ttu-id="5e3de-107">El kit de inicio en línea de Dynamics 365 Commerce proporciona un módulo que facilita esta tarea.</span><span class="sxs-lookup"><span data-stu-id="5e3de-107">The Dynamics 365 Commerce online starter kit provides a module that makes this task easy.</span></span>

<span data-ttu-id="5e3de-108">Puede agregar un logotipo directamente a una plantilla, diseño o página.</span><span class="sxs-lookup"><span data-stu-id="5e3de-108">You can add a logo directly to a template, layout, or page.</span></span> <span data-ttu-id="5e3de-109">De esta manera, puede cambiar fácilmente el logotipo que aparece en páginas específicas o grupos de páginas.</span><span class="sxs-lookup"><span data-stu-id="5e3de-109">In this way, you can easily change the logo that appears on specific pages or groups of pages.</span></span> <span data-ttu-id="5e3de-110">Sin embargo, este tema cubre el escenario más frecuente, donde agrega su logotipo a un fragmento de encabezado que puede reutilizarse en todas las páginas de su sitio.</span><span class="sxs-lookup"><span data-stu-id="5e3de-110">However, this topic covers the most frequent scenario, where you add your logo to a header fragment that can be reused across all the pages of your site.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5e3de-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5e3de-111">Prerequisites</span></span>

<span data-ttu-id="5e3de-112">Antes de poder agregar un logotipo a todas las páginas de su sitio, debe completar estas tareas.</span><span class="sxs-lookup"><span data-stu-id="5e3de-112">Before you can add a logo to all the pages of your site, you must complete these tasks.</span></span>

1. <span data-ttu-id="5e3de-113">Suba su logotipo al administrador de activos digitales, al que puede acceder desde la página **Activos**.</span><span class="sxs-lookup"><span data-stu-id="5e3de-113">Upload your logo to the digital assets manager, which you can access from the **Assets** page.</span></span>
1. <span data-ttu-id="5e3de-114">Crear un fragmento de encabezado.</span><span class="sxs-lookup"><span data-stu-id="5e3de-114">Create a header fragment.</span></span> <span data-ttu-id="5e3de-115">Para obtener más información sobre cómo crear y usar fragmentos, vea [Trabajar con fragmentos](work-with-fragments.md).</span><span class="sxs-lookup"><span data-stu-id="5e3de-115">For more information about how to create and use fragments, see [Work with fragments](work-with-fragments.md).</span></span>
1. <span data-ttu-id="5e3de-116">Incluya el fragmento de encabezado en la plantilla que usan las páginas de su sitio para su diseño y opciones de módulo.</span><span class="sxs-lookup"><span data-stu-id="5e3de-116">Include the header fragment in the template that the pages of your site use for their layout and module options.</span></span> <span data-ttu-id="5e3de-117">Para obtener más información sobre las plantillas, vea [Trabajar con plantillas](work-with-templates.md).</span><span class="sxs-lookup"><span data-stu-id="5e3de-117">For more information about templates, see [Work with templates](work-with-templates.md).</span></span>

## <a name="add-a-logo-to-a-header-fragment"></a><span data-ttu-id="5e3de-118">Agregar un logotipo a un fragmento de encabezado</span><span class="sxs-lookup"><span data-stu-id="5e3de-118">Add a logo to a header fragment</span></span>

<span data-ttu-id="5e3de-119">Para agregar un logotipo al fragmento de encabezado de su sitio, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="5e3de-119">To add a logo to the header fragment for your site, follow these steps.</span></span>

1. <span data-ttu-id="5e3de-120">En el panel de navegación a la izquierda, seleccione **Fragmentos** y luego seleccione el fragmento de encabezado que creó.</span><span class="sxs-lookup"><span data-stu-id="5e3de-120">In the navigation pane on the left, select **Fragments**, and then select the header fragment that you created.</span></span>
2. <span data-ttu-id="5e3de-121">Seleccione **Desproteger**.</span><span class="sxs-lookup"><span data-stu-id="5e3de-121">Select **Check out**.</span></span>
3. <span data-ttu-id="5e3de-122">Expanda el espacio **Encabezado** y el espacio **Logotipo**.</span><span class="sxs-lookup"><span data-stu-id="5e3de-122">Expand the **Header** slot and the **Logo** slot.</span></span>
4. <span data-ttu-id="5e3de-123">Seleccione el botón de puntos suspensivos (**...**) para el espacio **Logotipo** y, a continuación, seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="5e3de-123">Select the ellipsis button (**...**) for the **Logo** slot, and then select **Add module**.</span></span>
5. <span data-ttu-id="5e3de-124">Seleccione el módulo de logotipo.</span><span class="sxs-lookup"><span data-stu-id="5e3de-124">Select the logo module.</span></span>
6. <span data-ttu-id="5e3de-125">En el panel de propiedades de la derecha, configure el módulo logotipo para que muestre su logotipo.</span><span class="sxs-lookup"><span data-stu-id="5e3de-125">In the properties pane on the right, configure the logo module so that it shows your logo.</span></span>
7. <span data-ttu-id="5e3de-126">Guarde el fragmento de encabezado, protéjalo y publíquelo.</span><span class="sxs-lookup"><span data-stu-id="5e3de-126">Save the header fragment, check it in, and publish it.</span></span>

<span data-ttu-id="5e3de-127">Después de publicar el fragmento de encabezado actualizado, todas las páginas del sitio que usan la plantilla que contiene el fragmento de encabezado mostrarán su logotipo.</span><span class="sxs-lookup"><span data-stu-id="5e3de-127">After you publish the updated header fragment, all site pages that use the template that contains the header fragment will show your logo.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5e3de-128">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="5e3de-128">Additional resources</span></span>

[<span data-ttu-id="5e3de-129">Seleccionar un tema de sitio</span><span class="sxs-lookup"><span data-stu-id="5e3de-129">Select a site theme</span></span>](select-site-theme.md)

<span data-ttu-id="5e3de-130">[Trabajar con archivos de invalidaciones CSS](css-override-files.md) </span><span class="sxs-lookup"><span data-stu-id="5e3de-130">[Work with CSS override files](css-override-files.md)</span></span>

[<span data-ttu-id="5e3de-131">Agregar un icono de favoritos</span><span class="sxs-lookup"><span data-stu-id="5e3de-131">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="5e3de-132">Agregar un mensaje de bienvenida</span><span class="sxs-lookup"><span data-stu-id="5e3de-132">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="5e3de-133">Agregar un aviso de derechos de autor</span><span class="sxs-lookup"><span data-stu-id="5e3de-133">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="5e3de-134">Agregar idiomas al sitio</span><span class="sxs-lookup"><span data-stu-id="5e3de-134">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="5e3de-135">Agregar secuencia de comandos a páginas del sitio para admitir telemetría</span><span class="sxs-lookup"><span data-stu-id="5e3de-135">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

