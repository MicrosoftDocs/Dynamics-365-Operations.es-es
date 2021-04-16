---
title: Generar páginas personalizadas de respuesta para los errores de código de estado 4xx/5xx
description: Este tema describe cómo crear páginas de respuestas personalizadas para errores del código de estado 4xx y 5xx mediante las herramientas de creación en Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6b35b3c07b1edd41e6a3763c0001529e125e4636
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799665"
---
# <a name="build-custom-response-pages-for-4xx5xx-status-code-errors"></a><span data-ttu-id="13b27-103">Generar páginas personalizadas de respuesta para los errores de código de estado 4xx/5xx</span><span class="sxs-lookup"><span data-stu-id="13b27-103">Build custom response pages for 4xx/5xx status code errors</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="13b27-104">Este tema describe cómo crear páginas de respuestas personalizadas para errores del código de estado 4xx y 5xx mediante las herramientas de creación en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="13b27-104">This topic describes how to build custom response pages for 4xx and 5xx status code errors by using the authoring tools in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="13b27-105">Si una solicitud no es correcta, el servidor emite respuestas de error de código de estado HTTP.</span><span class="sxs-lookup"><span data-stu-id="13b27-105">If a request isn't successful, the server issues HTTP status code error responses.</span></span> <span data-ttu-id="13b27-106">Se captura y se devuelve el código de estado 404 si no se encuentra una página, y el código de estado 500 se captura y se devuelve si se produce un error de servidor.</span><span class="sxs-lookup"><span data-stu-id="13b27-106">The 404 status code is captured and returned if a page isn't found, and the 500 status code is captured and returned if a server error occurs.</span></span> <span data-ttu-id="13b27-107">En Dynamics 365 Commerce, los usuarios de aplicación pueden generar páginas de respuestas de error de código de estado personalizadas que se muestran a los usuarios para estas respuestas de error de código de estado.</span><span class="sxs-lookup"><span data-stu-id="13b27-107">In Dynamics 365 Commerce, application users can build custom status code error response pages that are shown to users for these status code error responses.</span></span>

## <a name="build-a-status-code-error-response-page"></a><span data-ttu-id="13b27-108">Crear una página de respuesta de error de código de estado</span><span class="sxs-lookup"><span data-stu-id="13b27-108">Build a status code error response page</span></span>

<span data-ttu-id="13b27-109">Para empezar a crear una página de respuesta de error de código de estado, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="13b27-109">To start to build a status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="13b27-110">En su explorador web preferido, inicie sesión en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="13b27-110">In your preferred web browser, sign in to Dynamics 365 Commerce.</span></span> 
1. <span data-ttu-id="13b27-111">Seleccione el sitio para el que desea crear una página de respuesta de error de código de estado 4xx/5xx.</span><span class="sxs-lookup"><span data-stu-id="13b27-111">Select the site that you want to build a 4xx/5xx status code error response page for.</span></span>

### <a name="build-the-template"></a><span data-ttu-id="13b27-112">Crear la plantilla</span><span class="sxs-lookup"><span data-stu-id="13b27-112">Build the template</span></span>

<span data-ttu-id="13b27-113">Para crear la plantilla para la página de respuesta de error de código de estado, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="13b27-113">To build the template for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="13b27-114">Vaya a **Plantillas**.</span><span class="sxs-lookup"><span data-stu-id="13b27-114">Go to **Templates**.</span></span>
1. <span data-ttu-id="13b27-115">Seleccione **Nuevo** para crear una plantilla de página.</span><span class="sxs-lookup"><span data-stu-id="13b27-115">Select **New** to create a page template.</span></span>
1. <span data-ttu-id="13b27-116">En el cuadro de diálogo **Nueva plantilla**, debajo de **Nombre de la plantilla**, ingrese un nombre para la nueva plantilla y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="13b27-116">In the **New Template** dialog box, under **Template Name**, enter a name for the new template, and then select **OK**.</span></span>
1. <span data-ttu-id="13b27-117">Cree la plantilla, en función de la estructura que desea que tenga la página de respuesta de error del código de estado.</span><span class="sxs-lookup"><span data-stu-id="13b27-117">Build the template, based on the structure that you want the status code error response page to have.</span></span>
1. <span data-ttu-id="13b27-118">Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="13b27-118">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span> 

### <a name="build-the-status-code-error-response-page"></a><span data-ttu-id="13b27-119">Crear la página de respuesta de error de código de estado</span><span class="sxs-lookup"><span data-stu-id="13b27-119">Build the status code error response page</span></span>

<span data-ttu-id="13b27-120">Para crear la página de respuesta de error de código de estado, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="13b27-120">To build the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="13b27-121">Vaya a **Páginas**.</span><span class="sxs-lookup"><span data-stu-id="13b27-121">Go to **Pages**.</span></span>
1. <span data-ttu-id="13b27-122">Seleccione **Nuevo** para crear una página.</span><span class="sxs-lookup"><span data-stu-id="13b27-122">Select **New** to create a page.</span></span>
1. <span data-ttu-id="13b27-123">En el cuadro de diálogo **Elegir una plantilla**, seleccione una plantilla y luego, debajo de **Nombre de la página**, ingrese un nombre para la página de respuesta de error del código de estado.</span><span class="sxs-lookup"><span data-stu-id="13b27-123">In the **Choose a template** dialog box, select a template, and then, under **Page name**, enter a name for the status code error response page.</span></span> <span data-ttu-id="13b27-124">Deje el campo **URL de página** en blanco.</span><span class="sxs-lookup"><span data-stu-id="13b27-124">Leave the **Page URL** field blank.</span></span>
1. <span data-ttu-id="13b27-125">Cree la página.</span><span class="sxs-lookup"><span data-stu-id="13b27-125">Build the page.</span></span>
1. <span data-ttu-id="13b27-126">Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="13b27-126">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="13b27-127">Puede crear las páginas de respuesta de error de código de estado independientes para errores de código de estado 4xx y 5xx.</span><span class="sxs-lookup"><span data-stu-id="13b27-127">You can create separate status code error response pages for 4xx and 5xx status code errors.</span></span> <span data-ttu-id="13b27-128">También puede usar la misma página de respuesta de error de código de estado general para ambas categorías de error.</span><span class="sxs-lookup"><span data-stu-id="13b27-128">Alternatively, you can use the same general status code error response page for both error categories.</span></span>

### <a name="set-up-a-redirect-for-the-status-code-error-response-page"></a><span data-ttu-id="13b27-129">Configurar una redirección para la página de respuesta de error de código de estado</span><span class="sxs-lookup"><span data-stu-id="13b27-129">Set up a redirect for the status code error response page</span></span>

<span data-ttu-id="13b27-130">Para configurar una redirección para la página de respuesta de error de código de estado, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="13b27-130">To set up a redirect for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="13b27-131">Vaya a **Direcciones URL \> Nuevo \> Nuevo alias** y seleccione la página de respuesta de error del código de estado que se creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="13b27-131">Go to **URLs \> New \> New Alias**, and select the status code error response page that you built earlier.</span></span>
1. <span data-ttu-id="13b27-132">En el campo **Alias**, escriba **default-4xx** o **default-5xx**, en función de la página de respuesta de error de código de estado para la que está configurando una redirección.</span><span class="sxs-lookup"><span data-stu-id="13b27-132">In the **Alias** field, enter either **default-4xx** or **default-5xx**, depending on the status code error response page that you're setting up a redirect for.</span></span> <span data-ttu-id="13b27-133">Estos alias se deben publicar.</span><span class="sxs-lookup"><span data-stu-id="13b27-133">These aliases must be published.</span></span> <span data-ttu-id="13b27-134">De lo contrario, la redirección no funcionará.</span><span class="sxs-lookup"><span data-stu-id="13b27-134">Otherwise, the redirect won't work.</span></span>
1. <span data-ttu-id="13b27-135">Seleccione **Aceptar** para confirmar la vinculación.</span><span class="sxs-lookup"><span data-stu-id="13b27-135">Select **OK** to commit the linking.</span></span>

> [!NOTE]
> <span data-ttu-id="13b27-136">Si utiliza una sola página de respuesta de error de código de estado para ambas categorías de error, repita este procedimiento para vincular un alias para la otra categoría de error a la misma página.</span><span class="sxs-lookup"><span data-stu-id="13b27-136">If you're using a single status code error response page for both error categories, repeat this procedure to link an alias for the other error category to the same page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="13b27-137">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="13b27-137">Additional resources</span></span>

[<span data-ttu-id="13b27-138">Trabajar con plantillas</span><span class="sxs-lookup"><span data-stu-id="13b27-138">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="13b27-139">Agregar una página de sitio nueva</span><span class="sxs-lookup"><span data-stu-id="13b27-139">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="13b27-140">Crear un URL de página</span><span class="sxs-lookup"><span data-stu-id="13b27-140">Create a page URL</span></span>](create-page-url.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
