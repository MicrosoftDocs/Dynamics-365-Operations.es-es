---
title: Agregar un mensaje de bienvenida
description: Este tema describe cómo agregar un mensaje de bienvenida en su sitio web de Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3e61f43eca7d1343d020e1c01b5b1140f07b63c6
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797392"
---
# <a name="add-a-welcome-message"></a><span data-ttu-id="0b053-103">Agregar un mensaje de bienvenida</span><span class="sxs-lookup"><span data-stu-id="0b053-103">Add a welcome message</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0b053-104">Este tema describe cómo agregar un mensaje de bienvenida en su sitio web de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0b053-104">This topic describes how to add a welcome message to your Microsoft Dynamics 365 Commerce website.</span></span>

<span data-ttu-id="0b053-105">Un mensaje de bienvenida en su sitio web de comercio electrónico puede informar a los visitantes acerca de las ventas continuas, las actualizaciones de sitio o la disponibilidad de colecciones de temporada.</span><span class="sxs-lookup"><span data-stu-id="0b053-105">A welcome message on your e-Commerce website can inform visitors about ongoing sales, site updates, or availability of seasonal collections.</span></span> <span data-ttu-id="0b053-106">El mensaje de bienvenida se establece mediante el módulo de alerta.</span><span class="sxs-lookup"><span data-stu-id="0b053-106">The welcome message is set by using the alert module.</span></span>

<span data-ttu-id="0b053-107">El módulo de alerta se debe agregar al espacio **Mensajes de error o información** del fragmento de encabezado.</span><span class="sxs-lookup"><span data-stu-id="0b053-107">The alert module should be added to the **Error/Information messages** slot of the header fragment.</span></span> <span data-ttu-id="0b053-108">El módulo de alerta le permite especificar el texto que se muestra, el color de texto y la alineación.</span><span class="sxs-lookup"><span data-stu-id="0b053-108">The alert module lets you specify the text that is shown, the text color, and the alignment.</span></span> <span data-ttu-id="0b053-109">También le permite especificar si los visitantes al sitio pueden descartar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="0b053-109">It also lets you specify whether visitors to the site can dismiss the message.</span></span>

<span data-ttu-id="0b053-110">Cuando se agrega un mensaje de bienvenida a un fragmento de encabezado compartido, se mostrará en todas las páginas que use la plantilla en la que se usa el fragmento de encabezado compartido.</span><span class="sxs-lookup"><span data-stu-id="0b053-110">When a welcome message is added to a shared header fragment, it will be shown on every page that uses the template where that shared header fragment is used.</span></span>

<span data-ttu-id="0b053-111">Para agregar un mensaje de bienvenida al sitio, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="0b053-111">To add a welcome message to your site, follow these steps.</span></span>

1. <span data-ttu-id="0b053-112">En el generador de sitios de Commerce, vaya a su sitio.</span><span class="sxs-lookup"><span data-stu-id="0b053-112">In Commerce site builder, go to your site.</span></span>
1. <span data-ttu-id="0b053-113">Seleccione **Fragmentos**.</span><span class="sxs-lookup"><span data-stu-id="0b053-113">Select **Fragments**.</span></span>
1. <span data-ttu-id="0b053-114">Seleccione el fragmento de encabezado al que agregar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="0b053-114">Select the header fragment to add the message to.</span></span>
1. <span data-ttu-id="0b053-115">En el árbol de esquema, expanda **Mensajes de error o información**.</span><span class="sxs-lookup"><span data-stu-id="0b053-115">In the outline tree, expand **Error/Information messages**.</span></span>
1. <span data-ttu-id="0b053-116">Seleccione el módulo de alerta y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0b053-116">Select the alert module, and then select **OK**.</span></span> <span data-ttu-id="0b053-117">Si no existe todavía un módulo de alerta, primero seleccione los puntos suspensivos (**...**) situados junto a **Mensajes de error o información** y, a continuación, seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="0b053-117">If an alert module doesn't yet exist, first select the ellipsis button (**...**) next to **Error/Information messages**, and then select **Add module**.</span></span>
1. <span data-ttu-id="0b053-118">En el panel de propiedades de la derecha, en la pestaña **Datos**, seleccione **Agregar origen de datos** y, a continuación, **Contenido**.</span><span class="sxs-lookup"><span data-stu-id="0b053-118">In the property pane on the right, on the **Data** tab, select **Add Data Source**, and then select **Content**.</span></span>
1. <span data-ttu-id="0b053-119">En el campo **Texto de entrada**, escriba el texto del mensaje de bienvenida.</span><span class="sxs-lookup"><span data-stu-id="0b053-119">In the **Input Text** field, enter the text of the welcome message.</span></span>
1. <span data-ttu-id="0b053-120">Seleccione **Guardar** y seleccione **Finalizar edición** para proteger el fragmento de encabezado y luego seleccione **Publicar** para publicarlo.</span><span class="sxs-lookup"><span data-stu-id="0b053-120">Select **Save**, select **Finish editing** to check in the header fragment, and then select **Publish** to publish it.</span></span> 

<span data-ttu-id="0b053-121">El mensaje de bienvenida aparecerá ahora en la parte superior de cada página del sitio que usa el fragmento de encabezado seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0b053-121">The welcome message will now appear at the top of every site page that uses the selected header fragment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0b053-122">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="0b053-122">Additional resources</span></span>

[<span data-ttu-id="0b053-123">Agregar un logotipo</span><span class="sxs-lookup"><span data-stu-id="0b053-123">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="0b053-124">Seleccionar un tema de sitio</span><span class="sxs-lookup"><span data-stu-id="0b053-124">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="0b053-125">Trabajar con archivos de invalidaciones CSS</span><span class="sxs-lookup"><span data-stu-id="0b053-125">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="0b053-126">Agregar un icono de favoritos</span><span class="sxs-lookup"><span data-stu-id="0b053-126">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="0b053-127">Agregar un aviso de derechos de autor</span><span class="sxs-lookup"><span data-stu-id="0b053-127">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="0b053-128">Agregar idiomas al sitio</span><span class="sxs-lookup"><span data-stu-id="0b053-128">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="0b053-129">Agregar secuencia de comandos a páginas del sitio para admitir telemetría</span><span class="sxs-lookup"><span data-stu-id="0b053-129">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
