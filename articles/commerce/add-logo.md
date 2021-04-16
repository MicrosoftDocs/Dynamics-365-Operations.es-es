---
title: Agregar un logotipo
description: En este tema se describe cómo agregar un logotipo a su sitio en Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d9e1cba6bd07e0c3d9ed7d741d87e10837d8021c
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797608"
---
# <a name="add-a-logo"></a><span data-ttu-id="99d0e-103">Agregar un logotipo</span><span class="sxs-lookup"><span data-stu-id="99d0e-103">Add a logo</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="99d0e-104">En este tema se describe cómo agregar un logotipo a su sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="99d0e-104">This topic describes how to add a logo to your site in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="99d0e-105">Cuando crea su sitio, una de las primeras cosas que probablemente hará es agregar el logotipo de su empresa o marca al encabezado del sitio.</span><span class="sxs-lookup"><span data-stu-id="99d0e-105">When you build your site, one of the first things that you will probably do is add your company or brand logo to the site's header.</span></span> <span data-ttu-id="99d0e-106">La biblioteca del módulo de Dynamics 365 Commerce Online proporciona un módulo que facilita esta tarea.</span><span class="sxs-lookup"><span data-stu-id="99d0e-106">The Dynamics 365 Commerce online module library provides a module that makes this task easy.</span></span>

<span data-ttu-id="99d0e-107">Puede agregar un logotipo directamente a una plantilla, diseño o página.</span><span class="sxs-lookup"><span data-stu-id="99d0e-107">You can add a logo directly to a template, layout, or page.</span></span> <span data-ttu-id="99d0e-108">De esta manera, puede cambiar fácilmente el logotipo que aparece en páginas específicas o grupos de páginas.</span><span class="sxs-lookup"><span data-stu-id="99d0e-108">In this way, you can easily change the logo that appears on specific pages or groups of pages.</span></span> <span data-ttu-id="99d0e-109">Sin embargo, este tema cubre el escenario más frecuente, donde agrega su logotipo a un fragmento de encabezado que puede reutilizarse en todas las páginas de su sitio.</span><span class="sxs-lookup"><span data-stu-id="99d0e-109">However, this topic covers the most frequent scenario, where you add your logo to a header fragment that can be reused across all the pages of your site.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="99d0e-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="99d0e-110">Prerequisites</span></span>

<span data-ttu-id="99d0e-111">Antes de poder agregar un logotipo a todas las páginas de su sitio, debe completar estas tareas.</span><span class="sxs-lookup"><span data-stu-id="99d0e-111">Before you can add a logo to all the pages of your site, you must complete these tasks.</span></span>

1. <span data-ttu-id="99d0e-112">Cargue su logotipo en la Biblioteca de medios.</span><span class="sxs-lookup"><span data-stu-id="99d0e-112">Upload your logo to the Media Library.</span></span>
1. <span data-ttu-id="99d0e-113">Crear un fragmento de encabezado.</span><span class="sxs-lookup"><span data-stu-id="99d0e-113">Create a header fragment.</span></span> <span data-ttu-id="99d0e-114">Para obtener más información sobre cómo crear y usar fragmentos, vea [Trabajar con fragmentos](work-with-fragments.md).</span><span class="sxs-lookup"><span data-stu-id="99d0e-114">For more information about how to create and use fragments, see [Work with fragments](work-with-fragments.md).</span></span>
1. <span data-ttu-id="99d0e-115">Incluya el fragmento de encabezado en la plantilla que usan las páginas de su sitio para su diseño y opciones de módulo.</span><span class="sxs-lookup"><span data-stu-id="99d0e-115">Include the header fragment in the template that the pages of your site use for their layout and module options.</span></span> <span data-ttu-id="99d0e-116">Para obtener más información sobre las plantillas, vea [Trabajar con plantillas](work-with-templates.md).</span><span class="sxs-lookup"><span data-stu-id="99d0e-116">For more information about templates, see [Work with templates](work-with-templates.md).</span></span>

## <a name="add-a-logo-to-a-header-fragment"></a><span data-ttu-id="99d0e-117">Agregar un logotipo a un fragmento de encabezado</span><span class="sxs-lookup"><span data-stu-id="99d0e-117">Add a logo to a header fragment</span></span>

<span data-ttu-id="99d0e-118">Para agregar un logotipo al fragmento de encabezado de su sitio, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="99d0e-118">To add a logo to the header fragment for your site, follow these steps.</span></span>

1. <span data-ttu-id="99d0e-119">En el panel de navegación de la izquierda, seleccione **Fragmentos**.</span><span class="sxs-lookup"><span data-stu-id="99d0e-119">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="99d0e-120">Seleccione el fragmento de encabezado que ha creado y, a continuación, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="99d0e-120">Select the header fragment that you created, and then select **Edit**.</span></span>
1. <span data-ttu-id="99d0e-121">Expanda el módulo de encabezado.</span><span class="sxs-lookup"><span data-stu-id="99d0e-121">Expand the header module.</span></span>
1. <span data-ttu-id="99d0e-122">En el panel de propiedades del módulo de encabezado, proporcione una imagen y un vínculo para el logotipo.</span><span class="sxs-lookup"><span data-stu-id="99d0e-122">In the property pane for the header module, provide an image and link for the logo.</span></span> 
1. <span data-ttu-id="99d0e-123">Guarde el fragmento de encabezado, termine de editarlo y publíquelo.</span><span class="sxs-lookup"><span data-stu-id="99d0e-123">Save the header fragment, finish editing it, and publish it.</span></span>

<span data-ttu-id="99d0e-124">Después de publicar el fragmento de encabezado actualizado, todas las páginas del sitio que usan la plantilla que contiene el fragmento de encabezado mostrarán su logotipo.</span><span class="sxs-lookup"><span data-stu-id="99d0e-124">After you publish the updated header fragment, all site pages that use the template that contains the header fragment will show your logo.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="99d0e-125">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="99d0e-125">Additional resources</span></span>

[<span data-ttu-id="99d0e-126">Seleccionar un tema de sitio</span><span class="sxs-lookup"><span data-stu-id="99d0e-126">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="99d0e-127">Trabajar con archivos de invalidaciones CSS</span><span class="sxs-lookup"><span data-stu-id="99d0e-127">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="99d0e-128">Agregar un icono de favoritos</span><span class="sxs-lookup"><span data-stu-id="99d0e-128">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="99d0e-129">Agregar un mensaje de bienvenida</span><span class="sxs-lookup"><span data-stu-id="99d0e-129">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="99d0e-130">Agregar un aviso de derechos de autor</span><span class="sxs-lookup"><span data-stu-id="99d0e-130">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="99d0e-131">Agregar idiomas al sitio</span><span class="sxs-lookup"><span data-stu-id="99d0e-131">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="99d0e-132">Agregar secuencia de comandos a páginas del sitio para admitir telemetría</span><span class="sxs-lookup"><span data-stu-id="99d0e-132">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
