---
title: Generar páginas personalizadas de respuesta para los errores de código de estado 4xx/5xx
description: Este tema describe cómo crear páginas de respuestas personalizadas para errores del código de estado 4xx y 5xx mediante las herramientas de creación en Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d21ce20b2c7ac8c656a718749dabd76f33893da8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4991474"
---
# <a name="build-custom-response-pages-for-4xx5xx-status-code-errors"></a><span data-ttu-id="e97b4-103">Generar páginas personalizadas de respuesta para los errores de código de estado 4xx/5xx</span><span class="sxs-lookup"><span data-stu-id="e97b4-103">Build custom response pages for 4xx/5xx status code errors</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="e97b4-104">Este tema describe cómo crear páginas de respuestas personalizadas para errores del código de estado 4xx y 5xx mediante las herramientas de creación en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e97b4-104">This topic describes how to build custom response pages for 4xx and 5xx status code errors by using the authoring tools in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="e97b4-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="e97b4-105">Overview</span></span>

<span data-ttu-id="e97b4-106">Si una solicitud no es correcta, el servidor emite respuestas de error de código de estado HTTP.</span><span class="sxs-lookup"><span data-stu-id="e97b4-106">If a request isn't successful, the server issues HTTP status code error responses.</span></span> <span data-ttu-id="e97b4-107">Se captura y se devuelve el código de estado 404 si no se encuentra una página, y el código de estado 500 se captura y se devuelve si se produce un error de servidor.</span><span class="sxs-lookup"><span data-stu-id="e97b4-107">The 404 status code is captured and returned if a page isn't found, and the 500 status code is captured and returned if a server error occurs.</span></span> <span data-ttu-id="e97b4-108">En Dynamics 365 Commerce, los usuarios de aplicación pueden generar páginas de respuestas de error de código de estado personalizadas que se muestran a los usuarios para estas respuestas de error de código de estado.</span><span class="sxs-lookup"><span data-stu-id="e97b4-108">In Dynamics 365 Commerce, application users can build custom status code error response pages that are shown to users for these status code error responses.</span></span>

## <a name="build-a-status-code-error-response-page"></a><span data-ttu-id="e97b4-109">Crear una página de respuesta de error de código de estado</span><span class="sxs-lookup"><span data-stu-id="e97b4-109">Build a status code error response page</span></span>

<span data-ttu-id="e97b4-110">Para empezar a crear una página de respuesta de error de código de estado, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="e97b4-110">To start to build a status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="e97b4-111">En su explorador web preferido, inicie sesión en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e97b4-111">In your preferred web browser, sign in to Dynamics 365 Commerce.</span></span> 
1. <span data-ttu-id="e97b4-112">Seleccione el sitio para el que desea crear una página de respuesta de error de código de estado 4xx/5xx.</span><span class="sxs-lookup"><span data-stu-id="e97b4-112">Select the site that you want to build a 4xx/5xx status code error response page for.</span></span>

### <a name="build-the-template"></a><span data-ttu-id="e97b4-113">Crear la plantilla</span><span class="sxs-lookup"><span data-stu-id="e97b4-113">Build the template</span></span>

<span data-ttu-id="e97b4-114">Para crear la plantilla para la página de respuesta de error de código de estado, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="e97b4-114">To build the template for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="e97b4-115">Vaya a **Plantillas**.</span><span class="sxs-lookup"><span data-stu-id="e97b4-115">Go to **Templates**.</span></span>
1. <span data-ttu-id="e97b4-116">Seleccione **Nuevo** para crear una plantilla de página.</span><span class="sxs-lookup"><span data-stu-id="e97b4-116">Select **New** to create a page template.</span></span>
1. <span data-ttu-id="e97b4-117">En el cuadro de diálogo **Nueva plantilla**, debajo de **Nombre de la plantilla**, ingrese un nombre para la nueva plantilla y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e97b4-117">In the **New Template** dialog box, under **Template Name**, enter a name for the new template, and then select **OK**.</span></span>
1. <span data-ttu-id="e97b4-118">Cree la plantilla, en función de la estructura que desea que tenga la página de respuesta de error del código de estado.</span><span class="sxs-lookup"><span data-stu-id="e97b4-118">Build the template, based on the structure that you want the status code error response page to have.</span></span>
1. <span data-ttu-id="e97b4-119">Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="e97b4-119">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span> 

### <a name="build-the-status-code-error-response-page"></a><span data-ttu-id="e97b4-120">Crear la página de respuesta de error de código de estado</span><span class="sxs-lookup"><span data-stu-id="e97b4-120">Build the status code error response page</span></span>

<span data-ttu-id="e97b4-121">Para crear la página de respuesta de error de código de estado, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="e97b4-121">To build the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="e97b4-122">Vaya a **Páginas**.</span><span class="sxs-lookup"><span data-stu-id="e97b4-122">Go to **Pages**.</span></span>
1. <span data-ttu-id="e97b4-123">Seleccione **Nuevo** para crear una página.</span><span class="sxs-lookup"><span data-stu-id="e97b4-123">Select **New** to create a page.</span></span>
1. <span data-ttu-id="e97b4-124">En el cuadro de diálogo **Elegir una plantilla**, seleccione una plantilla y luego, debajo de **Nombre de la página**, ingrese un nombre para la página de respuesta de error del código de estado.</span><span class="sxs-lookup"><span data-stu-id="e97b4-124">In the **Choose a template** dialog box, select a template, and then, under **Page name**, enter a name for the status code error response page.</span></span> <span data-ttu-id="e97b4-125">Deje el campo **URL de página** en blanco.</span><span class="sxs-lookup"><span data-stu-id="e97b4-125">Leave the **Page URL** field blank.</span></span>
1. <span data-ttu-id="e97b4-126">Cree la página.</span><span class="sxs-lookup"><span data-stu-id="e97b4-126">Build the page.</span></span>
1. <span data-ttu-id="e97b4-127">Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="e97b4-127">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="e97b4-128">Puede crear las páginas de respuesta de error de código de estado independientes para errores de código de estado 4xx y 5xx.</span><span class="sxs-lookup"><span data-stu-id="e97b4-128">You can create separate status code error response pages for 4xx and 5xx status code errors.</span></span> <span data-ttu-id="e97b4-129">También puede usar la misma página de respuesta de error de código de estado general para ambas categorías de error.</span><span class="sxs-lookup"><span data-stu-id="e97b4-129">Alternatively, you can use the same general status code error response page for both error categories.</span></span>

### <a name="set-up-a-redirect-for-the-status-code-error-response-page"></a><span data-ttu-id="e97b4-130">Configurar una redirección para la página de respuesta de error de código de estado</span><span class="sxs-lookup"><span data-stu-id="e97b4-130">Set up a redirect for the status code error response page</span></span>

<span data-ttu-id="e97b4-131">Para configurar una redirección para la página de respuesta de error de código de estado, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="e97b4-131">To set up a redirect for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="e97b4-132">Vaya a **Direcciones URL \> Nuevo \> Nuevo alias** y seleccione la página de respuesta de error del código de estado que se creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e97b4-132">Go to **URLs \> New \> New Alias**, and select the status code error response page that you built earlier.</span></span>
1. <span data-ttu-id="e97b4-133">En el campo **Alias**, escriba **default-4xx** o **default-5xx**, en función de la página de respuesta de error de código de estado para la que está configurando una redirección.</span><span class="sxs-lookup"><span data-stu-id="e97b4-133">In the **Alias** field, enter either **default-4xx** or **default-5xx**, depending on the status code error response page that you're setting up a redirect for.</span></span> <span data-ttu-id="e97b4-134">Estos alias se deben publicar.</span><span class="sxs-lookup"><span data-stu-id="e97b4-134">These aliases must be published.</span></span> <span data-ttu-id="e97b4-135">De lo contrario, la redirección no funcionará.</span><span class="sxs-lookup"><span data-stu-id="e97b4-135">Otherwise, the redirect won't work.</span></span>
1. <span data-ttu-id="e97b4-136">Seleccione **Aceptar** para confirmar la vinculación.</span><span class="sxs-lookup"><span data-stu-id="e97b4-136">Select **OK** to commit the linking.</span></span>

> [!NOTE]
> <span data-ttu-id="e97b4-137">Si utiliza una sola página de respuesta de error de código de estado para ambas categorías de error, repita este procedimiento para vincular un alias para la otra categoría de error a la misma página.</span><span class="sxs-lookup"><span data-stu-id="e97b4-137">If you're using a single status code error response page for both error categories, repeat this procedure to link an alias for the other error category to the same page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e97b4-138">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e97b4-138">Additional resources</span></span>

[<span data-ttu-id="e97b4-139">Trabajar con plantillas</span><span class="sxs-lookup"><span data-stu-id="e97b4-139">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="e97b4-140">Agregar una página de sitio nueva</span><span class="sxs-lookup"><span data-stu-id="e97b4-140">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="e97b4-141">Crear un URL de página</span><span class="sxs-lookup"><span data-stu-id="e97b4-141">Create a page URL</span></span>](create-page-url.md)
