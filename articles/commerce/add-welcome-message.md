---
title: Agregar un mensaje de bienvenida
description: Este tema describe cómo agregar un mensaje de bienvenida en su sitio web de Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ca10b01268b5dcd4c6fe448d90cd0ebd65a2673b
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001263"
---
# <a name="add-a-welcome-message"></a><span data-ttu-id="5bded-103">Agregar un mensaje de bienvenida</span><span class="sxs-lookup"><span data-stu-id="5bded-103">Add a welcome message</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="5bded-104">Este tema describe cómo agregar un mensaje de bienvenida en su sitio web de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5bded-104">This topic describes how to add a welcome message to your Microsoft Dynamics 365 Commerce website.</span></span>

## <a name="overview"></a><span data-ttu-id="5bded-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="5bded-105">Overview</span></span>

<span data-ttu-id="5bded-106">Un mensaje de bienvenida en su sitio web de comercio electrónico puede informar a los visitantes acerca de las ventas continuas, las actualizaciones de sitio o la disponibilidad de colecciones de temporada.</span><span class="sxs-lookup"><span data-stu-id="5bded-106">A welcome message on your e-Commerce website can inform visitors about ongoing sales, site updates, or availability of seasonal collections.</span></span> <span data-ttu-id="5bded-107">El mensaje de bienvenida se establece mediante el módulo de alerta.</span><span class="sxs-lookup"><span data-stu-id="5bded-107">The welcome message is set by using the alert module.</span></span>

<span data-ttu-id="5bded-108">El módulo de alerta se debe agregar al espacio **Mensajes de error o información** del fragmento de encabezado.</span><span class="sxs-lookup"><span data-stu-id="5bded-108">The alert module should be added to the **Error/Information messages** slot of the header fragment.</span></span> <span data-ttu-id="5bded-109">El módulo de alerta le permite especificar el texto que se muestra, el color de texto y la alineación.</span><span class="sxs-lookup"><span data-stu-id="5bded-109">The alert module lets you specify the text that is shown, the text color, and the alignment.</span></span> <span data-ttu-id="5bded-110">También le permite especificar si los visitantes al sitio pueden descartar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="5bded-110">It also lets you specify whether visitors to the site can dismiss the message.</span></span>

<span data-ttu-id="5bded-111">Cuando se agrega un mensaje de bienvenida a un fragmento de encabezado compartido, se mostrará en todas las páginas que use la plantilla en la que se usa el fragmento de encabezado compartido.</span><span class="sxs-lookup"><span data-stu-id="5bded-111">When a welcome message is added to a shared header fragment, it will be shown on every page that uses the template where that shared header fragment is used.</span></span>

<span data-ttu-id="5bded-112">Para agregar un mensaje de bienvenida al sitio, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="5bded-112">To add a welcome message to your site, follow these steps.</span></span>

1. <span data-ttu-id="5bded-113">En Dynamics 365 Commerce, vaya a su sitio.</span><span class="sxs-lookup"><span data-stu-id="5bded-113">In Dynamics 365 Commerce, go to your site.</span></span>
1. <span data-ttu-id="5bded-114">Seleccione **Fragmentos**.</span><span class="sxs-lookup"><span data-stu-id="5bded-114">Select **Fragments**.</span></span>
1. <span data-ttu-id="5bded-115">Seleccione el fragmento de encabezado al que agregar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="5bded-115">Select the header fragment to add the message to.</span></span>
1. <span data-ttu-id="5bded-116">En el árbol de esquema, expanda **Mensajes de error o información**.</span><span class="sxs-lookup"><span data-stu-id="5bded-116">In the outline tree, expand **Error/Information messages**.</span></span>
1. <span data-ttu-id="5bded-117">Seleccione el módulo de alerta.</span><span class="sxs-lookup"><span data-stu-id="5bded-117">Select the alert module.</span></span>

    <span data-ttu-id="5bded-118">Si no existe todavía un módulo de alerta, seleccione los puntos suspensivos (**...**) situados junto a **Mensajes de error o información** y, a continuación, seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="5bded-118">If an alert module doesn't yet exist, select the ellipsis button (**...**) next to **Error/Information messages**, and then select **Add module**.</span></span> <span data-ttu-id="5bded-119">Seleccione el módulo de alerta y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5bded-119">Select the alert module, and then select **OK**.</span></span>

1. <span data-ttu-id="5bded-120">En el panel de propiedades de la derecha, en la pestaña **Datos**, seleccione **Agregar origen de datos** y, a continuación, **Contenido**.</span><span class="sxs-lookup"><span data-stu-id="5bded-120">In the property pane on the right, on the **Data** tab, select **Add Data Source**, and then select **Content**.</span></span>
1. <span data-ttu-id="5bded-121">En el campo **Texto de entrada**, escriba el texto del mensaje de bienvenida.</span><span class="sxs-lookup"><span data-stu-id="5bded-121">In the **Input Text** field, enter the text of the welcome message.</span></span>
1. <span data-ttu-id="5bded-122">Guarde el fragmento de encabezado, protéjalo y publíquelo.</span><span class="sxs-lookup"><span data-stu-id="5bded-122">Save the header fragment, check it in, and publish it.</span></span>

<span data-ttu-id="5bded-123">El mensaje de bienvenida aparecerá ahora en la parte superior de cada página del sitio que usa el fragmento de encabezado seleccionado.</span><span class="sxs-lookup"><span data-stu-id="5bded-123">The welcome message will now appear at the top of every site page that uses the selected header fragment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5bded-124">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="5bded-124">Additional resources</span></span>

[<span data-ttu-id="5bded-125">Agregar un logotipo</span><span class="sxs-lookup"><span data-stu-id="5bded-125">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="5bded-126">Seleccionar un tema de sitio</span><span class="sxs-lookup"><span data-stu-id="5bded-126">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="5bded-127">Trabajar con archivos de invalidaciones CSS</span><span class="sxs-lookup"><span data-stu-id="5bded-127">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="5bded-128">Agregar un icono de favoritos</span><span class="sxs-lookup"><span data-stu-id="5bded-128">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="5bded-129">Agregar un aviso de derechos de autor</span><span class="sxs-lookup"><span data-stu-id="5bded-129">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="5bded-130">Agregar idiomas al sitio</span><span class="sxs-lookup"><span data-stu-id="5bded-130">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="5bded-131">Agregar secuencia de comandos a páginas del sitio para admitir telemetría</span><span class="sxs-lookup"><span data-stu-id="5bded-131">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

