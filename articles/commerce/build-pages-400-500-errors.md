---
title: Generar páginas personalizadas de respuesta para los errores de código de estado 4xx/5xx
description: Este tema describe cómo crear páginas de respuestas personalizadas para errores del código de estado 4xx y 5xx mediante las herramientas de creación en Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: bcceeb1bc68c6432442c863ca06b7ba81d0abed8
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697115"
---
# <a name="build-custom-response-pages-for-4xx5xx-status-code-errors"></a><span data-ttu-id="6a930-103">Generar páginas personalizadas de respuesta para los errores de código de estado 4xx/5xx</span><span class="sxs-lookup"><span data-stu-id="6a930-103">Build custom response pages for 4xx/5xx status code errors</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="6a930-104">Este tema describe cómo crear páginas de respuestas personalizadas para errores del código de estado 4xx y 5xx mediante las herramientas de creación en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6a930-104">This topic describes how to build custom response pages for 4xx and 5xx status code errors by using the authoring tools in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="6a930-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="6a930-105">Overview</span></span>

<span data-ttu-id="6a930-106">Si una solicitud no es correcta, el servidor emite respuestas de error de código de estado HTTP.</span><span class="sxs-lookup"><span data-stu-id="6a930-106">If a request isn't successful, the server issues HTTP status code error responses.</span></span> <span data-ttu-id="6a930-107">Se captura y se devuelve el código de estado 404 si no se encuentra una página, y el código de estado 500 se captura y se devuelve si se produce un error de servidor.</span><span class="sxs-lookup"><span data-stu-id="6a930-107">The 404 status code is captured and returned if a page isn't found, and the 500 status code is captured and returned if a server error occurs.</span></span> <span data-ttu-id="6a930-108">En Dynamics 365 Commerce, los usuarios de aplicación pueden generar páginas de respuestas de error de código de estado personalizadas que se muestran a los usuarios para estas respuestas de error de código de estado.</span><span class="sxs-lookup"><span data-stu-id="6a930-108">In Dynamics 365 Commerce, application users can build custom status code error response pages that are shown to users for these status code error responses.</span></span>

## <a name="build-a-status-code-error-response-page"></a><span data-ttu-id="6a930-109">Crear una página de respuesta de error de código de estado</span><span class="sxs-lookup"><span data-stu-id="6a930-109">Build a status code error response page</span></span>

<span data-ttu-id="6a930-110">Para empezar a crear una página de respuesta de error de código de estado, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="6a930-110">To start to build a status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="6a930-111">En su explorador web preferido, inicie sesión en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6a930-111">In your preferred web browser, sign in to Dynamics 365 Commerce.</span></span> 
1. <span data-ttu-id="6a930-112">Seleccione el sitio para el que desea crear una página de respuesta de error de código de estado 4xx/5xx.</span><span class="sxs-lookup"><span data-stu-id="6a930-112">Select the site that you want to build a 4xx/5xx status code error response page for.</span></span>

### <a name="build-the-template"></a><span data-ttu-id="6a930-113">Crear la plantilla</span><span class="sxs-lookup"><span data-stu-id="6a930-113">Build the template</span></span>

<span data-ttu-id="6a930-114">Para crear la plantilla para la página de respuesta de error de código de estado, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="6a930-114">To build the template for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="6a930-115">Vaya a **Plantillas \> Nueva plantilla**.</span><span class="sxs-lookup"><span data-stu-id="6a930-115">Go to **Templates \> New template**.</span></span>
1. <span data-ttu-id="6a930-116">Asigne un nombre a la nueva plantilla.</span><span class="sxs-lookup"><span data-stu-id="6a930-116">Name the new template.</span></span>
1. <span data-ttu-id="6a930-117">Cree la plantilla, en función de la estructura que desea que tenga la página de respuesta de error del código de estado.</span><span class="sxs-lookup"><span data-stu-id="6a930-117">Build the template, based on the structure that you want the status code error response page to have.</span></span>
1. <span data-ttu-id="6a930-118">Proteja la plantilla y publíquela.</span><span class="sxs-lookup"><span data-stu-id="6a930-118">Check the template in, and publish it.</span></span>

### <a name="build-the-status-code-error-response-page"></a><span data-ttu-id="6a930-119">Crear la página de respuesta de error de código de estado</span><span class="sxs-lookup"><span data-stu-id="6a930-119">Build the status code error response page</span></span>

<span data-ttu-id="6a930-120">Para crear la página de respuesta de error de código de estado, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="6a930-120">To build the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="6a930-121">Vaya a **Páginas \> Nueva página**.</span><span class="sxs-lookup"><span data-stu-id="6a930-121">Go to **Pages \> New Page**.</span></span>
1. <span data-ttu-id="6a930-122">Asigne un nombre a la página de respuesta de error de código de estado, pero **no** establezca el campo **URL**.</span><span class="sxs-lookup"><span data-stu-id="6a930-122">Name the status code error response page, but do **not** set the **URL** field.</span></span>
1. <span data-ttu-id="6a930-123">Cree la página.</span><span class="sxs-lookup"><span data-stu-id="6a930-123">Build the page.</span></span>
1. <span data-ttu-id="6a930-124">Proteja la página y publíquela.</span><span class="sxs-lookup"><span data-stu-id="6a930-124">Check the page in, and publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="6a930-125">Puede crear las páginas de respuesta de error de código de estado independientes para errores de código de estado 4xx y 5xx.</span><span class="sxs-lookup"><span data-stu-id="6a930-125">You can create separate status code error response pages for 4xx and 5xx status code errors.</span></span> <span data-ttu-id="6a930-126">También puede usar la misma página de respuesta de error de código de estado general para ambas categorías de error.</span><span class="sxs-lookup"><span data-stu-id="6a930-126">Alternatively, you can use the same general status code error response page for both error categories.</span></span>

### <a name="set-up-a-redirect-for-the-status-code-error-response-page"></a><span data-ttu-id="6a930-127">Configurar una redirección para la página de respuesta de error de código de estado</span><span class="sxs-lookup"><span data-stu-id="6a930-127">Set up a redirect for the status code error response page</span></span>

<span data-ttu-id="6a930-128">Para configurar una redirección para la página de respuesta de error de código de estado, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="6a930-128">To set up a redirect for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="6a930-129">Vaya a **Direcciones URL \> Nuevo \> Nuevo alias** y seleccione la página de respuesta de error del código de estado que se creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6a930-129">Go to **URLs \> New \> New Alias**, and select the status code error response page that you built earlier.</span></span>
1. <span data-ttu-id="6a930-130">En el campo **Alias**, escriba **default-4xx** o **default-5xx**, en función de la página de respuesta de error de código de estado para la que está configurando una redirección.</span><span class="sxs-lookup"><span data-stu-id="6a930-130">In the **Alias** field, enter either **default-4xx** or **default-5xx**, depending on the status code error response page that you're setting up a redirect for.</span></span> <span data-ttu-id="6a930-131">Estos alias se deben publicar.</span><span class="sxs-lookup"><span data-stu-id="6a930-131">These aliases must be published.</span></span> <span data-ttu-id="6a930-132">De lo contrario, la redirección no funcionará.</span><span class="sxs-lookup"><span data-stu-id="6a930-132">Otherwise, the redirect won't work.</span></span>
1. <span data-ttu-id="6a930-133">Seleccione **Aceptar** para confirmar la vinculación.</span><span class="sxs-lookup"><span data-stu-id="6a930-133">Select **OK** to commit the linking.</span></span>

> [!NOTE]
> <span data-ttu-id="6a930-134">Si utiliza una sola página de respuesta de error de código de estado para ambas categorías de error, repita este procedimiento para vincular un alias para la otra categoría de error a la misma página.</span><span class="sxs-lookup"><span data-stu-id="6a930-134">If you're using a single status code error response page for both error categories, repeat this procedure to link an alias for the other error category to the same page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6a930-135">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="6a930-135">Additional resources</span></span>

[<span data-ttu-id="6a930-136">Trabajar con plantillas</span><span class="sxs-lookup"><span data-stu-id="6a930-136">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="6a930-137">Agregar una página de sitio nueva</span><span class="sxs-lookup"><span data-stu-id="6a930-137">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="6a930-138">Crear un URL de página</span><span class="sxs-lookup"><span data-stu-id="6a930-138">Create a page URL</span></span>](create-page-url.md)
