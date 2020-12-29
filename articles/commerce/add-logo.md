---
title: Agregar un logotipo
description: En este tema se describe cómo agregar un logotipo a su sitio en Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 09/15/2020
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
ms.openlocfilehash: f15680deb0eab763ba68f2897139c915d1f8a6a3
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415483"
---
# <a name="add-a-logo"></a><span data-ttu-id="ee50d-103">Agregar un logotipo</span><span class="sxs-lookup"><span data-stu-id="ee50d-103">Add a logo</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ee50d-104">En este tema se describe cómo agregar un logotipo a su sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ee50d-104">This topic describes how to add a logo to your site in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="ee50d-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="ee50d-105">Overview</span></span>

<span data-ttu-id="ee50d-106">Cuando crea su sitio, una de las primeras cosas que probablemente hará es agregar el logotipo de su empresa o marca al encabezado del sitio.</span><span class="sxs-lookup"><span data-stu-id="ee50d-106">When you build your site, one of the first things that you will probably do is add your company or brand logo to the site's header.</span></span> <span data-ttu-id="ee50d-107">La biblioteca del módulo de Dynamics 365 Commerce Online proporciona un módulo que facilita esta tarea.</span><span class="sxs-lookup"><span data-stu-id="ee50d-107">The Dynamics 365 Commerce online module library provides a module that makes this task easy.</span></span>

<span data-ttu-id="ee50d-108">Puede agregar un logotipo directamente a una plantilla, diseño o página.</span><span class="sxs-lookup"><span data-stu-id="ee50d-108">You can add a logo directly to a template, layout, or page.</span></span> <span data-ttu-id="ee50d-109">De esta manera, puede cambiar fácilmente el logotipo que aparece en páginas específicas o grupos de páginas.</span><span class="sxs-lookup"><span data-stu-id="ee50d-109">In this way, you can easily change the logo that appears on specific pages or groups of pages.</span></span> <span data-ttu-id="ee50d-110">Sin embargo, este tema cubre el escenario más frecuente, donde agrega su logotipo a un fragmento de encabezado que puede reutilizarse en todas las páginas de su sitio.</span><span class="sxs-lookup"><span data-stu-id="ee50d-110">However, this topic covers the most frequent scenario, where you add your logo to a header fragment that can be reused across all the pages of your site.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ee50d-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ee50d-111">Prerequisites</span></span>

<span data-ttu-id="ee50d-112">Antes de poder agregar un logotipo a todas las páginas de su sitio, debe completar estas tareas.</span><span class="sxs-lookup"><span data-stu-id="ee50d-112">Before you can add a logo to all the pages of your site, you must complete these tasks.</span></span>

1. <span data-ttu-id="ee50d-113">Cargue su logotipo en la Biblioteca de medios.</span><span class="sxs-lookup"><span data-stu-id="ee50d-113">Upload your logo to the Media Library.</span></span>
1. <span data-ttu-id="ee50d-114">Crear un fragmento de encabezado.</span><span class="sxs-lookup"><span data-stu-id="ee50d-114">Create a header fragment.</span></span> <span data-ttu-id="ee50d-115">Para obtener más información sobre cómo crear y usar fragmentos, vea [Trabajar con fragmentos](work-with-fragments.md).</span><span class="sxs-lookup"><span data-stu-id="ee50d-115">For more information about how to create and use fragments, see [Work with fragments](work-with-fragments.md).</span></span>
1. <span data-ttu-id="ee50d-116">Incluya el fragmento de encabezado en la plantilla que usan las páginas de su sitio para su diseño y opciones de módulo.</span><span class="sxs-lookup"><span data-stu-id="ee50d-116">Include the header fragment in the template that the pages of your site use for their layout and module options.</span></span> <span data-ttu-id="ee50d-117">Para obtener más información sobre las plantillas, vea [Trabajar con plantillas](work-with-templates.md).</span><span class="sxs-lookup"><span data-stu-id="ee50d-117">For more information about templates, see [Work with templates](work-with-templates.md).</span></span>

## <a name="add-a-logo-to-a-header-fragment"></a><span data-ttu-id="ee50d-118">Agregar un logotipo a un fragmento de encabezado</span><span class="sxs-lookup"><span data-stu-id="ee50d-118">Add a logo to a header fragment</span></span>

<span data-ttu-id="ee50d-119">Para agregar un logotipo al fragmento de encabezado de su sitio, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ee50d-119">To add a logo to the header fragment for your site, follow these steps.</span></span>

1. <span data-ttu-id="ee50d-120">En el panel de navegación de la izquierda, seleccione **Fragmentos**.</span><span class="sxs-lookup"><span data-stu-id="ee50d-120">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="ee50d-121">Seleccione el fragmento de encabezado que ha creado y, a continuación, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ee50d-121">Select the header fragment that you created, and then select **Edit**.</span></span>
1. <span data-ttu-id="ee50d-122">Expanda el módulo de encabezado.</span><span class="sxs-lookup"><span data-stu-id="ee50d-122">Expand the header module.</span></span>
1. <span data-ttu-id="ee50d-123">En el panel de propiedades del módulo de encabezado, proporcione una imagen y un vínculo para el logotipo.</span><span class="sxs-lookup"><span data-stu-id="ee50d-123">In the property pane for the header module, provide an image and link for the logo.</span></span> 
1. <span data-ttu-id="ee50d-124">Guarde el fragmento de encabezado, termine de editarlo y publíquelo.</span><span class="sxs-lookup"><span data-stu-id="ee50d-124">Save the header fragment, finish editing it, and publish it.</span></span>

<span data-ttu-id="ee50d-125">Después de publicar el fragmento de encabezado actualizado, todas las páginas del sitio que usan la plantilla que contiene el fragmento de encabezado mostrarán su logotipo.</span><span class="sxs-lookup"><span data-stu-id="ee50d-125">After you publish the updated header fragment, all site pages that use the template that contains the header fragment will show your logo.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ee50d-126">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="ee50d-126">Additional resources</span></span>

[<span data-ttu-id="ee50d-127">Seleccionar un tema de sitio</span><span class="sxs-lookup"><span data-stu-id="ee50d-127">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="ee50d-128">Trabajar con archivos de invalidaciones CSS</span><span class="sxs-lookup"><span data-stu-id="ee50d-128">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="ee50d-129">Agregar un icono de favoritos</span><span class="sxs-lookup"><span data-stu-id="ee50d-129">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="ee50d-130">Agregar un mensaje de bienvenida</span><span class="sxs-lookup"><span data-stu-id="ee50d-130">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="ee50d-131">Agregar un aviso de derechos de autor</span><span class="sxs-lookup"><span data-stu-id="ee50d-131">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="ee50d-132">Agregar idiomas al sitio</span><span class="sxs-lookup"><span data-stu-id="ee50d-132">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="ee50d-133">Agregar secuencia de comandos a páginas del sitio para admitir telemetría</span><span class="sxs-lookup"><span data-stu-id="ee50d-133">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

