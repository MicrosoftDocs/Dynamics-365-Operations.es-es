---
title: Agregar un aviso de derechos de autor
description: En este tema se describe cómo agregar un aviso de derechos de autor a su sitio web de comercio electrónico.
author: psimolin
manager: AnnBe
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
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 58c2949057ef777f706d12cee2dd3341d1a3b7e6
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914589"
---
# <a name="add-a-copyright-notice"></a><span data-ttu-id="a74de-103">Agregar un aviso de derechos de autor</span><span class="sxs-lookup"><span data-stu-id="a74de-103">Add a copyright notice</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="a74de-104">En este tema se describe cómo agregar un aviso de derechos de autor a su sitio web de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="a74de-104">This topic describes how to add a copyright notice to your e-Commerce website.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a74de-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a74de-105">Prerequisites</span></span>

<span data-ttu-id="a74de-106">Para poder agregar un aviso de derechos de autor al sitio, debe tener los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="a74de-106">Before you can add a copyright notice to your site, you must have the following items:</span></span>

- <span data-ttu-id="a74de-107">Una plantilla que incluya un fragmento de pie de página compartido.</span><span class="sxs-lookup"><span data-stu-id="a74de-107">A template that includes a shared footer fragment.</span></span>
- <span data-ttu-id="a74de-108">Una página que use esa plantilla.</span><span class="sxs-lookup"><span data-stu-id="a74de-108">A page that uses that template.</span></span>

## <a name="add-a-copyright-notice"></a><span data-ttu-id="a74de-109">Agregar un aviso de derechos de autor</span><span class="sxs-lookup"><span data-stu-id="a74de-109">Add a copyright notice</span></span>

<span data-ttu-id="a74de-110">Para agregar un aviso de derecho de autor a la parte inferior de cada página que usa una plantilla específica, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a74de-110">To add a copyright notice to the bottom of every page that uses a specific template, follow these steps.</span></span>

1. <span data-ttu-id="a74de-111">Vaya a **Fragmentos** y después seleccione **Nuevo fragmento de página**.</span><span class="sxs-lookup"><span data-stu-id="a74de-111">Go to **Fragments**, and then select **New Page Fragment**.</span></span>
1. <span data-ttu-id="a74de-112">En el cuadro de diálogo, seleccione el módulo **Pie de página** y asigne un nombre al fragmento.</span><span class="sxs-lookup"><span data-stu-id="a74de-112">In the dialog box, select the **Footer** module, and name the fragment.</span></span> <span data-ttu-id="a74de-113">Por ejemplo, escriba **Pie de página-Derechos de autor**.</span><span class="sxs-lookup"><span data-stu-id="a74de-113">For example, enter **Footer-Copyright**.</span></span>
1. <span data-ttu-id="a74de-114">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a74de-114">Select **OK**.</span></span>
1. <span data-ttu-id="a74de-115">En el panel de navegación, seleccione los puntos suspensivos (**...**) junto a **Pie de página** y, a continuación, seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="a74de-115">In the navigation pane, select the ellipsis button (**...**) next to **Footer**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="a74de-116">En el cuadro de diálogo, seleccione **Categoría de pie de página** y después seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a74de-116">In the dialog box, select **Footer category**, and then select **OK**.</span></span>
1. <span data-ttu-id="a74de-117">En el panel de navegación, seleccione los puntos suspensivos (...) junto a **Categoría de pie de página** y, a continuación, seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="a74de-117">In the navigation pane, select the ellipsis button next to **Footer category**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="a74de-118">En el cuadro de diálogo, seleccione **Elemento de bloque de enriquecimiento de contenido** y después seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a74de-118">In the dialog box, select **Content rich block item**, and then select **OK**.</span></span>
1. <span data-ttu-id="a74de-119">En el panel de navegación, seleccione **Elemento de bloque de enriquecimiento de contenido**.</span><span class="sxs-lookup"><span data-stu-id="a74de-119">In the navigation pane, select **Content rich block item**.</span></span>
1. <span data-ttu-id="a74de-120">En el panel de propiedades de la derecha, en el campo **Párrafo**, agregue su mensaje de derechos de autor.</span><span class="sxs-lookup"><span data-stu-id="a74de-120">In the properties pane on the right, in the **Paragraph** field, add your copyright message.</span></span> <span data-ttu-id="a74de-121">Por ejemplo, especifique **(C) Fabrikam 2019**.</span><span class="sxs-lookup"><span data-stu-id="a74de-121">For example, enter **(C) Fabrikam 2019**.</span></span>
1. <span data-ttu-id="a74de-122">Seleccione **Guardar**, **Proteger** y **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="a74de-122">Select **Save**, select **Check In**, and then select **Publish**.</span></span>
1. <span data-ttu-id="a74de-123">Vaya a **Plantillas**, seleccione la plantilla y, a continuación, seleccione **Desproteger**.</span><span class="sxs-lookup"><span data-stu-id="a74de-123">Go to **Templates**, select the template, and then select **Check Out**.</span></span>
1. <span data-ttu-id="a74de-124">En **página Esquema**, expanda **Cuerpo** y, a continuación, expanda **Página predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="a74de-124">Under **Page Outline**, expand **Body**, and then expand **Default Page**.</span></span>
1. <span data-ttu-id="a74de-125">Seleccione el botón de puntos suspensivos junto a **Espacio de pie de página** y, a continuación, seleccione **Agregar fragmento**.</span><span class="sxs-lookup"><span data-stu-id="a74de-125">Select the ellipsis button next to **Footer Slot**, and then select **Add Fragment**.</span></span>
1. <span data-ttu-id="a74de-126">Seleccione el fragmento que haya creado anteriormente y después, **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="a74de-126">Select the fragment that you created earlier, and then select **Select**.</span></span>
1. <span data-ttu-id="a74de-127">Proteja la plantilla y publíquela.</span><span class="sxs-lookup"><span data-stu-id="a74de-127">Check in the template, and publish it.</span></span>

<span data-ttu-id="a74de-128">El pie de página que contiene el aviso de derechos de autor aparece automáticamente en la parte inferior de todas las páginas que utilicen la plantilla seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a74de-128">The footer that contains the copyright notice automatically appears at the bottom of all pages that use the selected template.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a74de-129">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a74de-129">Additional resources</span></span>

[<span data-ttu-id="a74de-130">Agregar un logotipo</span><span class="sxs-lookup"><span data-stu-id="a74de-130">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="a74de-131">Seleccionar un tema de sitio</span><span class="sxs-lookup"><span data-stu-id="a74de-131">Select a site theme</span></span>](select-site-theme.md)

<span data-ttu-id="a74de-132">[Trabajar con archivos de invalidaciones CSS](css-override-files.md) </span><span class="sxs-lookup"><span data-stu-id="a74de-132">[Work with CSS override files](css-override-files.md)</span></span>

[<span data-ttu-id="a74de-133">Agregar un icono de favoritos</span><span class="sxs-lookup"><span data-stu-id="a74de-133">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="a74de-134">Agregar un mensaje de bienvenida</span><span class="sxs-lookup"><span data-stu-id="a74de-134">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="a74de-135">Agregar idiomas al sitio</span><span class="sxs-lookup"><span data-stu-id="a74de-135">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="a74de-136">Agregar secuencia de comandos a páginas del sitio para admitir telemetría</span><span class="sxs-lookup"><span data-stu-id="a74de-136">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)
